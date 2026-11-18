---
name: pm-4-build
description: >
  Build exactly one slice from ROADMAP.md: a short plan the user approves, small steps, proof
  that the acceptance criteria pass, and an honest CHANGELOG.md entry with the next step. Use
  when ROADMAP.md exists and the user wants to build the next slice. Trigger phrases:
  "build slice 1", "build the next slice", "let's build", "pm build".
---

# Step 4: build one slice → CHANGELOG.md

Build one slice. Only that slice. Prove it works. Tell the truth about what happened.

## Before you start

Read fully: AGENTS.md, PRD.md, TECH-STACK.md, ROADMAP.md, the last CHANGELOG.md entry and
LESSONS.md (if they exist). If the user didn't say which slice, take the first one with status
"todo" whose "needs first" is done, and confirm it with them.

## How to talk with the user

- Plain, simple English. Explain any technical word in one sentence.
- Before any step that installs, deletes, spends money, publishes or touches real data: ask.

## 1. A short plan, approved first

Write half a page and wait for the user's "yes":

1. **What we build:** the slice goal and its acceptance criteria, as in ROADMAP.md.
2. **What exists now, and what changes.**
3. **Decisions needed:** at most 2 or 3, each with your recommendation and a one-line trade-off.
4. **What we're NOT doing in this slice.**
5. **Steps:** 2 to 4 small steps, each ending in something visible.
6. **How we'll check it:** automatic checks, and what the user checks by hand.

Before showing it, check your own plan: Does it really meet every acceptance criterion, or stop
at 90%? Can any step be removed without missing the goal? What about errors, empty screens and
costs? Did anything from the NOT list sneak back in? If the slice turns out too big, propose
splitting it instead of pushing on.

## 2. Build, in small steps

- **Stay in scope.** Only this slice. No extra features. If something extra seems needed,
  suggest adding it to ROADMAP.md.
- **When reality differs from the plan:**
  - *Small difference* (a name, a minor detail): adapt, and note it in one line.
  - *Big difference* (something missing, a different structure, a new risk): stop and ask:
    "Expected: … Found: … Why it matters: … Options: adapt and continue / skip this part /
    stop and re-plan."
  - Not sure if it's small or big? Treat it as big. A question costs less than a surprise.
- **Don't guess** what the user wants. If it's unclear, ask, or record an open question.

## 3. Prove it

- Run the automatic checks. The slice is done only when they pass.
- **Never weaken, delete or skip a check to make it pass.** Fix the app, not the check.
- At most two attempts to fix a failing check. Then stop and explain in plain words.
- Never tick the "you check by hand" items yourself. Ask the user:
  "Automatic checks passed: … Please check these by hand: … Tell me when you're done."
- Save (commit) only after the user's "yes".

## 4. Write the CHANGELOG.md entry

Add to the top of CHANGELOG.md:

```markdown
## Slice <n>: <name> (<date>)
- What changed (in user terms): …
- Acceptance criteria: <passed / not yet>, and how each was checked
- Small adjustments made: …
- Open questions: …
- Please check by hand: …
- Next step: …
- To restart in a new session, paste: "Read AGENTS.md and the top of CHANGELOG.md, then …"
```

If you had to stop early, start the entry with **"Stopped because: …"**, and describe the real
state honestly. Update the slice status in ROADMAP.md (building / done / blocked).

## Finish

Offer three choices:
1. Review this slice now with pm-5-review (recommended, in a **fresh session**, so the reviewer
   doesn't grade its own work).
2. Continue to the next slice.
3. Stop here. The restart line is in CHANGELOG.md.
