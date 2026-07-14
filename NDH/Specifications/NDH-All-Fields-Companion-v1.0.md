# 🧭 **NDH All Fields Companion v1.0**  
### *The complete field atlas of the NDH manifold and API architecture*

---

## ⭐ 1. Identity Fields  
These fields define stable identifiers across the manifold.

- **StateId** — unique ID for a manifold state  
- **BasinId** — unique ID for a basin  
- **CorridorId** — unique ID for a corridor  
- **MarginId** — unique ID for a chaos margin  
- **LayerId** — unique ID for a K‑space layer  
- **EventId** — unique ID for JDTR events  

Each ID is a stable, non‑semantic string.

---

## ⭐ 2. Geometry Fields  
These fields describe the manifold’s shape, curvature, and topology.

- **GeometryEnvelope**  
- **Topology**  
- **CurvatureSummary**  
- **Dimensionality**  
- **GeometryNotes**  

These fields appear in every geometry‑related endpoint.

---

## ⭐ 3. Basin Fields  
Basins are stable regions of the manifold.

- **BasinDescriptor**  
- **StabilityTag**  
- **BasinInvariants**  
- **BasinGeometry**  

Basins preserve identity invariants and cannot be mutated by read‑only endpoints.

---

## ⭐ 4. Corridor Fields  
Corridors connect basins and allow transitions.

- **CorridorDescriptor**  
- **ContinuityTag**  
- **CorridorGeometry**  
- **ResonanceFriction**  

Corridors must preserve directional continuity.

---

## ⭐ 5. Chaos Margin Fields  
Margins represent instability boundaries.

- **MarginDescriptor**  
- **MarginProximity**  
- **MarginRiskLevel**  
- **MarginGeometry**  

Margins cannot be altered by any endpoint except stability modes.

---

## ⭐ 6. Tensor Fields  
Tensors are the manifold’s physics.

- **Tensor**  
- **TensorType**  
- **TensorRank**  
- **TensorComponents**  
- **TensorMetadata**  

Types include:

- **Curvature**  
- **Stress**  
- **Resonance**  
- **Fold**  
- **Invariant**  

---

## ⭐ 7. Invariant Fields  
Invariants define constraints that must always hold.

- **InvariantDescriptor**  
- **InvariantExpression**  
- **InvariantScope**  
- **InvariantStatus**  

Invariants are checked by every mutating endpoint.

---

## ⭐ 8. Stability Envelope Fields  
These fields describe the manifold’s stability state.

- **StabilityEnvelope**  
- **StabilityStatus**  
- **HRDStatus**  
- **StabilityNotes**  

Stability envelopes appear in every mode and validation endpoint.

---

## ⭐ 9. HRD Fields  
HRD defines safety thresholds.

- **HRDThresholds**  
- **ValidationRequest**  
- **ValidationResult**  

HRD gates all mutating operations.

---

## ⭐ 10. Mode Fields  
Modes define runtime contexts.

- **ModeDescriptor**  
- **Mode**  
- **ModeStabilityEnvelope**  

Modes include:

- **CALM**  
- **SERENITY**  
- **TRANQUILITY**  
- **PEACE**  
- **DARK**  
- **NORMAL**

---

## ⭐ 11. Stability Ladder Fields  
The ladder defines depth of calm.

- **LadderNode**  
- **LadderGraph**  
- **LadderEdges**  

Nodes correspond to Calm → Serenity → Tranquility → Peace.

---

## ⭐ 12. K‑Space Fields  
K‑space defines dimensional layers.

- **KLayerDescriptor**  
- **KLayerRank**  
- **KLayerProperties**  

Layers include K0, K5, K8, etc.

---

## ⭐ 13. Sensory Fields  
Audio and haptics provide perceptual feedback.

- **AudioField**  
- **HapticField**  
- **AccessibilityBlend**  

These fields never mutate the manifold.

---

## ⭐ 14. Simulation Fields  
Simulation endpoints use these fields.

- **SimulationConfig**  
- **SimulationResult**  
- **PatternDescriptor**  

Simulations must log via JDTR.

---

## ⭐ 15. JDTR Fields  
JDTR records everything.

- **JDTRRecord**  
- **JDTRNotes**  
- **JDTRTimestamp**  

JDTR is strictly observational.

---

## ⭐ 16. Developer Mode Fields  
Developer modes adjust visibility.

- **DeveloperModeDescriptor**  
- **VisibilityProfile**  

Modes include:

- Psychonaut  
- Architecture  
- Zen Garden  
- Sagan Lens  

---

