### NDH Simulation & Execution Protocol  
*Formal runtime loop and execution semantics for NDH’s 50D semantic–geometric architecture*

---

## 1. Purpose

The NDH Simulation & Execution Protocol defines the **runtime loop** that advances NDH from one state \(S_t\) to the next \(S_{t+1}\). It specifies:

- unified state representation  
- kernel step semantics  
- update equations for geometry, fields, domains, entities, governance, and policy  
- transport and interaction integration  
- stability and safety checks  

This is the document that makes NDH **executable**.

---

## 2. Unified state representation

At simulation time \(t\), NDH is represented by:

\[
S_t = \{ g_{ij}, K_{ij}, \mathcal{F}, \Lambda_{ij}, G_{ij}, \Gamma, U, E, \mathcal{S}, \Pi \}
\]

Where:

- **Geometry:** \(g_{ij}(x,t)\) metric, \(K_{ij}(x,t)\) curvature  
- **Fields:** \(\mathcal{F} = \{\sigma, \mathcal{R}, \mathcal{P}, A, k\}\)  
- **Stability:** \(\Lambda_{ij}(x,t)\) stability tensor  
- **Governance:** \(G_{ij}(x,t)\) governance tensor  
- **Channels:** \(\Gamma(x,y,t)\) appateur/channel matrix  
- **Domains:** \(U = \{U_\alpha\}\) domain set and boundaries  
- **Entities:** \(E = \{E_n\}\) entity set and signatures  
- **Axioms:** \(\mathcal{S} = \{\mathcal{S}_\beta\}\) axiom set  
- **Policy:** \(\Pi\) active policy set and weights  

All simulation steps operate on \(S_t\).

---

## 3. Kernel step function

The core execution rule:

\[
S_{t+1} = \mathcal{K}(S_t)
\]

Where \(\mathcal{K}\) is decomposed into ordered phases:

1. **Geometry update**  
2. **Field evolution**  
3. **Domain update**  
4. **Entity update**  
5. **Interaction & transport**  
6. **Stability audit**  
7. **Governance update**  
8. **Policy evaluation & decision synthesis**  
9. **Action dispatch**  
10. **Axiom & global state update**

Each phase has explicit equations and invariants.

---

## 4. Phase 1 — Geometry update

Update metric and curvature:

\[
g_{ij}^{(t+1)} = g_{ij}^{(t)} + \Delta g_{ij}(\mathcal{F}, K_{ij}, \Lambda_{ij})
\]

\[
K_{ij}^{(t+1)} = K_{ij}^{(t)} + \Delta K_{ij}(g_{ij}, \mathcal{F})
\]

Geometry responds to field tensors and stability.

---

## 5. Phase 2 — Field evolution

Fields evolve via governed dynamics:

\[
\sigma^{(t+1)} = \sigma^{(t)} + \Delta \sigma(g_{ij}, \Lambda_{ij}, G_{ij})
\]

\[
\mathcal{R}^{(t+1)} = \mathcal{R}^{(t)} + \Delta \mathcal{R}(g_{ij}, \Omega, U)
\]

\[
\mathcal{P}^{(t+1)} = \mathcal{P}^{(t)} + \Delta \mathcal{P}(g_{ij}, U, E)
\]

\[
A^{(t+1)} = A^{(t)} + \Delta A(\Gamma, \mathcal{P}, G_{ij})
\]

\[
k^{(t+1)} = k^{(t)} + \Delta k(\Omega, \Pi)
\]

Where \(\Omega\) denotes operator activity.

---

## 6. Phase 3 — Domain update

Domains are updated using **Domain Ecology** and **Interaction Geometry**:

- **Formation:** new \(U_\alpha\) if gradients exceed thresholds  
- **Drift:** update domain positions via curvature and transport  
- **Boundary:** recompute \(\partial U_\alpha\) and interaction regions \(\mathcal{I}_{ij}\)  
- **Collapse:** mark domains unstable if \(\Lambda(U_\alpha) < 0\) or \(\mathcal{P}\) exceeds collapse thresholds  
- **Inheritance:** generate residues and seed new domains as specified in Domain Ecology and Lineage Codex  

---

## 7. Phase 4 — Entity update

Entities evolve according to **Entity Lineage** and **Entity Ecology**:

- **Genesis:** spawn entities where \(E(x) = f(\sigma, \mathcal{R}, \mathcal{P}, A, k)\) crosses creation thresholds  
- **Behavior:** update roles (stabilizers, amplifiers, disruptors, mediators, shifters) based on local fields and domains  
- **Migration:** move entities via transport tensors \(T_{ij}\) and channels \(\Gamma\)  
- **Extinction:** remove entities in collapse zones or exhausted domains  
- **Lineage:** update lineage records and hybridization states  

---

## 8. Phase 5 — Interaction & transport

Apply **Domain Interaction Geometry & Transport**:

- Compute fluxes:
  \[
  F_\sigma, F_{\mathcal{R}}, F_{\mathcal{P}}, F_A, F_k
  \]
- Compute corridor strengths:
  \[
  C_{ij} = \int_{\gamma_{ij}} \|\mathcal{R}\| \, ds
  \]
- Update paradox fronts:
  \[
  v_{\mathcal{P}} = \frac{\partial \mathcal{P}}{\partial t} \cdot g^{ij}
  \]
- Update channels:
  \[
  \Gamma^{(t+1)} = \Gamma^{(t)} + \Delta \Gamma(A, \mathcal{P}, G_{ij})
  \]

Transport modifies domain coupling, entity migration, and cross‑axiom behavior.

---

## 9. Phase 6 — Stability audit

Compute stability tensor and risks:

\[
\Lambda_{ij}^{(t+1)} = \Lambda_{ij}^{(t)} + \Delta \Lambda(g_{ij}, \mathcal{F}, U, E)
\]

Perform:

- collapse prediction  
- basin mapping  
- risk scoring per domain and corridor  

Flag regions where \(\Lambda(U_\alpha) < 0\) or paradox fronts exceed safe thresholds.

---

## 10. Phase 7 — Governance update

Update governance tensors:

\[
G_{ij}^{(t+1)} = G_{ij}^{(t)} + \Delta G_{ij}(\Lambda_{ij}, \mathcal{F}, U, E)
\]

Apply governance divergence:

\[
\nabla \cdot G_{ij} = \Phi_{\text{gov}}
\]

This yields updated authority, regulation, and policy pressure across domains and axioms.

---

## 11. Phase 8 — Policy evaluation & decision synthesis

Evaluate policies \(\Pi_k\) against \(S_t\):

\[
D_{ij}^{(k)} = \Pi_k(S_t, G_{ij}, \Lambda_{ij}, U, E)
\]

Aggregate decision tensors:

\[
D_{ij} = \sum_k w_k D_{ij}^{(k)}
\]

This is the **Policy Engine & Decision Tensor** layer.

---

## 12. Phase 9 — Action dispatch

Apply decisions to the state:

\[
S_{t+1} = S_{t+1} + \alpha D_{ij}
\]

Where \(\alpha\) is the policy application coefficient, and actions are mapped to:

- geometry modifications  
- field adjustments  
- operator throttling/amplification  
- appateur routing  
- domain stabilization/merge/split/collapse  
- entity role changes  

This is the execution bridge from policy to kernel.

---

## 13. Phase 10 — Axiom & global state update

Update axioms \(\mathcal{S}\):

- create new axioms when channel density and semantic flux exceed thresholds  
- merge or split axioms based on governance and stability  
- update cross‑axiom transport and domain placement  

Finalize \(S_{t+1}\) and advance simulation time.

---

## 14. Invariants & safety constraints

Key invariants:

- **Stability floor:** global \(\Lambda\) must not remain deeply negative for extended steps without governance intervention.  
- **Governance coherence:** governance tensors must remain consistent across domain boundaries (no ungoverned high‑risk corridors).  
- **Policy fail‑closed:** ambiguous or undefined policy conditions default to non‑action or stabilizing action.  
- **Channel sanity:** appateur channels must not create unconstrained paradox amplification loops.  

These invariants ensure NDH remains simulatable and non‑pathological.

---

## 15. Summary

The NDH Simulation & Execution Protocol:

- defines the unified state \(S_t\)  
- specifies the kernel step function \(\mathcal{K}\)  
- formalizes phase‑ordered updates for geometry, fields, domains, entities, transport, stability, governance, and policy  
- integrates all prior NDH specs into a single executable loop  

This is the **runtime protocol** that makes NDH’s 50D semantic–geometric universe **runnable**.

---

