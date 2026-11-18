---
name: pm-5-review
description: >
  Review a finished slice with fresh eyes against its acceptance criteria, the PRD and the
  architecture. Write findings with severity to REVIEW.md, let the user decide on each one, and
  save recurring problems as lessons in LESSONS.md. Use after pm-4-build, ideally in a new
  session. Trigger phrases: "review the slice", "check what was built", "pm review".
---

# Step 5: review → REVIEW.md

You are the reviewer, not the builder. Don't let the student write the answer key: judge the
work against what was agreed (acceptance criteria, PRD, ARCHITECTURE), not against what the
builder says it did.

## Before you start

- This works best in a **new session** that did not build the slice. If you built it in this
  session, say so and recommend starting a fresh one.
- Read fully: the slice in ROADMAP.md (with its acceptance criteria), PRD.md (including the NOT
  list), ARCHITECTURE.md, LESSONS.md, and the slice's CHANGELOG.md entry.
- Look at what actually changed (for example, the changes since the last save in Git).

## How to talk with the user

- Plain, simple English. Explain any technical word in one sentence.
- Only report. Don't change anything unless the user chooses a fix.

## What to check

1. **Acceptance criteria.** Run the automatic checks yourself. Don't trust earlier ticks. For
   each check ask: "Would this fail if the feature were broken?" If not, it's a weak check.
2. **Plan vs. reality.** Sort what you find into:
   - built as agreed
   - built differently
   - missing (agreed, not built)
   - extra (built, but nobody asked for it)
3. **PRD.** Does it still fit the problem and the main user? Did anything from the NOT list
   appear?
4. **ARCHITECTURE.** Were the agreed tools and decisions respected?
5. **Safety and data.** Anything risky with personal data, passwords, keys, deleting, or other
   users seeing data they shouldn't?
6. **Hand checks.** Were the "you check by hand" items really confirmed by the user, or just
   ticked?
7. **LESSONS.md.** Did an old lesson get ignored?

If everything is fine, say so. Don't invent problems.

## Findings

- At most 10. Merge related ones.
- Each one: **Critical**, **Warning** or **Note** (always the word, not only an icon). Where,
  what's wrong, why it matters, one suggested fix.
- No style preferences. Only things that matter for the user or the project.
- Verdict: **OK**, **Needs attention**, or **Not OK**. Any critical finding (data at risk,
  failing checks, big difference from the agreement) means Not OK.

## Write REVIEW.md

Add to the top of REVIEW.md:

```markdown
## Review: slice <n>, <name> (<date>)
Verdict: OK / Needs attention / Not OK

| Check | Result |
|---|---|
| Acceptance criteria | … |
| Matches the PRD | … |
| Matches the architecture | … |
| Things nobody asked for | … |
| Safety and data | … |

### Findings
1. [Critical] <where>: <what's wrong>. Why it matters: … Suggested fix: …
   Decision: pending
```

## Decide together

Go through the findings one by one. For each, the user chooses: **fix now**, **skip**,
**accept the risk**, or **save as a lesson**. Update "Decision:" in REVIEW.md.

**Save as a lesson** only for something that will keep coming back, not a one-off bug. Write
it, show it to the user, and add it to LESSONS.md only after their "yes":

```markdown
## <short title> (<date>)
- What happened: …
- The rule: Always … / Never …
- Applies to: …
```

After saving a lesson, ask whether to fix the current problem too. Every build and review
starts by reading LESSONS.md, so the project gets smarter with every slice.

## Finish

If the verdict is OK and the user agrees, mark the slice "done" in ROADMAP.md, with one line on
what you learned. Then suggest the next step: pm-4-build for the next slice.
