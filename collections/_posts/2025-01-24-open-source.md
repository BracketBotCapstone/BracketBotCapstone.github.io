---
layout: post
title: Open Source Design, Code and Documentation
date: 2025-01-24
summary: Open Source Design, Code and Documentation.
categories: open source
permalink: open-source
---

# Documentation

We have made the documentation for the robot open source to go from kit to robot in a few hours.

[Documentation](https://docs.bracket.bot)

# Open Source Design and Code

We engineered Bracket Bot to be simple, powerful, and upgradeable.

## Mechanical Design

- Modular aluminum extrusion frame for easy prototyping
- Low cost screw clamps to mount motors
- 3D printed mounts with open source CAD

![Mechanical Design](/images/design_wireframe.avif)

## Electrical Design

- Familiar Raspberry Pi 5
- ODrive3.6 FOC motor controller
- Common 20V drill battery
- Battery life of 20h+ idle, 4-5h of driving
- No soldering
- Upgradable to the new [Nvidia Jetson Nano Super](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/nano-super-developer-kit/)

![Electrical Design](/images/electrical_schematic.avif)

## Software

- Everything is written in Python. No need to build C++ files.
- Working 3D mapping and navigation examples
- Speaker, microphone, camera examples
- [Quickstart](https://github.com/BracketBotCapstone/quickstart) repo gets you up (literally) and running in 10 minutes.

![Software](/images/mapping.avif)

## Part List

The part list is open source, free for anyone to use.

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQQmE319tceGByLvz1FXWhRGoM_pfUTEIIWMFuFlXxz93pQWRhi4qB2XeprDzDi-LsSrjYzvvRTOgbD/pubhtml?gid=1339768699&single=true" width="100%" height="600"></iframe>
