### NDH Runtime Metrics & Logging Layer  
*Observability, diagnostics, and replay backbone for the NDH runtime*

---

## 1. Purpose

The NDH Runtime Metrics & Logging Layer provides **full observability** into the NDH simulation:

- per‑tick metrics  
- subsystem timings  
- stability and flux indicators  
- drift and transport statistics  
- structured logs for events, warnings, and failures  
- replay buffers for post‑hoc analysis  

It is the **diagnostic and introspection system** of NDH.

---

## 2. Responsibilities

This layer:

- collects metrics from all core subsystems:  
  - Runtime Scheduler  
  - Operator Pipeline  
  - Stability Auditor  
  - Axiom Manager  
  - Semantic Flux Integrator  
  - Domain Drift Engine  
  - Transport Dynamics API  
  - State Serializer  
- records structured logs for:  
  - critical events  
  - safety violations  
  - mode changes  
  - transport operations  
  - collapse events  
- exposes data to visualization and analysis tools  
- maintains replay buffers for selected runs  

---

## 3. Metrics

Key metric families:

- **Tick Metrics:** duration, mode, success/failure, rollback events  
- **Subsystem Timings:** per‑component execution time  
- **Stability Metrics:** global stability score, per‑domain scores, critical region count  
- **Flux Metrics:** semantic flux intensity, overload events, damping/amplification rates  
- **Drift Metrics:** domain drift velocity, boundary deformation, collapse propagation rate  
- **Transport Metrics:** corridor utilization, channel usage, front propagation speed  
- **Axiom Metrics:** axiom birth/fusion/split counts, drift rate, rupture warnings  

---

## 4. Logging

Structured logs include:

- **Event Logs:** tick start/end, mode changes, subsystem invocations  
- **Warning Logs:** approaching thresholds, marginal stability, high flux, high drift  
- **Error Logs:** critical instability, transport failure, serialization integrity failure  
- **Action Logs:** governance decisions, policy outcomes, axiom changes, domain transitions  

Logs are timestamped (simulation time), tagged by subsystem, and grouped by tick.

---

## 5. Replay Buffers

The layer maintains replay buffers:

- per‑tick snapshots of key metrics  
- event sequences  
- selected state summaries (not full state; that’s the serializer’s job)  

These buffers support:

- post‑hoc analysis  
- debugging  
- visualization  
- narrative reconstruction of NDH runs  

---

## 6. Interfaces

### Inputs

- metrics and events from all subsystems  
- configuration (logging level, buffer size, retention policy)  

### Outputs

- metrics streams  
- log streams  
- replay buffers  
- diagnostic reports  

---

## 7. Configuration

Key parameters:

- **logging_level:** minimal, normal, verbose, diagnostic  
- **metrics_granularity:** coarse, normal, fine  
- **replay_buffer_size:** number of ticks retained  
- **retention_policy:** time‑based or run‑based  
- **export_mode:** local, external, visualization‑ready  

---

