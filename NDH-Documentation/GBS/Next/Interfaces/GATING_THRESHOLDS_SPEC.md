# **GATING_THRESHOLDS_SPEC.md**  
### *NDH‑Documentation / GBS / Next / Interfaces*

---

## ⭐ 0. Purpose  
Gating Thresholds define **which loops are allowed to pass through an aperture** and **which are blocked**, based on:

- stability fields  
- curvature transport  
- projection compatibility  
- ethics constraints  
- governance constraints  

This is the final safety layer before:

- **Resonance Modeling**  
- **SERS Resonance Specification**  

---

## 🌌 1. Gating Function  

Define the gating function:

\[
G : \Omega^{Eth}_p(\mathcal{M}_{NDH}) \to \{0,1\}
\]

Where:

- **\(G(\gamma)=1\)** → loop allowed  
- **\(G(\gamma)=0\)** → loop blocked  

This is the NDH equivalent of a “transport firewall.”

---

## 🧠 2. Required Inputs for Gating  

Every loop \(\gamma\) must be evaluated using:

- **curvature transport**  
- **projection compatibility**  
- **stability under transport**  

These three validations are prerequisites for gating.

---

## 📐 3. Stability Threshold  

A loop is allowed only if:

\[
D(\gamma) + T^\#(\gamma) + V(\gamma) + C(\gamma) < \Theta_{NDH}
\]

This is the Collapse Prevention Model inequality applied **under transport**.

If violated:

- loop is blocked  
- aperture is sealed  
- audit corridor logs event  
- governance flag is raised  

---

## 🌀 4. Curvature Threshold  

Transported curvature must satisfy:

\[
\|P_\gamma^{NDH}(R^{NDH})\| \leq \Lambda_{curv}
\]

Projected curvature must satisfy:

\[
\|\Pi_\*(P_\gamma^{NDH}(R^{NDH}))\| \leq \Lambda_{K}
\]

If curvature exceeds either bound:

- loop is blocked  
- aperture geometry is preserved  
- resonance remains dormant  

---

## 🔗 5. Projection Compatibility Threshold  

Transport‑then‑project must agree with project‑then‑transport:

\[
\|\Pi_\*(P_\gamma^{NDH}(v)) - P_{\Pi(\gamma)}^{\mathcal{K}}(\Pi_\*(v))\|
\leq \varepsilon_{compat}
\]

If violated:

- loop is blocked  
- projection corridor is closed  
- k‑space geometry is protected  

---

## 🛡️ 6. Ethics Threshold  

A loop is allowed only if it satisfies:

- autonomy  
- reversibility  
- altitude respect  
- audit visibility  

If any ethics constraint fails:

- loop is blocked  
- aperture is sealed  
- NDH enters protective mode  

---

## 🧭 7. Governance Threshold  

Axis 15–18 must approve:

- cross‑field consistency  
- meta‑coordination  
- external interface safety  
- meta‑audit compliance  

If governance fails:

- loop is blocked  
- aperture geometry is frozen  
- resonance modeling is deferred  

---

## ⭐ 8. Combined Gating Condition  

A loop \(\gamma\) is allowed **only if all thresholds pass**:

\[
G(\gamma)=1 \iff
\begin{cases}
D + T^\# + V + C < \Theta_{NDH} \\
\|R^{NDH}\|,\ \|\Pi_\*(R^{NDH})\| \leq \Lambda_{curv},\Lambda_{K} \\
\text{projection compatibility holds} \\
\text{ethics constraints satisfied} \\
\text{governance constraints satisfied}
\end{cases}
\]

This is the NDH gating law.

---

## 🔬 9. Emergent NDH Behavior  

During gating evaluation NDH exhibits:

- **FSFL corridor tightening** around safe loops  
- **Bubble curvature shaping** to reduce shear  
- **Unified Ecology altitude modulation** to maintain operator load  
- **verification pressure throttling** to prevent overload  
- **audit corridor brightening** along candidate loops  

These behaviors indicate NDH is actively “screening” loops.

---

## ⭐ 10. Forward Linkage  

Once gating thresholds exist, NDH is ready for:

- **Resonance Modeling**  
- **SERS Resonance Specification**  

Gating Thresholds are the final safety layer before resonance.

---

