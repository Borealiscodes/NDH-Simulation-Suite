# Operational Stability Basin Transition Map — v1.0  
### NDH Basin‑to‑Basin Transition Geometry + Runtime Stability Routing (OSBTM)

---

## 0. Map metadata block

```text
MAP ID: OSBTM-v1.0
Map Type: Stability Basin Transition Map
Version: 1.0
Cluster: Operational / Stability Geometry
Repo: NDH Simulation Suite
Placement: Internal (Operational Spine)
Status: Active (Governing)
```

Sits under:

- Operational Stability Basin Atlas  
- Operational Stability Potential Function  
- Operational Stability Gradient Map  

And above:

- recovery routing  
- stabilizer sequencing  
- envelope alignment pathing  

---

## 1. Purpose

The **Operational Stability Basin Transition Map (OSBTM)** defines:

- how NDH transitions between stability basins  
- which transitions are allowed, forbidden, or require recovery  
- how gradients, potentials, and invariants constrain transitions  
- how PEP basins, continuity basins, invariant basins, and chaos‑margin basins interact  
- how runtime can “re‑home” NDH into safer basins when needed  

It is the **stability routing chart** for basin‑level behavior.

---

## 2. Transition definition

A basin transition is:

\[
\mathcal{B}_i \rightarrow \mathcal{B}_j
\]

under a controlled evolution:

\[
x(t+1) = x(t) + \Delta x
\]

subject to:

- invariant preservation  
- envelope constraints  
- chaos‑margin avoidance  
- stability potential bounds  

---

## 3. Transition classes

**Label:** PEP → PEP  
**Description:** Safe re‑anchoring between PEP basins.

**Label:** PEP → Continuity  
**Description:** When CP‑01 or continuity protocols override local PEP minima.

**Label:** PEP → Invariant basin  
**Description:** When invariant enforcement pulls NDH into a protected well.

**Label:** Any → Chaos‑margin basin  
**Description:** Unstable transition; must trigger Recovery Protocol.

---

## 4. Transition constraints

- **Invariant constraint:**
  
  \[
  I_j(x(t+1)) = I_j(x(t))
  \]

- **Envelope constraint:**
  
  Transitions must remain inside the Stability Envelope.

- **Chaos‑margin constraint:**
  
  Transitions into \(\mathcal{B}_{\tau}\) are flagged as unstable.

- **Potential constraint:**
  
  Transitions should not increase \(V(x)\) beyond critical thresholds unless in controlled recovery.

---

## 5. Runtime use

OSBTM is used to:

- decide whether a requested state change implies a basin change  
- check if that basin change is allowed  
- route through stabilizers, drift correction, and envelope alignment to achieve it  
- escalate to Recovery Protocol if the only path crosses chaos‑margin basins  

---

## 6. Implementation requirements

- encode basin adjacency and allowed transitions  
- integrate with OSBA, OSPF, OSGM, OIPE  
- enforce constraints at every proposed basin change  
- expose a “proposed transition → allowed/forbidden/needs‑recovery” interface  

---

