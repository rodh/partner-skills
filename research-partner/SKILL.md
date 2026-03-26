---
name: research-partner
description: Use when you need to research a topic — competitor patterns, technical approaches, industry practices, or focused factual questions
---

## 1. Scope

Ingest the research question from `$ARGUMENTS`. Scan `topics/` for existing `research-*.md` artifacts that overlap — if a prior artifact already answers the question, surface it instead of re-researching.

Classify depth:

- **Quick lookup** — factual question with a clear answer. Skip straight to Investigate (no stop).
- **Landscape survey** — mapping approaches, competitors, or patterns across a space.
- **Deep dive** — thorough investigation of a specific technique, tool, or domain.

For **landscape** or **deep dive**: present the scope (what's in, what's out, breadth of investigation) and **stop — wait for user confirmation** before proceeding.

For **quick lookup**: proceed directly to Investigate with no stop.

## 2. Investigate

Conduct research using available tools — web search, web fetch, codebase scan, whatever fits the question. Work iteratively: follow leads, cross-reference sources, and fill gaps.

Organize findings by **theme or approach**, not by source. Group related information together even if it came from different places.

## 3. Synthesize

Structure findings into a summary:

- **Question** — the research question as scoped
- **Findings** — organized by theme, with specifics (names, numbers, patterns — not vague summaries)
- **Key takeaways** — 2-5 bullets distilling what matters most
- **Implications for this project** — if project context exists, connect findings to the current work
- **Sources** — where applicable

Present the summary. **Stop and wait** for the user to confirm before saving.

## 4. Save

Save to `topics/<topic>/research-<slug>.md` with:

- H1 title: `# Research: <title>` summarizing the research question
- Date
- Full structured findings from Synthesize

The artifact must be **self-contained** — readable without conversation context.

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
- Organize by theme, not by source. The user cares about the landscape, not which URL said what.
- Quick lookups should be fast — don't over-structure a factual answer.
- Landscape surveys and deep dives earn their depth. Don't pad with shallow findings to look thorough.
- If research turns up nothing useful, say so. Don't dress up thin results.
- Artifacts must be self-contained. Someone reading the file with no conversation context should understand the findings.

$ARGUMENTS
