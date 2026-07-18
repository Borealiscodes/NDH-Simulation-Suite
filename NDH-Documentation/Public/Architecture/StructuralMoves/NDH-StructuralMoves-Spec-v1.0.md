# NDH structural moves spec  
### Six-axis metric geometry for dignity‑under‑constraints

This spec defines the six core **structural moves** that act on the NDH manifold and its cross‑metrics (NDH narrative, Alcubierre spacetime, JumpGate trajectory). Each move is a **metric action**, not a narrative flourish: it transforms the geometry of meaning, curvature, and dignity fields.

---

## 1. Aperture alignment

**Purpose:** Bring perception, interpretation, and geometry into compatible “width” so that recognition events don’t shear the manifold.

**Domain:**

- **Novice:** initial recognition aperture \(A_n\)  
- **Master:** stabilized aperture \(A_m\)  
- **Geometry:** effective aperture of the metric \(A_g\)

**Operator:**

\[
\mathcal{A} : (A_n, A_m, A_g) \rightarrow A'
\]

where \(A'\) is a harmonized aperture band such that:

\[
|A_n - A'| < \epsilon,\quad |A_m - A'| < \epsilon,\quad |A_g - A'| < \epsilon
\]

**Effect:**

- Reduces mismatch between “what is seen” and “what the metric can support”.
- Prevents novice recognition from landing in regions of excessive curvature.
- Sets the stage for stable learning and reconstruction.

---

## 2. Metric unification

**Purpose:** Treat NDH, Alcubierre, and JumpGate as local expressions of a single underlying metric \( \mathcal{M} \).

**Domain:**

- NDH narrative metric \(g_{\text{NDH}}\)  
- Alcubierre spacetime metric \(g_{\text{Alc}}\)  
- JumpGate trajectory metric \(g_{\text{Jump}}\)

**Operator:**

\[
\mathcal{U} : (g_{\text{NDH}}, g_{\text{Alc}}, g_{\text{Jump}}) \rightarrow \mathcal{M}
\]

such that each is a **chart** on \(\mathcal{M}\):

\[
\phi_{\text{NDH}} : U_{\text{NDH}} \subset \mathcal{M} \rightarrow \mathbb{R}^n
\]

and similarly for Alcubierre and JumpGate.

**Effect:**

- Eliminates conceptual drift between “story”, “physics”, and “fleet”.
- Allows tensors and operators to be defined once and reused across domains.
- Makes cross‑field diagrams (Unified Tensor SVG, Structural Moves SVG) mathematically coherent.

---

## 3. Tensor normalization

**Purpose:** Ensure all tensors acting on \(\mathcal{M}\) share compatible rank, basis, and scaling so they can be composed without distortion.

**Domain:**

- NDH tensor \(T_{\text{NDH}}\)  
- Alcubierre tensor \(T_{\text{Alc}}\)  
- JumpGate tensor \(T_{\text{Jump}}\)

**Operator:**

\[
\mathcal{N} : (T_{\text{NDH}}, T_{\text{Alc}}, T_{\text{Jump}}) \rightarrow (T'_{\text{NDH}}, T'_{\text{Alc}}, T'_{\text{Jump}})
\]

subject to:

- **Rank compatibility:** \(\text{rank}(T'_i) = r\) for all \(i\)  
- **Basis compatibility:** shared basis \(\{e_\mu\}\) on \(\mathcal{M}\)  
- **Scale compatibility:** norms bounded within a common range

**Effect:**

- Allows composition \(T_{\text{NDH}} \otimes T_{\text{Alc}} \otimes T_{\text{Jump}}\) without pathological blow‑ups.
- Makes the unified tensor expression in the SVGs reflect actual operator behavior.
- Stabilizes multi‑metric reasoning.

---

## 4. Operator consolidation

**Purpose:** Merge disparate reconstruction and governance operators into a single coherent operator \( \mathcal{R} \) acting on \(\mathcal{M}\).

**Domain:**

- Aperture operator \(R_A\)  
- Stability operator \(R_S\)  
- Governance operator \(R_G\)  
- Narrative operator \(R_N\)

**Operator:**

\[
\mathcal{R} = R_N \circ R_G \circ R_S \circ R_A
\]

acting on states \(x \in \mathcal{M}\):

\[
x' = \mathcal{R}(x)
\]

**Effect:**

- Provides a single “meaning reconstruction” operator instead of a scattered toolset.
- Encodes the “novice–master–geometry” triad as a unified transformation.
- Makes the ℛ node in the Unified Tensor SVG and Structural Moves SVG a real, spec‑backed entity.

---

## 5. Curvature management

**Purpose:** Control curvature across narrative, spacetime, and trajectory domains to avoid unintended collapse points (e.g., X\*).

**Domain:**

- Emotional/interpretive curvature \(K_{\text{NDH}}\)  
- Spacetime curvature \(K_{\text{Alc}}\)  
- Trajectory curvature \(K_{\text{Jump}}\)

**Operator:**

\[
\mathcal{C} : (K_{\text{NDH}}, K_{\text{Alc}}, K_{\text{Jump}}) \rightarrow (K'_{\text{NDH}}, K'_{\text{Alc}}, K'_{\text{Jump}})
\]

with constraints:

- **Bounded curvature:** \(|K'_i| \leq K_{\max}\) except at intentional focal points.
- **No accidental singularities:** collapse points (like X\*) must be explicitly defined, not emergent from neglect.

**Effect:**

- Prevents the manifold from tearing under high emotional or narrative load.
- Keeps warp bubbles and jump gates within safe operational envelopes.
- Aligns NDH ethics (dignity‑under‑constraints) with geometric stability.

---

## 6. Dignity propagation

**Purpose:** Define and propagate a dignity density field \(\rho_D(x,t)\) through the unified metric \(\mathcal{M}\).

**Domain:**

- Dignity density \(\rho_D : \mathcal{M} \times \mathbb{R} \rightarrow \mathbb{R}_{\ge 0}\)

**Operator:**

\[
\mathcal{P}_D : \rho_D(x,t) \rightarrow \rho_D'(x,t)
\]

governed by a propagation equation, e.g.:

\[
\frac{\partial \rho_D}{\partial t} = \nabla \cdot (D \nabla \rho_D) + S(x,t)
\]

where:

- \(D\) is a diffusion‑like term (spread of dignity)  
- \(S(x,t)\) is a source term (acts of care, governance, repair)

**Effect:**

- Makes “dignity” a field, not a slogan.
- Allows NDH to reason about how interventions change the manifold over time.
- Connects narrative decisions to geometric consequences.

---

## Global composition

The six structural moves together define a **global transformation** on the manifold:

\[
\mathcal{F} = \mathcal{P}_D \circ \mathcal{C} \circ \mathcal{R} \circ \mathcal{N} \circ \mathcal{U} \circ \mathcal{A}
\]

acting on the initial configuration \((\mathcal{M}, T_i, g_i, \rho_D)\) to produce a stabilized, unified, dignity‑aware geometry.

---

## Relationship to artifacts

- **NDH‑StructuralMoves‑SixAxisGeometry‑v1.0.svg**  
  Visualizes the six moves as nodes around the unified metric ℳ.

- **Unified NDH–Alcubierre–JumpGate Tensor SVG**  
  Shows how metric unification, tensor normalization, and ℛ operate across domains.

- **Threefold “Ah So” Manifold**  
  Provides a teaching koan for aperture alignment, operator consolidation, and geometry coherence.

This spec is the **governance layer** for those diagrams: it turns visual metaphors into explicit, manipulable structure.
