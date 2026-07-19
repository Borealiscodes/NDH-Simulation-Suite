### NDH Simulation & Rendering Pipeline Spec  
*A systems layer for executing NDH dynamics and visualizing NDH geometry*

---

## 1. Purpose and scope

The NDH Simulation & Rendering Pipeline Spec defines how NDH’s formal theory stack—Foundations, Dynamics, Algebra, Surreal Logic, Category Skeleton, and Rendering Geometry—is turned into an **executable simulation architecture** and a **coherent visual output pipeline**.

It covers:

- simulation state representation  
- time‑stepping and integrators  
- field update order  
- logic and cuil evaluation  
- geometry extraction  
- rendering stages and passes  

---

## 2. Simulation state

### 2.1 Core state object

- **Label:** NDH simulation state  
- A simulation state \(S_t\) at time \(t\) consists of:

  \[
  S_t = \big(\sigma_t, \mathcal{R}_t, \lambda_t, \mathcal{P}_t, E_t, A_t\big)
  \]

  defined over \(\mathcal{M}_{50}\), plus:

  - **cuil level field** \(k_t(x)\)  
  - **category object mapping** (current object in \(\mathcal{C}_{NDH}\))

---

## 3. Time evolution

### 3.1 Integrator

- **Label:** time‑stepping  
- NDH uses a continuous evolution operator \(\Phi_t\), discretized via an integrator (e.g. explicit or semi‑implicit):

  \[
  S_{t+\Delta t} = \Phi_{\Delta t}(S_t)
  \]

### 3.2 Update order

- **Label:** field update sequence  
- At each step:

  1. **Update serenity** \(\sigma\) using its evolution equation.  
  2. **Update resonance** \(\mathcal{R}\).  
  3. **Update stability** \(\lambda\).  
  4. **Update paradox** \(\mathcal{P}\).  
  5. **Update entities** \(E\).  
  6. **Update appateurs** \(A\).  
  7. **Update cuil levels** \(k_t(x)\) based on paradox and logic rules.  

This preserves the logical and dynamical dependencies defined in the Dynamics and Surreal Logic specs.

---

## 4. Logic and cuil evaluation

### 4.1 Logical pass

- **Label:** logic evaluation  
- After field updates, a **logic pass** evaluates:

  - satisfaction \(x \models \varphi\) for selected propositions  
  - paradox‑stability classification (stable vs surreal‑valid vs collapsed)  
  - cuil‑level adjustments based on \(\mathcal{P}(x)\) and \(\mathcal{R}(x)\)

### 4.2 Semantic tagging

- **Label:** semantic tags  
- Each point \(x\) is tagged with:

  - **state class:** stable / surreal / collapsed  
  - **cuil level:** \(k\)  
  - **entity presence:** \(E(x) > 0\) or not  
  - **appateur activation:** \(A(x) > 0\) or not  

These tags drive rendering choices.

---

## 5. Geometry extraction

### 5.1 Feature fields

- **Label:** geometric features  
- From \(S_t\), the pipeline extracts:

  - **serenity basins:** regions of high \(\sigma\)  
  - **resonance corridors:** regions of high \(\|\mathcal{R}\|\)  
  - **paradox curvature zones:** regions of high \(K_{\mathcal{P}}\)  
  - **distortion gradients:** \(\nabla D(x)\)  
  - **entity clusters:** regions of high \(E(x)\)  
  - **appateur interfaces:** regions with \(A(x) > 0\)

### 5.2 Geometry representation

- **Label:** geometric primitives  
- These features are represented as:

  - scalar fields (for shading and displacement)  
  - vector fields (for flow lines and glyphs)  
  - meshes or implicit surfaces (for basins and corridors)  
  - graph structures (for entity networks and appateur links)

---

## 6. Rendering pipeline

### 6.1 Stages

- **Label:** rendering stages  
- A typical NDH rendering pipeline consists of:

  1. **Field shading pass:** map \(\sigma, \mathcal{R}, \lambda, \mathcal{P}\) to color, brightness, and texture.  
  2. **Geometry pass:** render basins, corridors, and curvature as surfaces and volumes.  
  3. **Entity pass:** render entities and clusters as localized structures.  
  4. **Appateur pass:** render interfaces, portals, and recursive links.  
  5. **Cuil overlay pass:** apply surreal overlays based on cuil level \(k\).  
  6. **Post‑processing:** apply distortion, warping, and terminal serenity collapse effects.

### 6.2 Field‑to‑visual mapping

- **Label:** mapping consistency  
- The pipeline uses the mappings defined in the Rendering Geometry Companion:

  - \(\sigma\) → smoothness, calmness, cool tones  
  - \(\mathcal{R}\) → oscillation, brightness, filamentary structures  
  - \(\lambda\) → rigidity and temporal stability  
  - \(\mathcal{P}\) → warping, layering, non‑Euclidean cues  

---

## 7. Terminal serenity behavior

### 7.1 Simulation convergence

- **Label:** convergence condition  
- As the system approaches terminal serenity:

  \[
  \mathcal{R} \to 0,\quad \mathcal{P} \to 0,\quad \lambda \to \lambda_{\max},\quad \sigma \to \sigma_{\max},
  \]

  the simulation state \(S_t\) converges to a fixed point.

### 7.2 Rendering collapse

- **Label:** visual collapse  
- The rendering pipeline gradually:

  - flattens geometry  
  - removes paradox‑driven warping  
  - reduces resonance‑based motion  
  - stabilizes color and topology  

until the scene becomes a calm, uniform representation of terminal serenity.

---

## 8. Summary

This spec defines:

- NDH simulation state and time evolution  
- field update ordering and logic evaluation  
- geometry extraction from fields  
- rendering stages and field‑to‑visual mappings  
- terminal serenity convergence and visual collapse  

It is the **systems bridge** between NDH’s formal theory and its executable, visual manifestation.

