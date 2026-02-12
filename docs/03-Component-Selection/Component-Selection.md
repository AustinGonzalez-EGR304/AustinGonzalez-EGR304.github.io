---
title: Module's Selected Major Components
---

## My Role & Responsibilities

I am responsible for the Camera Actuation subsystem. This subsystem controls two stepper motor drivers to rotate a low-weight camera and uses a Hall effect sensor to establish a repeatable “home” position reference. The microcontroller generates STEP and DIR pulse signals (and enable control) for each motor driver, reads the Hall sensor as a digital interrupt input for homing, and communicates with the Control subsystem through a UART RX/TX link. The subsystem uses a 12V motor power rail for the stepper drivers/motors and a regulated 3.3V rail for the microcontroller and logic signals. The design prioritizes clean power distribution, grounding, and debouncing/filtering to prevent motor noise from causing resets or false home triggers.

---

## Module's Selected Major Components

### ESP32-S3-WROOM-1-N4

* **Manufacturer:** Espressif  
* **Core:** Dual-core Xtensa LX7  
* **Flash:** 4MB (N4 variant)  
* **Operating Voltage:** 3.3V  
* **GPIO:** Up to 45 programmable GPIO  
* **Wireless:** Wi-Fi + BLE (not required but available)  
* **Package:** SMD Module (castellated edges)  
* **Approx. Price:** ~$5–$7  
* **Product Page**

| Pros | Cons |
|------|------|
| Dual-core processor provides strong performance for motor control and sensor handling | Includes wireless hardware that is not required for this subsystem |
| Large GPIO count for stepper drivers, hall sensor, and debugging | Slightly higher cost than minimal MCUs |
| Mature ESP-IDF and Arduino ecosystem support | Higher power consumption than basic MCUs |
| Integrated USB support for easier programming/debugging | |
| Ample memory (4MB flash) for future expandability | |

---

### Raspberry Pi Pico W (Wireless Disabled)

* **Manufacturer:** Raspberry Pi  
* **Core:** Dual-core ARM Cortex-M0+ @ 133 MHz  
* **Flash:** 2 MB (on-board QSPI)  
* **Operating Voltage:** 3.3V  
* **GPIO:** ~26 usable GPIO  
* **Wireless:** Present but can be disabled  
* **Package:** SMD Module or small board  
* **Approx. Price:** ~$4  
* **Product Page**

| Pros | Cons |
|------|------|
| Very low cost | Fewer hardware peripherals compared to ESP32 |
| Strong support and examples for PWM / control | No native Wi-Fi/BLE if wireless is disabled |
| Dual cores suitable for motion control tasks | Less flash and SRAM than ESP32 |
| Extensive community support | Limited ADC resolution vs some MCUs |

---

### STM32G071RB (STM32G0 Series MCU)

* **Manufacturer:** STMicroelectronics  
* **Core:** ARM Cortex-M0+ @ 64 MHz  
* **Flash:** 128 KB  
* **Operating Voltage:** 1.8V – 3.6V  
* **GPIO:** Up to ~51 GPIO  
* **Wireless:** None  
* **Package:** LQFP or UFBGA  
* **Approx. Price:** ~$3  
* **Product Page**

| Pros | Cons |
|------|------|
| Good PWM and timer hardware for precise stepper control | Requires external debugger (e.g., ST-Link) |
| Excellent power efficiency | MCU ecosystem differs from ESP32 |
| No wireless hardware overhead | Less RAM than ESP32 |
| Many GPIO and peripheral options | Flash size smaller |

---

## Microcontroller Resource Check (Candidate: ESP32-S3-WROOM-1-N4)

| Resource / Feature | Needed? | ESP32-S3 Provides | Meets Need? | Notes |
|--------------------|--------:|-------------------|:-----------:|-------|
| Total usable GPIO | ~12–15 | Many GPIO available | ✅ | Enough for 2 drivers + hall + UART + debug |
| UART interfaces | 1 | Supported | ✅ | Reserve one for team communication |
| I2C interfaces | 0–1 | Supported | ✅ | Optional expansion |
| SPI interfaces | 0 | Supported | ✅ | Only needed if SPI drivers used |
| Interrupt-capable GPIO | 1 | Supported | ✅ | Hall sensor input |
| ADC | Optional | Available | ✅ | Required for analog Hall |
| 3.3V operation | Yes | Native | ✅ | Supplied from buck |
| Boot/strapping pins | Must avoid conflicts | GPIO0, GPIO45, etc. | ⚠️ | Avoid for STEP/HOME |
| Programming/Debug | Yes | Supported | ✅ | Provide reset/boot access |

---

## Power Management

### AP63203WU-7

* **Package:** TSOT-23-6  
* **Output:** Fixed 3.3V  
* **Max Current:** 2A  
* **Input Range:** 3.8V – 32V  
* **Approx. Price:** ~$0.50–$0.80  
* **DigiKey Link**

| Pros | Cons |
|------|------|
| High output current (2A) | Requires careful PCB layout |
| Wide input range (good for 12V systems) | Needs external inductor and capacitors |
| High efficiency | Small package harder to solder |
| Well-documented | |

---

### RT8008-33GB

* **Package:** SOT-23-5  
* **Output:** Fixed 3.3V  
* **Max Current:** ~600mA  
* **Input Range:** Up to ~23V  
* **Approx. Price:** ~$1.30–$1.50  
* **DigiKey Link**

| Pros | Cons |
|------|------|
| Very small footprint | Lower max current |
| Fixed 3.3V simplifies design | Not ideal for ESP32 + expansion |
| Fewer pins | Narrower input range |

---

### MP2451DT-LF-Z (Fixed 3.3V Variant)

* **Package:** TSOT-23-6  
* **Output:** Fixed 3.3V  
* **Max Current:** 1A  
* **Input Range:** Up to 36V  
* **Approx. Price:** ~$2.00–$2.50  
* **DigiKey Link**

| Pros | Cons |
|------|------|
| Handles higher input voltage | More expensive |
| Good efficiency | Lower current than AP63203 |
| Compact package | Requires careful layout |

**Selected:** AP63203 — provides sufficient current headroom and lower EMI for stable PCB integration.

---

## Sensor

### Allegro A1324 (SOT-23W Linear Hall Sensor)

* **Manufacturer:** Allegro MicroSystems  
* **Type:** Linear Analog Hall Sensor  
* **Operating Voltage:** 3.0V – 5.5V  
* **Package:** SOT-23W  
* **Approx. Price:** ~$1.00–$1.50  
* **Product Page**

| Pros | Cons |
|------|------|
| Analog output allows measurable value | Requires ADC |
| Enables firmware thresholding | Requires calibration |
| Compact SMD footprint | Slight firmware complexity |

---

### TI DRV5053 (Selected)

* **Manufacturer:** Texas Instruments  
* **Type:** Linear Analog Hall Sensor  
* **Operating Voltage:** 2.7V – 6.0V  
* **Package:** SOT-23 / SON  
* **Approx. Price:** ~$1.50–$2.50  
* **Product Page**

| Pros | Cons |
|------|------|
| Clean analog output | Requires ADC |
| Stable and noise resistant | Slightly higher cost |
| 3.3V compatible | |

---

### Diodes Inc. AH337

* **Manufacturer:** Diodes Incorporated  
* **Type:** Linear Analog Hall Sensor  
* **Operating Voltage:** 3.0V – 5.5V  
* **Package:** SOT-23  
* **Approx. Price:** ~$0.80–$1.30  
* **Product Page**

| Pros | Cons |
|------|------|
| Low cost | Requires ADC |
| Small footprint | Needs thresholding |
| Easy PCB integration | Mid-rail interpretation needed |

---

## Actuator

### 28BYJ-48 High Quality Stepper Motor

* **Type:** 4-phase unipolar  
* **Operating Voltage:** 12 V  
* **Rated Current:** ~50 mA/phase  
* **Step Angle:** 5.625°/64  
* **Approx. Price:** ~$1–$2  

| Pros | Cons |
|------|------|
| Very low current | Lower precision |
| Inexpensive | Plastic gears |

---

### Stepperonline NEMA 14 Bipolar Motor (Selected)

* **Type:** NEMA 14 bipolar  
* **Step Angle:** 1.8°  
* **Rated Current:** ~0.4 A/phase  
* **Operating Voltage:** 12 V  
* **Approx. Price:** ~$9–$20  

| Pros | Cons |
|------|------|
| Moderate torque | Larger footprint |
| Precision stepping | Requires driver tuning |

---

### NEMA-17 Size Stepper Motor

* **Type:** Bipolar  
* **Step Angle:** 1.8°  
* **Rated Current:** ~0.35 A/phase  
* **Operating Voltage:** 12 V  
* **Approx. Price:** ~$13–$15  

| Pros | Cons |
|------|------|
| Higher torque | Larger size |
| Smooth motion | More than needed |

---

## Stepper Driver Selection

### DRV8825

* **Operating Voltage:** 8.2V – 45V  
* **Max Current:** ~2.2A/phase  
* **Microstepping:** Up to 1/32  
* **Approx. Price:** ~$3–$5  

| Pros | Cons |
|------|------|
| Works natively at 12V | Requires current adjustment |
| High headroom | Larger module footprint |
| Reliable and documented | |

---

### DRV8834

* **Operating Voltage:** 2.5V – 10.8V  
* **Max Current:** ~1.5A/phase  
* **Microstepping:** Up to 1/32  
* **Approx. Price:** ~$5–$8  

| Pros | Cons |
|------|------|
| Compact SMD | Slightly low voltage rating |
| Good for integration | Layout complexity |

---

### TMC2209

* **Operating Voltage:** 4.75V – 36V  
* **Max Current:** ~1.2A RMS  
* **Microstepping:** Up to 1/256  
* **Approx. Price:** ~$6–$10  

| Pros | Cons |
|------|------|
| Very smooth/quiet | Higher cost |
| Excellent current control | More complex configuration |

---

## Final Recommendation

For prototyping and reduced risk, the DRV8825 is selected due to strong 12V compatibility and ease of integration. For final PCB refinement and improved motion smoothness, DRV8834 or TMC2209 may be used.
