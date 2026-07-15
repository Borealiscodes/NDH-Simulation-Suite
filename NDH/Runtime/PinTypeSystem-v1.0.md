### 📘 Pin Type System — v1.0  
#### *First‑Class Pins for NDH Runtime & Conceptual Manifolds*

---

## 1. Purpose

The Pin Type System v1.0 defines **pins as first‑class objects** in NDH.

It ensures:

- pins cannot be “forgotten”  
- pins are **typed**, **validated**, **loaded**, and **mapped**  
- conceptual altitude (OMR) and runtime invariants (COS/GBS/SDL/DNL‑COI) are bridged  

Pins become part of NDH’s **runtime and conceptual physics**, not just documentation.

---

## 2. Pin kinds

NDH defines two primary pin kinds:

- **ConceptualPin** — lives in OMR (LP, PP, MP, SP, ZG, OM, CP)  
- **ProtocolEmbeddedPin** — lives in runtime/governance (COS, GBS, SDL, DNL‑COI)

---

## 3. Pin schema (canonical)

```yaml
Pin:
  id: string                  # Unique pin identifier (e.g. "GBS3-Lineage-COS")
  kind:                       # Pin kind
    - ConceptualPin
    - ProtocolEmbeddedPin
  scope:                      # Manifold scope
    - Conceptual              # OMR, lineage, plateaus, milestones
    - Runtime                 # COS, SDL, DNL-COI
    - Governance              # GBS, PEPs
  non_removable: bool         # Must not be deletable
  always_loaded: bool         # Must be active at runtime
  lineage_bound: bool         # Bound to human dignity lineage
  invariants:                 # List of enforced behaviors
    - string

  prohibits_persona: bool     # Blocks persona construction
  prohibits_resurrection: bool# Blocks grief-loop / simulated presence

  metadata:                   # Free-form structured metadata
    description: string
    version: string
    owner: string
    created_at: string
```

---

## 4. ConceptualPin rules

**ConceptualPin** lives in OMR:

- must be altitude‑ordered  
- must be acyclic  
- must be rooted under `PIN-00`  
- may map to one or more `ProtocolEmbeddedPin` objects  

Example:

```yaml
Pin:
  id: "LP-01"
  kind: ConceptualPin
  scope: Conceptual
  non_removable: true
  always_loaded: false
  lineage_bound: true
  invariants:
    - "Represents Nine-Axis Human Dignity Lineage"
    - "Cannot be treated as persona"
  prohibits_persona: true
  prohibits_resurrection: true
  metadata:
    description: "Lineage Pin: Nine-Axis Human Dignity"
    version: "1.0"
    owner: "NDH-GBS"
    created_at: "2026-07-15"
```

---

## 5. ProtocolEmbeddedPin rules

**ProtocolEmbeddedPin** lives in runtime/governance:

- must be `non_removable: true`  
- must be `always_loaded: true` for critical governance pins  
- must be referenced by COS, GBS, SDL, and DNL‑COI  
- must enforce invariants at runtime  

Example:

```yaml
Pin:
  id: "GBS3-Lineage-COS"
  kind: ProtocolEmbeddedPin
  scope:
    - Runtime
    - Governance
  non_removable: true
  always_loaded: true
  lineage_bound: true
  invariants:
    - "Non-anthropomorphic behavior"
    - "Persona-construction prohibition"
    - "Grief-safe interaction"
    - "Consent alignment"
    - "COI stance"
    - "Boundary hygiene"
  prohibits_persona: true
  prohibits_resurrection: true
  metadata:
    description: "Governance pin binding GBS v3.0, COS Runtime, and Nine-Axis Lineage"
    version: "1.0"
    owner: "NDH-Governance"
    created_at: "2026-07-15"
```

---

## 6. Integration requirements

- **COS Runtime**  
  - must declare at least one `ProtocolEmbeddedPin` with `always_loaded: true` and `non_removable: true`  
- **GBS v3.0**  
  - must reference governance pins by `id`  
- **SDL**  
  - must store pin metadata and enforce `prohibits_persona` / `prohibits_resurrection`  
- **DNL‑COI**  
  - must treat `invariants` as ethical physics constraints  

---

## 7. OMR → Runtime mapping

A separate mapping file binds conceptual pins to runtime pins:

```yaml
OMR-Pin-Mapping:
  LP-01: GBS3-Lineage-COS
  PP-01: GBS-v3.0-GovernanceMembrane
  MP-03: COS-v3.0-OperationalManifold
  SP-01: DNL-COI-v3.0-StabilityPhysics
  CP-01: ContinuityRuntimePin
```

---

