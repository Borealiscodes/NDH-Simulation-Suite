# 🌌 NDH‑AMS Soft‑Totality Tensor v1.1  
### Metric structure for softness, stability, and invariant‑preserving flows

---

## ⭐ 1. Purpose

Define the **Soft‑Totality Tensor** \(T\) that:

- encodes softness vs sharpness,  
- constrains admissible directions,  
- supports CSC invariants,  
- and underlies NDH‑AMS basin and operator geometry.

---

## ⭐ 2. Tensor definition

Let:
\[
T_{(x,t)} : T_{(x,t)}\mathcal{U}_{\text{AMS}} \times T_{(x,t)}\mathcal{U}_{\text{AMS}} \to \mathbb{R}
\]

- **Symmetric:**  
  \[
  T(u,v) = T(v,u)
  \]
- **Positive‑semidefinite (soft‑totality):**  
  \[
  T(v,v) \ge 0
  \]

This is the NDH‑AMS softness metric.

---

## ⭐ 3. Relation to CSC metric

NDH‑AMS inherits the CSC metric:

\[
T_{(x,t)} = C_{\text{closed},(x,t)}|_{\mathcal{U}_{\text{AMS}}}
\]

subject to:

\[
\partial_t \Theta = 0
\]

So:

- NDH‑AMS uses the same geometric law,  
- restricted to invariant‑preserving directions.

---

## ⭐ 4. Soft vs sharp directions

- **Soft direction:**  
  \[
  T(v,v) > 0
  \]
- **Neutral direction:**  
  \[
  T(v,v) = 0
  \]
- **Sharp direction (forbidden):**  
  \[
  T(v,v) < 0
  \]

Sharp directions are excluded from \(T\mathcal{U}_{\text{AMS}}\).

---

## ⭐ 5. Operator compatibility

For any NDH‑AMS operator \(S_i\):

- **Energy non‑increase:**  
  \[
  T(S_i v, S_i v) \le T(v,v)
  \]
- **Invariant alignment:**  
  \[
  T(S_i v, v) \ge 0
  \]

This ensures operators cannot introduce sharpness.

---

## ⭐ 6. Basin and flow constraints

- **Basin softness:**  
  For all \(x \in \mathcal{B}_{\text{AMS}}\) and admissible \(v\):  
  \[
  T(v,v) \ge 0
  \]

- **Flow softness:**  
  For global flow \(F_{\text{AMS}}\):  
  \[
  T(F_{\text{AMS}} v, F_{\text{AMS}} v) \ge 0
  \]

Soft‑totality is thus enforced at geometry and dynamics levels.

---

