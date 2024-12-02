---
layout: post
title: Software Design
date: 2024-11-11
summary: Software Design.
categories: software design
permalink: software-design
---

# Software Architecture

The overall software architecture is shown below:

![Software Architecture](/images/software-arch.png)

To make the software more modular and easier to understand, we decided to separate the software into several different packages and keep it in Python.

We have multiple nodes for each of the main components of the robot:

* `control`: Controls the base of the robot for balancing with the LQR controller
* `localization`: Handles the localization of the robot using a particle filter
* `planning`: Handles the planning of the robot's path
* `mapping`: Handles the mapping of the robot's environment
* `imu`: Handles the IMU sensor data
* `realsense-camera`: Handles the RealSense camera data

Then we use MQTT to communicate between the different nodes. For this we have a message broker running on the Raspberry Pi and a set of publishers and subscribers in each node. The messages are defined in a TOML configuration file, and automatically generated into Python classes using a helper script.

A snapshot of the message configuration file is shown below:

![Message Config](/images/messages.png)

The node dataflow is shown below for how messages are passed between the different nodes:

![Node Dataflow](/images/node-dataflow.png)

## Visualization

To visualize the robot's state and the different components, we use rerun which in an open source tool with a python integration package.

![Rerun](/images/rerun-viz.png)

## Localization

To localize the robot using IMU and wheel odometry data, we use an Extended Kalman Filter (EKF) using an open source package explained in the below paper: [https://arxiv.org/pdf/2310.15774](https://arxiv.org/pdf/2310.15774)

![EKF](/images/ekf.png)

It is a simple on-manifold extended kalman filter (EKF) with a standard inertial navigation process model, and encoder measurement model, with some static initialization smarts for sensor biases.

What does this give us?
* Centimeter accuracy for short-term submap building
* Decimeter accuracy for long-term environmental mapping
* A probabilistic and consistent representation of uncertainty (how bad is our estimate)?
* Obviously, long-term drift (don’t care as much for this iteration)

# Mapping

To map the robot's environment and provide information for what obstacles are in the robot's path, we use a combination of a RealSense camera and the robot pose estimate from the localization node.

We use the open source PyWaveMap package to build a 3D occupancy grid of the robot's environment, from the paper: [https://arxiv.org/pdf/2306.01279](https://arxiv.org/pdf/2306.01279)

![PyWaveMap](/images/wavemap.png)

This provides us a complete volumetric and hierarchical representation of an environment.

* Measurement model is still Bayesian, so the map benefits from an accurate pose uncertainty
* Wavelet-based, so we can scale the fidelity of the map losslessly (abides by MRA conditions)
* Updates are applied in the wavelet space, so are extremely efficient, and allow us to run dense 5cm mapping at 20Hz on a base RPI

What does this give us?

* Collision avoidance, path planning, environmental exploration and reconstruction…
* The ability to integrate sparse (LiDAR) and dense (RGB-D) measurements in a single map

The results from mapping implemented are shown below:

![Mapping Results](/images/mapping-results.png)
