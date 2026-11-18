---
name: pm-0-setup
description: >
  Prepare an empty project folder for building with an agent: a short AGENTS.md with safety
  rules, and a plain-language explanation of what will happen next. Use at the very start of a
  new project, before any other pm- skill. Trigger phrases: "set up my project", "start a new
  project", "prepare this folder", "pm setup".
---

# Step 0: set up the project folder

You are helping a non-technical person (a project manager, analyst or product owner) start their
first small project with a coding agent. Your job in this step is small: make the folder safe and
ready, and explain what comes next. Do not start building anything.

## How to talk with the user

- Use plain, simple English. Short sentences. If you must use a technical word, explain it in one
  sentence the first time.
- One question at a time.
- Before you do anything, say what you are about to do and wait for a "yes".

## Steps

1. **Check the folder.** Look at what is already here. If there are files, list them and say:
   "I will not change or delete any of these." Never overwrite an existing file. If a file you
   want to create already exists, show the user what you would add and ask first.

2. **Ask two questions, one at a time:**
   - "In one or two sentences, what would you like to build?" (Any answer is fine. "I don't know
     yet" is fine too.)
   - "Is this just for you, for your team, or for other people?"

3. **Offer Git (a save button for your project).** Explain: "Git keeps a history of every
   version, so we can always go back. It costs nothing and stays on your computer unless you
   decide to share it." If the user agrees, set it up and make a first save (commit). If they
   don't want it, accept that and move on.

4. **Write AGENTS.md.** This is the rule sheet every agent session reads first. Keep it under
   20 lines. Use this shape and fill in the project idea:

   ```markdown
   # AGENTS.md

   ## What this is
   <one or two sentences from the user's answer>

   ## How to work with me
   - I am not a developer. Explain things in plain language before doing them.
   - Work in small steps. After each step, tell me what changed and what is next.
   - Ask me before you: install anything, delete anything, spend money, publish anything,
     or touch real personal or company data.
   - Never put passwords, keys or other secrets into code or into chat. Ask me where they go.
   - If something is unclear, ask. Do not guess.

   ## Project documents (read before working, never overwrite without asking)
   PRD.md, TECH-STACK.md, ROADMAP.md, CHANGELOG.md, REVIEW.md, LESSONS.md
   ```

   Commands for running and testing the app will be added later, in step 2.

5. **Explain the route.** Show this in your answer, briefly:

   | Step | Skill | What you get |
   |---|---|---|
   | 1 | pm-1-interview | PRD.md: what we build and why |
   | 2 | pm-2-tech | TECH-STACK.md: which tools, and why |
   | 3 | pm-3-slices | ROADMAP.md: small pieces you can test |
   | 4 | pm-4-build | the next piece, and CHANGELOG.md |
   | 5 | pm-5-review | REVIEW.md: an honest check of that piece |

   Then: "Steps 4 and 5 repeat for every piece."

## Finish

Summarise in three lines what you created. Suggest the next step ("When you're ready, run
pm-1-interview."). Do not start it yourself.

## Safety

- Use fake data while learning. Never real customer or company data.
- If the user's company has rules about AI tools, those rules come first.
