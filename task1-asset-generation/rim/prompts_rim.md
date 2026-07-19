# Task 1 — Asset Generation
## Category: Rim (3 designs)

All three prompts share the same structure (camera angle, background,
lighting, cut-out style) so the outputs stay visually consistent as a set.
Only the design language and finish change between variants.

---

<!-- Rim #1 — Sport Multi-Spoke -->
```
Professional automotive product photography of a single alloy wheel/rim, 
multi-spoke sport design, matte black finish with machined edges, 
shot at exactly 45-degree front three-quarter angle, wheel centered 
in frame, solid pure white background (RGB 255,255,255), no 
transparency, no black background, studio lighting with soft shadow 
directly beneath wheel, high resolution, photorealistic, cut-out 
product shot, plain center cap with no text, no logo, no brand name, 
no lettering, no other objects, no tire, no vehicle
```

---

<!-- Rim #2 — Classic Chrome -->
```
Professional automotive product photography of a single alloy wheel/rim, 
5-spoke classic design, polished chrome finish, 
shot at exactly 45-degree front three-quarter angle, wheel centered 
in frame, solid pure white background (RGB 255,255,255), no 
transparency, no black background, studio lighting with soft shadow 
directly beneath wheel, high resolution, photorealistic, cut-out 
product shot, no other objects, no tire, no vehicle
```

---

<!-- Rim #3 — Racing Mesh Bronze -->
```
Professional automotive product photography of a single alloy wheel/rim, 
mesh-style multi-spoke racing design, bronze/gold finish, 
shot at exactly 45-degree front three-quarter angle, wheel centered 
in frame, solid pure white background (RGB 255,255,255), no 
transparency, no black background, studio lighting with soft shadow 
directly beneath wheel, high resolution, photorealistic, cut-out 
product shot, plain center cap with no text, no logo, no brand name, 
no lettering, no other objects, no tire, no vehicle
```

---

### Notes / Iteration Log
- Initial prompts used a vague "front three-quarter view" phrase, which
  produced inconsistent angles and an inconsistent (sometimes black/
  transparent) background across designs.
- Added explicit RGB lock (`RGB 255,255,255`) and `no transparency, no
  black background` to force a true solid white background.
- Added `plain center cap with no text, no logo, no brand name, no
  lettering` after an earlier bronze output generated a fake brand-like
  logo on the hub, which broke consistency with the other two designs.
- Final structure keeps camera angle, background, lighting, and framing
  identical across all three prompts — only the spoke design, finish,
  and color differ.
