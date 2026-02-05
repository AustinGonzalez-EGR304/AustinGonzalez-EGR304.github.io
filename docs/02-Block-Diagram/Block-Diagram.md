---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Overview
The purpose of this block diagram is to illustrate the design of the Team 201 Camera Actuation subsystem and how it integrates with the broader scope of the project. This system features two stepper motors that control camera motion, allowing for nearly 180 degrees of viewing range.

Both 12 V and 3.3 V power supplies are used to power the stepper motors, motor drivers, and the ESP32 microcontroller. The subsystem receives commands from the Control subsystem via the ESP32’s UART communication interface and sends digital output signals to the motor drivers to accurately control camera movement.

Debugging features included in the design are on-board debug buttons, status indicator LEDs, and configurable jumpers.

## Block Diagram 

![Indivial Block diagram ](docs/02-Block-Diagram/314AustinBlockDiagram.drawio.png)
