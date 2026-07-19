# Task 1 — Asset Generation
## Category: Front Bumper (3 designs)

Same core prompt skeleton as Rim and Tire (background, lighting,
no-logo rule). Camera angle differs from both: a straight-on frontal
view is used instead of a 3/4 angle, for reasons explained below.

---

<!-- Front Bumper #1 — Aggressive Sport -->
```
Professional automotive product photography of a single front bumper 
component (isolated part, not attached to a vehicle), aggressive sport 
design with large lower air intakes and sharp character lines, gloss 
black finish, shot at exactly straight-on frontal view (0-degree, 
direct front elevation, symmetrical composition), component centered 
in frame, solid pure white background (RGB 255,255,255), no 
transparency, no black background, studio lighting with soft shadow 
directly beneath component, high resolution, photorealistic, cut-out 
product shot, plain grille mesh with no badge, no logo, no brand name, 
no lettering, no other objects, no vehicle body
```

---

<!-- Front Bumper #2 — Luxury Clean -->
```
Professional automotive product photography of a single front bumper 
component (isolated part, not attached to a vehicle), clean luxury 
design with minimal horizontal chrome trim accent, matte grey finish, 
shot at exactly straight-on frontal view (0-degree, direct front 
elevation, symmetrical composition), component centered in frame, 
solid pure white background (RGB 255,255,255), no transparency, no 
black background, studio lighting with soft shadow directly beneath 
component, high resolution, photorealistic, cut-out product shot, 
plain grille mesh with no badge, no logo, no brand name, no lettering, 
no other objects, no vehicle body
```

---

<!-- Front Bumper #3 — Off-Road Rugged -->
```
Professional automotive product photography of a single front bumper 
component (isolated part, not attached to a vehicle), rugged off-road 
design with integrated skid plate and tow hook, textured black finish, 
shot at exactly straight-on frontal view (0-degree, direct front 
elevation, symmetrical composition), component centered in frame, 
solid pure white background (RGB 255,255,255), no transparency, no 
black background, studio lighting with soft shadow directly beneath 
component, high resolution, photorealistic, cut-out product shot, 
plain grille mesh with no badge, no logo, no brand name, no lettering, 
no other objects, no vehicle body
```

---

### Notes / Iteration Log
- Started with the same 45-degree front three-quarter angle used for
  Rim and Tire. Composition, background, and lighting came out correct,
  but the bumper's nose consistently faced the same direction across
  every attempt.
- Tried several ways to force the opposite direction:
  1. Explicit "left/right" wording in the prompt — no effect.
  2. Describing the bumper's own asymmetric geometry (tapered corner
     vs. rounded corner) as an anchor — this broke the composition and
     angle entirely, since a front bumper is actually left-right
     symmetric and the model had no real asymmetry to latch onto.
  3. Anchoring direction to an implied vehicle + camera position
     ("photographed as if mounted on a car facing left, camera at the
     front-right corner") — composition stayed intact this time, but
     the nose direction still did not change.
- Conclusion: for this specific asset type and tool, directional
  language (in any phrasing) does not reliably override the model's
  learned default orientation for an isolated bumper product shot.
  Rather than keep fighting this in the prompt, the angle was switched
  to a straight-on frontal (0-degree) view. Since a front bumper is
  symmetric left-to-right, a straight-on shot has no "direction" to get
  wrong, which permanently resolves the issue and also matches a
  common, legitimate automotive catalog photography style.
- All three final outputs matched on the first attempt with the
  straight-on prompt: consistent white background, consistent framing,
  consistent 0-degree symmetrical angle, no grille badge or text.
