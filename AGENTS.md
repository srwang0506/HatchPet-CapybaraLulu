# Capybara Lulu contributor instructions

- Keep the public pet id and filenames stable: `capybara-lulu`, `pet.json`, and `spritesheet.webp`.
- `spriteVersionNumber: 2` is the Codex sprite protocol and must not be removed or treated as a project release number.
- Preserve Lulu's identity: no eyebrows, no tail, exactly two arms and two legs, orange muzzle, orange fruit and green leaf on the head.
- The idle runtime uses one waving paw; the opposite paw must remain lowered at the side throughout the gesture.
- The working/laptop motion uses Lulu's anatomical left arm on the viewer-right; keep it continuously attached from shoulder to paw in every phase.
- Preserve the 20-phase synchronized state runtime and its 15 named visual clips. Codex still has exactly 9 native triggers; never describe the clips as new desktop event types.
- Rebuild galleries with `python3 scripts/build_gallery.py` and run the test commands in the README before proposing asset changes.
- Never commit generated caches, version-suffixed experiments, absolute local paths, or intermediate chroma-key strips.
