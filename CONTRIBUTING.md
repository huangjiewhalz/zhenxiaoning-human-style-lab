# Contributing

Thanks for considering a contribution. This project is still early, so the most useful contributions are concrete examples, reproducible failures, clearer reference rules, and small documentation improvements.

## What This Project Accepts

- Improvements to Skill routing in `SKILL.md`.
- Better reference rules in `references/`.
- New QA checks for AI-flavor drift, visual subject consistency, or platform image sizing.
- Examples that use your own authorized content.
- Bug reports with input, expected behavior, actual behavior, and which reference file should have prevented the issue.

## What This Project Does Not Accept

- Prompts or examples that imitate living artists, bloggers, creators, or public figures.
- Third-party IP, celebrity likenesses, or unauthorized brand characters.
- "AI detector bypass" techniques.
- Generic prompt packs that are not tied to personal style assets.
- Large unrelated rewrites.

## Local Review Checklist

Before opening a pull request, check:

- `SKILL.md` stays short and routes to references instead of becoming a long prompt.
- Any visual subject rule preserves one subject across a series.
- Any user-owned IP example includes an authorization note or clearly says it is a placeholder.
- Any platform image size advice mentions ratio and safe area, not just pixels.
- Any anti-AI-flavor rule improves style evidence and judgment, not fake human mistakes.
- No `.DS_Store`, temporary files, private paths, tokens, credentials, or chat logs are committed.

## Suggested Pull Request Format

```markdown
## What Changed

## Why It Matters

## Files Touched

## Validation

## Remaining Risk
```

Small, focused PRs are preferred.
