# Changelog

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
