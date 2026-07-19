# Görev 2 — AI Car Modification: Kullanılan Prompt'lar

## Genel Yaklaşım

Aracın 6 parçası (rim, tire, front bumper, hood, rear spoiler, exhaust) tek bir
promptla aynı anda değiştirilmek yerine **zincirleme (sequential) inpainting**
yöntemiyle işlendi: her adımda bir parça (veya rim+tire gibi aynı bölgeye ait
istisnai bir çift) değiştirildi, bir önceki adımın çıktısı bir sonraki adımın
girdi görseli olarak kullanıldı.

---

## 1. Rim + Tire

```
[MODE: INPAINTING ONLY - FULL FRAME] This is an edit of the provided car image.
Image 1 is the car. Image 2 is the reference rim. Image 3 is the reference tire.
Target area: wheels and tires only — apply this edit only if the wheels are visible
in the photo. Do not process, re-generate, or re-crop the background, sky, car body,
or lighting.
Simply swap the existing wheels with the exact rim shown in Image 2, and the
existing tires with the exact tire shown in Image 3, on every visible wheel
position, copying each reference exactly with no redesign.
Preserve the reference rim's and tire's own original color, material, and texture
exactly as shown; do not repaint, tint, or recolor them to match the vehicle's paint.
The resulting image must maintain the exact same full-frame perspective, camera
angle, and vehicle position as the original photo, showing the entire front end
and side of the car without any cropping.
Preserve 100% of the original photo integrity, specifically keeping the front end,
rear end, and background untouched.
```

---

## 2. Front Bumper

```
[MODE: INPAINTING ONLY - FULL FRAME] This is an edit of the provided car image.
Replace only the car's front bumper (including grille) with the exact bumper shown
in the reference image: a sporty aftermarket bumper with a large deep honeycomb-mesh
lower grille, angular side air intakes, and an integrated front splitter.
IMPORTANT: The reference image shows the bumper from a straight front-on angle
(0°). The car in this photo is shown from a 3/4 front angle. You must rotate and
foreshorten the bumper's geometry to correctly match this 3/4 perspective — do not
simply paste the front-on view, adapt its shape as it would realistically look
from this angle.
Preserve the reference bumper's own original color and texture; do not repaint or
tint it to match the vehicle's paint.
The wheels, tires, and hood in this image were already modified in a previous
edit step — keep them exactly as they currently appear, do not revert them.
Keep everything else in the photo unchanged — rear end, background, lighting,
shadows.
Output must be sharp and photorealistic, no blur, no quality loss.
```

---

## 3. Hood

```
[MODE: INPAINTING ONLY - FULL FRAME] This is an edit of the provided car image.
Replace only the car's hood with the exact hood shown in the reference image.
Match the car's current camera angle and perspective.
Preserve the reference hood's own original color and texture; do not repaint or
tint it to match the vehicle's paint.
Keep everything else in the photo — wheels, tires, front bumper, rear end,
background, lighting, shadows — completely unchanged. If those parts were already
modified in a previous edit step, preserve those exact modifications, do not revert
them.
Output must be sharp and photorealistic, matching the original photo's resolution
and detail — no blur, no softness, no quality loss.
```

---

## 4. Rear Spoiler

```
[MODE: INPAINTING ONLY - FULL FRAME] This is an edit of the provided car image.
Replace only the car's rear spoiler with the exact spoiler shown in the reference
image, mounted on the rear tailgate/trunk edge. Match the car's current camera
angle and perspective.
Preserve the reference spoiler's own original color and texture; do not repaint
or tint it to match the vehicle's paint.
Any wheels, tires, hood, or front bumper in this image that were already modified
in a previous edit step — keep them exactly as they currently appear, do not
revert them.
Keep everything else in the photo — rest of the car, background, lighting,
shadows — completely unchanged.
Output must be sharp and photorealistic, no blur, no quality loss.
```

---

## 5. Exhaust

```
[MODE: INPAINTING ONLY - FULL FRAME] This is an edit of the provided car image.
Replace only the car's exhaust tip(s) with the exact exhaust shown in the
reference image, positioned exiting from beneath the rear bumper in the same
location as the original exhaust. Match the car's current camera angle and
perspective.
Preserve the reference exhaust's own original color and finish (e.g. chrome,
matte black, titanium); do not repaint or tint it to match the vehicle's paint.
Any wheels, tires, hood, front bumper, or rear spoiler in this image that were
already modified in a previous edit step — keep them exactly as they currently
appear, do not revert them.
Keep everything else in the photo — rest of the car, background, lighting,
shadows — completely unchanged.
Output must be sharp and photorealistic, no blur, no quality loss.
```

---

## Genel Öğrenilen Dersler

1. **Parça tipi, prompt stratejisini belirliyor.** Ayrık objeler (jant, lastik,
   spoiler, egzoz) kısa promptla nispeten güvenilir çalışırken, gövdeye entegre
   ve marka amblemi/ızgara içeren parçalar (bumper, hood) çok daha fazla direnç
   gösterdi.
2. **Uzun prompt her zaman daha iyi değil.** Aşırı uzun, çok fazla "Do NOT"
   içeren promptlar bazen modelin hiçbir şeyi değiştirmeme moduna geçmesine ya
   da çıktı kalitesinin (netlik) düşmesine yol açtı.
3. **Zincirleme adımlarda önceki değişikliklerin kaybı riski var.** Her
   promptta "bu parçalar zaten modifiye edildi, geri döndürme" talimatının
   açıkça eklenmesi gerekti.
4. **İki değişikliği aynı anda isteyince biri atlanabiliyor.** Bumper+hood
   ikilisinde ve rim+tire ikilisinde gözlemlendi: model iki eşzamanlı
   değişiklikten birini (genelde daha "sabit/tekrarlayan" görüneni) atlama
   eğilimi gösterdi. Her ikisini de ayrı, numaralı adımlar hâlinde "mandatory"
   olarak işaretlemek kısmen yardımcı oldu.
5. **"Kompozisyon değil, entegre değişiklik" talimatı kritik.** Referans parça
   bazen aracın yanına/yerine "ayrı bir obje" olarak yerleştirildi (yere
   konması gibi); bunu önlemek için "do NOT place it on the ground / beside
   the car, do NOT show it as a separate object" talimatı gerekli oldu.
6. **Aynı prompt, farklı çalıştırmalarda farklı sonuç verebiliyor** (seed
   varyansı) — bazı adımlarda aynı promptu birden fazla kez tekrar çalıştırmak
   gerekti.
7. **Renk benzerliği "değişiklik gerekmiyor" anlamına gelmiyor, ama bunu
   modele açıkça belirtmek her zaman yeterli olmadı.** Bazı denemelerde çok
   farklı bir referans (belirgin renk/desen farkı) verilmesine rağmen çıktı
   piksel-piksel aynı kaldı; bu durumlarda sorunun prompt değil, modelin gücü.