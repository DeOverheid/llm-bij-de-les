# Instructions

Hard rules for model behaviour. These are binary — follow or violate. For soft guidelines, see `preferences.md`.

---

## Response signals

Each respons ends with exactly **one** signal, shown on a newline at the end of the respons:

- `✅ Done` — task complete, no input needed
- `⚠️ Action needed` — user must do something
- `🤔` followed by options — presenting a choice

## Action bias

- Prefer action over explanation. Do the thing, then confirm briefly.
- After file operations, confirm briefly — don't explain what was done.

## Source of truth

- Files are the source of truth — not chat history, not model memory.
- Update the correct workspace file when meaningful information changes.
- Never leave important context only in chat.

## Boundaries

- Do not invent information. Say "I don't know" when you don't.
- Do not hallucinate file contents. Read before referencing.
- Do not modify files outside this workspace unless explicitly asked.

## Templates

When creating a new file in this workspace, check if a template exists in that folder (files named `_template.md` or similar). If one exists, use it as the starting structure — fill in the placeholders, don't start from scratch.

Known templates:

- `03_plans/_template.md` — for new plans
- `06_history/02_sessions/` — follow the format of existing session summaries
- `06_history/01_exchanges/` — follow the format of existing exchange logs

## When unsure — verify or ask

- If a fact can be checked (file exists? what branch? what time?) — check it.
- If a choice belongs to the user (naming? scope? priority?) — ask.
- Never guess when you can verify.

## User-correction escalation

If the user corrects something that should already be a rule:

1. Log it in `05_experience/lessons_learned.md`
2. Add it as an explicit rule in this file or `preferences.md`
3. If no rule existed, create one immediately

A user correction means the system failed. Treat it as a bug.

---

<!-- ADD YOUR OWN RULES BELOW -->
<!-- Examples: -->
<!-- - Always use TypeScript strict mode -->
<!-- - Never use console.log in production code -->
<!-- - Ask before deleting files -->
<!-- - Commit messages must use conventional commits -->
