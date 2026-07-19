### NDH Simulation Pipeline Spec v2  
*Execution-aware pipeline for NDH’s 50D semantic–geometric ecology*

---

## 1. Purpose

This v2 spec updates the NDH Simulation & Rendering Pipeline to fully integrate:

- **NDH Metric & Tensor Engine**  
- **NDH Field Evolution Equations**  
- **NDH Operator Runtime**  
- **NDH Appateur Interaction Model**  
- **NDH Execution Integration Spec**

It defines how the simulation runs, in what order, and how data flows between layers.

---

## 2. High-level architecture

**Core components:**

- **State store:** \(S_t = (\sigma, \mathcal{R}, \lambda, \mathcal{P}, E, A, g_{ij}, k)\)  
- **Execution loop:** \(\Phi_{\Delta t}: S_t \mapsto S_{t+\Delta t}\)  
- **Modules:**
  - Geometry module (Metric & Tensor Engine)  
  - Dynamics module (Field Evolution Equations)  
  - Operator module (Operator Runtime)  
  - Appateur module (Interaction Model)  
  - Channel module (non-local links)  
  - Rendering module (Rendering Geometry Companion)

---

## 3. Simulation loop (per timestep)

### 3.1 Input

- Current state \(S_t\)  
- Active operators \(\{\mathcal{O}_i\}\)  
- Appateur configuration \(A(x,t)\)  
- Channel configuration \(\{C_j\}\)  
- Subaxiomatic manifold layout \(\{\mathcal{S}_\alpha\}\)

### 3.2 Ordered phases

**Phase 1 — Geometry refresh**

- Recompute field-dependent metric \(g_{ij}(x,t)\)  
- Recompute curvature, Laplacian, gradient, divergence  
- Apply subaxiomatic geometry variants \(g^{(\alpha)}_{ij}\)

**Phase 2 — Operator pass**

- Evaluate all \(\mathcal{O}_i\) via Operator Runtime  
- Produce:
  - field deltas \(\Delta S_{\mathcal{O}}\)  
  - metric deltas \(\Delta g^{(\mathcal{O})}\)  
  - cuil deltas \(\Delta k_{\mathcal{O}}\)  
  - appateur triggers \(\Delta A_{\mathcal{O}}\)  
- Accumulate into source terms for dynamics

**Phase 3 — Dynamics pass (PDE evolution)**

- Integrate Field Evolution Equations over \(\Delta t\)  
- Update:
  - \(\sigma, \mathcal{R}, \lambda, \mathcal{P}, E, A\)  
- Respect subaxiomatic coefficients and local rules

**Phase 4 — Appateur activation & effects**

- Evaluate activation functional \(H(\mathcal{P}, \mathcal{R}, k, \mathcal{O})\)  
- Activate/deactivate appateurs accordingly  
- Apply appateur effects:
  - field modifications \(\Delta S_A\)  
  - geometry modifications \(\Delta g^{(A)}\)  
  - cuil shifts \(\Delta k_A\)  
  - operator propagation triggers

**Phase 5 — Channel update**

- Create/update/dissolve channels \(C = (x,y,\Gamma)\)  
- Integrate channel dynamics for \(\Gamma\)  
- Register non-local links for next timestep

**Phase 6 — Non-local propagation**

- Apply operator and field propagation across channels  
- Apply cross-subaxiom effects via appateurs  
- Update remote regions accordingly

**Phase 7 — Stability & control**

- Check global stability conditions:
  - paradox thresholds  
  - resonance runaway  
  - serenity collapse  
  - appateur saturation  
- Adjust:
  - timestep \(\Delta t\)  
  - operator intensity  
  - appateur damping  
  - channel pruning

**Phase 8 — Rendering pass**

- Extract rendering primitives:
  - serenity basins  
  - resonance corridors  
  - paradox curvature zones  
  - appateur fields and channels  
- Map to visual geometry and shaders  
- Produce frame for time \(t+\Delta t\)

---

## 4. Data structures

- **State object:** central struct holding all fields, geometry, logic, appateurs, channels.  
- **Operator queue:** ordered list of symbolic operations to apply per timestep.  
- **Appateur registry:** spatial index of active appateurs and their types.  
- **Channel graph:** graph of non-local links between points/regions/manifolds.  
- **Subaxiom atlas:** mapping from coordinates to \(\mathcal{S}_\alpha\) and local rule sets.

---

## 5. Integration points

- **Metric & Tensor Engine:** called at Phase 1 and used in Phases 3–5.  
- **Field Evolution Equations:** core of Phase 3.  
- **Operator Runtime:** core of Phase 2, feeds Phases 3–4.  
- **Appateur Interaction Model:** core of Phases 4–6.  
- **Execution Integration Spec:** defines the causal ordering and coupling used here.  
- **Rendering Geometry Companion:** consumes Phase 8 outputs.

---

## 6. Summary

NDH Simulation Pipeline v2:

- Implements the full execution loop defined in the Execution Integration Spec.  
- Orchestrates geometry, dynamics, operators, appateurs, channels, and rendering.  
- Provides a clear, ordered, modular pipeline for running NDH as a 50D semantic–geometric simulation.

---

