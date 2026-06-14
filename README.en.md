# Zhenxiaoning Human Style Lab

[简体中文](README.md) | [English](README.en.md)

> You do not need a longer prompt. You need reusable style assets that keep reminding the AI what feels like you and what does not.

Zhenxiaoning Human Style Lab is a Codex Skill for turning a creator's own work, preferences, anti-style rules, visual subject rules, and hand-drawn illustration taste into reusable personal style assets.

It is not a generic Skill Creator. It focuses on one concrete problem:

> Make AI remember my style, instead of guessing from scratch every time.

## Latest Updates

- **2026-06-14**: Added five practical workflows so users can test the Skill before building a full style asset pack:
  - **First-run onboarding**: asks only for the minimum useful material and gives a first test task.
  - **Before/After comparison**: shows the difference between a default AI-flavored version and a style-asset version.
  - **Style drift scorecard**: evaluates whether the output still feels like the user.
  - **Failure sample library**: turns "this does not feel like me" feedback into reusable rules.
  - **One-click content transformation**: turns articles, posts, links, product notes, or drafts into publishable content in the user's style.
- **2026-06-14**: Improved short-prompt entry. When the user says "make this into a Xiaohongshu / X / WeChat post", the Skill now defaults to in-chat copy, titles, visual planning, and image output instead of silently creating a Markdown publishing package.
- **2026-06-14**: Strengthened visual subject consistency. When the user uploads or specifies a character, continuous illustrations must keep the same subject.
- **2026-06-14**: Added bilingual README entry points for Chinese and English users.

See [`CHANGELOG.md`](CHANGELOG.md) for the full changelog.

## Shortest Usage

```text
Use Zhenxiaoning Human Style Lab to explain what this Skill does and how to use it. I want to post it on Xiaohongshu.
```

The Skill should infer the target format and generate:

- post copy
- title candidates
- carousel / illustration planning
- hand-drawn image prompts or generated images when the runtime supports image generation
- a style drift scorecard

You can replace Xiaohongshu with X, WeChat Official Account, Instagram, video cover, forum post, or another platform.

## What Problem It Solves

Many creators do not struggle because AI cannot write. They struggle because AI output often:

- sounds smooth but not like them
- uses template-like titles and summaries
- turns everything into a generic marketing tone
- makes visuals too polished, too commercial, or too "AI-generated"
- keeps changing the user's character or visual IP
- requires the creator to explain the same preferences again and again

This Skill turns those preferences into reusable assets: style DNA, anti-style rules, content patterns, visual subject rules, illustration constraints, and QA checklists.

## Five Practical Workflows

These workflows are designed for real use. The user does not need to understand the entire asset structure before trying the Skill.

### 1. First-Run Onboarding

Use this when the user has just installed the Skill or asks "how do I start?"

It outputs a minimal starting checklist:

- intended use case: writing, visuals, titles, scripts, reviews, or platform publishing
- sample material: ideally 3-10 pieces of the user's own work
- anti-style dislikes: AI flavor, marketing tone, visual clutter, polished commercial illustration, unstable character, etc.
- whether a visual character is needed
- a first test task

Example:

```text
Use Zhenxiaoning Human Style Lab for first-run onboarding. Tell me the minimum material I need to provide and how to run the first test.
```

### 2. Before / After Comparison

Use this when the user wants to see the value of the Skill.

It uses the same source material to produce:

- a default AI-flavored version
- a style-asset version
- an explanation of what changed
- optional visual planning
- a style drift scorecard

Example:

```text
Use Zhenxiaoning Human Style Lab to make a Before/After comparison for the text below. First show the default AI-flavored version, then the style-asset version, and include a scorecard.
```

### 3. Style Drift Scorecard

Use this when the user asks "does this still sound like me?" or "why does this feel off?"

The scorecard checks:

- whether it feels like the user
- AI-flavor level
- factual reliability
- structure fit
- anti-style hits
- visual subject consistency
- layout freshness

It should not just give scores. It should explain the evidence, list the top fixes, and propose rules for the next version.

Example:

```text
Use Zhenxiaoning Human Style Lab to check whether this draft still feels like me. Give me a style drift scorecard and next-version rules.
```

### 4. Failure Sample Library

Use this when the user says things like:

- "this does not sound like me"
- "too AI"
- "too crowded"
- "the character is wrong"
- "do not do this again"

The Skill turns feedback into reusable rules:

- what went wrong
- the user's exact feedback
- issue type: facts, tone, structure, visual subject, layout, density, platform size, or compliance
- new anti-style rule
- affected asset file
- corrected sample

Example:

```text
This version feels too AI, and the character is just standing in the corner. Use Zhenxiaoning Human Style Lab to record a failure sample and define the next-version rules.
```

### 5. One-Click Content Transformation

Use this when the user provides an article, post, link, product note, long conversation, or draft and wants it turned into publishable content.

The Skill first separates:

- usable facts
- parts that must not be copied, such as a third-party author's personal style or signature structure
- target platform

Then it outputs:

- transformation strategy
- rewritten version
- title candidates
- visual plan
- image prompts or generated images when available
- style drift scorecard
- new rules worth keeping

Example:

```text
Use Zhenxiaoning Human Style Lab to transform this post into my own expression. Output the rewritten version, title candidates, visual plan, and a style drift scorecard. Treat third-party content only as source material, not as a style to imitate.
```

## Core Capabilities

### Personal Style DNA

Extracts reusable style evidence from the user's own work:

- tone and rhythm
- title habits
- paragraph structure
- judgment style
- content values
- visual taste
- evidence-backed assumptions

Core output: `style-dna.md`

### Anti-Style Rules

Defines what should not appear:

- banned words
- banned sentence patterns
- disliked structures
- AI-flavor signals
- visual failure signals
- correction rules

Core output: `anti-style.md`

### Content Patterns

Captures reusable patterns for:

- titles
- openings
- paragraphs
- endings
- scripts
- visual planning
- platform-specific variants

Core output: `content-patterns.md`

### Visual IP Subject

The user can upload their own character or start from an original subject seed.

The character should not be a decorative mascot in the corner. It should participate in the core action: recording, filtering, correcting, sorting, publishing, or reviewing.

For short-term use, upload the character in the conversation. For long-term use, place an authorized reference image under:

```text
assets/references/characters/<subject-slug>-reference.png
```

Then define identity points, forbidden changes, action library, and consistency rules in `ip-subject.md`.

### Hand-Drawn Anti-AI Visuals

The visual system is designed to reduce polished AI flavor. It supports:

- white-background colored-pencil sketch
- pencil sketch
- red-pen review style

These are not meant to imitate a specific artist. They are reusable visual constraints: hand-drawn texture, visible imperfection, white space, short handwritten notes, and physical metaphors.

Core output: `visual-style-seed.md`

### Everyday Action Metaphors

The visual system does not start by choosing "cards", "timelines", or "UI panels".

It first asks: what everyday action does this idea feel like?

Examples:

- finding information: pulling a wrinkled note from under a blanket
- filtering real needs: shaking an old tablecloth and keeping only the useful pieces
- reducing AI flavor: crumpling an overly smooth draft and adding handwritten patches
- platform adaptation: fitting the same image into old frames of different sizes
- social feedback: taping over a noisy notification dot while one useful clue remains visible

Core output: `composition-patterns.md`

### Platform Image Sizes

The Skill does not default every image to 16:9.

It plans for common publishing surfaces:

- Xiaohongshu carousel: 1080 x 1440, 3:4
- WeChat Official Account cover: 900 x 383, with a center-square safety area
- WeChat article image: 16:9 or 3:2
- X feed image: 1200 x 675 / 1280 x 720
- Instagram / Facebook feed: 1080 x 1350
- vertical video / Stories / Reels: 1080 x 1920

Core reference: `references/platform-image-sizes.md`

## Quick Start

Use the repository as a Skill in a Skill-compatible environment, or place the folder in your local Skills directory.

Then trigger it with:

```text
Use Zhenxiaoning Human Style Lab to build my personal style assets from the following samples.

Use cases: Xiaohongshu posts + long-form articles + product explanations
Goal: make future writing and visuals feel more like me, with less AI flavor
Anti-style: no clickbait, no generic summaries, no polished commercial illustrations
Visual subject: use my uploaded character
Source material: ...
```

For a lighter test:

```text
Use Zhenxiaoning Human Style Lab to run first-run onboarding. Tell me the minimum material I need and the first test task.
```

## Project Structure

```text
.
├── SKILL.md
├── README.md
├── README.en.md
├── LICENSE
├── NOTICE.md
├── CONTRIBUTING.md
├── SECURITY.md
├── CHANGELOG.md
├── references/
│   ├── intake-and-modes.md
│   ├── experience-workflows.md
│   ├── style-dna-schema.md
│   ├── skill-pack-template.md
│   ├── ai-flavor-recovery-system.md
│   ├── visual-ip-system.md
│   ├── handdrawn-style-seeds.md
│   ├── layout-selection-engine.md
│   ├── presentation-carriers.md
│   ├── platform-image-sizes.md
│   ├── window-experiment-log.md
│   ├── model-runtime-requirements.md
│   ├── qa-checklist.md
│   └── compliance-boundaries.md
├── examples/
└── assets/
```

## Compliance Boundaries

This Skill is intended for:

- the user's own work
- user-authorized brand or project materials
- abstract style directions such as "more restrained", "more documentary", or "less marketing-like"

It should not be used to clone a public figure, living creator, blogger, artist, designer, brand mascot, or any recognizable third-party style or IP.

If a user asks to imitate a third party, rewrite the request into abstract constraints instead of copying that person's style.

## One-Line Summary

Turn your work, preferences, anti-style rules, and visual subject into reusable personal style assets, so AI output feels more like you and less like a default model.
