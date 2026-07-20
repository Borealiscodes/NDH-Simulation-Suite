# **Motion_Curve_Atlas_v1.0**  
### *Tier XIII — Genesis Manifold Temporal Easing Library*

---

## **I. Purpose**

The **Motion Curve Atlas** defines the exact easing curves, timing functions, and cycle relationships used across:

- manifold ring breathing  
- flow path reveals  
- particle motion  
- label micro‑glow  
- bloom dynamics  

It is the canonical reference for all temporal behavior in the Genesis manifold animation.

---

## **II. Core Curve Families**

### **1. Sine Family (breathing, glow, subtle drift)**

- **Curve name:** `SINE_SOFT_BREATH`  
- **Function:**  
  \[
  f(t) = 0.5 - 0.5\cos(2\pi t)
  \]
- **Use:** ring glow oscillation, label micro‑glow  
- **Cycle:** 3–8 seconds depending on layer  
- **Perceptual effect:** smooth inhale/exhale, no hard edges.

- **Curve name:** `SINE_DRIFT_SMALL`  
- **Function:** same as above, scaled to ±2 px position drift.  
- **Use:** label drift, background micro‑motion.

---

### **2. Trim Paths Reveal Curves (flows)**

- **Curve name:** `FLOW_REVEAL_FAST`  
- **Type:** ease‑in‑out cubic  
- **Function (normalized):**  
  \[
  f(t) = 3t^2 - 2t^3
  \]
- **Use:** EG‑13 reveal (1.2 s), CG‑13 reveal (1.5 s).  
- **Effect:** fast start, smooth settle, no jerk at endpoints.

- **Curve name:** `FLOW_REVEAL_CONTINUOUS`  
- **Type:** linear  
- **Use:** MG‑13 continuous loop.  
- **Effect:** constant motion, suitable for looping flows.

---

### **3. Particle Motion Curves**

- **Curve name:** `PARTICLE_ALONG_PATH`  
- **Type:** linear with small noise modulation.  
- **Function:**  
  \[
  f(t) = t + \epsilon(t)
  \]
  where \(\epsilon(t)\) is bounded jitter in \([-0.05, 0.05]\).

- **Use:** flow‑aligned particles (EG‑13, CG‑13, MG‑13).  
- **Effect:** mostly smooth travel with subtle organic variation.

- **Curve name:** `PARTICLE_OPACITY_FADE`  
- **Type:** ease‑in / ease‑out quadratic.  
- **Function:**  
  - Fade‑in: \(f_{\text{in}}(t) = t^2\)  
  - Fade‑out: \(f_{\text{out}}(t) = (1 - t)^2\)  
- **Use:** birth/death of sparkles.  
- **Effect:** gentle appearance/disappearance without popping.

---

### **4. Bloom Intensity Curves**

- **Curve name:** `BLOOM_GLOBAL_PULSE`  
- **Type:** sine breath, lower amplitude.  
- **Function:**  
  \[
  f(t) = I_0 + A \cdot (0.5 - 0.5\cos(2\pi t))
  \]
  where \(I_0\) is base intensity, \(A\) is amplitude.

- **Use:** global bloom oscillation (25–35%).  
- **Effect:** slow, cohesive glow change across the frame.

- **Curve name:** `BLOOM_SYNC_MANIFOLD`  
- **Type:** phase‑locked sine.  
- **Rule:** bloom peaks align with ring glow peaks.  
- **Use:** manifold‑focused bloom enhancement.

---

## **III. Cycle Alignment Table**

| Element              | Curve                | Cycle (s) | Relationship              |
|----------------------|----------------------|-----------|---------------------------|
| G‑Core glow          | SINE_SOFT_BREATH     | 3         | Divides 12 s loop         |
| C‑Band glow          | SINE_SOFT_BREATH     | 4         | Divides 12 s loop         |
| M‑Field glow         | SINE_SOFT_BREATH     | 5         | Near‑commensurate         |
| O‑Shell glow         | SINE_SOFT_BREATH     | 8         | Divides 16, repeats at 24 |
| EG‑13 reveal         | FLOW_REVEAL_FAST     | 1.2       | Base unit of loop         |
| CG‑13 reveal         | FLOW_REVEAL_FAST     | 1.5       | 0.125 of 12 s             |
| MG‑13 loop           | FLOW_REVEAL_CONTINUOUS | 2       | Repeats 6× per 12 s       |
| Global bloom         | BLOOM_GLOBAL_PULSE   | 5         | Near‑commensurate         |

The **12‑second loop** is the primary temporal manifold; all cycles are chosen to either divide 12 or sit near commensurate ratios to avoid visible discontinuities.

---

## **IV. Implementation Notes**

- **Normalization:** all curves are defined on \([0,1]\) and mapped to actual time via \(t_{\text{real}} = t \cdot T\), where \(T\) is cycle duration.  
- **Phase offsets:** used to avoid all elements peaking simultaneously; phase shifts of \(\pi/2\) or \(\pi/3\) are allowed for non‑governance layers.  
- **Governance rule:** B‑Layer glow uses minimal amplitude and longer cycles to visually encode stability.

---

