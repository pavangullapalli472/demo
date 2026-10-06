---
name: ponytail
description: Tie up loose ends before finishing a task. Use when the user asks to wrap up, finish, clean up, or check for leftovers before committing — finds TODO/FIXME markers, stray debug output, commented-out code, and uncommitted or untracked files in the changed code.
---

# Ponytail — tie up loose ends

Gather the loose ends in the current work, report them, and offer to fix them.

## Steps

1. **Find what changed.** Run `git status --porcelain` and `git diff HEAD` (or `git diff` if there is no `HEAD` yet). Focus only on changed and untracked files; do not audit the whole repo.
2. **Scan the changed lines** for:
   - `TODO`, `FIXME`, `XXX`, `HACK` markers added in this change
   - Debug output: `console.log`, `print(`, `debugger`, `dbg!`, `fmt.Println`, `var_dump`, and similar
   - Large blocks of commented-out code
   - Merge conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
   - Secrets or credentials that look accidentally committed (keys, tokens, `.env` files)
3. **Check the tree:** untracked files that look like they belong in the change, and stray files that shouldn't be committed (build output, logs, editor swap files).

## Report

Give a short checklist grouped by category, each item as `file:line — what was found`. If nothing turned up, say so in one line.

Then ask before changing anything. Never delete code, files, or markers without the user's go-ahead.
