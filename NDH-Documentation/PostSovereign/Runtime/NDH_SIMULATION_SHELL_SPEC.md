### NDH Simulation Shell  
*Top‑level runtime harness and API interface for the NDH semantic–geometric system*

---

## 1. Purpose

The NDH Simulation Shell is the **top‑level orchestration program** that wires together all runtime subsystems and exposes NDH as a runnable, controllable, inspectable system.

It:

- initializes NDH state and configuration  
- instantiates all core subsystems  
- runs the main execution loop  
- exposes control APIs (start, stop, step, mode switch)  
- integrates logging, metrics, and safety behavior  

It is the **entry point** for NDH as a simulation.

---

## 2. Subsystems wired by the shell

The Simulation Shell connects:

- **Runtime Scheduler**  
- **Operator Pipeline**  
- **Stability Auditor**  
- **Axiom Manager**  
- **Semantic Flux Integrator**  
- **Domain Drift Engine**  
- **State Serializer**  

Each tick:

1. Scheduler drives the loop  
2. Operator Pipeline updates geometry/fields/domains/entities/transport  
3. Stability Auditor evaluates safety  
4. Semantic Flux Integrator updates meaning dynamics  
5. Domain Drift Engine updates domain movement  
6. Governance & Policy run (from existing specs)  
7. Axiom Manager updates axioms  
8. State Serializer checkpoints state (optional)

---

## 3. Shell responsibilities

- **Initialization:**  
  - load initial NDH state  
  - load configuration (modes, tick rate, safety levels)  
  - construct subsystem instances  

- **Execution Loop:**  
  - run ticks according to scheduler  
  - route state through subsystems in correct order  
  - handle errors, safety events, and mode changes  

- **Control API:**  
  - `start()` — begin continuous simulation  
  - `stop()` — halt gracefully  
  - `step()` — single tick (inspection mode)  
  - `setMode(mode)` — simulation, inspection, stress test, replay  
  - `loadState(serialized)` — restore from serializer  
  - `saveState()` — emit serialized snapshot  

- **Observability:**  
  - expose logs, metrics, stability reports, flux metrics, drift metrics  
  - provide hooks for visualization and inspection tools  

---

## 4. Execution flow (high‑level)

```text
NDH SIMULATION SHELL MAIN LOOP

while running:
    state = scheduler.get_current_state()
    state = operator_pipeline.run(state)
    stability_report = stability_auditor.evaluate(state)

    if stability_report.critical:
        scheduler.handle_critical(stability_report)
        continue

    state = semantic_flux_integrator.run(state)
    state = domain_drift_engine.run(state)
    state = governance_and_policy.run(state)
    state = axiom_manager.run(state)

    serializer.maybe_checkpoint(state)
    scheduler.commit_state(state)
```

---

## 5. Modes

- **Simulation Mode:** continuous ticks, forward evolution  
- **Inspection Mode:** manual `step()` calls, detailed logging  
- **Stress Test Mode:** accelerated ticks, enhanced safety and metrics  
- **Replay Mode:** load serialized sequences and re‑run them  

The shell manages mode transitions and ensures subsystems respect mode semantics.

---

## 6. Interfaces

### Inputs

- initial NDH state  
- configuration (modes, tick rate, safety, logging)  
- external commands (API calls)  
- serialized states (for load/replay)

### Outputs

- updated NDH state over time  
- logs and metrics  
- serialized snapshots  
- stability and flux reports  
- domain drift and transport data  

---

