# 🌌 **NDH‑AMS Phase 4.1 — Teaching API Integration Layer**  
### *API‑First Interface for Opera House, Accessibility, and Narrative Geometry*

Phase 4.1 extends the Opera House Constructor by providing a **formal API layer** that exposes NDH‑AMS concepts, accessibility modes, and narrative geometry through a stable, text‑native interface.  
This ensures NDH‑AMS remains teachable, accessible, and fully functional even in low‑resource, non‑visual, or non‑global‑North environments.

---

# ⭐ 1. Purpose of Phase 4.1  
Phase 4.1 defines the **Teaching API**, the contract through which NDH‑AMS concepts are:

- requested  
- transformed  
- visualized (optionally)  
- narrated  
- accessibility‑adjusted  
- delivered to learners  

It is the **API wrapper** around Phase 4’s creative engine.

This layer ensures NDH‑AMS can be taught:

- with or without PNG/SVG  
- with or without rendering tools  
- with or without high‑bandwidth devices  
- with or without visual literacy  

The Teaching API is the **public interface** for NDH‑AMS education.

---

# ⭐ 2. Core Components of Phase 4.1

---

## 📦 Module 4.1.1 — Tile Metadata API  
Tiles are the atomic teaching units of NDH‑AMS.

Endpoints:

- **Tile Index** — list all tiles  
- **Tile Detail** — retrieve tile content  
- **Tile Accessibility** — retrieve accessibility variants  

Tiles contain:

- text content  
- metadata  
- optional visual references  
- narrative geometry hooks  
- accessibility modes  

---

## 🖼️ Module 4.1.2 — PNG/SVG Asset Contracts  
PNG/SVG assets are **optional**.

Endpoints:

- **PNG Metadata**  
- **SVG Metadata**  

If assets do not exist, the API returns:

- “asset not found”  
- fallback ASCII diagrams  
- narrative geometry substitutions  

This is the **poverty‑safe design**.

---

## 🌀 Module 4.1.3 — Visual Generation Hooks  
Endpoints:

- **Generate SVG**  
- **Generate PNG**  

These return **instructions**, not files.

Rendering can be done using:

- Inkscape  
- GIMP  
- Krita  
- Draw.io  
- SVG‑edit  

All free, all optional.

---

## ♿ Module 4.1.4 — Accessibility Modes  
Accessibility is embedded at the API level.

Modes:

- CognitiveEase  
- VisualEase  
- SensoryMinimal  
- AudioOnly  

Each mode transforms:

- brightness  
- contrast  
- geometry smoothing  
- resonance reduction  
- narrative substitution  

Endpoints:

- **Accessibility Mode**  
- **Accessibility Tile**  

---

## 🎙️ Module 4.1.5 — Narrative Geometry API  
This module exposes NDH metaphors programmatically.

Mappings:

- operator → performer  
- flow → choreography  
- tensor → material  
- basin → room  
- invariant → architectural law  

Endpoints:

- **Narrative Map**  
- **Narrative Tile**  

This ensures NDH remains teachable even without visuals.

---

# ⭐ 3. Integration with Phase 4  
Phase 4.1 binds the Teaching API to:

- Opera House Constructor  
- Kitty Accessibility Familiar  
- Bill Nye Tile Greeter  
- Narrative Geometry Engine  

This creates a unified, human‑facing interface for NDH‑AMS.

---

# ⭐ 4. Deliverables  
Phase 4.1 produces:

- Teaching API Blueprint  
- Tile Metadata Schema  
- Accessibility Mode Contracts  
- Narrative Geometry API  
- PNG/SVG Optionality Framework  
- ASCII‑native fallback system  
- Integration with Phase 4 creative engine  
- Public‑facing educational interface for NDH‑AMS v4.1.0  

---

