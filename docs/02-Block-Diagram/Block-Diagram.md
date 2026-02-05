---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Overview
This needs to be updated with a brief purpose for having the block diagram.
Things to mention are:
* power levels
* sensor
* Actuator
* team connections
* Power source

The purpose of this block diagram is to illustrate the design of the Team 201 Camera Actuation subsystem and how it integrates with the broader scope of the project. This system features two stepper motors that control camera motion, allowing for nearly 180 degrees of viewing range.

Both 12 V and 3.3 V power supplies are used to power the stepper motors, motor drivers, and the ESP32 microcontroller. The subsystem receives commands from the Control subsystem via the ESP32’s UART communication interface and sends digital output signals to the motor drivers to accurately control camera movement.

Debugging features included in the design are on-board debug buttons, status indicator LEDs, and configurable jumpers.

To get some initial formatting help, one can view ["here"](https://embedded-systems-design.github.io/EGR304DataSheetTemplate/Appendix/basic-markdown-examples/) some basic techniques.


## Example Block Diagram 
Showing an example of how to import a screenshot of the block diagram created outside of git and brought into a page.

![Example of Indivial Block diagram ](individual-block-diagram.png)
