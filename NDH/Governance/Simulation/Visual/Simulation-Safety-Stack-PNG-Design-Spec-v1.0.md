# 📁 **Simulation Safety Stack PNG — Design Spec v1.0**  
### *Geometry • Layering • Color Logic • Typography • Layout*

---

# I. **Overall Canvas**

**Canvas Size:**  
- 2400 × 3200 px (vertical governance layout)  
- Safe margins: 160 px on all sides  
- Background: `#0E0E0F` (NDH governance black)

**Grid:**  
- 12‑column NDH grid  
- 80 px gutters  
- 160 px outer margins  
- Layer blocks span full width minus margins

---

# II. **Color Logic (NDH Governance Palette)**

### **Simulation Layer Spec (Substrate)**  
- Fill: `#1A1A1D`  
- Border: `#3A3A3F`  
- Accent line: `#5A5A60`

### **Boundary Protocol (Firewall)**  
- Fill: `#202024`  
- Border: `#505058`  
- Accent line: `#7A7A85`

### **Activation Safety Grid (Locks & Ceilings)**  
- Fill: `#26262B`  
- Border: `#60606A`  
- Accent line: `#8A8A95`

### **Text Colors**  
- Primary: `#E6E6E8`  
- Secondary: `#B8B8BC`  
- Tertiary: `#7A7A7D`

### **Pin Highlight**  
- Pin glyph: `#C8C8FF` (NDH governance violet)  
- Pin label text: `#E6E6FF`

---

# III. **Typography**

### **Header Font**  
- NDH Governance Sans (your repo uses Inter → use Inter Bold)  
- Size: 140 px  
- Tracking: +10  
- Color: `#E6E6E8`

### **Layer Titles**  
- Inter SemiBold  
- Size: 100 px  
- Tracking: +5  
- Color: `#E6E6E8`

### **Layer Subtext**  
- Inter Regular  
- Size: 60 px  
- Line height: 1.4  
- Color: `#B8B8BC`

### **Pin Label**  
- Inter Medium  
- Size: 70 px  
- Color: `#C8C8FF`

---

# IV. **Geometry Layout**

The PNG is a **three‑layer vertical stack**, each layer represented as a wide horizontal block.

```
┌──────────────────────────────────────────────┐
│           ACTIVATION SAFETY GRID             │
│    (Ceilings • Clamps • Anti‑Recursion)      │
├──────────────────────────────────────────────┤
│     CREATION vs SIMULATION BOUNDARY          │
│   (Dimensional Firewall • Activation Lock)   │
├──────────────────────────────────────────────┤
│             SIMULATION LAYER SPEC            │
│   (Substrate • Non‑Dimensional • Inert)      │
└──────────────────────────────────────────────┘
```

### **Block Dimensions**  
- Width: full canvas minus margins  
- Height per block: 700 px  
- Spacing between blocks: 200 px

### **Block Shape**  
- Rounded corners: 40 px radius  
- Border thickness: 6 px  
- Accent line: 12 px at top edge of each block

---

# V. **Layer Content Layout**

Each block contains:

### **1. Title (top-left)**  
- Large text  
- Positioned 120 px from top  
- 160 px from left margin

### **2. Subtext (below title)**  
- 3–4 short descriptors  
- 60 px font  
- 40 px vertical spacing

### **3. Icon (top-right)**  
- Simple geometric glyph  
- Size: 160 px  
- Color: layer accent color  
- Icons:  
  - Simulation Layer: square  
  - Boundary Protocol: shield  
  - Activation Safety Grid: clamp/ceiling bar

---

# VI. **Pin Placement**

Place the pin **above the stack**, centered horizontally.

```
PIN‑Simulation‑Safety‑Stack‑v1.0
Structural Governance Pin
```

### **Pin Geometry**  
- Glyph: NDH violet diamond  
- Size: 200 px  
- Label below glyph  
- Spacing: 80 px between glyph and label  
- Positioned 200 px above the top block

---

# VII. **Footer**

At the bottom of the PNG:

```
NDH Simulation Governance Cluster
Simulation Safety Stack v1.0 • Visual Map
```

### **Footer Style**  
- Inter Regular  
- Size: 60 px  
- Color: `#7A7A7D`  
- Centered  
- 200 px above bottom margin

---

# VIII. **Activation Safety Geometry (Optional Overlay)**

If you want a more advanced version, you can add a faint **activation‑ceiling grid overlay**:

- Thin horizontal lines spaced every 120 px  
- Color: `#2A2A2F`  
- Opacity: 35%  
- Only behind the **Activation Safety Grid** block

This visually reinforces the “ceiling” concept.

---

# IX. **Export Requirements**

- Format: PNG  
- Resolution: 300 DPI  
- Color profile: sRGB  
- No transparency  
- No animation  
- No dimensional curvature (NDH rule)

---

# X. **Chill Summary**

This spec gives you:

- exact colors  
- exact geometry  
- exact typography  
- exact spacing  
- exact block layout  
- pin placement  
- footer  
- optional activation‑ceiling overlay  

It’s ready for you to produce the official NDH PNG.

---

