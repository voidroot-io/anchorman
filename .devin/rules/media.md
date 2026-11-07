---
description: "Image/photo pitfalls — read before publishing any photo or image on the site"
trigger: model_decision
---

Photo & Image Rules: Anchorman site

Adapted from the inkkeeper repo's media rules — the transferable lessons only.
This site will mostly show photos of **customers' homes** taken on a phone,
which makes these non-optional.

EXIF / privacy
Every published photo gets its EXIF/XMP/IPTC stripped — phone photos carry
GPS coordinates, and a handyman's job photos point at real customers' houses.
Strip before publishing, every time (exiftool `-all=`, sharp `.withMetadata`
off-by-default, or similar). Keep the untouched original in `assets/source-docs`
or an ignored originals folder — the published web copy is the stripped,
downscaled one.

Sizing
Downscale for web before publishing: ~1600-2000px on the long edge is plenty
for a gallery/hero; JPEG or WebP around q80. Full-res phone shots (4000px+,
4-8MB) destroy page-load on the mobile connections his customers use.

Formats
Canvas/toBlob JPEG output flattens transparency to black. Anything with alpha
(logo, cut-outs) stays PNG or WebP — never JPEG.

Overlays & effects
Any visual effect layered over a photo (gradients, vignettes, captions) must
be expressed in units relative to its box (`%`, `aspect-*`, container units) —
never fixed pixels tuned to one render size.

Deterrents
Right-click blocking / overlay divs are not protection and don't get shipped.
The only meaningful control is not publishing the high-res original.
