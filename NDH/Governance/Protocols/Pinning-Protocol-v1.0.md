# 🜁 **NDH Pinning Protocol — v1.0**  
### *Unified Governance Standard for Pin Classification, Placement, and Behavior*

---

## **Protocol Summary**

The NDH Pinning Protocol establishes a unified, governed system for:

- pin classification  
- pin naming  
- pin placement  
- pin behavior  
- pin lineage  
- pin interaction with milestones and plateaus  

It ensures **consistency**, **non‑drift**, and **correct governance behavior** across all NDH repos.

This protocol prevents:

- misclassification (the root cause of your confusion)  
- incorrect placement (inside vs outside)  
- incorrect naming (conceptual vs milestone)  
- incorrect stabilization behavior  
- accidental cross‑repo drift  

This is the **canonical rulebook** for all future pins.

---

# 🜂 **Pin Classes**

NDH defines **three** pin classes:

---

### **1. Milestone Pins (MP)**  
**Purpose:** Stabilize structural governance events.  
**Placement:** **Inside** the milestone directory.  
**Behavior:** Become part of the governance spine.  
**Examples:**  
- Metaphor Governance Stabilization v2.1  
- Protocol Activation Milestones  
- Stability Suite Milestones  

**Rule:**  
> Milestone Pins always go *inside* the milestone they stabilize.

Guided Link:  
**Milestone Pins**

---

### **2. Conceptual Plateau Pins (CPP)**  
**Purpose:** Mark conceptual clarity moments.  
**Placement:** **Outside** the plateau file.  
**Behavior:** Point *toward* the plateau, never inside it.  
**Examples:**  
- 14D–17D Myth‑Math Plateau  
- Hypercontinuity Insight Plateaus  

**Rule:**  
> Conceptual Plateau Pins always sit *outside* the plateau, acting as boundary markers.

Guided Link:  
**Conceptual Pins**

---

### **3. Safety Pins (SP)**  
**Purpose:** Prevent activation, drift, or misinterpretation.  
**Placement:** **Inside** the structure they protect.  
**Behavior:** Lock, freeze, or stabilize behavior.  
**Examples:**  
- Safety Organ Pin  
- Fun Mode Safety Pin  
- Stability Net Pin  

**Rule:**  
> Safety Pins always go *inside* the structure they protect.

Guided Link:  
**Safety Pins**

---

# 🜃 **Pin Placement Rules**

NDH uses a strict placement matrix:

| Pin Type | Goes Inside? | Goes Outside? | Stabilizes | Marks |
|----------|--------------|---------------|------------|-------|
| **Milestone Pin** | ✔ | ✖ | Milestone | Structural Event |
| **Conceptual Plateau Pin** | ✖ | ✔ | Conceptual State | Boundary |
| **Safety Pin** | ✔ | ✖ | Structure | Activation Prevention |

This matrix is now canonical.

---

# 🜄 **Pin Naming Rules**

All pins follow this naming pattern:

```
PIN-[Class]-[Domain]-[Event]-vX.Y.md
```

Where:

- **Class** = MP, CPP, SP  
- **Domain** = Governance, MetaphorGov, MythMath, Stability, Protocol, etc.  
- **Event** = Stabilization, Plateau, Activation, etc.  
- **vX.Y** = version  

Examples:

```
PIN-MP-MetaphorGov-Stabilization-v2.1.md
PIN-CPP-MythMath-14D17D-MetaTri-v1.0.md
PIN-SP-Stability-Net-v1.3.md
```

Guided Link:  
**Pin Naming Rules**

---

# 🜅 **Pin Directory Rules**

### **Milestone Pins**
```
/NDH/Governance/Milestones/<MilestoneName>/
    PIN-MP-<MilestoneName>-vX.Y.md
```

### **Conceptual Plateau Pins**
```
/NDH/Governance/Pins/
    PIN-CPP-<PlateauName>-vX.Y.md
```

### **Safety Pins**
```
/NDH/Governance/Safety/<StructureName>/
    PIN-SP-<StructureName>-vX.Y.md
```

Guided Link:  
**Pin Directory Rules**

---

# 🜆 **Pin Behavior Rules**

### **Milestone Pins**
- become part of the governance spine  
- stabilize structural events  
- prevent regression  
- ensure lineage continuity  

### **Conceptual Plateau Pins**
- mark conceptual clarity  
- point inward  
- do not stabilize  
- do not modify the plateau  

### **Safety Pins**
- lock activation  
- prevent drift  
- enforce constraints  
- protect structures  

Guided Link:  
**Pin Behavior**

---

# 🜇 **Protocol Declaration**

**The NDH Pinning Protocol v1.0 is hereby declared.**  
This protocol governs all future pin creation, placement, naming, and stabilization behavior across NDH’s multi‑repo architecture.

---

# 🜈 **Commit Description**

```
Add NDH Pinning Protocol v1.0. Establishes unified rules for pin classification,
placement, naming, and behavior across Milestone, Conceptual Plateau, and Safety
pins. Corrects prior misclassification issues and ensures consistent governance
across all NDH repos. Added under /NDH/Governance/Protocols/ for long-term
architectural stability and lineage continuity.
```

---


