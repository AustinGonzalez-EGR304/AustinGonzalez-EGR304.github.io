---
title: Module's Requirements
---

## Module Requirements
The following sections document the requirements that the this module need to fulfills to create a camera actuator that can cover near 360 degree coverage in the horizontal and 90 in the vertical direction. The actuation of the camera should be easy to control from the controller it self and should have safguards inplace ot prevent self inflicted damage. 

| **Requirement Description** | **Measure of<br> Threshold** | **Target<br>Measure** | **Stretch<br>Requirement<br>(Y-N)** |
|-----------------------------|------------------------------|------------------------|:----------------------------------:|
| 12V power input for motor rail | Accepts 11.0–13.0V | Nominal 12.0V input | No |
| 3.3V regulated logic supply for ESP32 | 3.2–3.4V under load | 3.30V ±2% | No |
| Microcontroller is ESP32-based | ESP32 running firmware and issuing motor pulses | ESP32 DevKit / ESP32-WROOM | No |
| Motor type supports precise camera rotation | Repeatable incremental motion without stalling | 2x stepper motors (Pan + Tilt) | No |
| Dedicated driver per stepper motor | send commands to motor | 2x stepper drivers  | No |
| Pan axis rotation control | Executes commanded position change | Pan motion with accel/decel ramp | No |
| Tilt axis rotation control | Executes commanded position change | Tilt motion with accel/decel ramp | No |
| Home setting capability for repeatable “zero” | Finds reference after power cycle | Home both axes on command/startup | Yes |
| End-of-travel protection (hardware) | Detects travel limit before mechanical bind | Limit switch/hall effect sensor at each end of travel (min/max) | No |
| Team command interface (wired) | Receives rotation commands reliably | UART command interface to main controller | No |
| Wireless command option (ESP32) | Able to send/receive Wi-Fi data | Wi-Fi command link (MQTT if required) | Yes |
| Connectorized wiring| Reliable build + maintenance | Screw/JST connectors for power, motors, switches | No |

