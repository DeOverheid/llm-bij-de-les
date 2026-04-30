# Session End Checklist

Run this when the user prompts `end session`.

---

## 1. Write session summary

- Read today's exchange log from `06_history/01_exchanges/`
- Write a summary to `06_history/02_sessions/YYYY-MM-DD-session-summary.md`
- Cover: what was done, key decisions, what's next
- Add a one-line entry to `06_history/03_timeline/timeline.md`

## 2. Update state files

- `02_state/current_state.md` — reflect what is active or shifted
- `02_state/next_actions.md` — concrete next steps only

## 3. Check for unwritten context

- Is any durable insight still only in chat? Write it to the correct file.
- Did decisions get made? Add to `05_experience/decisions.md`.

## 4. Git

- Check if working directory is clean (`git status`)
- If uncommitted changes exist, commit and push
