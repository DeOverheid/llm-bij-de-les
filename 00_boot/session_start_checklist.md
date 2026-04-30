# Session Start Checklist

Run this sequence at every `start session` or `restart session`.

---

## 1. Read boot files

Follow `00_boot/loading_order.md` Steps 1–4 (mandatory reads).

## 2. Check for first run

If `01_profile/identity.md` still contains setup questions (not filled in):
- Run the setup interview — ask the user each question and fill in their answers
- Once done, confirm the profile is complete

## 3. Scan project (if first time or stale)

- Check if `04_overview/structure.md` exists and has content
- If empty or missing: scan `../` and generate the project tree
- Check if `04_overview/stack.md` exists and has content
- If empty or missing: detect tech stack from config files

## 4. Summarise understanding

Before starting work, briefly state:
- Who the user is (from identity)
- What's currently active (from current_state)
- What the immediate next steps are (from next_actions)

Then ask: "Ready to work. What's the task?"
