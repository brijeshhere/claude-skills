# caveman setup

Terse "caveman" response voice for Claude Code. Core skill only. Credit: [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) (Apache-2.0, see `LICENSE` and `NOTICE`).

## 1. Install

Copy the `caveman` folder to `~/.claude/skills/caveman/`:

- Windows: `%USERPROFILE%\.claude\skills\caveman\`
- macOS/Linux: `~/.claude/skills/caveman/`

```sh
git clone https://github.com/brijeshhere/claude-skills.git && mkdir -p ~/.claude/skills && cp -r claude-skills/caveman ~/.claude/skills/
```

## 2. Always-on (optional)

Add this line to `~/.claude/CLAUDE.md`:

```
- Use caveman voice (the `caveman` skill rules) in every response by default, every session, until I say "stop caveman" or "normal mode". It does not apply to code, commits, docs or files written to disk.
```

Skip it to use `/caveman` on demand instead.

## 3. Verify

Start a new session and ask something. Replies should be terse. Run `/caveman status`.

## 4. Turn off

Say "stop caveman" or "normal mode", or remove the CLAUDE.md line.

## Not included on purpose

The hooks, MCP server, proxy and sub-skills of the full upstream plugin. Want them? Install the upstream plugin instead.

## Dependencies

No MCP server or other dependency needed.
