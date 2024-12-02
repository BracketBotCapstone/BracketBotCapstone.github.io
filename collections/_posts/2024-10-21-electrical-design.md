---
layout: post
title: Electrical Design
date: 2024-10-21
summary: Electrical Design.
categories: electrical design
permalink: electrical-design
---

# Electrical Design

The electrical design is based on the Wheeled-Base Robot design and is shown below:

![Electrical Design](/images/electrical-design.png)

## Compute: Raspberry Pi 5

The Raspberry Pi 5 is used as the main compute for the robot. It is responsible for running the operating system, the user interface, and any AI models.

## Power: 20V Drill Battery

The 20V drill battery is used to power the robot. It is a powerful battery that is more than enough to power the robot and the components, and is easily accessible and available.

## Power Switch: E-stop Button

The E-stop button is used to immediately stop the robot in case of an emergency. It is a simple and effective way to stop the robot and is easily accessible.

## Voltage Regulator: XH-M609

The XH-M609 is used to step down the voltage from the battery to the appropriate voltage for the Raspberry Pi and the rest of the components.

## Motor Controller: ODrive3.6 FOC Controller

The ODrive3.6 is used to control the motors. It is a Field-Oriented Control (FOC) motor controller that is capable of high-performance motion control, and easy integration with the Raspberry Pi over UART communication and with the 24V hoverboard motors we are using.

## Motor: 24V Hoverboard Motors

The 24V hoverboard motors are used to power the wheels of the robot. They are powerful motors that are capable of providing the necessary traction for the robot to move.

They are a 3 phase FOC motor with an integrated hall effect encoder and are ideal for the application.

## Auto-deploy legs: MG90S Micro Servo

The MG90S Micro Servo is used to deploy the legs of the robot. It is a simple and effective way to deploy the legs and is easily accessible.

## Camera: Intel RealSense D435i

The Intel RealSense D435i is used to provide the robot with depth perception. It is a powerful camera that is capable of providing the necessary depth information for the robot to navigate and interact with the environment.

## IMU: LSM6DS3

The LSM6DS3 is used to provide the robot with orientation information. It is a simple 6 DOF IMU that is capable of providing the necessary orientation information for the robot to navigate and interact with the environment.
