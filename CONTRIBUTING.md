# Contributing to Capybara Lulu

Thanks for helping Lulu feel more alive. Please keep changes focused, reviewable, and reproducible.

## Visual invariants

- No eyebrows or tail.
- Exactly two arms and two legs.
- Preserve the yellow plush body, orange muzzle, orange fruit, green leaf, glossy dark eyes, and round proportions.
- Directional run cycles must alternate contacts and remain visually mirrored without reversing frame order.
- Expressive idle uses the viewer-right paw; the viewer-left paw remains lowered throughout.
- Every gesture returns to neutral without a scale, baseline, torso, or fixed-limb jump.

## Before opening a pull request

1. Rebuild public assets with `python scripts/build_gallery.py`.
2. Run the three validation commands and unit tests in the README.
3. Inspect every changed GIF at normal pet size.
4. Include before/after visuals for animation changes.
5. Keep experiments and version-suffixed output directories outside the repository.

Pull requests should explain the user-visible reason for the change, the affected rows or phases, and the validation performed.
