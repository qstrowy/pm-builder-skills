---
name: pm-3-slices
description: >
  Cut the PRD into small vertical slices (each one something a user can actually do and test),
  with acceptance criteria written before building, and save them in ROADMAP.md. Use after
  PRD.md (and ideally ARCHITECTURE.md) exist. Trigger phrases: "slice it", "make a roadmap",
  "split into small steps", "pm slices".
---

# Step 3: small slices → ROADMAP.md

A slice is a thin piece through the whole app that a user can actually click and use. Like a
slice of cake: a little of every layer, not one whole layer. "The user can save their first
contact" is a slice. "Build the database" is not.

## Before you start

Read PRD.md and ARCHITECTURE.md fully, and LESSONS.md if it exists. If PRD.md is missing or too
thin to slice (no smallest first use, no must-haves), stop and suggest going back to
pm-1-interview.

## How to talk with the user

- Plain, simple English. Explain any technical word in one sentence.
- Show the full draft first, then ask for changes. Ask at most 2 or 3 questions.

## How to cut slices

- **Vertical, never layers.** Every slice ends with something a user can see or do.
- **Small.** Usually one user action per slice. A slice is too big if it has more than one main
  user action, mixes setup and main features, or carries more than one big unknown. Split it
  into smaller *user results*, not into layers.
- **Slice 1 proves the idea.** The thinnest path through the smallest first use from the PRD.
  Everything after it adds to it.
- **Setup only when needed.** Login, hosting and other plumbing go into the first slice that
  needs them, in the smallest form. "We'll need it eventually" is not a reason.
- **Order by what depends on what.** No dates, no time estimates: with an agent they are rarely
  right.
- **Nothing new.** Every slice must trace back to the PRD. New ideas that come up go to "Parked",
  not into a slice.
- **Blocked by a question?** Mark the slice "blocked" and say who can answer it.

## Acceptance criteria: the answer key, written before building

- Write 3 to 5 checks per slice, as things a user would observe:
  "After saving, the contact appears in the list." Never "function X works".
- Add at least one **unhappy path**: empty input, a duplicate, the wrong person trying to see
  something.
- Pin down vague words. If a criterion says "latest", "duplicate" or "top 3", ask what happens
  in the edge case: "Two contacts with the same name: what should happen?"
- Split the checks into **"the agent can check automatically"** and **"you check by hand"**.
- The expected results come from the PRD and the user. Never from code. A check copied from the
  code always passes, bugs included.
- Once per project, ask: "What worries you most about this breaking?" Use the answer to add
  criteria.

## Write ROADMAP.md

```markdown
# Roadmap: <short name>

## Slices

### Slice 1: <the user can …>
- Status: todo
- What you'll see when it's done: …
- Acceptance criteria:
  - Agent checks: …
  - You check by hand: …
- Needs first: nothing
- Not in this slice: …
- Open question / risk: …

### Slice 2: <the user can …>
…

## Parked (not now)
- … (from the PRD's NOT list, or new ideas)

## Open questions
- … (who can answer)
```

Status values: todo, building, done, blocked.

## Finish

Recommend **one** slice to build first, with a one-line reason (usually slice 1). Ask the user to
read the acceptance criteria: "These are the answer key. Do they describe what you want?"
Suggest the next step: pm-4-build. Do not start it yourself.
