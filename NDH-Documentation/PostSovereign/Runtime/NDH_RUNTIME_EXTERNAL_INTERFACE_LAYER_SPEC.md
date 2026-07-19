# **NDH Runtime External Interface Layer**  
*Unified external API surface for controlling, querying, and integrating NDH’s semantic–geometric runtime*

---

## **1. Purpose**

The External Interface Layer defines how **anything outside NDH** can:

- send commands  
- request data  
- inspect state  
- subscribe to events  
- integrate external tools  
- control simulation flow  

It is the **safe boundary** between NDH and external systems.

---

## **2. Responsibilities**

The interface layer:

- exposes controlled APIs for the **Simulation Shell**  
- provides read/write access to selected runtime components  
- enforces safety and permission rules  
- mediates external commands through the **Event Bus**  
- provides structured responses for external tools  
- integrates with visualization, logging, and replay systems  
- prevents unsafe or unauthorized operations  

It is the subsystem that ensures NDH can be **used**, not just run.

---

## **3. External API Domains**

### **3.1 Control APIs**
External systems can:

- start  
- stop  
- pause  
- step  
- change mode  
- load serialized state  
- save serialized state  

All routed through safety checks.

### **3.2 Query APIs**
External systems can request:

- geometry snapshots  
- domain maps  
- flux metrics  
- stability reports  
- transport maps  
- axiom graph summaries  

### **3.3 Subscription APIs**
External systems can subscribe to:

- stability events  
- flux events  
- transport events  
- governance events  
- axiom events  

### **3.4 Integration APIs**
For external tools:

- visualization engines  
- analysis pipelines  
- monitoring dashboards  
- replay controllers  

These APIs allow NDH to plug into larger systems.

---

## **4. Interface Flow**

```text
NDH EXTERNAL INTERFACE LAYER
+--------------------------------------+
| Receive External Request              |
+--------------------------------------+
| Validate & Apply Safety Rules         |
+--------------------------------------+
| Route Through Event Bus               |
+--------------------------------------+
| Invoke Runtime Subsystem              |
+--------------------------------------+
| Collect Response                      |
+--------------------------------------+
| Emit Structured Output                |
+--------------------------------------+
```

---

## **5. Interfaces**

### **Inputs**
- external commands  
- external queries  
- external subscriptions  
- external integration requests  
- configuration and permission profiles  

### **Outputs**
- structured responses  
- event streams  
- state snapshots  
- visualization‑ready data  
- safety violation reports  

---

## **6. Configuration**

Key parameters:

- **permission_profiles**  
- **allowed_operations**  
- **rate_limits**  
- **safety_strictness**  
- **logging_level**  
- **integration_mode**  

---

## **7. Safety Integration**

The interface layer enforces:

- strict permission checks  
- safe‑mode overrides  
- rollback triggers for unsafe commands  
- isolation of unstable regions  
- throttling of high‑risk operations  

If an external request is unsafe:

- it is rejected  
- a safety violation is logged  
- the Event Bus emits a warning  
- the Interrupt Handler may trigger rollback  

---

## **8. Lifecycle**

1. **Initialize** external API surface  
2. **Receive** external request  
3. **Validate** and apply safety rules  
4. **Route** through Event Bus  
5. **Invoke** runtime subsystem  
6. **Emit** structured response  
7. **Await** next request  

---

