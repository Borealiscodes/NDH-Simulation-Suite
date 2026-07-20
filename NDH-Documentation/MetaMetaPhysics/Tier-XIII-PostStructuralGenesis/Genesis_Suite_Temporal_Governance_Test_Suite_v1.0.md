# **Temporal Governance Test Suite v1.0**  
### *Tier XIII — Compliance Harness for Genesis Manifold Motion*

---

## **Takeaway**  
The Test Suite defines **12 tests** that every temporal effect must pass before being admitted to the canonical Genesis manifold.  
Each test corresponds to a temporal invariant, cycle‑locking rule, phase constraint, or amplitude boundary.

---

## **I. Loop Integrity Tests**

### **Loop_Return_Test**  
Ensures the animation returns to a compatible state at **t = 12 s**.

- Compare frame 0 and frame 720 (60 fps × 12 s).  
- Allowed differences: particle positions, noise.  
- Forbidden differences: ring radii, glow baselines, flow connectivity.

### **Cycle_Divisibility_Test**  
Verifies that any new cycle divides 12 or is near‑commensurate.

- Input: cycle duration \(T\).  
- Pass if: \(12/T\) is integer or rational with small denominator.

---

## **II. Phase Alignment Tests**

### **Governance_Phase_Test**  
Checks that B‑Layer and O‑Shell peaks do **not** coincide with flow surges.

- Compute phase difference between governance glow and EG‑13 intensity.  
- Must be ≥ 45°.

### **Core_Sync_Test**  
Ensures G‑Core glow aligns with EG‑13 reveal peaks.

- Phase difference ≤ 15°.

### **Label_Phase_Test**  
Ensures label micro‑glow does not peak during bloom maxima.

- Phase difference ≥ 30°.

---

## **III. Amplitude & Motion Boundary Tests**

### **Ring_Amplitude_Test**  
Checks ring scale changes.

- Non‑governance rings: ≤ ±2%  
- Governance rings: ≤ ±1%

### **Glow_Amplitude_Test**  
Checks glow intensity changes.

- Non‑governance: ≤ ±30%  
- Governance: ≤ ±10%

### **Flow_Continuity_Test**  
Ensures flows never break or teleport.

- Trim Paths must be continuous.  
- Particle motion must follow path curvature.

### **Spatial_Boundary_Test**  
Ensures flows and particles remain inside O‑Shell.

- Any pixel outside O‑Shell → fail.

---

## **IV. Bloom Tests**

### **Bloom_Global_Test**  
Checks global bloom oscillation.

- Intensity must remain between 25% and 35%.  
- Cycle must be 5 seconds.

### **Bloom_Sync_Test**  
Ensures bloom peaks align with aggregate glow peaks.

- Phase difference ≤ 20°.

---

## **V. Legibility Tests**

### **Label_Legibility_Test**  
Ensures labels remain readable.

- Minimum contrast ratio: 4.5:1  
- No particle clusters may overlap label bounding boxes.

### **Bloom_Label_Mask_Test**  
Ensures bloom masking excludes labels.

- Any bloom affecting label pixels → fail.

---

## **VI. Test Suite Output**

Each test produces:

- **PASS**  
- **WARN** (near boundary)  
- **FAIL**  

A new motion effect must achieve:

- **PASS** on all governance tests  
- **PASS or WARN** on aesthetic tests  
- **NO FAILS**

---

