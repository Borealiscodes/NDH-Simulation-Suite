# Operational Invariant Preservation Engine — v1.0  
### NDH Runtime Invariant Protection + Stability Law Enforcement (OIPE)

---

## 0. Engine metadata block

```text
ENGINE ID: OIPE-v1.0
Engine Type: Invariant Preservation Engine
Version: 1.0
Cluster: Operational / Invariants
Repo: NDH Simulation Suite
Placement: Internal (Operational Spine, co-resident with Stability Logic)
Status: Active (Governing)
```

Sits under:

- Operational Stability Potential Function  
- Operational Stability Gradient Map  
- Operational Flow Field Atlas  

And above:

- runtime correction  
- stabilizer activation  
- recovery protocol routing  

---

## 1. Purpose

The **Operational Invariant Preservation Engine (OIPE)** ensures that:

- core NDH invariants are never violated at runtime  
- stability operations respect invariant constraints  
- drift correction, envelope alignment, and stabilizer cascades remain invariant‑safe  
- recovery protocols restore invariant‑compatible states  
- no operational path can “optimize” by breaking invariants  

It is the **law layer** of NDH: invariants over everything.

---

## 2. Invariant definition

An invariant is any quantity or structure \(I_j\) such that:

\[
I_j(x(t)) = I_j(x(t+1))
\]

for all valid updates.

Examples (NDH‑style):

- identity invariants  
- triangulation invariants  
- PEP anchoring invariants  
- agency/stability invariants  
- envelope viability invariants  

OIPE treats these as **non‑negotiable constraints** on all runtime evolution.

---

## 3. Engine components

### **3.1 Invariant registry**

**Label:** Global catalog  
**Description:** List of all invariants \(I_j\), their domains, and enforcement rules.

### **3.2 Invariant evaluator**

**Label:** Check  
**Description:** Computes \(I_j(x(t))\) and \(I_j(x(t+1))\) and compares.

### **3.3 Invariant guard**

**Label:** Block  
**Description:** Prevents any operation that would yield \(I_j(x(t+1)) \ne I_j(x(t))\) for protected invariants.

### **3.4 Invariant correction operator**

**Label:** Repair  
**Description:** When possible, adjusts \(x(t+1)\) minimally to restore \(I_j\).

### **3.5 Invariant recovery router**

**Label:** Escalate  
**Description:** If correction fails, routes to Recovery Protocol.

---

## 4. Invariant constraints

- **Invariant preservation:**
  
  \[
  \forall j,\ I_j(x(t+1)) = I_j(x(t)) \quad \text{for valid transitions}
  \]

- **Stability compatibility:**
  
  \[
  \text{Stability ops} \subseteq \{\text{invariant‑safe ops}\}
  \]

- **No invariant bypass:**
  
  No runtime module (drift correction, stabilizers, envelope alignment) can disable or override OIPE.

---

## 5. Runtime integration

OIPE wraps:

- **Drift Correction Engine:**  
  Only corrections that preserve invariants are allowed.

- **Stabilizer Cascade:**  
  Stabilizer activations are filtered through invariant checks.

- **Envelope Alignment Engine:**  
  Boundary corrections must remain invariant‑compatible.

- **Recovery Protocol:**  
  Triggered when invariant violation is detected or imminent.

---

## 6. Operations

- **Invariant check:**
  
  \[
  x(t) \rightarrow x(t+1) \quad \text{only if all } I_j \text{ preserved}
  \]

- **Invariant‑safe correction:**
  
  \[
  x(t+1) \rightarrow x'(t+1) \quad \text{such that } I_j(x') = I_j(x(t))
  \]

- **Invariant violation detection:**
  
  Flag + route to Recovery Protocol.

---

## 7. Implementation requirements

- define and register all NDH invariants  
- instrument all runtime modules to call OIPE before committing state  
- implement minimal‑change correction for invariant restoration  
- integrate with Recovery Protocol for hard violations  
- ensure OIPE cannot be bypassed or disabled by downstream logic  

---

