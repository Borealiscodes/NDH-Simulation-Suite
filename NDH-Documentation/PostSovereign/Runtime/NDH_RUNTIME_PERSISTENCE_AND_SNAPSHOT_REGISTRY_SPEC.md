### NDH Runtime Persistence & Snapshot Registry  
*Memory palace and state archive for the NDH runtime*

---

## 1. Purpose

The NDH Runtime Persistence & Snapshot Registry manages **named, versioned, and archived states** of the NDH simulation over time.  
It provides:

- long‑term storage of important NDH states  
- named snapshots and checkpoints  
- versioned simulation runs  
- multi‑branch histories (forked timelines)  
- cross‑session continuity  

It is the **memory palace** of NDH.

---

## 2. Responsibilities

The registry:

- coordinates with the **State Serializer** to store and retrieve serialized states  
- maintains a catalog of snapshots, runs, and branches  
- tracks metadata (time, mode, profile, tags, notes) for each snapshot  
- supports branching from previous states (forked simulations)  
- enforces retention and archival policies  
- exposes APIs for listing, tagging, loading, and deleting snapshots  

---

## 3. Snapshot Model

Each snapshot includes:

- serialized NDH state (via serializer)  
- unique ID and human‑readable name  
- timestamp (simulation and wall‑clock, if desired)  
- mode and safety profile at capture time  
- tags (e.g., `pre-collapse`, `lab-run-42`, `demo-state`)  
- optional notes or annotations  

Simulation runs can be:

- linear sequences of snapshots  
- branched timelines (tree of runs)  

---

## 4. Registry Operations

Core operations:

- **createSnapshot(name, tags, notes)**  
- **listSnapshots(filter)**  
- **getSnapshot(id or name)**  
- **loadSnapshot(id or name)**  
- **deleteSnapshot(id or name)**  
- **createBranch(fromSnapshotId, newRunName)**  
- **listRuns()** and **inspectRun(runId)**  

These operations integrate with the Simulation Shell and Serializer.

---

## 5. Interfaces

### Inputs

- serialized states from the State Serializer  
- snapshot creation requests  
- query and listing requests  
- load and delete requests  
- configuration (retention, archival, naming rules)

### Outputs

- stored snapshots and runs  
- snapshot metadata and catalogs  
- loaded states for replay or continuation  
- archival and deletion reports  

---

## 6. Configuration

Key parameters:

- **retention_policy** (by age, count, or importance)  
- **archival_policy** (cold storage, compression level)  
- **naming_conventions**  
- **branching_rules**  
- **logging_level**  

---

