### NDH Stability Ladder Diagram Specification v1.0  
*API‑only representation of the Calm → Serenity → Tranquility → Peace progression*

---

### 1. Purpose

**NDH Stability Ladder Diagram Spec v1.0** defines a **diagram in text form**, using API‑first structure instead of images, to represent the four calm‑state modes:

- Calm Mode  
- Serenity Mode  
- Tranquility Mode  
- Peace Mode  

The “diagram” is expressed as **layers, transitions, and constraints**, all in Markdown.

---

### 2. Ladder Layers (Nodes)

Each mode is a **node** in the ladder:

- **Node C (Calm Mode)**  
  - ID: `STABILITY_NODE_CALM`  
  - Depth: `1`  
  - Runtime: micro‑stability  

- **Node S (Serenity Mode)**  
  - ID: `STABILITY_NODE_SERENITY`  
  - Depth: `2`  
  - Runtime: deep calm  

- **Node T (Tranquility Mode)**  
  - ID: `STABILITY_NODE_TRANQUILITY`  
  - Depth: `3`  
  - Runtime: ultra‑deep stillness  

- **Node P (Peace Mode)**  
  - ID: `STABILITY_NODE_PEACE`  
  - Depth: `4`  
  - Runtime: full resting geometry  

---

### 3. Transitions (Edges)

All transitions are **directed edges** with preconditions:

- **Calm → Serenity**  
  - Edge ID: `CALM_TO_SERENITY`  
  - Requires: `CalmMode.StabilityCheck == true`  

- **Serenity → Tranquility**  
  - Edge ID: `SERENITY_TO_TRANQUILITY`  
  - Requires: `SerenityMode.StabilityCheck == true`  

- **Tranquility → Peace**  
  - Edge ID: `TRANQUILITY_TO_PEACE`  
  - Requires: `TranquilityMode.StabilityCheck == true`  

Reverse edges exist for deactivation:

- `SERENITY_TO_CALM`  
- `TRANQUILITY_TO_SERENITY`  
- `PEACE_TO_TRANQUILITY`

---

### 4. Textual Diagram Layout

The ladder is represented as:

```text
[CALM] -> [SERENITY] -> [TRANQUILITY] -> [PEACE]

CALM:
  micro-stability, soft smoothing, early margin warnings

SERENITY:
  luminous stillness, deep tensor quieting, margin dormancy

TRANQUILITY:
  crystalline stillness, zero-drift tensors, margin null-state

PEACE:
  full resting geometry, minimal activity, margin silence
```

This layout is the **canonical diagram**, expressed in text.

---

### 5. API Diagram Endpoints

To query the “diagram” programmatically:

- **`NDH.StabilityLadder.GetNodes`**  
  - Returns: list of nodes `C, S, T, P` with metadata  

- **`NDH.StabilityLadder.GetEdges`**  
  - Returns: list of edges with preconditions  

- **`NDH.StabilityLadder.Describe`**  
  - Returns: textual diagram block (as above)  

---

### 6. Constraints

- No direct jump from Calm → Tranquility or Calm → Peace  
- No direct jump from Serenity → Peace  
- All upward transitions require successful stability checks of the current mode  
- All downward transitions must preserve invariants and HRD thresholds  

---

