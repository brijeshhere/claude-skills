# claude-skills

Personal Claude Code skills, modified from the mattpocock-skills plugin.

## Install

Copy a skill folder (e.g. `grilling/`) into `~/.claude/skills/`.

## Credit

Forked from the [mattpocock-skills](https://github.com/mattpocock/skills) plugin by Matt Pocock (MIT, see LICENSE). Changes vs the originals:

- `grilling`: asks each round's questions via selectable AskUserQuestion forms (recommended option first) instead of numbered markdown; looks up facts inline.
- `research`: saves findings to the current working directory as `research-<short-kebab-topic>.md`.
- `handoff`: saves to the current working directory as `handoff-<YYYY-MM-DD-HHMM>.md`, never to temp dirs.
