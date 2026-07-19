# Task 1 — Asset Generation
## Category: Exhaust (3 designs)

Same core prompt skeleton as previous categories (background, lighting,
no-logo rule). Camera angle went through the most exploration of any
category — this file documents why straight-on rear view was chosen
over a three-quarter angle.

---

<!-- Exhaust #1 — Dual Sport Tips -->
```
Professional automotive product photography of a single exhaust 
system tip component (isolated part, not attached to a vehicle), 
dual round sport exhaust tips side by side sharing one body, polished 
stainless steel finish, shot at exactly straight-on rear view 
(0-degree, direct frontal elevation, camera dead-center behind the 
tips, symmetrical composition), with both tip openings (bores) facing 
directly toward the camera, camera positioned at a low, near-eye-level 
height relative to the component, component centered in frame, solid 
pure white background (RGB 255,255,255), completely uniform white 
with no gradient, no vignette, no grey corners, no transparency, no 
black background, no reflective floor, no mirror surface, matte white 
flooring only, studio lighting with a single soft shadow directly 
beneath the component, high resolution, photorealistic, cut-out 
product shot, plain surface with absolutely no text, no logo, no 
brand name, no lettering, no decals, no stickers, no other objects, 
no vehicle body
```

---

<!-- Exhaust #2 — Quad Titanium -->
```
Professional automotive product photography of a single exhaust 
system tip component (isolated part, not attached to a vehicle), 
four round exhaust tips arranged in a 2x2 cluster sharing one body, 
brushed titanium finish, shot at exactly straight-on rear view 
(0-degree, direct frontal elevation, camera dead-center behind the 
tips, symmetrical composition), with all tip openings (bores) facing 
directly toward the camera, camera positioned at a low, near-eye-level 
height relative to the component, component centered in frame, solid 
pure white background (RGB 255,255,255), completely uniform white 
with no gradient, no vignette, no grey corners, no transparency, no 
black background, no reflective floor, no mirror surface, matte white 
flooring only, studio lighting with a single soft shadow directly 
beneath the component, high resolution, photorealistic, cut-out 
product shot, plain surface with absolutely no text, no logo, no 
brand name, no lettering, no decals, no stickers, no other objects, 
no vehicle body
```

---

<!-- Exhaust #3 — Single Large Bore -->
```
Professional automotive product photography of a single exhaust 
system tip component (isolated part, not attached to a vehicle), one 
single large-bore performance exhaust tip, matte black finish, shot 
at exactly straight-on rear view (0-degree, direct frontal elevation, 
camera dead-center behind the tip, symmetrical composition), with the 
tip opening (bore) facing directly toward the camera, camera 
positioned at a low, near-eye-level height relative to the component, 
component centered in frame, solid pure white background (RGB 
255,255,255), completely uniform white with no gradient, no vignette, 
no grey corners, no transparency, no black background, no reflective 
floor, no mirror surface, matte white flooring only, studio lighting 
with a single soft shadow directly beneath the component, high 
resolution, photorealistic, cut-out product shot, plain surface with 
absolutely no text, no logo, no brand name, no lettering, no decals, 
no stickers, no other objects, no vehicle body
```

---

### Notes / Iteration Log
- Ran an initial angle-free test to observe the model's natural
  tendency for this object type: all three outputs pointed the tip
  opening (bore) toward the camera at varying degrees, confirming that
  the bore is the feature the model treats as most important to show —
  the same way the wheel face is the key feature for Rim, and the tread
  pattern is the key feature for Tire.
- First attempt at locking a 30-degree front three-quarter angle
  produced three different rotation amounts across the three designs
  (near side-on, mild three-quarter, near straight-on) — direction/
  rotation control on this roughly axially-symmetric object proved as
  unreliable as it was on Front Bumper.
- Switched to a straight-on rear view (0-degree, dead-center camera),
  the same fix that worked for Front Bumper: removing rotation
  ambiguity entirely by using a symmetric, non-rotated composition.
  This produced consistent results across all three designs on the
  first attempt.
- Also tried a side three-quarter angle (referencing real exhaust tip
  catalog photography from brands like Borla, which typically show
  the body length and angle-cut together) and a straight-on side
  profile — both still showed inconsistent rotation/angle across the
  three designs for this specific tool. Straight-on rear view remained
  the most reliable and was kept as the final choice.
- To keep the three designs clearly distinct (beyond just color/finish)
  the differentiator was shifted to tip count and layout: single tip,
  dual tips side-by-side, and quad tips in a 2x2 cluster — a much
  stronger visual distinction than finish/color alone.
