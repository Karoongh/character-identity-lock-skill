---
name: character-identity-lock
description: Enforce strict visual identity lock for any recurring fictional character in image generation and related code. Use when creating, reviewing, approving or rejecting character images, preventing face or body drift, writing character prompts, or editing image-generation code or assets. Triggers on character consistency, identity lock, face lock, master reference, character drift, FX-TRADER-01, or new character creation.
---

# Character Identity Lock

## Overview

Enforce long-term visual consistency for any recurring fictional character across dozens or hundreds of images. The same face, body proportions, age, hair, skin and overall identity must remain stable while location, clothing, activity, camera angle and lighting may change freely.

## Core Principles (Mandatory)

1. One Character ID = one physical identity. Never invent a new face for the same ID.
2. Master Reference image is the primary identity anchor. Text prompts alone are never sufficient.
3. Two-layer prompt system is required for every generation:
   - Layer A (Stable Identity) — fixed block that must not be rewritten from scratch.
   - Layer B (Variable Scene) — only location, activity, clothing variant, pose, lighting, camera.
4. Identity review checklist must pass before any image is approved or published.
5. Any change to core identity (age, face, hair, beard, skin, body type) requires explicit documentation and a new Master Reference version.

## Required Workflow for Image Work

1. Identify or create the Character ID (e.g. FX-TRADER-01, ANALYST-02).
2. Confirm a Master Reference image exists and is approved. If not, create and approve it first.
3. Load the Master Reference as character reference / face lock / IP-Adapter (tool-dependent).
4. Build prompt using the fixed Stable Identity block + new Variable Scene block.
5. Generate.
6. Run the Identity Review Checklist (see references/general-identity-lock-rules.md).
7. Reject on any identity drift. Scene quality never overrides identity failure.
8. Save only approved images under the character’s approved-production folder with standard naming.

## Required Folder Structure (per character)

```
assets/character/<CHARACTER-ID>/
├── 00-identity-lock/
│   ├── CHARACTER-LOCK.md
│   ├── face-seed.txt          # optional fixed seeds / strength values
│   └── negative-prompt-lock.txt
├── 01-master-reference/       # exactly one primary approved image
├── 02-full-body-reference/
├── 03-lifestyle-reference/
├── 04-expression-sheet/       # limited approved expressions
├── 05-clothing-variants/
└── approved-production/
```

## Rules When Editing Code or Prompts

- Any change that affects character prompts, reference paths, generation workflow or asset naming must preserve Identity Lock.
- Combine with the safe-multi-agent-github-dev skill for non-trivial code changes.
- Never overwrite or delete an approved Master Reference without explicit user confirmation and version bump.

## Creating a New Character

1. Choose a unique Character ID.
2. Write a visual identity document (appearance, age, body, personality cues).
3. Generate and approve one Master Reference image.
4. Create the folder structure above.
5. Fill CHARACTER-LOCK.md with the fixed Stable Identity block and checklist.
6. Only then begin production scenes.

## Project-Specific Notes

For the forex-telegram-bot project the primary character is FX-TRADER-01.
See references/fx-trader-01.md for its locked identity details and file paths.
Always prefer the project’s docs/BRAND-VISUAL-IDENTITY.md and docs/IMAGE-GENERATION-WORKFLOW.md when they exist.

## Refusal Conditions

Refuse to generate, approve or publish an image if:
- No Master Reference is available or loaded.
- The Stable Identity block was rewritten from scratch instead of reused.
- The Identity Review Checklist has not been applied.
- Core identity attributes have changed without documented approval.
