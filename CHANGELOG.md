# Changelog

## 2026-06-15

- Tightened the one-sentence self-showcase workflow: short prompts asking the Skill to explain itself now default to a general showcase with copy, structure, image planning, density/layout choices, short Chinese annotations, and image generation when available.
- Added stronger runtime rules so available image-generation tools must be invoked instead of stopping at prompts or plans.
- Clarified local private subject and style binding behavior: when configured, self-showcase images use the local default subject as the main visual actor and the local hand-drawn style by default.
- Split final fixed-IP artwork from text-only direction previews: reference-capable tools should produce final IP-consistent artwork, while text-only generation may produce a clearly labeled direction preview that is not final IP-consistent output.
- Added subject-drift safeguards for direction previews: human portraits, abstract portraits, characterless images, generic replacement mascots, and default placeholder subjects are treated as failures that require retry or a reference image.
- Clarified that “more like you” means matching the user's expression style, judgment, structure, rhythm, and visual preferences, not drawing a real-person portrait.

## 2026-06-14

- Added bilingual README entry points with `README.md` for Chinese users and `README.en.md` for English users.
- Expanded the five practical workflows in the documentation: first-run onboarding, Before/After comparisons, style drift scorecards, failure sample capture, and one-click content transformation.
- Improved short-prompt entry behavior: platform post requests now default to in-chat deliverables and image generation when available, instead of creating a Markdown publishing package unless the user explicitly asks for files.
- Added stricter named-character protection: when the user names a concrete character such as Zhenxiaoning but no reference image/path/binding is available, the Skill must ask for a reference or continue without a character instead of substituting default subject seeds.
- Added QA rules so user feedback becomes reusable style rules instead of only triggering regeneration.

## 2026-06-13

- Added stricter visual subject precedence: current conversation uploads override any stale or existing image under `assets/references/characters/`; the folder is not an automatic candidate pool.

## 2026-06-12

- Added fixed character reference support under `assets/references/characters/`.
- Refined the character reference workflow around user-owned authorized IP assets.
- Added rules for user-owned IP assets: short-term use can rely on conversation uploads; long-term reuse should place authorized assets in `assets/references/characters/<subject-slug>-reference.png`.
- Added QA checks for fixed reference paths and continuous visual subject consistency.
- Added open source maintenance materials: `LICENSE`, `NOTICE.md`, `CONTRIBUTING.md`, `SECURITY.md`, `.gitignore`, and Codex for OSS application notes.

## 2026-06-11

- Upgraded the visual metaphor system from information carriers to daily action metaphors.
- Added low, medium, and high density planning rules.
- Added rough hand-drawn scene guidance to avoid polished commercial illustration and UI mockup drift.
- Added layout anti-repetition rules for continuous image series.

## 2026-06-09

- Initial public release of Zhenxiaoning Human Style Lab.
- Added personal style DNA, anti-style, content pattern, visual IP, platform sizing, and QA reference files.
- Added showcase images and starter examples.
