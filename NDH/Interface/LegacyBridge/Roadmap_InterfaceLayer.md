# **NDH Interface Layer Roadmap**
*A structured plan for preparing the old repo to communicate with the new NDH stability‑geometry repo.*

---

## **Phase 1 — Establish the Interface Manifold**
Create the structural hinge between repos.

### **1. Create the interface directory**
```
/NDH/Interface/LegacyBridge/
```

### **2. Add foundational mapping files**
- **OperatorMapping** — maps old operators to new manifold constructs  
- **LegacyToManifold** — defines translation rules  
- **SerenityReference** — references `Serenity.bsfn` without duplicating it  
- **StabilityCompatibilityNotes** — documents what carries over safely  
- **MigrationGuidelines** — outlines future movement into the new repo  

This phase creates the **Quiet Apex** between repos.

---

## **Phase 2 — Define Translation Logic**
Build the actual “bridge” rules.

### **3. Map old operators to new geometry**
Document how early NDH constructs relate to:

- manifold state  
- resonance field  
- stability metric  
- basin functions  

### **4. Establish directional flow**
Old → Interface → New  
Never New → Old.

### **5. Document deprecated constructs**
Mark early prototypes that should not migrate.

This phase ensures **non‑dual stability** between repos.

---

## **Phase 3 — Prepare the New Repo**
Set up the destination manifold.

### **6. Create the new repo structure**
```
/NDH/Manifold/
  /Core/
  /Stability/
    /Geometry/
      /BasinFunctions/
```

### **7. Place Serenity.bsfn in its canonical location**
```
/NDH/Manifold/Stability/BasinFunctions/Serenity.bsfn
```

### **8. Add stability geometry definitions**
- **ResonanceField**  
- **StabilityMetric**  
- **EnergyFunctional**  

This phase builds the **Serenity basin** in code form.

---

## **Phase 4 — Connect the Repos**
Make them “talk” without merging.

### **9. Add reference pointers in the old repo**
Old repo files should reference:

- Quiet Apex  
- Serenity basin  
- stability geometry  

via the interface layer only.

### **10. Add compatibility notes**
Explain how old constructs conceptually map to new ones.

### **11. Validate manifold separation**
Ensure:

- no basin functions in the old repo  
- no legacy operators in the new repo  
- all cross‑talk goes through `/LegacyBridge/`

This phase preserves **dimensional integrity**.

---

## **Phase 5 — Begin Migration**
Move logic gradually.

### **12. Migrate stable constructs first**
Anything already aligned with NDH geometry moves early.

### **13. Leave prototypes behind**
Old experimental logic stays in the old repo.

### **14. Document each migration**
Every move gets a mapping entry in:

- `MigrationGuidelines.md`  
- `LegacyToManifold.map`

This phase is the **relaxation flow** from old manifold → new manifold.

---

## **Phase 6 — Finalize the Interface Layer**
Lock the hinge.

### **15. Freeze the interface layer**
Once stable:

- no new operators added  
- no basin functions added  
- only mapping updates allowed  

### **16. Treat the interface as canonical**
It becomes the permanent bridge between:

- early NDH  
- full NDH manifold  

### **17. Maintain forward compatibility**
Future NDH expansions extend the new repo, not the old.

This phase completes the **Quiet Apex → Serenity** transition at the repo level.

---

# **Single‑Sentence Summary**
> The roadmap builds a formal interface layer that lets the old NDH repo communicate with the new stability‑geometry repo without merging, preserving manifold boundaries and enabling structured migration.

---

