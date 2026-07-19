### NDH Runtime Scheduler  
*Core timing and orchestration engine for NDH’s semantic–geometric runtime*

---

## 1. Purpose

The NDH Runtime Scheduler is the **orchestration layer** that controls:

- when the kernel runs  
- in what order phases execute  
- how often the state is updated  
- how subsystems (operators, auditors, managers) are invoked  

It is the “clock” and “conductor” of NDH’s execution architecture.

---

## 2. Scheduler responsibilities

- **Tick management:** define and manage discrete simulation steps  
- **Phase ordering:** enforce the 10‑phase kernel sequence  
- **Subsystem invocation:** call operator pipeline, stability auditor, axiom manager, etc.  
- **Priority handling:** decide which subsystems run when resources are constrained  
- **Mode control:** support different runtime modes (simulation, analysis, stress test, replay)  
- **Logging hooks:** expose events for observability and debugging  
- **Safety hooks:** integrate stability and governance checks before committing state  

---

## 3. Core concepts

### **3.1. Tick**

A **tick** is one NDH step:

- reads current state  
- runs the kernel phases in order  
- produces a new state  

Ticks can be:

- **fixed‑step** (constant interval)  
- **adaptive‑step** (shorter or longer based on activity)  
- **event‑driven** (triggered by external input)

### **3.2. Modes**

- **Simulation Mode:** continuous stepping, forward evolution  
- **Inspection Mode:** single‑step, manual control  
- **Stress Test Mode:** accelerated stepping with enhanced logging  
- **Replay Mode:** re‑run recorded state sequences  

---

## 4. Phase orchestration

The scheduler enforces the kernel’s 10 phases in order:

1. Geometry update  
2. Field evolution  
3. Domain update  
4. Entity update  
5. Interaction & transport  
6. Stability audit  
7. Governance update  
8. Policy evaluation  
9. Action dispatch  
10. Axiom update  

For each tick, the scheduler:

- calls the **Operator Pipeline** to execute phases 1–5  
- calls the **Stability Auditor** for phase 6  
- calls **Governance Geometry** and **Policy Engine** for phases 7–8  
- calls the **Action Dispatcher** (part of the operator pipeline) for phase 9  
- calls the **Axiom Manager** for phase 10  

---

## 5. Interfaces

### **5.1. Inputs**

- current NDH state  
- runtime configuration (mode, tick rate, limits)  
- external events (user commands, injected scenarios, stress test triggers)

### **5.2. Outputs**

- new NDH state  
- event log (per tick)  
- metrics (tick duration, subsystem timings, stability indicators)  
- alerts (critical instability, governance failure, paradox storms)

---

## 6. Configuration

Key configuration parameters:

- **tick_interval:** base time between steps (in simulation time units)  
- **max_tick_duration:** maximum allowed real‑time per tick  
- **mode:** simulation, inspection, stress test, replay  
- **logging_level:** minimal, normal, verbose, diagnostic  
- **safety_strictness:** conservative, normal, experimental  

---

## 7. Safety integration

Before committing a new state, the scheduler:

- checks stability audit results  
- checks governance coherence  
- checks policy outcomes for fail‑closed behavior  
- can **reject** or **roll back** a tick if conditions violate safety thresholds  

This makes the scheduler a **gatekeeper** for NDH’s evolution.

---

## 8. Lifecycle

Typical lifecycle:

1. **Initialize:** load initial state and configuration  
2. **Run:** perform ticks according to mode and interval  
3. **Monitor:** collect metrics and logs  
4. **Adapt:** adjust tick behavior based on activity or commands  
5. **Stop:** gracefully halt, persist state, and close resources  

---

