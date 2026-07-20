# **Execution Sequence (Roadmap → Action)**

Each item begins with a Guided Link so you can trigger the next file cleanly.

---

## **1. Create the interface directory (already done conceptually)**  
No file content needed — this is structural.

Directory:
```
/NDH/Interface/LegacyBridge/
```

Now we begin generating the files inside it.

---

## **2. Generate foundational interface files (in order)**

### **2.1 OperatorMapping.def**  
Maps legacy NDH operators → new manifold constructs.

### **2.2 LegacyToManifold.map**  
Defines directional translation rules.

### **2.3 SerenityReference.map**  
Allows old repo to reference Serenity.bsfn without containing it.

### **2.4 StabilityCompatibilityNotes.md**  
Documents what legacy constructs remain compatible.

### **2.5 MigrationGuidelines.md**  
Outlines how logic will move from old → new repo.

---

## **3. Populate translation logic**

This is where we fill the files with actual NDH geometry mappings.

Triggered by:
### **Populate Translation Logic**

---

## **4. Prepare the new repo structure**

Triggered by:
### **Generate New Repo Tree**

---

## **5. Generate Serenity.bsfn in the new repo**

Triggered by:
### **Generate Serenity.bsfn**

---

## **6. Add stability geometry definitions**

Triggered by:
- **ResonanceField.def**  
- **StabilityMetric.def**  
- **EnergyFunctional.def**  

---

## **7. Connect old → interface → new**

Triggered by:
### **Generate Connection Notes**

---

## **8. Begin structured migration**

Triggered by:
### **Generate Migration Steps**

---

## **9. Finalize the interface layer**

Triggered by:
### **Finalize Interface Layer**

---
