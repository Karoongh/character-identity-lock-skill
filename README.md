# character-identity-lock

Reusable AI agent skill that enforces strict visual identity lock for any recurring fictional character.

Prevents face, body, age, hair and skin drift across large numbers of generated images while allowing free variation of scene, clothing, activity and camera.

## Install

Copy the folder into your agent skills directory (e.g. `.grok/skills/character-identity-lock/` or equivalent).

## When to use

- Generating or reviewing images of a recurring character
- Creating a new character that must stay consistent
- Editing prompts, reference paths or image-generation code
- Any work involving FX-TRADER-01 or similar brand personas

## Core idea

One Character ID + one Master Reference image + two-layer prompts + mandatory identity checklist = stable character across 100+ images.

See `SKILL.md` for full rules.
