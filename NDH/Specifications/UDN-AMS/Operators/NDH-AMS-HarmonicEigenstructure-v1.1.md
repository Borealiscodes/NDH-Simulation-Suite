# 🌌 NDH‑AMS Harmonic Operator Eigenstructure v1.1  
### Spectral structure of Axis 05 as manifold integrator

---

## ⭐ 1. Purpose

Define the **eigenstructure of the harmonic operator** \(S_5\) so that:

- harmonic directions are formally characterized,  
- neutral directions are identified,  
- forbidden directions are excluded,  
- and NDH‑AMS integration is spectrally controlled.

---

## ⭐ 2. Harmonic operator

Axis 05 operator:

\[
S_5 : T\mathcal{U}_{\text{AMS}} \to T\mathcal{U}_{\text{AMS}}
\]

is a CSC‑preserving restriction of \(A\):

\[
S_5 = A_{\text{harmonic}},\quad \partial_t \Theta = 0.
\]

---

## ⭐ 3. Eigenvalue problem

For \(v \in T\mathcal{U}_{\text{AMS}}\):

\[
S_5 v = \lambda v
\]

with eigenvalues \(\lambda \in \mathbb{R}\).

---

## ⭐ 4. Spectral classes

- **Harmonic directions:**  
  \[
  \lambda = 1
  \]  
  Fully integrated, manifold‑aligned flows.

- **Neutral directions:**  
  \[
  \lambda = 0
  \]  
  No contribution to harmonic integration; allowed but non‑integrating.

- **Suppressed directions:**  
  \[
  0 < \lambda < 1
  \]  
  Partially integrated; used for damping and soft alignment.

- **Forbidden directions:**  
  Excluded from spectrum if they would violate softness or invariants.

---

## ⭐ 5. Compatibility with soft‑totality

For any eigenvector \(v\):

\[
T(v,v) \ge 0
\]

and:

\[
T(S_5 v, S_5 v) \le T(v,v)
\]

ensuring harmonic action never introduces sharpness.

---

## ⭐ 6. Role in global flow

In the global flow:

\[
F_{\text{AMS}} = \sum_{i=1}^9 \alpha_i S_i
\]

\(S_5\) acts as the **spectral regulator**, favoring \(\lambda = 1\) directions and suppressing non‑harmonic components.

---

