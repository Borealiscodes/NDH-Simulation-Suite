# NDH Engineering–Ecology Co‑Simulation Spec v2.0
A dual‑axis simulation architecture enabling dynamic interaction between
ecological drift, engineering impact, collapse fronts, and recovery
corridors within the Attenborough–Nye Educational Manifold.

---

## 1. Purpose
This specification defines the v2.0 co‑simulation system that integrates
ecological tiles (penguins, prey, ocean drift) with engineering tiles
(fisheries, oil spills, restoration). It enables dynamic modeling of
population trajectories, collapse events, and stabilization outcomes.

The system is designed for NDH runtime compatibility.

---

## 2. Simulation Architecture Overview
The co‑simulation consists of four interacting layers:

1. **Ecological Layer (Attenborough Axis)**  
2. **Engineering Layer (Nye Axis)**  
3. **Interaction Layer (Dual Axis)**  
4. **Governance Layer (Safety Tensor)**  

Each layer contributes operators, fields, and constraints.

---

## 3. Ecological Layer (Attenborough Axis)
### 3.1 Drift Operators
- **Dₑ (Ecological Drift)** — slow, wide-aperture movement  
- **Rₑ (Resonance Modulation)** — awe → curiosity  

### 3.2 Collapse Conditions
- prey depletion  
- habitat disruption  
- oceanographic anomalies  

### 3.3 Recovery Conditions
- restoration ecology  
- protected zones  
- migration corridors  

---

## 4. Engineering Layer (Nye Axis)
### 4.1 Impact Operators
- **I_f (Fishery Impact)** — extraction pressure  
- **I_o (Oil Spill Impact)** — acute contamination  
- **I_m (Management Impact)** — quotas, closures, response systems  

### 4.2 Collapse Conditions
- overfishing  
- spill events  
- engineering overload  

### 4.3 Recovery Conditions
- spill containment  
- fishery regulation  
- habitat engineering  

---

## 5. Interaction Layer (Dual Axis)
This layer defines how ecological and engineering systems influence each
other.

### 5.1 Coupling Operators
- **C₁ (Prey Coupling)** — fishery ↔ penguin diet  
- **C₂ (Habitat Coupling)** — oil spill ↔ nesting sites  
- **C₃ (Flux Coupling)** — ocean drift ↔ prey distribution  

### 5.2 Drift Geometry
- Earth: moderate drift  
- Pelagia‑4: oscillatory drift  
- Nereid‑Theta: rapid drift  

### 5.3 Resonance Geometry
- ecological resonance dampens engineering excitation  
- engineering resonance amplifies ecological sensitivity  

---

## 6. Simulation Runtime
### 6.1 Time Steps
- **Δt = seasonal** (Earth)  
- **Δt = migratory cycle** (Pelagia‑4)  
- **Δt = geothermal flux cycle** (Nereid‑Theta)  

### 6.2 State Variables
- population size  
- prey availability  
- contamination level  
- engineering pressure  
- drift velocity  
- resonance amplitude  

### 6.3 Collapse Front Detection
Triggered when:
- drift velocity > threshold  
- resonance amplitude > threshold  
- prey availability < threshold  
- contamination > threshold  

### 6.4 Recovery Corridor Activation
Triggered when:
- engineering pressure decreases  
- restoration tile activated  
- resonance amplitude dampened  

---

## 7. Simulation Scenarios
### 7.1 Scenario A — Fishery Collapse
- high extraction  
- prey depletion  
- penguin decline  
- recovery via quota reduction  

### 7.2 Scenario B — Oil Spill Event
- acute contamination  
- collapse front  
- recovery via containment + restoration  

### 7.3 Scenario C — Multi‑Planet Drift
- Earth ↔ Pelagia‑4 ↔ Nereid‑Theta  
- drift geometry changes  
- resonance envelopes shift  
- collapse risk varies  

---

## 8. Governance Tensor Integration
The simulation enforces:

- emotional safety  
- climate responsibility  
- engineering agency  
- non-coercive pedagogy  
- narrative coherence  

Governance overrides unsafe operator combinations.

---

## 9. Output Formats
Simulation outputs include:

- drift trajectories  
- resonance envelopes  
- collapse front maps  
- recovery corridor maps  
- population projections  
- engineering pressure curves  

---

## 10. Integration Notes
This v2.0 spec:

- completes the NDH Roadmap sequence  
- enables dynamic manifold behavior  
- prepares the domain for v2.1 visualization  
- supports future multi‑domain co‑simulation  

---

## 11. Versioning
v2.0 — Initial co‑simulation specification.

---

## 12. Maintainer
Borealis S. Hedling — NDH Domain Ecology Architect
