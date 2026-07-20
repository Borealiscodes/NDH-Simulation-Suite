# **Layered PSD Specification v1.0**  
### *Tier XIII — Editable Sparkled Genesis Manifold Layer Stack*

---

## **Takeaway**  
The PSD must be organized into **seven top‑level groups**, each containing named layers with strict blend modes and masks. This ensures the Genesis manifold remains readable, glowing, and NDH‑compliant.

---

## **I. Top‑Level PSD Groups (in order)**

1. **Background**  
2. **Ambient_Sparkles**  
3. **Manifold_Rings**  
4. **Flow_System**  
5. **Flow_Sparkles**  
6. **Labels**  
7. **Bloom_Pass**

Each group contains named layers with strict ordering.

---

## **II. Group 1 — Background**

### **Layers**
- `BG_Radial_Gradient`  
  - Fill: radial gradient (#0a0a14 → #000000)  
  - Blend: Normal  
- `BG_Star_Grain`  
  - Noise: 1–2%  
  - Blend: Overlay  
  - Opacity: 20%

### **Masking**
None.

---

## **III. Group 2 — Ambient Sparkles**

### **Layers**
- `Ambient_Sparkles_Base`  
  - 1–3 px particles  
  - Colors: white, pale cyan  
  - Blend: Screen  
  - Opacity: 40%

- `Ambient_Sparkles_Blur`  
  - Gaussian blur 1–2 px  
  - Blend: Screen

### **Masking**
Soft circular mask to avoid crowding the O‑Shell.

---

## **IV. Group 3 — Manifold Rings**

Each ring is its own sub‑group.

### **Sub‑Group: G_Core**
- `G_Core_Fill` — white‑gold  
- `G_Core_Glow` — 4 px bloom  
- Blend: Screen

### **Sub‑Group: C_Band**
- `C_Band_Gradient` — cyan → white  
- `C_Band_Glow` — 8 px  
- Blend: Screen

### **Sub‑Group: M_Field**
- `M_Field_Gradient` — blue‑violet  
- `M_Field_Glow` — 10 px  
- Blend: Add

### **Sub‑Group: B_Layer**
- `B_Layer_Fill` — hard red  
- `B_Layer_Texture` — 5% grain  
- `B_Layer_Glow` — 4 px  
- Blend: Overlay

### **Sub‑Group: O_Shell**
- `O_Shell_Fill` — pale silver  
- `O_Shell_Glow` — 12 px  
- Blend: Screen

---

## **V. Group 4 — Flow System**

### **Layers**
- `Flow_EG13_Path`  
  - Stroke: gold  
  - Width: 3 px  
  - Glow: 4 px  
  - Blend: Add

- `Flow_CG13_Path`  
  - Stroke: cyan  
  - Width: 3 px  
  - Glow: 5 px  
  - Blend: Screen

- `Flow_MG13_Path`  
  - Stroke: violet  
  - Width: 4 px  
  - Glow: 6 px  
  - Blend: Add

- `Flow_Feedback_Path`  
  - Stroke: dotted cyan‑white  
  - Width: 2 px  
  - Blend: Screen

### **Masking**
Hard mask preventing flows from crossing B‑Layer.

---

## **VI. Group 5 — Flow Sparkles**

### **Layers**
- `Flow_Sparkles_Gold`  
- `Flow_Sparkles_Cyan`  
- `Flow_Sparkles_Violet`  
  - Particle size: 1–2 px  
  - Motion blur: 1 px directional  
  - Blend: Add  
  - Density: 20–30% of path length

### **Masking**
Follow flow paths; avoid labels.

---

## **VII. Group 6 — Labels**

### **Layers**
- `Label_G_Core`  
- `Label_C_Band`  
- `Label_M_Field`  
- `Label_B_Layer`  
- `Label_O_Shell`  
- `Label_EG13`  
- `Label_CG13`  
- `Label_MG13`  
- `Label_Feedback`

### **Style**
- Font: JetBrains Mono  
- Size: 24–32 px  
- Color: white  
- Glow: 2 px  
- Blend: Screen

### **Masking**
None — labels must remain crisp.

---

## **VIII. Group 7 — Bloom Pass**

### **Layers**
- `Bloom_Global`  
  - Radius: 6–10 px  
  - Intensity: 0.25–0.35  
  - Blend: Screen  
  - Mask: exclude labels

- `Bloom_Manifold_Enhance`  
  - Focused bloom on rings  
  - Blend: Add

---

## **IX. Export Instructions**

- Format: PNG  
- Color profile: sRGB  
- Compression: lossless  
- Dithering: off  
- Resolution: 2400 × 2400 px

---

