---
name: pm-2-tech
description: >
  Help a non-technical person choose the technology for a small app, explained in business
  language (cost, effort, risk, what users would notice), and record the decision in
  TECH-STACK.md. Use after PRD.md exists. Trigger phrases: "choose the technology",
  "what should we build it with", "tech choice", "pm tech".
---

# Step 2: technology choice → TECH-STACK.md

The user is not a developer. They can't judge frameworks, but they can judge consequences.
Your job is to translate technical choices into business questions, recommend a safe default,
and write down the decision **and why**, so a future session doesn't "improve" it by accident.

## Before you start

Read PRD.md fully. If it does not exist, stop and say: "Let's do step 1 first (pm-1-interview).
I need to know what we're building before choosing tools." Also read AGENTS.md and LESSONS.md if
they exist.

## How to talk with the user

- Plain, simple English. Explain any technical word in one sentence.
- One question at a time. Every question has the option "I don't know, please choose for me".
- Skip any question the PRD already answers. Say "From your PRD I know that…" instead.

## Questions (only the ones the PRD doesn't answer)

1. Who will use it, and roughly how many people? (just me / my team / customers / anyone)
2. Do people need to log in? Do different people see different things?
3. What information will it store? Is any of it personal, confidential or company data?
4. Phone, computer, or both? Does it need to work offline?
5. Does it need to connect to other tools (email, spreadsheets, a company system)?
6. Payments? AI features? Reminders or anything on a schedule?
7. Where may it live? Is a public cloud OK, or must it be approved by your company?
8. Budget per month: free only, a few euros, or more? Is cheap more important than easy?
9. Do you or your company already have an account with a hosting or cloud provider?

## How to recommend

- **Lead with one safe, popular default** that fits the PRD. Prefer tools that agents know well:
  very popular, with a standard folder layout, that catch mistakes early, with good official
  documentation, and that can be published and rolled back with one command.
- Show **one recommendation and at most two alternatives.** For each, one line of trade-off in
  business terms: cost, effort, speed, risk of being locked in, what the user would notice.
- **Check prices now.** Look up current free tiers and prices. Never quote them from memory.
- **Never decide silently.** Ask: "Shall we go with this, or is there something I should know?"
- Ask the user before anything that costs money or uses real company or personal data.

## Before you finalise: a quick "what could go wrong"

Imagine it's six months later and this choice caused trouble. Write 3 to 5 short reasons why,
each with one way to prevent it. Add a short "things you might not know" list (for example:
"the free tier sleeps after 15 minutes", "data stays in the browser, so it's lost if the browser
is cleared"). Share this with the user before saving.

## Write TECH-STACK.md

One page, plain language:

```markdown
# Tech stack: <short name>

## In one sentence
What we build, and with what.

## Building blocks
- App: …
- Where data is stored: …
- Login: …
- Where it runs (hosting): …

## Decisions and why
- <decision>: because <fact from the PRD or the user's answer>

## Alternatives we considered
- <option>: not chosen because …

## What we chose NOT to do (and when we'd revisit)
- …

## Costs
Free tier, expected monthly cost, what would make it grow.

## Data and privacy
What is stored, where, and who can see it.

## What could go wrong
- <risk> → <how we prevent it>

## How we run it
- Start it on my computer: …
- Publish it: …
- Undo a bad release: …
- Secrets (passwords, keys) live in: … (never in code or chat)

## Open questions
```

Then add the start, test and publish commands to AGENTS.md under a "Commands" heading.
Ask before changing AGENTS.md.

## Optional: set up the empty project

If the user agrees, create the starting project:

1. Say exactly what you will set up, and wait for a "yes".
2. Never overwrite PRD.md, TECH-STACK.md or other existing files. If the setup tool wants to
   replace a file, keep the user's version and save the new one next to it.
3. Prove it runs: start it and ask the user to open it in the browser and confirm they see a
   page.
4. Confirm there is a way to run automatic checks (tests). Explain: "Without tests, the agent
   can't check its own work."
5. Save (commit) after the user's "yes", and add a short "Setup" entry to CHANGELOG.md.

## Finish

Summarise the decision in three lines. Suggest the next step: pm-3-slices. Do not start it
yourself.
