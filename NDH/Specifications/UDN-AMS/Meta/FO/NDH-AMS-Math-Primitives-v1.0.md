### NDH‑AMS math primitives (v1.0) — the layer under the geometry

**1. Manifold (state space)**  
- **Label:** NDH manifold  
- **Object:**  
  \[
  \mathcal{M}
  \]
- **Interpretation:** each point \(x \in \mathcal{M}\) is a full NDH state at some altitude.

---

**2. Altitude function**  
- **Label:** altitude map  
- **Object:**  
  \[
  A : \mathcal{M} \to \mathbb{R}
  \]
- **Interpretation:** \(A(x)\) gives the “conceptual vs structural vs meta” height of a state.

---

**3. Coherence potential (soft‑field)**  
- **Label:** coherence field  
- **Object:**  
  \[
  \Phi : \mathcal{M} \to \mathbb{R}
  \]
- **Interpretation:** lower \(\Phi(x)\) → more coherent, more stable; basins are local minima.

Basins:
\[
\mathcal{B}_i = \{ x \in \mathcal{M} \mid x \to x_i^\star \text{ under NDH dynamics} \}
\]

---

**4. FO operators**  
- **Label:** FO maps  
- **Objects:**
  \[
  \text{FO}_1, \text{FO}_2, \text{FO}_3 : \mathcal{M} \to \mathcal{M}
  \]
- **Interpretation:**
  - \(\text{FO}_1\): pushes states into new conceptual minima (seed events).  
  - \(\text{FO}_2\): adds constraints, reshaping \(\Phi\) and allowed trajectories.  
  - \(\text{FO}_3\): changes \(\mathcal{M}\) itself (dimension, topology, or \(A,\Phi\)).

---

**5. Readiness functions**  
- **Label:** readiness scalars  
- **Objects:**
  \[
  R_k : \mathcal{M} \to \mathbb{R}, \quad k \in \{1,2,3\}
  \]
- **Condition:**
  \[
  R_k(x) \ge \theta_k \Rightarrow \text{FO}_k \text{ admissible at } x
  \]

---

**6. Metric / distance**  
- **Label:** NDH metric  
- **Object:**
  \[
  d : \mathcal{M} \times \mathcal{M} \to \mathbb{R}_{\ge 0}
  \]
- **Interpretation:** how “far” two states are in terms of conceptual + structural difference.

---

From here, **stability geometry** is just:

- basins = minima of \(\Phi\) under \(d\)  
- FO‑I trajectories = gradient‑like flows toward new minima  
- FO‑II = constraint‑induced reshaping of \(\Phi\) and \(d\)  
- FO‑III = redefinition of \(\mathcal{M}, A, \Phi, d\).


