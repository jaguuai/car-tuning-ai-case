# Task 1 — Asset Generation
## Category: Rear Spoiler (3 designs)

Same core prompt skeleton as previous categories (background, lighting,
no-logo rule), with extra emphasis added on camera height/tilt and
orientation — this category needed more iteration than the others to
reach a consistent result across all three designs.

---

<!-- Rear Spoiler #1 — Racing Wing -->
```
Professional automotive product photography of a single rear spoiler 
component (isolated part, not attached to a vehicle), tall racing wing 
design with dual support struts, carbon fiber texture. CRITICAL 
ORIENTATION: the wing must lie horizontally, like a wing resting flat 
above its mounting struts — NOT tilted upright, NOT angled like a fin 
pointing skyward. The long horizontal blade spans left to right across 
the frame, with the vertical struts below it holding it up at a normal, 
low mounting height. shot from a side-angled perspective with slight 
three-quarter rotation revealing the blade depth and curvature (not a 
flat side silhouette), camera positioned at a low, near-eye-level 
height relative to the component (roughly 15-20 degrees above the 
horizontal plane of the spoiler, not a steep top-down look), so the 
viewer sees mostly the front/side face with only a thin sliver of the 
top surface visible, solid pure white background (RGB 255,255,255), 
completely uniform white with no gradient, no vignette, no grey 
corners, no transparency, no black background, no reflective floor, 
no mirror surface, matte white flooring only, studio lighting with a 
single soft shadow directly beneath the component, high resolution, 
photorealistic, cut-out product shot, plain surface with absolutely 
no text, no logo, no brand name, no lettering, no decals, no stickers 
anywhere on the spoiler, no other objects, no vehicle body
```

---

<!-- Rear Spoiler #2 — Subtle Lip -->
```
Professional automotive product photography of a single rear spoiler 
component (isolated part, not attached to a vehicle), subtle 
low-profile lip spoiler design, gloss black finish, shot from a 
side-angled perspective with slight three-quarter rotation revealing 
the blade depth and curvature (not a flat side silhouette), camera 
positioned at a low, near-eye-level height relative to the component 
(roughly 15-20 degrees above the horizontal plane of the spoiler, not 
a steep top-down look), so the viewer sees mostly the front/side face 
with only a thin sliver of the top surface visible, solid pure white 
background (RGB 255,255,255), completely uniform white with no 
gradient, no vignette, no grey corners, no transparency, no black 
background, no reflective floor, no mirror surface, matte white 
flooring only, studio lighting with a single soft shadow directly 
beneath the component, high resolution, photorealistic, cut-out 
product shot, plain surface with absolutely no text, no logo, no brand 
name, no lettering, no decals, no stickers anywhere on the spoiler, 
no other objects, no vehicle body
```

---

<!-- Rear Spoiler #3 — Ducktail Sport -->
```
Professional automotive product photography of a single rear spoiler 
component (isolated part, not attached to a vehicle), ducktail sport 
design with integrated upward lip edge, body-color matte grey finish, 
shot from a side-angled perspective with slight three-quarter rotation 
revealing the blade depth and curvature (not a flat side silhouette), 
camera positioned at a low, near-eye-level height relative to the 
component (roughly 15-20 degrees above the horizontal plane of the 
spoiler, not a steep top-down look), so the viewer sees mostly the 
front/side face with only a thin sliver of the top surface visible, 
solid pure white background (RGB 255,255,255), completely uniform 
white with no gradient, no vignette, no grey corners, no transparency, 
no black background, no reflective floor, no mirror surface, matte 
white flooring only, studio lighting with a single soft shadow 
directly beneath the component, high resolution, photorealistic, 
cut-out product shot, plain surface with absolutely no text, no logo, 
no brand name, no lettering, no decals, no stickers anywhere on the 
spoiler, no other objects, no vehicle body
```

---

### Notes / Iteration Log
- This category required significantly more iteration than Rim, Tire,
  Front Bumper, or Hood, mainly because "rear spoiler" covers a much
  wider range of physical shapes (tall winged struts vs. thin body-hugging
  lips), which made a single fixed angle harder to lock in.
- First attempts using an explicit "45-degree rear three-quarter angle"
  produced a reflective/mirror-like floor and a flat side silhouette
  instead of the intended depth — not consistent with the matte white
  floor and soft shadow used in every other category.
- Removing the angle instruction entirely and letting the model choose
  its own natural composition produced a much better, more consistent
  result — the model's default framing for this object type turned out
  to be more reliable than an explicitly forced angle.
- A fake brand logo ("TASARIM") appeared on one output's endplate; this
  was fixed by adding an explicit, strongly worded no-text/no-logo/
  no-decal instruction targeting the endplate surface specifically.
- The Racing Wing design (tall struts + large endplates) initially
  rendered standing nearly vertical, like a fin — a different failure
  mode than the flat/reflective floor issue seen earlier. This was
  fixed by adding an explicit "must lie horizontal, NOT tilted upright"
  instruction, since this design's more complex geometry was more
  prone to being mis-oriented by the model.
- Once Subtle Lip and Ducktail Sport reached a consistent look, their
  camera height/tilt description (~15–20 degrees above the spoiler's
  horizontal plane) was copied back into the Racing Wing prompt to
  bring all three into alignment. Final versions above reflect that
  aligned, three-way-consistent result.
