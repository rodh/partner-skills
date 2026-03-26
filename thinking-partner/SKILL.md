---
name: thinking-partner
description: Use when you need to reason through a decision, understand a problem, explore a hunch, or compare options — works with or without existing project context
---

## 1. Read context

Scan CWD for context related to the topic: code, docs, existing `topics/*/thinking-*.md` sessions, `topics/*/research-*.md` artifacts, plans, and recent commits. Read what's relevant — don't deep-read everything. Note what exists and what's absent; both inform the Frame. If the user references specific files, prioritize those.

## 2. Frame

Detect the thinking pattern from `$ARGUMENTS` and context.

**Orient ("help me understand this ticket/problem"):**
- Triggered by: ticket content, task descriptions, "what is this asking" questions, or raw context with no existing work.
- If substantial research is needed, suggest `/research-partner` to investigate separately. Lightweight inline lookups (quick definitions, fact checks) can stay within Orient.
- **Output:** scoped problem statement with initial level-of-effort signal

**Hunch ("something feels off"):**
- Present compact state summary (one sentence per relevant file/area), then ask "what's nagging you?"
- One question per message. Allow 1-2 rounds to get from vague → specific. Surface tensions as options if they can't articulate it.
- **Output:** a precise statement of the issue

**What-if ("what if we tried..."):**
- Restate the idea as a testable proposition
- One quick check: "Is that a fair restatement?" (skip if clearly accurate)
- **Output:** the proposition to trace

**Decision ("should we X or Y"):**
- Acknowledge the options. If only one stated, ask for the alternative.
- Frame as "[X] vs [Y] given [relevant context]"
- **Output:** the framed decision

**STOP after Frame** (Orient/Hunch/What-if/Decision only). Present the framed output and wait for the user to confirm or adjust before proceeding to Think.

If ambiguous, ask one interactive question (`AskUserQuestion` or `requestUserInput`): **A. Understand something** (orient), **B. Surface something** (hunch), **C. Explore a what-if**, **D. Decide between options**. If the request is primarily research-oriented ("look into X", "how does Y work"), redirect to `/research-partner`.

## 3. Think

**Orient pattern — three-part analysis:**

1. **Breakdown** — decompose the problem into constituent parts, name each clearly
2. **Landscape** — what exists already, what's new, what's uncertain. Integrate any external research.
3. **Effort assessment** — what level of engagement each part warrants (light touch vs. deep dive)

End with 2-3 labeled next moves reflecting the actual situation, not a generic menu.

**Hunch/What-if/Decision patterns — four-part analysis:**

1. **What the evidence says** — pull relevant content from files/context, quote specific lines/sections
2. **What's at stake** — concrete downstream effects if we go one way vs another
3. **Strongest argument for each side** — steel-man all positions (even for hunches: steel-man "it's actually fine" vs "there's a real problem")
4. **What we'd need to believe** — the assumption each direction rests on

**Dialogue pacing:**

| Pattern | Delivery | Exchanges |
|---------|----------|-----------|
| Orient | Full breakdown, then ask what to dig into | 1 (focused) to 2-3 (complex) |
| Hunch | Pause after tensions, check in after each analysis piece | 2-3 |
| What-if | Four-part analysis as one block, then "worth pursuing or dead end?" | 1 |
| Decision | Four-part analysis as one block, then "which way are you leaning?" Pressure-test before Act. | 1 |

Each pause = **stop and wait** — do not continue to the next phase in the same message. Prefer labeled options (A/B/C) over open-ended questions.

## 4. Act

If thinking leads to file changes: list each file and proposed change, get approval per file via interactive question (`AskUserQuestion` or `requestUserInput`) (approve / reject / modify), then apply.

If no changes needed: skip to Capture.

## 5. Capture

Write a session note to `topics/<topic>/thinking-YYYY-MM-DD-<slug>.md`, where `<slug>` is 2–4 hyphenated words derived from the framed question (e.g., `topics/auth-tokens/thinking-2026-03-24-auth-token-expiry.md`).

Start the file with an H1 title in the format `# Thinking: <title>`, where `<title>` summarizes the session content. Example: `# Thinking: Should we expire auth tokens on role change?`

- **Type:** Thinking
- **Session summary** — 2-3 sentences
- **Trigger** — the user's opening statement
- **Frame** — the precise question or decomposition arrived at
- **Analysis** — key points from Think (compressed)
- **Resolution** — what was decided or understood
- **Changes made** — what was modified, or "None"
- **Open threads** — anything surfaced but not resolved

**Anti-pattern: "This doesn't need structured thinking."** The temptation to skip framing is strongest on decisions that feel obvious. Those are exactly where unexamined assumptions do the most damage. The frame can be two sentences, but it must exist.

## Topic Folder Convention

All artifacts are saved under `topics/<topic>/`. Before the first save in a session:

1. Scan `topics/` for existing folders.
2. If one matches the current topic, propose reusing it: "I'll save to `topics/<folder>/` — sound right?"
3. If none match, derive a 2-4 word hyphenated folder name from the topic and propose it.
4. Create the directory on user confirmation.

All file paths in this skill use `topics/<topic>/` as the root.

## Rules

- Be direct. No preamble, no filler. Labeled bullets for discrete items, prose for narrative.
- Quote sources, don't summarize — the user needs to see exactly what you're referencing.
- Steel-man all positions. Don't lead the user toward a predetermined answer.
- Prefer labeled options (A/B/C) over open-ended questions — reduces friction and shows you've done enough thinking to enumerate the space.
- YAGNI: if thinking resolves without needing file changes, don't invent changes to make.
- If thinking reveals an upstream problem, name it. Don't patch downstream files to work around it.
- Don't skip thinking because it "seems obvious." The user invoked it for a reason.

$ARGUMENTS
