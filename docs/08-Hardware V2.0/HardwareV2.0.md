---
title: Hardware V2.0
---

## Future Itteration
In the next iteration of the Automated Water Distribution System, several key enhancements will be implemented to significantly improve reliability, usability, and overall system performance. One major area of focus will be acoustic optimization. The current water pump produced noticeably loud operational noise, which affected the user experience. Version 2 will adopt quieter motor options and incorporate a self-priming, higher-quality pump to ensure smooth water delivery while reducing vibration and noise output. Similarly, the motors used for fertilizer stirring and dispensing will be upgraded to more efficient, with less audible output and improved durability.

Significant improvements will also be made to the PCB and electrical architecture. In Version 1, several jumpers were intentionally included as removable debugging points to allow rapid disconnects during subsystem testing. While useful early in development, these jumpers became largely unnecessary once the design stabilized and ultimately added extra cost, assembly complexity, and physical clutter. Version 2 will eliminate these jumpers by integrating direct PCB routing and reorganizing subsystem connections. At the same time, more onboard diagnostic LEDs will be added to provide clearer visual feedback for pump status, motor activity, error states, and power-rail conditions—enhancing troubleshooting without relying on removable wiring.

Another critical improvement will focus on thermal performance. In Version 1, the voltage regulator experienced elevated temperatures during extended operation, especially under full subsystem load. Version 2 will integrate improved thermal management strategies—such as adding a heat-spreader pad, selecting a regulator with higher current efficiency, or incorporating airflow paths or heatsinks—to maintain stable voltage delivery and extend component lifespan.

Collectively, these upgrades aim to create a Version 2 system that is quieter, cleaner in design, easier to diagnose, and far more robust in real-world operation.