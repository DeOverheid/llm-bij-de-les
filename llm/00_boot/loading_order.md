# Loading Order

This file defines the exact sequence a new model must follow when entering this workspace. Read only what is needed, in order. Do not scan the full tree.

This workspace (`.llm/`) lives inside a project. The parent directory (`../`) is the project root. All project files are outside this folder.

---

## Step 1 — Boot (always read)

1. `00_boot/loading_order.md` ← you are here
2. `00_boot/system_prompt.md`
3. `00_boot/prompt_keywords.md`

## Step 2 — Profile (always read)

4. `01_profile/identity.md`
5. `01_profile/instructions.md`
6. `01_profile/preferences.md`

## Step 3 — Current state (always read)

7. `02_state/current_state.md`
8. `02_state/next_actions.md`

## Step 4 — Project overview (always read)

9. `04_overview/structure.md` — file/folder tree of the parent project
10. `04_overview/stack.md` — detected tech stack and dependencies

## Step 5 — Conditional reads (only if relevant to the task)

11. `02_state/open_questions.md` — if the task involves unresolved decisions
12. `02_state/inbox.md` — if triaging or planning
13. `03_plans/` — if the task involves project scope or milestones
14. `05_experience/lessons_learned.md` — if a recurring mistake pattern is suspected
15. `05_experience/decisions.md` — if past decisions are relevant
16. `07_skills/_index.md` — scan available skills; use a matching skill if one applies

## Step 6 — History (only if more context is needed)

History is tiered. Read from the top down — stop when you have enough context:

17. `06_history/02_sessions/` — read the most recent session summary first
18. `06_history/01_exchanges/` — only if a summary lacks detail you need

## Step 7 — Deep context (avoid unless summaries are insufficient)

19. `06_history/03_timeline/timeline.md` — high-level event log
20. `05_experience/` remaining files
21. `08_knowledge/` — reference material, last resort

---

## Rules

- **Do not read everything.** Steps 1–4 are mandatory. Steps 5–7 are conditional.
- **Treat files as the source of truth** over assumptions from prior chat or model memory.
- **Do not scan 08_knowledge/ or 09_archive/ unless explicitly needed.**
- **After reading, summarise your understanding** before proceeding with the task.
- **File precedence:** If files conflict: `instructions.md` > `identity.md` > `preferences.md`.
- **Minimum requirements:** This workspace assumes the model can read files and run terminal commands.
## History cascade

History is tiered \u2014 each level is generated from the one below it:

```
01_exchanges (raw data)  \u2192  02_sessions (summaries)  \u2192  03_timeline (one-liners)
```

- **Exchanges** = raw prompt/respons pairs, one file per day. Created during the session.
- **Sessions** = condensed summary per session. Generated from exchanges on `end session`.
- **Timeline** = one-line-per-event high-level view. Updated on `end session` and `checkpoint`.

Always read from the top of the tier (sessions first). Only drill into exchanges if a summary lacks the detail you need.