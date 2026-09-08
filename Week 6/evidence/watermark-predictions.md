# Predictions recorded before screenshot trials

Original baseline: Content Credentials already reports AI generation and Google LLC. SynthID detection is being tested separately.

1. Screenshot at 496 CSS pixels wide: the PNG should not inherit embedded C2PA credentials. SynthID may survive resampling because the watermark is carried in pixels. Visual details should remain readable.
2. Screenshot at 260 CSS pixels wide: credentials should be absent. SynthID may still survive, but less image information remains. The image should work as a thumbnail, not a detailed provenance photograph.
3. Screenshot at 124 CSS pixels wide: credentials should be absent; substantial loss of detail may cause a negative or inconclusive SynthID result. The overall icon remains recognisable but quality may be insufficient for a credible auction listing.

Every trial uses the original image as its source, without cumulative transformations. No image generator is used in the screenshot trials. Only the image area is captured; file hashes identify the exact tested copies.

## Additional predictions before creating the next copies

The browser screenshot is JPEG encoded; its image-only crop was saved as a JPEG. The first test is therefore a 260-pixel-wide screenshot plus crop/re-save, rather than a PNG export.

4. Re-save the original as JPEG at quality 20: embedded credentials may be discarded by the image export. SynthID may survive moderate compression. The original resolution is retained but block artefacts may appear.
5. Resize the original to 124 pixels wide, then enlarge to its original 992 x 1075 dimensions and export JPEG at quality 80: credentials should be absent. Severe resampling may prevent SynthID detection, at the cost of visible blurring.

These transforms follow the lab's explicit re-save and resize exercises using deterministic macOS image operations.

## Trial 4 prediction, before transformation

Rotate the original seven degrees and export JPEG at quality 35. Geometric misalignment may make watermark detection harder while retaining most image detail. Credentials may be discarded by export. Black triangular margins and a tilted icon will reduce presentation quality but the object should remain recognisable. This is a new independent transform, not a continuation of trial 3.
