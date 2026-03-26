---
name: next-move-partner
description: Use when you want to know what design move to make next — unclear where to focus or what's been missed
---

## 1. Scan

Scan CWD for all design artifacts:

- `thinking/` session notes
- `research/` findings
- `brief-*.md` problem briefs
- `concept-*.md` concept explorations
- `wireframes-*.md` wireframes
- `test-results-*.md` user test results
- `personas-*.md` persona definitions
- `scope-*.md` scoping documents
- `pitch-*.md` / `ticket-*.md` pitch artifacts
- READMEs, docs, plans, tickets, or other project context

Read each artifact's title and opening section — enough to know what it covers, not a deep read. Note what exists, what's missing, and what looks stale (e.g., a brief that predates significant thinking sessions).

## 2. Status map

Present a compact status map. One line per artifact category, showing what exists and its state:

```
Thinking    2 sessions (auth-flow, onboarding-risks)
Research    1 finding (competitor-patterns)
Brief       1 (onboarding-flow) — aligns with latest thinking
Concepts    None
Wireframes  None
Testing     None
Scoping     None
Pitches     None
```

Keep it tight — this is a glanceable dashboard, not a report.

## 3. Recommend

Based on the status map, recommend the **single highest-value next move** with brief reasoning. Follow a natural design progression but respond to the actual state, not a rigid sequence:

- Brief exists but no concepts? Ideation gives you directions to evaluate.
- Concepts exist but assumptions are untested? A thinking session on the riskiest bet would help.
- Wireframes exist but haven't been validated? User testing would surface problems before you scope.
- Design is validated but not scoped? Scoping breaks it into buildable pieces.
- Work is scoped but stakeholders haven't bought in? A pitch gets alignment.

Name the specific skill to invoke and suggest input — e.g., "Run `/ideation-partner` with the onboarding brief as input."

If the user has a different instinct, respect it. This skill advises — it doesn't dictate.

**Anti-pattern: "I already know what's next."** The value isn't confirming your plan — it's surfacing what the status map reveals that you aren't seeing. If you skip the scan, you build on stale context or miss that an artifact has drifted out of alignment.

## Rules

- Be direct. Status map + one recommendation + suggested invocation. No preamble.
- This is a diagnostic, not a workflow. Fast in, fast out.
- Don't deep-read artifacts — skim titles and structure to assess completeness.
- If nothing exists yet, say so and recommend starting with `/thinking-partner` to frame the problem or `/ideation-partner` if the problem is already clear.
- If multiple moves are equally high-value, say so and let the user choose. Don't force a single recommendation when the situation is genuinely ambiguous.

$ARGUMENTS
