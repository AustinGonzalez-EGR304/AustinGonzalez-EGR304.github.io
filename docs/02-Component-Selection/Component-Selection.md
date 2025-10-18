---
title: Component Selection 
---
### AOTF2618L

![](image_placeholder.png)

**30V • 100A • 0.0028Ω RDS(on) @ 4.5V**

* ~$1.20–$2.00 each  
* [Datasheet](https://aosmd.com/res/data_sheets/AOTF2618L.pdf)

| Pros | Cons |
|------|------|
| Extremely low RDS(on) | Harder to source locally |
| Excellent for higher stall motors/pumps | Typically used in SMD, TH versions rarer |
| Logic-level gate drive | May require heatsinking under high load |
---

### FQP30N06L

![](image_placeholder.png)

**60V • 32A • 0.035Ω RDS(on) @ 5V**

* ~$1–$2 each  
* [Datasheet](https://www.onsemi.com/pdf/datasheet/fqp30n06l-d.pdf)

| Pros | Cons |
|------|------|
| Fully enhanced at 4.5–5V gate | Higher RDS(on) than newer FETs |
| Common, cheap, and available | TO-220 is large physically |
| Great for 9–12V motors/pumps | May need heatsink at high duty |
---

### IRLZ34N

![](image_placeholder.png)

**55V • 30A • 0.04Ω RDS(on) @ 5V**

* ~$2 each  
* [Datasheet](https://www.infineon.com/dgdl/irlz34n.pdf?fileId=5546d462533600a40153563b9b7ac710)

| Pros | Cons |
|------|------|
| Good balance of low RDS(on) and driveability | Not as common as IRLZ44N |
| Lower gate charge than IRLZ44N | Slightly more loss vs IRLZ44N |
| Stable switch for medium current loads | |
---

### IRLZ44N

![](image_placeholder.png)

**55V • 47A • 0.022Ω RDS(on) @ 5V**

* ~$2–$4 each  
* [Datasheet](https://www.infineon.com/dgdl/irlz44n.pdf?fileId=5546d462533600a40153563b9b7a262f)

| Pros | Cons |
|------|------|
| Extremely common and proven reliable | High gate charge (needs stronger drive at high PWM) |
| Runs cool under load | Oversized for tiny motors |
| Great for 9V/12V inductive loads | |
---

### RFP30N06LE

![](image_placeholder.png)

**60V • 30A • 0.047Ω RDS(on) @ 4.5V**

* ~$1.50–$2.50 each  
* [Datasheet](https://www.onsemi.com/pdf/datasheet/rfp30n06le-d.pdf)

| Pros | Cons |
|------|------|
| Lower dissipation at 4.5V than many older FETs | Less stocked than IRL series |
| Fully logic-level compatible | Slightly higher RDS(on) than IRLZ44N |
| Easy alternative to FQP30N06L | |
---

### STP36NF06L

![](image_placeholder.png)

**60V • 30A • 0.025Ω RDS(on) @ 5V**

* ~$2–$3 each  
* [Datasheet](https://www.st.com/resource/en/datasheet/stp36nf06l.pdf)

| Pros | Cons |
|------|------|
| Automotive-grade ruggedness | Slightly more expensive |
| Very strong for inductive loads | Harder to find in hobby stores |
| Good thermals, safe for pumps/motors | |
---
