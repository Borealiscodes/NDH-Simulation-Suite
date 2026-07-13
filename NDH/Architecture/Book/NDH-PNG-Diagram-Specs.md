# 📐 **NDH Architecture Book — PNG Diagram Specifications**  
### *GitHub‑Safe • ND‑Stable • Architecture‑Grade*

---

## 🌌 0. Global PNG Standards (Apply to All Diagrams)

### **Canvas**
- Size: **2400 × 2400 px**  
- Format: **PNG (non‑interlaced)**  
- Background: **#FFFFFF** (pure white)  
- Padding: **160 px** on all sides  

### **Typography**
- Header font: **Inter Bold 96px**  
- Section font: **Inter SemiBold 64px**  
- Body font: **Inter Regular 48px**  
- Line spacing: **1.25×**  
- No italics, no underlines.

### **Color Palette (NDH‑Safe)**
- Black: **#000000**  
- Gray‑1: **#4A4A4A**  
- Gray‑2: **#7A7A7A**  
- Blue‑NDH: **#2F5FFF**  
- Gold‑NDH: **#C8A24B**  
- Red‑NDH (incident markers only): **#D64545**

### **Shape Rules**
- All boxes: **8px corner radius**  
- All connectors: **4px lines**  
- No drop shadows  
- No gradients  
- No transparency  

### **Export Rules**
- Filename format:  
  ```
  ndh-[diagram-name]-v1.0.png
  ```
- Store in:  
  ```
  /NDH/Architecture/Book/assets/
  ```

---

# 🧱 1. Governance Layer Diagram Spec

### **Filename**
```
ndh-governance-layer-diagram-v1.0.png
```

### **Structure**
Top‑down vertical stack:

1. **Header:** “Governance Layer”
2. **Block 1:** Stability Envelope v3.0  
3. **Block 2:** MLTL‑v1.0  
4. **Block 3:** SE‑MLTL Fusion Block  
5. **Block 4:** Incident Ledger  
6. **Block 5:** Governance Overview

### **Connectors**
- Straight vertical spine  
- Blue‑NDH connectors between SE ↔ MLTL ↔ Fusion  
- Red‑NDH connector from Incident Ledger → SE

### **Special Rule**
Incident Ledger block must include a **red border** (4px).

---

# 🧠 2. Logic Layer Diagram Spec

### **Filename**
```
ndh-logic-layer-diagram-v1.0.png
```

### **Structure**
Four‑quadrant layout:

- **Top‑Left:** Epistemic Logic  
- **Top‑Right:** Mythic Logic  
- **Bottom‑Left:** Aesthetic Logic  
- **Bottom‑Right:** Symbolic Logic  

### **Connectors**
- Mythic → Aesthetic (blue arrow)  
- Mythic → Symbolic (blue arrow)  
- Symbolic ↔ Epistemic (bidirectional gray arrow)  
- Mythic → Epistemic (thin gold arrow, labeled “bifurcation only”)

### **Special Rule**
Mythic Logic quadrant uses **Gold‑NDH** header text.

---

# 🌀 3. Manifold Layer Diagram Spec

### **Filename**
```
ndh-manifold-layer-diagram-v1.0.png
```

### **Structure**
Central geometric diagram:

- Root Axis (vertical)  
- Trunk Axis (vertical continuation)  
- Branch Axes (angled 30° left/right)  
- Runtime Surfaces (horizontal plates)  

### **Tensor Overlays**
Place five tensor icons around the geometry:

- Stability Spine Tensor  
- Meaning‑Metric Tensor  
- Lens‑Stress Tensor  
- Projection Tensor  
- Mythic‑Intensity Tensor  

### **Special Rule**
Runtime surfaces must be **gold‑outlined**.

---

# 🔧 4. Core Engine Diagram Spec

### **Filename**
```
ndh-core-engine-diagram-v1.0.png
```

### **Structure**
Three‑layer horizontal diagram:

1. **Left:** Conceptual Engine  
2. **Center:** Interaction Layer  
3. **Right:** Operational Engine  

### **Connectors**
- Conceptual → Interaction (blue arrow)  
- Interaction → Operational (blue arrow)  
- Operational → Conceptual (thin gray return arrow)

### **Special Rule**
Interaction Layer block uses **blue background (#2F5FFF)** with **white text**.

---

# 🌱 5. NDH Root Chapter Diagram Spec

### **Filename**
```
ndh-root-chapter-diagram-v1.0.png
```

### **Structure**
Four‑pillar layout:

- Purpose  
- Lineage  
- Principles  
- Philosophy  

### **Connectors**
None — this diagram is static.

### **Special Rule**
Each pillar header uses **Gold‑NDH**.

---

# 🧭 6. NDH Coherence Diagram Spec

### **Filename**
```
ndh-coherence-diagram-v1.0.png
```

### **Structure**
Closed loop diagram:

Governance → Logic → Manifold → Core Engine → Governance

### **Connectors**
- Thick blue arrows forming a loop  
- Gold arrow overlay showing lineage flow  
- Gray inner loop showing coherence protocols

### **Special Rule**
Loop must be **perfect circle** (no ellipse).

---

