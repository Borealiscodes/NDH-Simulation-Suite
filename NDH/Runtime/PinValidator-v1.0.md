# 📘 **Pin Validator — v1.0**  
### *Build‑Time Enforcement for NDH Runtime & Governance Pins*

---

## **1. Purpose**

The **Pin Validator v1.0** ensures NDH **cannot compile** unless:

- all required **ProtocolEmbeddedPins** exist  
- all required **ConceptualPins** are mapped  
- COS Runtime declares its governance pins  
- GBS references the same pins  
- SDL stores pin metadata  
- DNL‑COI enforces pin invariants  

This validator eliminates the **Pin‑Forgetting Cascade** documented in  
**EC‑004**.

---

## **2. Validator Inputs**

The validator consumes four registries:

- **Pin Registry** — all pins defined in NDH  
- **COS Runtime Spec** — required runtime pins  
- **GBS Governance Spec** — required governance pins  
- **OMR→Runtime Mapping Table** — conceptual→runtime bindings  

All must be present.

---

## **3. Validation Rules (Canonical)**

Each rule begins with a Guided Link.

---

### **Rule 1 — Required Governance Pins Must Exist**  
**Governance Pins** must appear in the Pin Registry.

If missing → **compile failure**.

---

### **Rule 2 — COS Runtime Must Declare Required Pins**  
COS must declare:

- `non_removable: true`  
- `always_loaded: true`  
- `lineage_bound: true`  

If any flag is missing → **compile failure**.

---

### **Rule 3 — GBS Must Reference COS Pins**  
GBS must reference the same pin IDs declared in COS.

If mismatch → **compile failure**.

---

### **Rule 4 — SDL Must Store Pin Metadata**  
SDL must store:

- invariants  
- lineage binding  
- persona/resurrection prohibitions  

If missing → **compile failure**.

---

### **Rule 5 — DNL‑COI Must Enforce Pin Invariants**  
DNL‑COI must list pin invariants in its ethical physics.

If missing → **compile failure**.

---

### **Rule 6 — OMR→Runtime Mapping Must Be Complete**  
Every conceptual pin in OMR must map to a runtime pin.

If unmapped → **compile failure**.

---

### **Rule 7 — No Duplicate Pin IDs**  
Pin IDs must be globally unique.

If duplicates → **compile failure**.

---

### **Rule 8 — No Missing Invariants**  
Every pin must declare at least one invariant.

If empty → **compile failure**.

---

## **4. Validator Output**

If all checks pass:

```
NDH Runtime: Pin Validation Successful
All required pins present, mapped, and enforceable.
```

If any check fails:

```
ERROR: Pin Validation Failed
Reason: <specific rule violation>
NDH v3.0 cannot compile without required pins.
```

---

## **5. Example Validation Report**

```yaml
PinValidatorReport:
  status: "FAILED"
  errors:
    - "COS Runtime missing required ProtocolEmbeddedPin: GBS3-Lineage-COS"
    - "OMR→Runtime mapping incomplete: LP-01 unmapped"
    - "SDL missing persona/resurrection prohibitions for pin: CP-01"
```

---

## **6. Integration Requirements**

- Validator must run **before** COS Runtime initialization  
- Validator must run **before** any PEP (including PEP‑003)  
- Validator must run **before** OMR backfill  
- Validator must run **before** DNL‑COI activation  

This ensures NDH cannot drift.

---

