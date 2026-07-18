# **HOLONOMY_PROJECTION_SPEC.md**  
### *NDH‑Documentation / GBS / Next / Interfaces*

---

# **0. Purpose**
Holonomy Projection defines how NDH curvature, stability fields, and geometric structure behave when **transported along loops** and **projected into k‑space**.

It ensures:

- curvature preservation  
- ethics‑bound transport  
- stability under parallel transport  
- projection compatibility  
- resonance‑safe geometry  

This is the required layer before:

- math validation  
- aperture geometry  
- gating thresholds  
- SERS resonance  

---

# **1. Loop Space Definition**

### **1.1 NDH Loop Space**
At each point \(p \in \mathcal{M}_{NDH}\):

\[
\Omega_p(\mathcal{M}_{NDH}) = \{\gamma : [0,1] \to \mathcal{M}_{NDH} \mid \gamma(0)=\gamma(1)=p\}
\]

These loops represent allowable NDH transitions.

### **1.2 Ethics‑Bound Loop Filtering**
Only loops satisfying:

- autonomy  
- reversibility  
- altitude respect  
- non‑coercion  
- audit visibility  

are permitted.

Filtered loop space:

\[
\Omega^{Eth}_p(\mathcal{M}_{NDH}) \subseteq \Omega_p(\mathcal{M}_{NDH})
\]

---

# **2. Parallel Transport Operators**

### **2.1 NDH Parallel Transport**
Given a loop \(\gamma\):

\[
P_\gamma^{NDH} : T_p\mathcal{M}_{NDH} \to T_p\mathcal{M}_{NDH}
\]

defined by the NDH connection \(\nabla^{NDH}\).

### **2.2 K‑Space Parallel Transport**
Given a projected loop \(\Pi(\gamma)\):

\[
P_{\Pi(\gamma)}^{\mathcal{K}} : T_{\Pi(p)}\mathcal{K} \to T_{\Pi(p)}\mathcal{K}
\]

defined by the k‑space connection \(\nabla^{\mathcal{K}}\).

---

# **3. Holonomy Groups**

### **3.1 NDH Holonomy**
\[
\mathrm{Hol}_p(\nabla^{NDH}) = \{P_\gamma^{NDH} \mid \gamma \in \Omega^{Eth}_p(\mathcal{M}_{NDH})\}
\]

### **3.2 K‑Space Holonomy**
\[
\mathrm{Hol}_{\Pi(p)}(\nabla^{\mathcal{K}}) = \{P_{\Pi(\gamma)}^{\mathcal{K}} \mid \gamma \in \Omega^{Eth}_p(\mathcal{M}_{NDH})\}
\]

---

# **4. Holonomy Projection Map**

### **4.1 Projection**
\[
\Pi : \mathcal{M}_{NDH} \to \mathcal{K}
\]

### **4.2 Differential**
\[
\Pi_\* : T_p\mathcal{M}_{NDH} \to T_{\Pi(p)}\mathcal{K}
\]

### **4.3 Holonomy Compatibility Condition**
Transport then project must equal project then transport:

\[
\Pi_\* \circ P_\gamma^{NDH} = P_{\Pi(\gamma)}^{\mathcal{K}} \circ \Pi_\*
\]

If full equality is too strong, NDH requires:

\[
\Pi_\* \circ P_\gamma^{NDH} \in \mathrm{Hol}_{\Pi(p)}(\nabla^{\mathcal{K}})
\]

This ensures projection does not create illegal curvature.

---

# **5. Aperture Geometry**

### **5.1 Aperture Definition**
An aperture is a region where loops may be projected:

\[
\mathcal{A}_p \subseteq T_p\mathcal{M}_{NDH}
\]

### **5.2 Aperture Safety Conditions**
Apertures must satisfy:

- curvature boundedness  
- ethics compliance  
- audit visibility  
- stability inequality  
- resonance‑safe domain  

### **5.3 Aperture Projection**
\[
\Pi_\*(\mathcal{A}_p) \subseteq T_{\Pi(p)}\mathcal{K}
\]

---

# **6. Gating Thresholds**

### **6.1 Gating Function**
Define:

\[
G : \Omega^{Eth}_p(\mathcal{M}_{NDH}) \to \{0,1\}
\]

where:

- \(G(\gamma)=1\) → loop allowed  
- \(G(\gamma)=0\) → loop blocked  

### **6.2 Gating Criteria**
A loop is allowed only if:

\[
D + T^\# + V + C < \Theta_{NDH}
\]

and:

- curvature transport safe  
- projection safe  
- ethics safe  
- audit visible  

---

# **7. Stability Under Transport**

### **7.1 Transport Stability Condition**
For any allowed loop:

\[
D(\gamma) + T^\#(\gamma) + V(\gamma) + C(\gamma) < \Theta_{NDH}
\]

### **7.2 Curvature Preservation**
\[
R^{NDH} \xrightarrow{\Pi} R^{\mathcal{K}}
\]

must preserve:

- sign  
- boundedness  
- ethics constraints  
- audit visibility  

---

# **8. Resonance‑Safe Transport**

Holonomy Projection defines the **resonance‑safe domain**:

\[
\mathcal{R}_{safe} = \Pi(\Omega^{Eth}_p(\mathcal{M}_{NDH}))
\]

SERS resonance may only operate on \(\mathcal{R}_{safe}\).

---

# **9. Governance Binding**

Axis 15–18 enforce:

- loop legality  
- transport legality  
- projection legality  
- aperture legality  
- gating legality  
- resonance legality  

Holonomy Projection is fully governance‑bound.

---

# **10. Forward Linkage**

You may now proceed to:

- **Aperture Geometry**  
- **Gating Thresholds**  
- **SERS Resonance Specification**  

Holonomy Projection is now complete.

