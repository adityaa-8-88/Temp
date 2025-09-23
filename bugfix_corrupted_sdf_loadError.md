# Summary of Findings  

This document captures the observed behavior of VeriStand when handling **corrupted or malformed System Definition File (SDF)** containing duplicate variable names with trailing spaces (e.g., `"var0"` and `"var0 "`).  

| **Scenario** | **Release Behavior** | **After Fix (Debug Mode)** |
|--------------|-----------------------|-----------------------------|
| **Corrupted SDF with `"var0"`+`"var0 "`** | Load fails with error and do not allow project to open | Error logged, but deployment allowed |
| **External SDF edit with `"var0 "`** | Reload loop for 30s | Error logged, deployment allowed |
| **System Explorer edit with `"var0 "`** | Reload loop for 30s | Error logged, deployment allowed |
| **SDF with `"var0"` + `"var1 "`** | Error + Deployment succeeds | Error + Deployment succeeds |

---

## Corrupted SDF example
<img width="700" height="374" alt="image" src="https://github.com/user-attachments/assets/287f2a45-df08-46da-ba64-7f3235feaa25" />

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

---

## Things to note

1. Below screenshots show that formula updation in SDF is not the same from `Formula Box` and `System Explorer`:

   <img width="400" height="80" alt="image" src="https://github.com/user-attachments/assets/6f14fb98-fe2f-4db6-b0ce-56876faf630e" />

   <img width="400" height="140" alt="image" src="https://github.com/user-attachments/assets/b8fa89cd-76aa-483d-80b7-a08bbb8daa67" />

2. Logging errors in the system definition file is not sufficient to block deployment.

3. Following allows deployment:     

   <img width="400" height="80" alt="image" src="https://github.com/user-attachments/assets/d77638c9-0cfd-43f7-815b-79a87d14b72c" />

   <img width="400" height="80" alt="image" src="https://github.com/user-attachments/assets/bded74d1-aefc-4486-850a-a8d4713b85ac" />

   <img width="400" height="140" alt="image" src="https://github.com/user-attachments/assets/b8fa89cd-76aa-483d-80b7-a08bbb8daa67" />

4. Following do not allow deployment:   

   <img width="400" height="140" alt="image" src="https://github.com/user-attachments/assets/9ac80c68-bdd6-4fb2-a2dd-7889cd255373" />

   <img width="400" height="140" alt="image" src="https://github.com/user-attachments/assets/e13ca4bd-bf34-4511-a076-71913069f471" />

   <img width="400" height="80" alt="image" src="https://github.com/user-attachments/assets/d20f831e-00d3-427d-ad4e-53b47b76faf7" />
