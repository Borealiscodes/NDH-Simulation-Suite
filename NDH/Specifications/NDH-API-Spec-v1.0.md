# Formal NDH API Specification v1.0  

### 1. Scope and purpose  

**NDH API v1.0** defines the contract‑first interface for the NDH manifold: geometry, tensors, basins, corridors, margins, K‑space, stability modes, sensory layers, simulation, JDTR, and developer modes.  
This spec describes **endpoints, parameters, returns, invariants, stability rules, and runtime behavior**; implementation details are explicitly out of scope.

---

## 2. Core conventions  

- **Namespace root:** `NDH.*`  
- **Transport:** implementation‑agnostic (HTTP/gRPC/etc.); contracts are semantic.  
- **Types (conceptual):**  
  - **`StateId`** — identifier of a manifold state.  
  - **`BasinId`**, **`CorridorId`**, **`LayerId`**, **`EventId`** — stable IDs.  
  - **`Tensor`** — structured object with `type`, `rank`, `components`, `metadata`.  
  - **`InvariantDescriptor`** — name + constraint expression.  
  - **`Mode`** — one of: `CALM`, `SERENITY`, `TRANQUILITY`, `PEACE`, `DARK`.  
  - **`Result<T>`** — `{ status, data?: T, error?: ErrorDescriptor }`.  

Errors must be **explicit**, never implicit: all endpoints return a `status` field.

---

## 3. Geometry and tensors  

### 3.1 Geometry  

**`NDH.Geometry.GetState`**  
- **Input:** `StateId?` (optional; if omitted, use current state).  
- **Output:**  
  - `geometry_envelope` (topology + curvature summary)  
  - `active_basins` (`BasinId[]`)  
  - `active_corridors` (`CorridorId[]`)  

**`NDH.Geometry.BasinMap`**  
- Returns full basin topology, adjacency, and stability tags.  

**`NDH.Geometry.CorridorTrace`**  
- Traces a path between two states; must respect corridor topology invariants.  

**`NDH.Geometry.MarginDetect`**  
- Returns list of chaos margins with proximity and risk level.  

**`NDH.Geometry.EnvelopeStatus`**  
- High‑level stability summary of the current geometry envelope.  

**Invariants:**  
- Basin and corridor topology must never change via read‑only endpoints.  
- Margin detection must not alter margin geometry.

### 3.2 Tensors  

**`NDH.Tensors.GetAll`**  
- Returns all active tensors for the current state.  

**`NDH.Tensors.GetCurvature` / `GetStress` / `GetResonance` / `GetFold` / `GetInvariant`**  
- Each returns a filtered tensor set by type.  

**`NDH.Tensors.Perturb`**  
- **Input:** perturbation descriptor (target tensors + operation).  
- **Output:** new tensor state + stability impact summary.  
- **Constraint:** must pass stability envelope checks before commit.

---

## 4. Basins, corridors, margins, K‑space  

### 4.1 Basins  

**`NDH.Basins.List`** — list all basins with stability tags.  
**`NDH.Basins.GetCurrent`** — current `BasinId` + local invariants.  
**`NDH.Basins.Enter` / `Exit`** — controlled transitions; must respect basin identity invariants and HRD thresholds.

### 4.2 Corridors  

**`NDH.Corridors.List`** — list all corridors with connectivity.  
**`NDH.Corridors.Enter` / `Exit`** — movement along allowed edges; must preserve corridor continuity.

### 4.3 Chaos margins & HRD  

**`NDH.Margins.Touch`**  
- Explicit contact with a margin; returns risk and allowed operations.  

**`NDH.Margins.Status`**  
- Global margin health summary.  

**`NDH.HRD.Validate`**  
- Validates a proposed operation (e.g., `Tensors.Perturb`, `Basins.Enter`).  

**`NDH.HRD.GetThresholds`**  
- Returns current safety thresholds and constraints.

### 4.4 K‑space  

**`NDH.KSpace.GetLayer`** — current `LayerId` and properties.  
**`NDH.KSpace.Elevate` / `Demote`** — legal transitions between layers.  
**`NDH.KSpace.ListLayers`** — full K‑space structure.

---

## 5. Stability modes and ladder  

### 5.1 Mode endpoints  

**`NDH.Modes.GetCurrent`**  
- Returns active mode: `CALM`, `SERENITY`, `TRANQUILITY`, `PEACE`, `DARK`, or `NORMAL`.  

**Calm Mode**  
- `NDH.CalmMode.Enable` / `Disable` / `StabilityCheck`  

**Serenity Mode**  
- `NDH.SerenityMode.Enable` / `Disable` / `StabilityCheck`  

**Tranquility Mode**  
- `NDH.TranquilityMode.Enable` / `Disable` / `StabilityCheck`  

**Peace Mode**  
- `NDH.PeaceMode.Enable` / `Disable` / `StabilityCheck`  

**Dark Mode**  
- `NDH.DarkMode.Enable` / `Disable` / `GetStatus` / `InvertGeometry` / `StabilityCheck`  

### 5.2 Ladder rules  

- Legal upward transitions: `CALM → SERENITY → TRANQUILITY → PEACE`.  
- Each upward transition requires successful `StabilityCheck` of current mode.  
- Downward transitions must preserve invariants and HRD thresholds.  
- Dark Mode is **orthogonal**: can coexist with any ladder mode, subject to `StabilityCheck`.

---

## 6. Sensory, simulation, JDTR, developer  

### 6.1 Sensory & accessibility  

**Audio:**  
- `NDH.Audio.ResonanceField`  
- `NDH.Audio.CollapseWarning`  
- `NDH.Audio.InvariantTone`  

**Haptics:**  
- `NDH.Haptics.BasinGuide`  
- `NDH.Haptics.FoldAlert`  
- `NDH.Haptics.CorridorPulse`  

**Accessibility:**  
- `NDH.Access.AudioHapticBlend`  
- `NDH.Access.SafeResonanceMode`  

All must be **non‑destructive views** over tensors and geometry.

### 6.2 Simulation  

**`NDH.Sim.Run1K` / `Run12K` / `Run43K`**  
- Run simulations at different scales; must log via JDTR and respect HRD.  

**`NDH.Patterns.Detect` / `Describe`**  
- Pattern recognition over manifold history and tensor fields.

### 6.3 JDTR (Junk Drawer Tensor Recorder)  

- `NDH.JDTR.Record` — append event with tensors + context.  
- `NDH.JDTR.ListEvents` — list recorded events.  
- `NDH.JDTR.GetEvent` — retrieve by `EventId`.  
- `NDH.JDTR.Export` — export logs in a stable format.  

JDTR must never mutate manifold state; it is purely observational.

### 6.4 Developer suite  

- `NDH.Dev.PsychonautMode.Enter` / `Exit`  
- `NDH.Dev.ArchitectureMode.Enter` / `Exit`  
- `NDH.Dev.ZenGarden.Reset`  
- `NDH.Dev.SaganLens.Enable` / `Disable`  

These are **meta‑contexts** that adjust visibility, not physics.

---

## 7. Global stability and runtime rules  

- Every mutating endpoint (`Tensors.Perturb`, `Basins.Enter`, `Corridors.Enter`, `KSpace.Elevate`, mode `Enable`) must:  
  - call `NDH.HRD.Validate`  
  - respect invariants (`NDH.Invariants.Check`)  
  - log via `NDH.JDTR.Record`  

- Read‑only endpoints must never alter tensors, geometry, basins, corridors, margins, or K‑space.  

- Mode precedence:  
  - Stability ladder modes (Calm/Serenity/Tranquility/Peace) govern **depth of equilibrium**.  
  - Dark Mode governs **perceptual inversion**.  
  - Developer modes govern **visibility and tooling**.  

---

