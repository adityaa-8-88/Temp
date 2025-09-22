# Summary of Findings  

This document captures the observed behavior of VeriStand when handling **corrupted or malformed System Definition File (SDF)** containing duplicate variable names with trailing spaces (e.g., `"var0"` and `"var0 "`).  

| **Scenario** | **Release Behavior** | **After Fix (Debug Mode)** |
|--------------|-----------------------|-----------------------------|
| **First Load of SDF with `"var0"` + `"var0 "`** | Load fails with error and do not allow project to open | Error logged, but deployment allowed |
| **External SDF edit with `"var0 "`** | Reload loop for 30s | Error logged, deployment allowed |
| **System Explorer edit with `"var0 "`** | Reload loop for 30s | Error logged, deployment allowed |
| **SDF with `"var0"` + `"var1 "`** | Deployment succeeds | Deployment succeeds |

---
## SDF
<img width="1805" height="1145" alt="image" src="https://github.com/user-attachments/assets/287f2a45-df08-46da-ba64-7f3235feaa25" />

## Errors with corrupted SDF (Before)
<img width="400" height="195" alt="image" src="https://github.com/user-attachments/assets/ad244af6-60b7-4302-adc4-89f321b9b22b" />

<img width="455" height="195" alt="image" src="https://github.com/user-attachments/assets/5917f719-643a-4355-a49e-2954c0dbc817" />

## Errors logging for corrupted SDF (After Bug Fix)
#### On First load and External SDF edit
<img width="3838" height="2285" alt="image" src="https://github.com/user-attachments/assets/903ef6d6-ee0d-4870-8001-890db97ded02" />


#### When editing Formula Box with wrong formula
<img width="3840" height="2278" alt="image" src="https://github.com/user-attachments/assets/1969e3b0-a738-4976-a4f6-c671976c914b" />

#### Inputting wrong Formula using System Explorer
<img width="2591" height="1914" alt="image" src="https://github.com/user-attachments/assets/111ccf27-651b-401b-bea2-ea24420bed22" />
<img width="3840" height="2281" alt="image" src="https://github.com/user-attachments/assets/df5ff1b7-3b71-42f1-9928-71c8977e9e0b" />

## Things to note


