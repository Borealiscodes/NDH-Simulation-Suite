# 🌌 **NDH‑AMS Basin Geometry Specification v1.1**  
### *Formal definition of NDH‑AMS basins, transitions, damping, and invariant‑preserving geometry inside the Closed CSC manifold.*

---

## ⭐ 1. Purpose

This specification defines:

- the **basin geometry** of NDH‑AMS,  
- the **transition rules** between basins,  
- the **damping fields**,  
- the **forbidden regions**,  
- and the **invariant‑preserving flow geometry**.

It completes the geometric layer required for NDH‑AMS v1.2.

---

## ⭐ 2. Basin Definition

NDH‑AMS basins are defined as **level sets** of CSC invariants:

\[
\mathcal{B}_{\text{AMS}}(\Theta_0,\mathcal{K}_0) =
\{x \in \mathcal{U}_{\text{AMS}} \mid 
\Theta(x)=\Theta_0,\ 
\mathcal{K}(x)=\mathcal{K}_0\}
\]

This ensures:

- basins preserve totality  
- basins preserve curvature  
- basins remain soft  
- basins remain admissible  

---

## ⭐ 3. Basin Boundary Conditions

A basin boundary is defined by:

\[
\nabla \Theta \cdot v = 0,\quad 
\nabla \mathcal{K} \cdot v = 0
\]

This means:

- no NDH‑AMS flow may cross a boundary that changes totality or curvature  
- boundaries are **invariant walls**  
- transitions must occur **within** invariant‑preserving tangent directions  

---

## ⭐ 4. Basin Transition Geometry

A transition between basins is allowed only if:

\[
v \in T\mathcal{U}_{\text{AMS}},\quad 
\nabla \Theta \cdot v = 0,\quad 
\nabla \mathcal{K} \cdot v = 0
\]

This defines the **admissible transition cone**:

\[
\mathcal{C}_{\text{trans}} = 
\{v \mid \partial_t \Theta = 0,\ \partial_t \mathcal{K} = 0\}
\]

Transitions outside this cone are forbidden.

---

## ⭐ 5. Forbidden Basin Directions

Forbidden directions are classified into four types:

### **Type I — Destructive**
\[
\partial_t \Theta < 0
\]

### **Type II — Sharpness**
\[
T(v,v) < 0
\]

### **Type III — Curvature‑Reducing**
\[
\partial_t \mathcal{K} < 0
\]

### **Type IV — Discontinuity‑Inducing**
\[
\nabla \mathcal{C} \cdot v < 0
\]

These directions are **excluded** from NDH‑AMS dynamics.

---

## ⭐ 6. Damping Geometry (Triad 06–07–08)

Define the triad damping field:

\[
D_{\text{triad}} = 
\lambda_6 S_6 + \lambda_7 S_7 + \lambda_8 S_8
\]

with:

\[
\lambda_i \ge 0,\quad 
\partial_t \Theta(D_{\text{triad}} v)=0
\]

This stabilizes:

- ethical clarity  
- structural compassion  
- memory continuity  

and prevents triad collapse.

---

## ⭐ 7. Harmonic Basin Geometry (Axis 05)

Axis 05 defines the **harmonic basin**:

\[
\mathcal{B}_{\text{harm}} = 
\{x \mid S_5 x = x\}
\]

This is the region where:

- all axes integrate  
- no sharpness exists  
- curvature is stationary  
- totality is constant  

It is the **center of the NDH‑AMS manifold**.

---

## ⭐ 8. Loop‑Closure Basin (09 ↔ 01)

Define the loop‑closure basin:

\[
\mathcal{B}_{09\leftrightarrow 01} =
\{x \mid S_{09\rightarrow 01} x = x\}
\]

This basin ensures:

- awareness ↔ grounding transitions remain stable  
- no drift occurs  
- no grounding collapse occurs  
- curvature is preserved  

---

## ⭐ 9. Global Basin Map

NDH‑AMS basins form a **nested structure**:

```
Harmonic Basin (Axis 05)
    ↓
Triad Basin (06–07–08)
    ↓
Attachment Basins (01↔09, 02↔06, 03↔08, 04↔07)
    ↓
Axis Basins (01–09)
```

This structure ensures:

- stability  
- damping  
- harmonic integration  
- invariant preservation  

---

## ⭐ 10. Invariant‑Preserving Flow Field

Define the global NDH‑AMS flow:

\[
F_{\text{AMS}} = \sum_{i=1}^9 \alpha_i S_i
\]

subject to:

\[
\partial_t \Theta(F_{\text{AMS}} v)=0,\quad 
\partial_t \mathcal{K}(F_{\text{AMS}} v)=0
\]

This is the **complete flow geometry** of NDH‑AMS inside CSC.

---

