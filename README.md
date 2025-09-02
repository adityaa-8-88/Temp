# Labview Custom Controls - C#

## Table of Contents
- [Completed Tasks](#completed-tasks)
- [Currently Working On](#currently-working-on)
- [Reference to Flow Diagram (my understanding till now)](#reference-to-flow-diagram-my-understanding-till-now)
- [Suggestions](#suggestions)

---

## Completed Tasks

---

- **Changed project name** from `CustomControlExamples` to `LabviewCustomControls`  
  [USER STORY 3216412](https://dev.azure.com/ni/DevCentral/_workitems/edit/3216412)

  <img width="2136" height="392" alt="Screenshot 2025-08-20 122822" src="https://github.com/user-attachments/assets/73bb0453-d14b-406c-9325-ae02dd0d416f" />

---

- **Removed unwanted components and code files** from  
  [skolthay-VS-LVCustomScreenControl](https://dev.azure.com/ni/Users/_git/skolthay-VS-LVCustomScreenControl?path=/Source/CustomControlExample/VeriStandCustomControls)  
  and made [adisingh-VS-LVCustomScreenControl](https://dev.azure.com/ni/Users/_git/adisingh-VS-LVCustomScreenControl)  
  [USER STORY 3220416](https://dev.azure.com/ni/DevCentral/_workitems/edit/3220416)

  <img width="311" height="230" alt="Screenshot 2025-08-20 123549" src="https://github.com/user-attachments/assets/fa437afc-ed5e-409e-86be-6d58d44c4639" />

  <div style="display:flex; gap:10px; align-items:flex-start;">
    <img width="300" height="700" alt="Screenshot 2025-08-20 124010" src="https://github.com/user-attachments/assets/a46d1d87-6968-4f7f-9076-0ee2639c7bd1" />
    <img width="350" height="600" alt="image" src="https://github.com/user-attachments/assets/7e43dbf7-1825-42c8-8ef8-7b7f18cf2bc7" />
  </div>

---

- **Implemented proper MVVM patterns** and cleaned `viewModels` and `models`  
  [USER STORY 3185830](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185830),  
  [USER STORY 3185829](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185829),  
  [USER STORY 3210573](https://dev.azure.com/ni/DevCentral/_workitems/edit/3210573)

  <img width="350" height="400" alt="Screenshot 2025-08-20 125930" src="https://github.com/user-attachments/assets/1acd1ec9-913b-47ba-b140-5fdf21e79edd" />

---

- `Veristand.exe` no longer remains in the task manager  
  [USER STORY 3185748](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185748) `[BUG]veristand.exe`  

  <img width="650" height="250" alt="Screenshot 2025-08-20 134519" src="https://github.com/user-attachments/assets/4df26f32-bdd5-421b-8cbd-c851a78d149b" /><br>

  - Called `CloseVIAsync()` which was not being called earlier → **solved half of the test cases**  
  - Ensured proper calling and now its closing `veristand.exe` for all test cases

---

- **Fixed the schema for the XML (no JSON string)**  
  [USER STORY 3185761](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185696)

  <img width="3363" height="391" alt="Screenshot 2025-08-20 140509" src="https://github.com/user-attachments/assets/b15cdd11-e173-4e92-8d45-fb22a9a33527" />
  <img width="2410" height="924" alt="Screenshot 2025-08-20 140751" src="https://github.com/user-attachments/assets/ba62235b-54bf-4058-9db8-e5aee2b25ec0" />

---

- **Control Library**: tested types → String, Boolean, File path, Numeric  
  [USER STORY 3185762](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185762)

  <img width="380" height="300" alt="Screenshot 2025-08-20 135143" src="https://github.com/user-attachments/assets/0216d3f0-bf85-4ca5-8838-c2f4ecd4b3a2" />

---

- **Model Reduction**: There are multiple model files storing the same or overlapping information. So reduced 6 models to just 3 models. 
  [USER STORY 3245247](https://dev.azure.com/ni/DevCentral/_workitems/edit/3245247)

<img width="2562" height="1260" alt="image" src="https://github.com/user-attachments/assets/43fca743-af04-4587-aba4-df39c343c5dd" />
<img width="2743" height="1036" alt="image" src="https://github.com/user-attachments/assets/77abb1b2-6c60-4693-8b75-cabcb0967969" />





## Currently Working On

---

- **Resource Cleanup** : Trying to implement IDisposable pattern  
  [USER STORY 3185837](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185837)
  
- **Array and DataSource not implemented/tested yet**  + **Trying collapsible section and grouping**  
  [USER STORY 3185762](https://dev.azure.com/ni/DevCentral/_workitems/edit/3185762)

---

## Reference to Flow Diagram (my understanding till now)

---

<img width="5243" height="4106" alt="diagram-export-9-2-2025-4_08_16-PM" src="https://github.com/user-attachments/assets/59a933ce-bc18-4b77-b449-c2c8bf2558e6" />

---

## Suggestions

---

### 🔹 Reducing Redundancy
- There are multiple `model` files storing the same or overlapping information.  
- Can we explore integrating these into **one or fewer models** to:  
  - Reduce redundancy  
  - Improve maintainability  
  - Simplify the structure  

---
