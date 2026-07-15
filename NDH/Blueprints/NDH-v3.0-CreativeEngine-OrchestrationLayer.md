### NDH v3.0 Creative Engine Orchestration Layer  
*A lightweight, API‑first automation layer that runs your whole creative workflow for you.*

---

### 1. Purpose

The **Orchestration Layer** automates the NDH Creative Engine Workflow Map:

- takes a concept  
- generates a tile  
- attaches SVG/ASCII visuals  
- creates accessibility variants  
- runs goat‑union governance checks  
- integrates into runtime  
- logs everything via JDTR  

All via **simple, chained API calls**, so you don’t have to manually step through each stage.

---

### 2. Orchestration Flow (Single Call View)

You call one orchestration endpoint:

```http
POST /orchestrate/concept
```

With a body like:

```json
{
  "title": "Goat Veto in K-Space",
  "summary": "Goats block unsafe dimensional transitions.",
  "tags": ["goat", "kspace", "safety"]
}
```

The Orchestration Layer then:

1. **Creates concept** → `/teach/concept/create`  
2. **Generates tile** → `/teach/tile/create`  
3. **Generates SVG + ASCII** → `/teach/svg/generate`, `/teach/ascii/generate`  
4. **Creates accessibility variants** → `/teach/accessibility/*`  
5. **Runs governance checks** → `/governance/validate`  
6. **Integrates into runtime** → `/runtime/integrate`  
7. **Logs via JDTR** → `/jdtr/log`

You get back a single response with:

- concept ID  
- tile ID  
- asset references  
- accessibility endpoints  
- governance status  
- runtime integration status  

---

### 3. Orchestration Endpoints

- **POST `/orchestrate/concept`**  
  Full pipeline from concept → runtime.

- **POST `/orchestrate/tile/{id}`**  
  Runs visuals, accessibility, governance, runtime for an existing tile.

- **POST `/orchestrate/accessibility/{id}`**  
  Regenerates all accessibility variants for a concept/tile.

- **POST `/orchestrate/visuals/{id}`**  
  Regenerates SVG + ASCII diagrams.

All are **poverty‑safe**: they work even if you don’t have PNGs or external tools.

---

### 4. Poverty‑Safe Design

- Uses **text‑only JSON + SVG + ASCII**.  
- No dependency on paid rendering stacks.  
- No requirement for pre‑existing assets.  
- Orchestration can be run on a minimal machine or even conceptually on paper.

---

