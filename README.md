# Framing Partner Skills

AI coding agent skills for structured thinking and creative ideation — reason through decisions, explore hunches, and generate divergent solution directions with quick wireframe sketches to make each concept tangible.

## Skills

**`/thinking-partner`** — Reason through a decision, understand a problem, explore a hunch, or compare options. Works with or without existing project context. Reads your codebase and docs to ground the conversation, then follows structured thinking patterns (orient, hunch, what-if, decision) to help you reach clarity.

**`/ideation-partner`** — Explore a problem space and generate genuinely different solution directions. Works from tickets, notes, screenshots, or a verbal description. Asks targeted questions to frame the problem, then produces multiple distinct concepts — not variations on one idea.

## Install

```bash
git clone https://github.com/rodhoward/framing-partner-skills.git ~/.local/share/framing-partner-skills
~/.local/share/framing-partner-skills/install.sh
```

The install script detects supported platforms and symlinks each skill into the appropriate skills directory. Symlinks keep them updatable with `git pull`.

### Other commands

```bash
./install.sh status      # Show what's linked where
./install.sh update      # git pull + re-install + prune stale links
./install.sh uninstall   # Remove symlinks (leaves the clone intact)
```

## Requirements

- An AI coding agent that supports skills (e.g., [Claude Code](https://claude.com/claude-code), [Codex CLI](https://github.com/openai/codex))
- Bash 3.2+ (macOS default works)
