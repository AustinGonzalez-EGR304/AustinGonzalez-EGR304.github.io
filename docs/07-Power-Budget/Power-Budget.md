---
title: Power Budget
---

## Overview
## Overview
After selecting components in [Component Selection](https://austingonzalez-egr304.github.io/02-Component-Selection/Component-Selection/) we needed to ensure that the subsection would have the power it needs with the added requirement of a safety margin. Therefore, we took the active components, meaning we excluded switches and passive components, and ensured our power supply as well as our regulators were able to get the power needed. The specifications for each piece came from their datasheet except in the case of the motor where it will only get power through the motor driver so it has different tolerances.


![budget1](Power Budget T102 EGR 304.png){style width:"350" height:"300;"}

## Conclusions
I was able to determine that I had originally sourced a voltage regulator and power supply that were not sufficient to power the system. Fortunately, this issue was caught early in the design stage, allowing us to replace them with higher-capacity components with minimal impact on the estimated budget.

From the prepared Power Budget, it was determined that the total current draw of all components are within the 12 V 5 A barrel-jack supply if all loads operated simultaneously. This estimate uses stall current values for the motors, which represent worst-case startup conditions. In practice, the motors will not all start or run at the same time, and the control logic limits concurrent operation of high-current devices (motors), but enough room for error is allocated. 
## Resouces

The power budget as a PDF download is available [*here*](Power Budget T102 EGR 304.pdf), and a Microsoft Excel Sheet [*here*](Power Budget T102 EGR 304.xlsx).