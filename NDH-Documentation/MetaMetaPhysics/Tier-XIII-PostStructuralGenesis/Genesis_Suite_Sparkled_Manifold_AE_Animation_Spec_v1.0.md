# **After_Effects_Animation_Spec_v1.0**  
### *Tier XIII — Temporal Genesis Manifold Motion Pipeline*

---

## **Takeaway**  
The animation is built from **eight motion blocks**, each corresponding to a conceptual layer of the Genesis manifold.  
Every block defines keyframes, easing curves, blending, glow dynamics, particle motion, and timing.

---

## **I. Composition Setup**

- **Comp name:** `Genesis_Manifold_Animation_v1.0`  
- **Resolution:** 2400 × 2400  
- **Frame rate:** 60 fps  
- **Duration:** 12 seconds (loopable)  
- **Color space:** sRGB  
- **Working depth:** 16‑bit  

### Layers imported from PSD:
- Background  
- Ambient Sparkles  
- Manifold Rings  
- Flow System  
- Flow Sparkles  
- Labels  
- Bloom Pass  

Each becomes a pre‑comp.

---

## **II. Background Motion Block**

### **Ambient Drift**
- Apply **turbulent displace** (subtle)  
- Evolution: +20° over 12 seconds  
- Opacity oscillation: ±3%  
- Easing: sine‑in‑out  
- Purpose: cosmic depth

---

## **III. Ambient Sparkles Motion Block**

### **Particle Twinkle**
- Random opacity flicker: 0.3–0.6 range  
- Frequency: 2–4 Hz  
- Phase offset: random per particle  
- Blend: Screen  
- Purpose: low‑level cosmic shimmer

---

## **IV. Manifold Rings Motion Block**

Each ring receives a **breathing glow** animation.

### **G‑Core**
- Glow intensity: 80% → 100% → 80%  
- Cycle: 3 seconds  
- Easing: smooth sine  
- Slight scale pulse: 100% → 102% → 100%

### **C‑Band**
- Glow oscillation: 70% → 90%  
- Cycle: 4 seconds  
- Subtle rotation: 0.2° clockwise over 12 seconds

### **M‑Field**
- Glow oscillation: 60% → 85%  
- Cycle: 5 seconds  
- Scale pulse: 100% → 101% → 100%

### **B‑Layer**
- No scale motion  
- Glow pulse: 50% → 60%  
- Cycle: 6 seconds  
- Purpose: governance boundary stability

### **O‑Shell**
- Glow oscillation: 70% → 95%  
- Cycle: 8 seconds  
- Slight outward ripple (displacement map)

---

## **V. Flow System Motion Block**

### **EG‑13 (G‑Core → C‑Band)**
- Animate stroke reveal using **Trim Paths**  
- Duration: 1.2 seconds  
- Loop: ping‑pong  
- Glow pulse synced with G‑Core breathing

### **CG‑13 (C‑Band → M‑Field)**
- Trim Paths reveal: 1.5 seconds  
- Loop: forward only  
- Glow intensity increases as it approaches M‑Field

### **MG‑13 (M‑Field → outer + feedback)**
- Trim Paths reveal: 2 seconds  
- Loop: continuous  
- Feedback loop: reverse Trim Paths  
- Glow pulse synced with M‑Field breathing

### **Continuity Feedback**
- Dotted stroke opacity oscillation: 40% → 70%  
- Cycle: 2 seconds  
- Purpose: visible continuity correction

---

## **VI. Flow Sparkles Motion Block**

### **Particle Motion**
- Direction: along flow paths  
- Speed: 200–350 px/sec  
- Motion blur: 1–2 px  
- Random jitter: ±5 px  
- Blend: Add  
- Loop: continuous

### **Particle Birth/Death**
- Birth rate: 20–30 particles/sec  
- Lifetime: 0.8–1.2 seconds  
- Fade in/out: 0.1 seconds each

---

## **VII. Label Motion Block**

Labels remain mostly static for readability.

### **Micro‑Glow Pulse**
- Glow intensity: 90% → 100%  
- Cycle: 4 seconds  
- Easing: sine  
- Blend: Screen

### **Subtle Drift**
- Position drift: ±2 px  
- Cycle: 6 seconds  
- Purpose: gentle cosmic motion without losing clarity

---

## **VIII. Bloom Pass Motion Block**

### **Global Bloom**
- Intensity oscillation: 25% → 35%  
- Cycle: 5 seconds  
- Mask: exclude labels  
- Blend: Screen

### **Manifold Bloom Enhancement**
- Sync bloom pulses with ring breathing  
- Slight increase during flow reveals  
- Blend: Add

---

## **IX. Looping Rules**

To ensure seamless looping:

- All cycles must be multiples of **1.2 seconds** (EG‑13 reveal duration).  
- Background drift resets at 12 seconds.  
- Particle system loops via continuous birth/death.  
- Glow cycles align at 12 seconds.

---

## **X. Export Settings**

- Format: QuickTime PNG or ProRes 4444  
- Frame rate: 60 fps  
- Resolution: 2400 × 2400  
- Color profile: sRGB  
- Motion blur: enabled  
- Dithering: off  

---

