# 🌌 **NDH v3.0 Teaching API Blueprint (Poverty‑Safe Edition)**  
### *API‑first, asset‑second, zero‑cost architecture for PNG/SVG educational systems.*

---

## ⭐ 1. Core Principle  
**The API comes first.  
The visuals come second.  
The system must work even if you never generate a single PNG or SVG.**

This means:

- The API defines *what* a diagram is.  
- The API defines *how* a diagram is requested.  
- The API defines *how* accessibility modifies visuals.  
- The API defines *how* NDH concepts map to visual objects.  

PNG/SVG are **optional outputs**, not required inputs.

---

# ⭐ 2. Teaching API (Full, Poverty‑Safe Specification)

## 2.1 Tile Metadata  
Every educational tile is a JSON object.

- **GET `/teach/tiles`**  
  Returns a list of tiles with IDs, titles, and concept tags.

- **GET `/teach/tile/{id}`**  
  Returns the tile’s text content and references to optional visuals.

---

## 2.2 PNG/SVG Asset References  
These endpoints **do not require actual PNG/SVG files** to exist.  
They simply define the *contract*.

- **GET `/teach/assets/png/{name}`**  
  Returns metadata describing the PNG (if it exists).

- **GET `/teach/assets/svg/{name}`**  
  Returns metadata describing the SVG (if it exists).

If you never generate the files, the API still works —  
it just returns “asset not found” gracefully.

This is poverty‑safe.

---

## 2.3 Visual Generation Hooks  
These endpoints describe *how* visuals should be generated,  
but do not require you to generate them.

- **POST `/teach/generate/svg`**  
  Body: NDH concept → returns SVG instructions.

- **POST `/teach/generate/png`**  
  Body: NDH concept → returns PNG instructions.

You can use:

- **Inkscape** (free)  
- **GIMP** (free)  
- **Krita** (free)  
- **SVG‑edit** (free, browser‑based)  
- **Draw.io** (free, browser‑based)  

No cost.  
No proprietary stack.

---

## 2.4 Accessibility Variants  
Accessibility is baked into the API.

- **GET `/teach/accessibility/{mode}`**  
  Returns accessibility‑adjusted versions of tile content and visual metadata.

Modes include:

- CognitiveEase  
- VisualEase  
- SensoryMinimal  
- AudioOnly  

These modes modify:

- brightness floors  
- contrast  
- geometry smoothing  
- resonance reduction  

Again: **no actual PNG/SVG required**.

---

## 2.5 Interactive Modules (Text‑Only Fallback)  
Even if you cannot afford interactive graphics, the API still works.

- **GET `/teach/interactive/{concept}`**  
  Returns either:
  - interactive module metadata  
  - or a text‑only fallback explanation  

This ensures NDH is teachable even without visuals.

---

# ⭐ 3. Poverty‑Safe PNG/SVG Strategy  
Here’s how NDH handles visuals without cost:

### 3.1 SVG First  
SVG is:

- free  
- text‑based  
- editable in any text editor  
- version‑controllable  
- tiny file size  
- accessible  

SVG is the **primary visual format**.

### 3.2 PNG Optional  
PNG is only used when:

- rasterization is needed  
- accessibility requires brightness floors  
- diagrams need shading  

PNG is **secondary**.

### 3.3 No Paid Rendering Stack  
All rendering is done using:

- free tools  
- browser‑based editors  
- open‑source libraries  

### 3.4 API Does Not Require Assets  
The API is designed so:

- assets can be added later  
- assets can be missing  
- assets can be text‑only  
- assets can be replaced with ASCII diagrams  

This is the core poverty‑safe design.

---

