# ponytail

A Claude Code plugin that ties up loose ends before you wrap up a piece of work.

It checks your changed files for leftover `TODO`/`FIXME` markers, debug output, commented-out code, conflict markers, likely secrets, and untracked or stray files, then reports a checklist and asks before fixing anything.

## Install

```
/plugin marketplace add pavangullapalli472/demo
/plugin install ponytail@ponytail-marketplace
```

## Use

- `/ponytail` — check the whole working tree
- `/ponytail src/` — check only a path
- Or just say "wrap this up" or "any loose ends?" and the `ponytail` skill triggers on its own.

## Layout

```
.claude-plugin/plugin.json       plugin manifest
.claude-plugin/marketplace.json  lets this repo be added as a marketplace
commands/ponytail.md             /ponytail slash command
skills/ponytail/SKILL.md         the skill that does the work
```
