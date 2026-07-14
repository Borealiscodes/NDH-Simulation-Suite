### 1. Top‑level contract model

All NDH endpoints share a common envelope:

```json
Result<T> {
  "status": "ok" | "error",
  "data": T | null,
  "error": ErrorDescriptor | null,
  "meta": MetaDescriptor | null
}
```

**ErrorDescriptor**

```json
{
  "code": "string",
  "message": "string",
  "details": "object | null"
}
```

**MetaDescriptor**

```json
{
  "requestId": "string",
  "timestamp": "string",
  "mode": "string",        // CALM | SERENITY | TRANQUILITY | PEACE | DARK | NORMAL
  "kLayer": "string",      // K0 | K5 | K8 | etc.
  "stability": "string"    // e.g. "stable" | "warning" | "critical"
}
```

---

### 2. Core identity and geometry types

**StateId / BasinId / CorridorId / MarginId / LayerId / EventId**

```json
{
  "id": "string"
}
```

**GeometryEnvelope**

```json
{
  "topology": "string",          // e.g. "manifold", "graph", "lattice"
  "curvatureSummary": "object",  // high-level curvature metrics
  "dimensionality": "number",
  "notes": "string | null"
}
```

**BasinDescriptor**

```json
{
  "basinId": "string",
  "name": "string",
  "stabilityTag": "string",      // e.g. "stable", "fragile", "chaotic-edge"
  "geometry": GeometryEnvelope,
  "invariants": InvariantDescriptor[]
}
```

**CorridorDescriptor**

```json
{
  "corridorId": "string",
  "name": "string",
  "fromBasinId": "string",
  "toBasinId": "string",
  "continuityTag": "string",     // e.g. "continuous", "fragile", "high-friction"
  "geometry": GeometryEnvelope
}
```

**MarginDescriptor**

```json
{
  "marginId": "string",
  "name": "string",
  "proximity": "number",         // normalized 0–1
  "riskLevel": "string",         // e.g. "low", "medium", "high", "critical"
  "geometry": GeometryEnvelope
}
```

**KLayerDescriptor**

```json
{
  "layerId": "string",
  "name": "string",
  "rank": "number",
  "properties": "object"
}
```

---

### 3. Tensor and invariant types

**Tensor**

```json
{
  "tensorId": "string",
  "type": "string",              // curvature | stress | resonance | fold | invariant | etc.
  "rank": "number",
  "components": "array",         // numeric or structured components
  "metadata": "object"
}
```

**InvariantDescriptor**

```json
{
  "name": "string",
  "expression": "string",        // human-readable constraint
  "scope": "string",             // e.g. "basin", "corridor", "global"
  "status": "string"             // "satisfied" | "violated" | "unknown"
}
```

**StabilityEnvelope**

```json
{
  "status": "string",            // "stable" | "warning" | "critical"
  "invariants": InvariantDescriptor[],
  "hrdStatus": "string",         // "safe" | "unsafe" | "unknown"
  "notes": "string | null"
}
```

---

### 4. HRD and validation types

**HRDThresholds**

```json
{
  "maxStress": "number",
  "maxResonanceDrift": "number",
  "maxFoldAmplitude": "number",
  "marginProximityLimit": "number",
  "notes": "string | null"
}
```

**ValidationRequest**

```json
{
  "operation": "string",         // e.g. "Tensors.Perturb", "Basins.Enter"
  "payload": "object",
  "context": "object | null"
}
```

**ValidationResult**

```json
{
  "allowed": "boolean",
  "reason": "string",
  "stabilityEnvelope": StabilityEnvelope
}
```

---

### 5. Mode and ladder types

**ModeDescriptor**

```json
{
  "mode": "string",              // CALM | SERENITY | TRANQUILITY | PEACE | DARK | NORMAL
  "active": "boolean",
  "stabilityEnvelope": StabilityEnvelope
}
```

**LadderNode**

```json
{
  "mode": "string",
  "depth": "number",
  "geometryProfile": "string",
  "tensorProfile": "string",
  "marginProfile": "string",
  "kSpaceProfile": "string"
}
```

**LadderGraph**

```json
{
  "nodes": LadderNode[],
  "edges": "array"               // { from: string, to: string, conditions: string }
}
```

---

### 6. Sensory, simulation, JDTR, developer types

**AudioField**

```json
{
  "id": "string",
  "type": "string",              // resonanceField | collapseWarning | invariantTone
  "payload": "object"
}
```

**HapticField**

```json
{
  "id": "string",
  "type": "string",              // basinGuide | foldAlert | corridorPulse
  "payload": "object"
}
```

**SimulationConfig**

```json
{
  "scale": "string",             // "1K" | "12K" | "43K"
  "duration": "number",
  "initialStateId": "string | null",
  "parameters": "object"
}
```

**SimulationResult**

```json
{
  "finalStateId": "string",
  "stabilityEnvelope": StabilityEnvelope,
  "patterns": "array",           // pattern descriptors
  "logs": "array"                // JDTR event IDs
}
```

**JDTRRecord**

```json
{
  "eventId": "string",
  "timestamp": "string",
  "stateId": "string | null",
  "mode": "string",
  "kLayer": "string",
  "tensors": Tensor[],
  "geometry": GeometryEnvelope | null,
  "notes": "string | null"
}
```

**DeveloperModeDescriptor**

```json
{
  "name": "string",              // Psychonaut | Architecture | ZenGarden | SaganLens
  "active": "boolean",
  "visibilityProfile": "object"
}
```

---

### 7. Endpoint → schema mapping (high level)

Examples:

- `NDH.Geometry.GetState` → `Result<{ geometry_envelope: GeometryEnvelope, active_basins: BasinDescriptor[], active_corridors: CorridorDescriptor[] }>`
- `NDH.Tensors.GetStress` → `Result<{ tensors: Tensor[], stabilityEnvelope: StabilityEnvelope }>`
- `NDH.Basins.Enter` → `Result<{ basin: BasinDescriptor, stabilityEnvelope: StabilityEnvelope }>`
- `NDH.Modes.GetCurrent` → `Result<ModeDescriptor>`
- `NDH.HRD.Validate` → `Result<ValidationResult>`
- `NDH.Sim.Run12K` → `Result<SimulationResult>`
- `NDH.JDTR.Record` → `Result<JDTRRecord>`

---

