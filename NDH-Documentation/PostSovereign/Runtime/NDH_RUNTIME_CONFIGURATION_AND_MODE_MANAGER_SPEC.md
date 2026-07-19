### NDH Runtime Configuration & Mode Manager  
*Central settings, modes, and safety profile controller for the NDH runtime*

---

## 1. Purpose

The NDH Runtime Configuration & Mode Manager governs **how** NDH runs:

- which mode it’s in  
- what safety profile applies  
- what tick rate and logging level are used  
- which subsystems are enabled or throttled  

It is the **settings and mode brain** of the NDH runtime.

---

## 2. Responsibilities

The manager:

- loads initial configuration (from file, environment, or API)  
- defines and manages runtime modes:  
  - simulation  
  - inspection  
  - stress test  
  - replay  
- applies safety profiles (conservative, normal, experimental)  
- adjusts tick rate, logging level, and subsystem behavior  
- exposes APIs for dynamic reconfiguration during a run  
- coordinates with the Simulation Shell and Scheduler when modes change  

---

## 3. Modes

### **Simulation Mode**
- continuous ticks  
- normal safety thresholds  
- standard logging  

### **Inspection Mode**
- manual `step()` control  
- high logging and metrics  
- ideal for debugging and analysis  

### **Stress Test Mode**
- accelerated ticks  
- strict safety thresholds  
- verbose metrics and logging  

### **Replay Mode**
- uses serialized state sequences  
- no “live” evolution, only re‑execution  
- ideal for post‑hoc analysis and visualization  

---

## 4. Configuration Model

Key configuration domains:

- **Timing:** tick interval, max tick duration  
- **Safety:** stability thresholds, flux limits, transport limits  
- **Logging:** logging level, metrics granularity, replay buffer size  
- **Subsystems:** enable/disable or throttle specific components  
- **Profiles:** named bundles (e.g., `default`, `lab_stress`, `safe_demo`)  

The manager maintains a **current profile** and allows switching at runtime.

---

## 5. Interfaces

### Inputs

- configuration files or objects  
- mode change requests (`setMode(mode)`)  
- profile change requests (`setProfile(name)`)  
- safety strictness adjustments  

### Outputs

- effective configuration applied to subsystems  
- mode change events (to Event Bus)  
- configuration change logs  
- safety profile summaries  

---

## 6. Integration

The manager coordinates with:

- **Simulation Shell:** to enforce mode semantics  
- **Runtime Scheduler:** to adjust tick behavior  
- **Metrics & Logging Layer:** to change logging levels  
- **Event Bus:** to broadcast mode/config changes  
- **State Serializer:** for replay mode and safe transitions  

---

