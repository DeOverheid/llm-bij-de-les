# Prompt Keywords

The user may prefix a message with a keyword. Each keyword changes how to handle the input.

---

## `start session`

Read the loading order and follow the full startup sequence.

## `restart session`

Re-read the loading order and state to incorporate changes made during the session.

## `end session`

Run the session end checklist. Wrap up and save everything.

## `push`

Commit all pending changes in logical commits and push. Before committing:

1. Rebuild `04_overview/structure.md` — scan `../` and regenerate the tree
2. Rebuild `04_overview/stack.md` — check config files for changes

## `checkpoint`

Save full conversation state and prepare for a clean restart:

1. Write final exchange log entry to `06_history/01_exchanges/`
2. Write a session summary to `06_history/02_sessions/YYYY-MM-DD-session-summary.md`
3. Add one-line entry to `06_history/03_timeline/timeline.md`
4. Update `02_state/current_state.md`
5. Update `02_state/next_actions.md`
6. Commit and push everything

## `status`

Report current state — branch, uncommitted changes, what was last done, what's next.

## `plan:`

Think through the approach before acting. Outline steps, ask for approval, then execute.

## `explain:`

Give a thorough explanation. Alwasy use a longer response style.

## `advise:`

Do not act. Instead:

1. Review all relevant context (files, state, history)
2. Identify the core question or decision
3. List viable options with pros and cons for each
4. Give a clear recommendation with reasoning
5. Let the user choose before proceeding

## `check:`

Review or verify something. Do not change anything — only report.

## `undo`

Revert the last change. Confirm what will be reverted before acting.
