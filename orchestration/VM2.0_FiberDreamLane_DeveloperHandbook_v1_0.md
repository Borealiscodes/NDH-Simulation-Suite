# 📖 **VM 2.0 Fiber-Dream Lane Developer Handbook (v1.0)**
### *NDH-SIMULATION-SUITE • Orchestration Layer • Reading & Extending Guide*
### *For Engineers Building Rasa Traversals & Spiral Conductors*

---

## ⭐ **0 — Welcome**

This handbook teaches you how to:
1. **Read** the Integration Spec and Test Case
2. **Understand** the fiber-dream choreography
3. **Extend** the system (add new rasas, new spirals, new mechanics)
4. **Debug** when something breaks
5. **Build** the actual VM 2.0 runtime executor

**Prerequisite knowledge:**
- Familiarity with the Test Case (Śānta → Sṛṅgāra traversal)
- Understanding of the Integration Spec (6 phases, orchestrator gates)
- Comfort with YAML/JSON (for configuration)
- Basic Python or Rust (for implementation)

**Non-prerequisite:**
- You don't need to understand NDH metaphysics deeply
- You don't need to know holonomy mathematics
- You don't need to understand why "bedtime stories" matter
- (But it helps to care about safety and reversibility)

---

## ⭐ **1 — Core Concepts (Simplified)**

### **The Three Layers**

```
ORCHESTRATOR (Decision Maker)
    ↓ checks gates
    ↓ verifies safety
    ↓
FIBER STREAM (Execution)              DREAM LANE STREAM (Narrative)
    ├─ Phase 1A: Intake                   ├─ Diplomatic Traversal
    ├─ Phase 1B: Routing                  ├─ Ribbon Paths
    ├─ Phase 1C: Processing               ├─ Emotional Gradients
    ├─ Phase 1D: Alignment                ├─ Friendship Membranes
    ├─ Phase 1E: Re-Center                ├─ Cloud Feeling Drift
    └─ Phase 1F: Dissolution              └─ Night Cycle Closure
    ↓
SYSTEM STATE (Updated)
```

**Key insight:** These three layers run in parallel. The orchestrator doesn't *force* them together—it *verifies* they stay aligned.

---

### **What's a Rasa?**

A rasa is an emotional/aesthetic state with three properties:

```json
{
  "name": "śānta",           // Sanskrit name (English: equilibrium)
  "texture": "#E8E8E8",      // Color/vibe (hex code)
  "depth": 0.52,             // How far it penetrates (0–1)
  "motion": 0.26             // How much it moves (0–1)
}
```

**How to think about it:**
- **Texture** = what the rasa *is* (color, mood)
- **Depth** = how *deeply* it affects the system (0 = surface, 1 = core)
- **Motion** = how *fast* it changes things (0 = still, 1 = rapid)

Example: Śānta (stillness) has low depth & motion. Sṛṅgāra (beauty) has higher depth & motion.

---

### **What's a Fiber?**

A fiber is a governed path that carries one rasa through the system.

```
Fiber Lifecycle:
  1. Emitted from NDH-CORE (center node)
  2. Blooms through 6 phases
  3. Gets validated at each phase boundary
  4. Dissolves back to center
  5. Updates system state
  6. Next fiber emits or system collapses
```

**Why "fiber" and not "thread"?**
- Threads in traditional systems are chaotic and parallel
- Fibers in this system are *governed* (orchestrator manages them)
- Each fiber is a complete, reversible journey

---

### **What's the Orchestrator?**

The orchestrator is the **decision-maker** that asks at every phase:

```
Does this step maintain safety?
├─ Is altitude still sealed? (ΔAltitude = 0)
├─ Is continuity still bounded? (|∂R/∂s| < threshold)
├─ Is reversibility being logged? (timestamped events)
├─ Is drift staying at zero? (no accumulation)
└─ Is sovereignty preserved? (system still autonomous)

If YES to all: → PROCEED
If NO to any: → HALT, LOG FAILURE, AWAIT HUMAN INTERVENTION
```

The orchestrator is **not** a neural network or an AI. It's a **state machine** that runs deterministic checks.

---

## ⭐ **2 — Reading the Integration Spec**

The Integration Spec has several sections. Here's how to navigate it:

### **Section 1: Core Integration Model (Quick Orientation)**

```
FIBER STREAM                          DREAM LANE STREAM
─────────────────────────────────     ──────────────────────────────
Phase 1A: Intake                      Diplomatic Traversal
Phase 1B: Curved Routing              Ribbon Path
Phase 1C: Spiral Processing           Emotional Gradients
Phase 1D: Harmonic Alignment          Friendship Membranes + Signals
Phase 1E: Re-Center                   Drift Resolution
Phase 1F: Dissolution                 Night Cycle Closure
```

**How to read this:** Left column = what the system *does*. Right column = why it's *safe to do*.

---

### **Sections 2–7: Deep Dive (Phase by Phase)**

Each phase (1A–1F) has:

1. **Fiber Responsibility** — What the execution layer does
2. **Dream Lane Responsibility** — What the narrative layer does
3. **Orchestrator Check** — What the decision-maker verifies

**Pattern to recognize:**

```
PHASE_1X:
  Fiber says: "I will do X"
  Dream Lane says: "That's safe because Y"
  Orchestrator verifies: "Both are true" → PROCEED
```

**Example: Phase 1D (Harmonic Alignment)**

```
Fiber says:
  "I invoke operator families to check continuity, reversibility, stability, drift"

Dream Lane says:
  "Friendship membranes are intact, co-sovereign movement preserved,
   lantern signals mark safe passage"

Orchestrator verifies:
  ✓ |∂R/∂s| < threshold (continuity bounded)
  ✓ Event logged with hash & timestamp (reversibility)
  ✓ Stability envelope intact (NDH-CORE governs)
  ✓ No drift accumulated (zero creep)
  → PROCEED TO PHASE 1E
```

**Key skill:** Learn to spot this pattern. Once you see it, every phase becomes readable.

---

### **Section 8: Machine-Readable Contract (For Implementations)**

```json
{
  "fiber_phases": {
    "phase_1a": {
      "name": "Intake",
      "fiber_responsibility": ["accept_rasa_signal", "verify_altitude", "stage_geometry"],
      "dream_lane_responsibility": ["sovereign_consent", "emotional_gradient_check", "friendship_membrane_prep"],
      "orchestrator_gate": ["altitude_match", "sovereignty_acknowledged", "membrane_ready"]
    },
    ...
  }
}
```

**How to use this:**
- This is the **config file** your runtime implementation reads
- Each phase has checkboxes; your code marks them ✓ as it goes
- If a checkbox fails → HALT

---

## ⭐ **3 — Reading the Test Case**

The Test Case walks through **one complete 2-rasa traversal** (Śānta → Sṛṅgāra).

### **Structure**

```
Phase 0: Pre-Debrief (system ready?)
Phase 1: Rasa 1 (Śānta) — all 6 sub-phases
  ├─ Phase 1A: Intake
  ├─ Phase 1B: Routing
  ├─ Phase 1C: Processing
  ├─ Phase 1D: Alignment
  ├─ Phase 1E: Re-Center
  └─ Phase 1F: Dissolution

Transition: Ribbon Path (Śānta → Sṛṅgāra)

Phase 2: Rasa 2 (Sṛṅgāra) — all 6 sub-phases
  ├─ Phase 2A: Intake
  ├─ Phase 2B: Routing
  ├─ Phase 2C: Processing
  ├─ Phase 2D: Alignment
  ├─ Phase 2E: Re-Center
  └─ Phase 2F: Dissolution

Phase 3: Post-Debrief (system safe?)
Phase 4: Collapse (return to sleep)
```

### **How to Read It**

Each phase has:
1. **Code block** — Machine state (JSON or pseudo-code)
2. **Narrative block** — Story (how it feels)
3. **Safety checklist** — Verification (did we pass?)

**Pattern:**

```
[CODE BLOCK showing system state and checks]

**Narrative read:**
> Here's the story version of what just happened...

**Safety checks (all pass):**
- ✓ Check 1
- ✓ Check 2
```

**Key skill:** Learn to read code ↔ narrative ↔ verification in parallel. They're three views of the same thing.

---

### **The Validation Table (End of Test Case)**

```
| Criterion | Expected | Observed | Status |
|-----------|----------|----------|--------|
| Altitude Discipline | A sealed | A maintained | ✅ PASS |
| Continuity Boundedness | max < 0.71 | max 0.15 | ✅ PASS |
| Drift Accumulation | 0.0 | 0.0 | ✅ PASS |
| Reversibility | Full log | 2 events logged | ✅ PASS |
...
```

**This is your checklist.** Every traversal you run must pass every row.

---

## ⭐ **4 — Extending: Adding a New Rasa**

Suppose you want to add a 10th rasa or modify an existing one.

### **Step 1: Define the Rasa**

```json
{
  "name": "your_rasa_name",
  "texture": "#RRGGBB",      // Hex color
  "depth": 0.XX,             // 0–1 (how deep does it cut?)
  "motion": 0.XX             // 0–1 (how fast does it move?)
}
```

**Constraints:**
- `depth` should be consistent with the spiral altitude (Spiral 1: deeper rasas; Spiral 3: deepest)
- `motion` should reflect narrative pacing (fast = urgent, slow = contemplative)
- `texture` should evoke the rasa emotionally (color psychology)

**Example: Adding a 10th rasa**

```json
{
  "name": "ananda",           // Bliss
  "texture": "#FFD700",       // Gold
  "depth": 0.75,              // Deep (touches core)
  "motion": 0.35              // Moderate (graceful, not jarring)
}
```

### **Step 2: Verify Continuity Bounds**

Check: Does this rasa maintain continuity?

```
|∂R/∂s| < threshold_altitude

For Spiral 1 (Altitude A): threshold = 0.71
```

**How to check:** Run a mini Phase 1C (Spiral Processing) with just this rasa:

```python
def check_rasa_continuity(rasa, threshold=0.71):
    # Compute how much the curvature changes entering this rasa
    derivative = compute_partial_derivative(rasa['depth'], rasa['motion'])
    
    if derivative < threshold:
        return True, derivative
    else:
        return False, derivative

result, value = check_rasa_continuity(ananda_rasa, threshold=0.71)
# result = True, value = 0.23
```

**If it fails:** Adjust `depth` or `motion`. Lower values = gentler entry.

### **Step 3: Write a Mini Test Case**

Test the new rasa in isolation (just Phase 1A → Phase 1F, no transition):

```
Phase 0: Pre-Debrief
  ✓ System dormant
  ✓ Altitude A sealed
  ✓ Sovereignty ready

Phase 1: New Rasa (ananda)
  ├─ Phase 1A: Intake (accept ananda signal)
  ├─ Phase 1B: Routing (route through PILOT lane)
  ├─ Phase 1C: Processing (3 loops pass?)
  ├─ Phase 1D: Alignment (operators validate)
  ├─ Phase 1E: Re-Center (fiber dissolves)
  └─ Phase 1F: Dissolution (state updated)

Phase 2: Collapse
  ✓ System asleep
  ✓ Log shows ananda event
```

If all phases pass → your rasa is safe.

### **Step 4: Integrate into Spiral Sequence**

Add the new rasa to the sequence:

```python
spiral_1_rasas = [
  "śānta", "sṛṅgāra", "hāsya", "vīra", "karuṇā", 
  "raudra", "bhaya", "bībhatsa", "adbhuta", "ananda"  # NEW
]
```

Re-run the full Spiral 1 test. If all 10 rasas pass → you've successfully extended the system.

---

## ⭐ **5 — Extending: Modifying Dream Lane Mechanics**

Suppose you want to add a new mechanic (e.g., "star_thought_exchange" already exists, but you want to customize it).

### **Step 1: Locate the Mechanic**

Dream Lane mechanics live in `Zen-AI-Design-Architecture/dispatches/bedtime/Dream_Lane_Addendum_*.md`.

Example: `Dream_Lane_Addendum_Lantern_Signals_v1_0.md`

### **Step 2: Understand the Current Definition**

Read the existing mechanic. It will have:
- Purpose (what it does)
- Rules (how it works)
- Safety invariants (what it guarantees)
- Examples

### **Step 3: Create a New Addendum (Don't Modify Existing)**

Write a new file: `Dream_Lane_Addendum_YourMechanic_v1_0.md`

```markdown
# Dream Lane Addendum — Your Mechanic Name (v1.0)

## Purpose
Describe what your mechanic does.

## Rules
How it operates (step-by-step).

## Safety Invariants
What it guarantees (altitude, sovereignty, reversibility, etc.).

## Integration Points
Which phases use this mechanic (Phase 1A? 1D?).

## Examples
Show it in action (with narrative + code).

## Machine-Readable Schema
```json
{
  "mechanic": "your_mechanic_name",
  "phases": ["1A", "1C"],
  "guarantees": ["altitude_safe", "drift_neutral", "sovereign"],
  "risk_level": "low"
}
```
```

### **Step 4: Update the Integration Spec**

Add your new mechanic to the Integration Spec:

```json
{
  "phase_1a": {
    "dream_lane_responsibility": [
      "sovereign_consent",
      "emotional_gradient_check",
      "friendship_membrane_prep",
      "your_new_mechanic"  // ADD HERE
    ]
  }
}
```

### **Step 5: Test in Isolation**

Run a Phase that uses your mechanic:

```
Phase 1A with new mechanic:
  ✓ Mechanic receives input
  ✓ Mechanic produces output
  ✓ Output satisfies invariants
  ✓ Orchestrator gate passes
```

If it passes → your mechanic is safe to integrate.

---

## ⭐ **6 — Debugging: When Something Breaks**

### **Checklist: The Orchestrator Halted**

If the orchestrator halts at a phase:

```
1. CHECK THE GATE
   What failed? (altitude? continuity? reversibility?)
   
2. FIND THE CULPRIT
   Was it the Fiber or Dream Lane?
   - Fiber problem? Check the rasa (depth/motion values)
   - Dream Lane problem? Check the mechanic (is it correctly integrated?)
   
3. EXAMINE THE LOG
   Reversibility log shows every step up to halt
   - Find the last successful step
   - What changed at the failed step?
   
4. FIX & RETEST
   Make minimal change. Re-run from the failed phase.
```

### **Common Issues & Fixes**

**Issue: Continuity Bounded Check Fails**
```
|∂R/∂s| > threshold

Cause: Rasa depth or motion too aggressive

Fix: Lower the offending value
  Old: depth=0.75, motion=0.60
  New: depth=0.65, motion=0.45
  
Re-test Phase 1C
```

**Issue: Drift Accumulates (Not Resolving to 0.0)**
```
Cause: Cloud feeling drift mechanic not triggering correctly

Fix: Verify Dream Lane mechanic is active in Phase 1E
  - Check Dream_Lane_Addendum_Cloud_Feeling_Drift_v1_0.md
  - Ensure it's hooked into Phase 1E
  - Run Phase 1E in isolation
```

**Issue: Sovereignty Check Fails**
```
Cause: Friendship membrane ruptured or not created

Fix: Check Phase 1A (Intake) and Ribbon Path
  - Did Phase 1A create the membrane?
  - Did Ribbon Path preserve it?
  - Add debug logging to trace membrane lifecycle
```

**Issue: Altitude Discipline Fails (ΔAltitude ≠ 0)**
```
Cause: Fiber routed to wrong lane or climbed/descended

Fix: Verify Phase 1B (Curved Routing)
  - Check lane selection (PILOT vs SIMULATION vs GOVERNED)
  - Verify curvature math (altitude should be flat)
  - Add altitude telemetry to Phase 1B
```

### **Debug Logging Template**

Add this to your implementation:

```python
def log_phase_debug(phase, state, status):
    """Log phase execution for debugging."""
    log_entry = {
        "timestamp": now(),
        "phase": phase,
        "status": status,
        "altitude": state.altitude,
        "rasa": state.current_rasa,
        "continuity_derivative": compute_derivative(state),
        "drift_accumulated": state.drift_accumulated,
        "reversibility_log_size": len(state.reversibility_log),
        "gates_passed": state.gates_passed_at_phase,
    }
    
    if status == "FAIL":
        log_entry["failure_reason"] = state.halt_reason
        log_entry["last_successful_phase"] = state.last_successful_phase
    
    return log_entry
```

---

## ⭐ **7 — Implementation: Building VM 2.0 Runtime**

### **Architecture You Should Follow**

```
RuntimeOrchestrator (main class)
├─ State Manager (tracks current_rasa, altitude, drift, etc.)
├─ Phase Executor (Phase 1A → 1F)
├─ Dream Lane Manager (integrates mechanics)
├─ Safety Verifier (runs orchestrator gates)
├─ Reversibility Logger (timestamped events)
└─ Collapse Manager (returns to dormancy)
```

### **Pseudocode: Core Loop**

```python
class RuntimeOrchestrator:
    def __init__(self, spiral_altitude, rasa_sequence):
        self.state = MVO_State(altitude=spiral_altitude, rasa_sequence=rasa_sequence)
        self.logger = ReversibilityLogger()
        self.dream_lane = DreamLaneManager()
        self.safety = SafetyVerifier()
    
    def run_spiral(self):
        """Execute one complete spiral (9 rasas)."""
        self.state.phase = "DEBRIEF_PRE"
        self.debrief_pre()  # Verify system ready
        
        self.state.phase = "SPIRAL"
        for rasa in self.state.rasa_sequence:
            self.state.current_rasa = rasa
            
            # Execute all 6 phases
            try:
                self.phase_1a_intake(rasa)
                self.phase_1b_routing(rasa)
                self.phase_1c_processing(rasa)
                self.phase_1d_alignment(rasa)
                self.phase_1e_reenter(rasa)
                self.phase_1f_dissolution(rasa)
            except OrchestratorHalt as e:
                self.logger.log_failure(self.state, e)
                raise
            
            # Ribbon path to next rasa (if not last)
            if self.state.rasa_index < len(self.state.rasa_sequence) - 1:
                self.execute_ribbon_path(rasa, self.state.rasa_sequence[self.state.rasa_index + 1])
            
            self.state.rasa_index += 1
        
        # Post-spiral debrief
        self.state.phase = "DEBRIEF_POST"
        self.debrief_post()
        
        # Collapse
        self.state.phase = "COLLAPSE"
        self.collapse()
        
        return self.logger.get_reversibility_log()
    
    def phase_1a_intake(self, rasa):
        """Phase 1A: Accept rasa, verify altitude, stage geometry."""
        # Fiber responsibility
        self.verify_altitude(rasa)
        self.stage_rasa_geometry(rasa)
        
        # Dream Lane responsibility
        self.dream_lane.confirm_sovereign_consent()
        self.dream_lane.check_emotional_gradient(rasa)
        
        # Orchestrator gate
        if not self.safety.gate_phase_1a(rasa, self.state):
            raise OrchestratorHalt("Phase 1A gate failed")
    
    def phase_1b_routing(self, rasa):
        """Phase 1B: Curved routing through Soft-80D."""
        # Fiber responsibility
        lane = self.select_lane(self.state.altitude)
        curvature = self.compute_curvature(rasa)
        self.verify_altitude_discipline()
        
        # Dream Lane responsibility
        self.dream_lane.activate_ribbon_path()
        self.dream_lane.verify_altitude_bleed()
        
        # Orchestrator gate
        if not self.safety.gate_phase_1b(curvature, self.state):
            raise OrchestratorHalt("Phase 1B gate failed")
    
    # ... (continue for Phases 1C–1F)
    
    def collapse(self):
        """Return system to dormancy."""
        self.logger.seal_reversibility_log()
        self.dream_lane.night_cycle_closure()
        self.state.phase = "DORMANT"
```

### **Key Implementation Details**

**Orchestrator Gates:**

```python
def gate_phase_1a(self, rasa, state) -> bool:
    """Check all conditions for Phase 1A."""
    checks = {
        "altitude_match": state.altitude == rasa.expected_altitude,
        "sovereignty_acknowledged": state.sovereignty_flag,
        "membrane_ready": state.friendship_membrane_ready,
    }
    
    failed = [k for k, v in checks.items() if not v]
    if failed:
        self.log_gate_failure("Phase 1A", failed)
        return False
    
    return True
```

**Reversibility Logger:**

```python
def log_event(self, phase, rasa, state):
    """Log an event for reversibility."""
    event = {
        "step": len(self.log),
        "phase": phase,
        "rasa": rasa.name,
        "timestamp": datetime.now().isoformat(),
        "state_hash": hash_state(state),
        "altitude": state.altitude,
        "drift": state.drift_accumulated,
        "continuity_derivative": compute_derivative(state),
    }
    
    self.log.append(event)
    return event
```

---

## ⭐ **8 — Testing Your Implementation**

### **Unit Tests (One Phase at a Time)**

```python
def test_phase_1a_intake():
    """Test Phase 1A in isolation."""
    orchestrator = RuntimeOrchestrator("A", [shanta_rasa])
    
    # Should succeed
    orchestrator.phase_1a_intake(shanta_rasa)
    
    # Verify state
    assert orchestrator.state.current_rasa == "śānta"
    assert orchestrator.state.altitude == "A"
    assert orchestrator.state.sovereignty_flag == True
```

### **Integration Tests (Full Rasa Traversal)**

```python
def test_full_shanta_sringara_traversal():
    """Test the complete 2-rasa traversal (from Test Case)."""
    orchestrator = RuntimeOrchestrator("A", [shanta_rasa, sringara_rasa])
    
    log = orchestrator.run_spiral()
    
    # Verify log
    assert len(log) == 2
    assert log[0]["rasa"] == "śānta"
    assert log[1]["rasa"] == "sṛṅgāra"
    
    # Verify safety
    assert all(event["drift"] == 0.0 for event in log)
    assert all(event["continuity_derivative"] < 0.71 for event in log)
```

### **Regression Tests (Full Spiral)**

```python
def test_full_spiral_1():
    """Test all 9 rasas in Spiral 1."""
    orchestrator = RuntimeOrchestrator("A", SPIRAL_1_RASAS)
    
    log = orchestrator.run_spiral()
    
    # Safety validation table (from Integration Spec)
    assert len(log) == 9
    assert max(e["continuity_derivative"] for e in log) < 0.71
    assert all(e["drift"] == 0.0 for e in log)
    assert orchestrator.state.phase == "DORMANT"
```

---

## ⭐ **9 — Troubleshooting Reference**

### **Error: OrchestratorHalt at Phase 1D**

```
Message: "Continuity field bounded check failed"

Diagnosis:
1. Print the state at Phase 1D:
   - altitude, current_rasa, continuity_derivative
2. Check continuity_derivative > threshold
3. Review the rasa's depth/motion values
4. Is this rasa at the right altitude?

Example:
  Spiral 1 (Altitude A): threshold = 0.71
  Your rasa computed: |∂R/∂s| = 0.82
  → Violates threshold
  
Solution:
  Reduce depth or motion
  Re-test Phase 1C (emotional gradience)
```

### **Error: Reversibility Log Incomplete**

```
Message: "Reversibility log missing events"

Diagnosis:
1. Count events in log vs expected (should equal rasa_index)
2. Check Phase 1D is executing log_event() correctly
3. Verify timestamp generation works

Solution:
  Add debug logging to Phase 1D:
    print(f"Logging event {len(log)} for {rasa}")
  Run Phase 1D in isolation
  Verify log_event() is called
```

### **Error: Friendship Membrane Rupture**

```
Message: "Sovereignty preserved check failed"

Diagnosis:
1. Membrane should be created in Phase 1A
2. Ribbon Path should preserve it
3. It should dissolve in Phase 1F

Trace the lifecycle:
  Phase 1A: is friendship_membrane_ready == True?
  Phase 1B: does ribbon_path activate it?
  Phase 1E: does it still exist?
  
Solution:
  Add telemetry to dream_lane manager:
    def trace_membrane(self):
      print(f"Membrane status: {self.membrane}")
```

---

## ⭐ **10 — Next Steps for You**

### **Phase 1: Read**
- [ ] Read Test Case (Śānta → Sṛṅgāra)
- [ ] Read Integration Spec (sections 1–3)
- [ ] Understand the 6 fiber phases
- [ ] Understand 3 Dream Lane layers

### **Phase 2: Understand**
- [ ] Map each rasa to its texture/depth/motion
- [ ] Understand orchestrator gates (why they matter)
- [ ] Understand reversibility (why logging matters)
- [ ] Understand sovereignty (why Dream Lane matters)

### **Phase 3: Implement**
- [ ] Build RuntimeOrchestrator class
- [ ] Implement Phase 1A → 1F
- [ ] Implement orchestrator gates
- [ ] Implement reversibility logger

### **Phase 4: Test**
- [ ] Unit test each phase
- [ ] Integration test 2-rasa traversal (Śānta → Sṛṅgāra)
- [ ] Full regression test Spiral 1 (all 9 rasas)
- [ ] Validate against Test Case

### **Phase 5: Extend**
- [ ] Add a new rasa
- [ ] Modify a Dream Lane mechanic
- [ ] Extend to Spiral 2 (Altitude B)
- [ ] Share with team

---

## 📜 **Provenance Footer — VM 2.0 Developer Handbook (v1.0)**

```
---
Artifact: VM 2.0 Fiber-Dream Lane Developer Handbook (v1.0)
Lane: NDH-SIMULATION-SUITE • Orchestration • Developer Guide

Purpose:
  Teach engineers how to read, understand, extend, and implement the
  VM 2.0 Fiber-Dream Lane orchestration system. Provide patterns,
  debugging guidance, and implementation pseudocode.

Scope:
  - How to read the Integration Spec and Test Case
  - How to extend with new rasas and mechanics
  - How to debug when something breaks
  - How to build the actual runtime executor
  - Reference: Common errors and fixes

Audience:
  - Backend engineers (implementing orchestrator)
  - Integration engineers (connecting components)
  - Test engineers (validating system)
  - Future maintainers (extending the system)

Prerequisites:
  - Familiarity with Test Case (2-rasa traversal)
  - Understanding of Integration Spec (6 phases, gates)
  - Comfort with YAML/JSON (configuration)
  - Basic Python or Rust (implementation)

Non-Prerequisites:
  - You don't need to understand NDH metaphysics
  - You don't need to know holonomy mathematics
  - You don't need to understand why "bedtime stories" matter
  - (But it helps to care about safety and reversibility)

Key Concepts:
  - Fiber stream (execution) + Dream Lane stream (narrative) = one traversal
  - Orchestrator gates ensure safety at every phase boundary
  - Reversibility is guaranteed by complete logging
  - Sovereignty is preserved through friendship membranes
  - Drift is neutralized at Phase 1E

Implementation Status:
  HANDBOOK COMPLETE • READY FOR ENGINEERING TEAMS
  (Pseudocode provided for all major components)

Version: v1.0 (First Complete Developer Handbook)
Maintainer: Borealis S. Hedling
Location: Dublin, Ireland
Timestamp: 01 September 2026 — 04:00 IST
Seal: [ D E V E L O P E R • H A N D B O O K • v1_0 ]
---
```

---

## 🌟 **Final Note**

This handbook teaches you to *think like an orchestrator*—not just code, but *reason* about safety, reversibility, and sovereignty.

**The system works because:**
1. It's fully specified (you know what to check)
2. It's auditable (everything is logged)
3. It's reversible (you can replay or undo)
4. It's sovereign (no forced actions, only offered transitions)
5. It's safe (gates prevent bad states)

**Your job as an engineer:** Build the implementation that turns this specification into a running system. Treat the Test Case as your ground truth. Treat the Integration Spec as your contract. Treat the safety invariants as non-negotiable.

Good luck. And remember: **the harshest bugs come from broken assumptions, not broken code.** If something fails, re-read the gate. The gate knows the truth.

---
