# **NDH Accessibility Spec v1.0**  
### *Formal accessibility contract for NDH’s multi‑modal, API‑first manifold.*

---

## **1. Purpose & Scope**  
NDH is a sensory‑integrated manifold. Accessibility is not an add‑on — it is a **first‑class architectural requirement**.

This specification defines:

- accessibility profiles  
- sensory fallback rules  
- intensity‑reduction modes  
- cognitive‑ease behaviors  
- API‑level accessibility fields  
- rendering guidelines for Unity, Unreal, Godot, OpenXR, WebXR  
- haptic/audio/visual safety constraints  
- HRD accessibility validation  

This spec governs **all NDH clients**.

---

## **2. Accessibility Profiles**  
NDH supports structured accessibility profiles.  
Each profile is declared in API requests via:

```json
"accessibilityProfile": "<profile-name>"
```

### Profiles  
- **Low‑Vision**  
- **No‑Vision**  
- **Audio‑Only**  
- **Haptic‑Primary**  
- **Visual‑Minimal**  
- **Cognitive‑Ease**  

Each profile modifies sensory dispatch, intensity, and fallback behavior.

---

## **3. Sensory Fallback Rules**  
NDH must guarantee **multi‑modal redundancy**.

### Rules  
- **AudioFallback** — every visual cue must have an audio equivalent.  
- **HapticFallback** — every margin warning must have a haptic equivalent.  
- **VisualFallback** — every audio cue must have a visual equivalent unless profile forbids.  
- **TextFallback** — every sensory cue must have a text/log equivalent.  

Fallbacks are enforced by HRD.

---

## **4. Intensity‑Reduction Modes**  
NDH must support reduced sensory intensity for users who need calmer experiences.

### Modes  
- **SoftMode** — reduces amplitude of all sensory fields.  
- **QuietMode** — suppresses non‑critical audio.  
- **GentleHaptics** — reduces haptic sharpness.  
- **LowContrastVisuals** — reduces visual intensity.  

These modes can be combined with accessibility profiles.

---

## **5. Cognitive‑Ease Behaviors**  
NDH must support users who need simplified or slower sensory transitions.

### Behaviors  
- **SlowTransitions** — longer fade‑in/out for mode changes.  
- **SimplifiedGeometry** — fewer visual elements.  
- **ReducedTensorNoise** — suppresses non‑critical tensor cues.  
- **PredictivePrompts** — anticipatory guidance before transitions.  

These behaviors reduce cognitive load.

---

## **6. API‑Level Accessibility Fields**  
Accessibility is declared at the API level.

### Required Fields  
- **accessibilityProfile** — profile name  
- **sensoryMode** — soft/quiet/gentle/low‑contrast  
- **cognitiveEase** — true/false  
- **fallbackPriority** — audio/haptic/visual/text  

### Example  
```json
{
  "accessibilityProfile": "audio-only",
  "sensoryMode": "soft",
  "cognitiveEase": true,
  "fallbackPriority": "haptic"
}
```

---

## **7. Rendering Guidelines (Unity, Unreal, Godot, OpenXR)**  
NDH clients must follow accessibility rules when rendering NDH state.

### Unity  
- **UnityAudioMapping**  
- **UnityHapticMapping**  
- **UnityVisualSimplification**  

### Unreal  
- **UnrealMaterialIntensity**  
- **UnrealSpatialAudio**  
- **UnrealHapticRouting**  

### Godot  
- **GodotLowContrastMode**  
- **GodotSimplifiedGeometry**  

### OpenXR / WebXR  
- **XRHapticSafety**  
- **XRSpatialAudioFallback**  
- **XRVisualMinimalMode**  

---

## **8. Sensory Safety Constraints**  
NDH must enforce sensory safety through HRD.

### Constraints  
- **MaxHapticAmplitude**  
- **MaxAudioPeak**  
- **MaxVisualFlashRate**  
- **MaxTransitionSpeed**  
- **MarginWarningIntensityLimit**  

These constraints prevent sensory overload.

---

## **9. HRD Accessibility Validation**  
HRD must validate every accessibility‑related operation.

### Validation Rules  
- **HRDCheckIntensity**  
- **HRDCheckFallbacks**  
- **HRDCheckModeSafety**  
- **HRDCheckCognitiveEase**  

If validation fails, the operation is rejected.

---

## **10. JDTR Accessibility Logging**  
JDTR must log:

- profile changes  
- fallback activations  
- intensity reductions  
- cognitive‑ease transitions  
- accessibility‑related HRD rejections  

This ensures traceability.

---

## **11. Accessibility Compliance Requirements**  
All NDH clients must:

- implement fallback rules  
- respect intensity limits  
- support cognitive‑ease  
- expose accessibility settings  
- log accessibility events  
- pass HRD validation  

Compliance is mandatory.

---

