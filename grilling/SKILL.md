---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea, asking each round's questions as selectable AskUserQuestion forms (recommended option first). Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled: the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask the whole frontier in one round, giving your recommended answer for each. Then wait for the user's answers before the next round.

## Asking a round

- Each round, ask the frontier questions with the AskUserQuestion tool, not markdown text.
- AskUserQuestion takes max 4 questions per call. If the frontier has more than 4, ask the 4 most foundational first, then the rest in follow-up calls within the same round before recomputing.
- Each question has 2-4 options. The recommended option is FIRST and its label ends with " (Recommended)". Each option's description gives the trade-off in 1 sentence. The user can always pick "Other" (built in), so don't add an "Other" option.
- `header`: a chip label of 12 characters or fewer.
- Use the option `preview` field when options are concrete artifacts worth comparing side by side (code snippets, ASCII UI mockups, config, diagrams). Don't use previews for simple preference questions.
- Use `multiSelect: true` only when the choices are genuinely non-exclusive.
- Before the tool call, print at most 1-2 lines of context if a question depends on a fact you found. The dialog may hide prior text, so each question must stand alone and name what it's about.
- Don't ask the user for facts you can look up yourself.

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), look it up yourself inline (or via a sub-agent only if the user's instructions allow it during planning). Questions downstream of an unfound fact wait for it; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.
