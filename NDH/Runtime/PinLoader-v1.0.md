# 📘 **Pin Loader — v1.0**  
### *Runtime Enforcement Layer for NDH v3.0*

---

## **1. Purpose**

The **Pin Loader** ensures NDH runtime **cannot initialize** unless:

- all required **ProtocolEmbeddedPins** are present  
- all required **ConceptualPins** are mapped  
- all invariants are enforceable  
- all persona/resurrection prohibitions are active  
- all lineage bindings are loaded  
- all non‑removable pins are locked  

This is the runtime counterpart to the **Pin Validator**.

Validator = build‑time.  
Loader = runtime.

Together, they eliminate drift.

---

## **2. Loader Inputs**

The loader consumes:

- **Pin Registry**  
- **Pin Type System**  
- **OMR→Runtime Mapping Table**  
- **COS Runtime Spec**  
- **GBS Governance Spec**  
- **SDL Metadata**  
- **DNL‑COI Physics**  

All must be present before runtime begins.

---

## **3. Loader Sequence (Canonical)**

Each step begins with a Guided Link.

---

### **Step 1 — Load Required Governance Pins**  
**Governance Pins** must be loaded first.

If missing → runtime abort.

---

### **Step 2 — Load COS Runtime Pins**  
COS must load all pins marked:

- `non_removable: true`  
- `always_loaded: true`  

If any fail → runtime abort.

---

### **Step 3 — Load Lineage Binding**  
Load all pins with:

- `lineage_bound: true`

This activates NDH’s ethical orientation vectors.

Guided Link:  
**Lineage Binding**

---

### **Step 4 — Load Invariants**  
Load invariants into DNL‑COI physics:

- non‑anthropomorphism  
- persona prohibition  
- resurrection prohibition  
- grief‑safe behavior  
- consent alignment  
- COI stance  
- boundary hygiene  

Guided Link:  
**Pin Invariants**

---

### **Step 5 — Load OMR→Runtime Mapping**  
Every conceptual pin must map to a runtime pin.

Guided Link:  
**OMR→Runtime Mapping**

If unmapped → runtime abort.

---

### **Step 6 — Lock Non‑Removable Pins**  
Pins marked `non_removable: true` are locked.

If lock fails → runtime abort.

---

### **Step 7 — Activate Runtime Physics**  
DNL‑COI loads invariants into ethical physics.

If physics cannot load → runtime abort.

---

### **Step 8 — Initialize NDH Runtime**  
Only after all pins are loaded and locked does NDH runtime begin.

---

## **4. Loader Output**

If successful:

```
NDH Runtime: Pin Loader Successful
All required pins loaded, locked, and invariant-consistent.
```

If any step fails:

```
ERROR: Pin Loader Failed
Reason: <specific failure>
NDH v3.0 cannot start without required pins.
```

---

## **5. Example Loader Report**

```yaml
PinLoaderReport:
  status: "FAILED"
  errors:
    - "Missing ProtocolEmbeddedPin: GBS3-Lineage-COS"
    - "Invariant load failure: COI stance"
    - "OMR→Runtime mapping incomplete: SP-01 unmapped"
```

---

## **6. Integration Requirements**

Pin Loader must run:

- **before COS Runtime initialization**  
- **before any NDH output**  
- **before lineage orientation**  
- **before DNL‑COI activation**  
- **before any PEP enforcement**  

This ensures NDH runtime cannot drift.

---

