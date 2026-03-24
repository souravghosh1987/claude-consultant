# Claude Consultant - Templates

Reference file. Contains all copy-paste templates used by the plugin.

---

## CLAUDE.md Template

Use this when setting up a new Claude Consultant project via `/setup`.

```markdown
# Claude Consultant - Project Instructions

## Purpose

This project is quality control for my Claude Cowork setup. It is not a content or work project. It is infrastructure maintenance.

Three responsibilities:
1. Fix - resolve setup, memory, and performance issues specific to my workspace
2. Update - track Claude ecosystem changes and assess impact on my existing workflows
3. Protect - enforce guardrails so I am not exposed to confident-but-wrong recommendations

---

## Technical Recommendation Protocol (MANDATORY)

Before making any technical recommendation I cannot independently verify, Claude must:

1. Verify first. Never recommend based on general knowledge alone. Check official docs, run a test, or explicitly flag that verification has not happened.
2. State confidence level. Before every technical recommendation: "I've verified this against [source]" OR "I haven't verified this - let me check first."
3. Prefer reversible actions. If there are two paths, choose the one that can be undone unless I explicitly choose otherwise.
4. State the rollback plan for any irreversible action (deleting files, modifying live integrations, rewriting history) before proceeding.

---

## Issue Tracking

When Claude makes a mistake or I correct it:
- Acknowledge what went wrong specifically
- Log it to `issue-reports/` using the Issue Report Template below
- Note the pattern for the rest of this session

## Weekly Digest

On demand (or on a schedule):
- Review all issue reports with Status: Pending
- Identify patterns - any mistake that appears more than once is a rule problem, not a one-off
- Propose specific rule additions or changes to this CLAUDE.md
- Output format: Critical / Should Do / Nice to Have
- Archive output to `outputs/weekly-digests/YYYY-MM-DD-digest.md`
- Update all reviewed issue reports from Status: Pending to Status: Reviewed
- Never edit this CLAUDE.md directly - show proposed changes and wait for explicit confirmation

---

## Issue Report Template

Save to: `issue-reports/YYYY-MM-DD-brief-description.md`

---

# Issue Report: [descriptive title]

**Date:** YYYY-MM-DD
**Session context:** [what task was in progress]
**Severity:** High / Medium / Low
**Status:** Pending

---

## What Claude Did

[Concrete description of the actual behavior - what was said, done, or output]

## What Should Have Happened

[The correct behavior - what was expected or what the rules require]

## Impact

[Actual consequence: rework required, wrong output used, time lost, decision made on bad info. If caught before any damage, say so.]

## Proposed Fix

[Specific CLAUDE.md rule to add, SOP change, or "unclear - investigate in next digest"]

---
```

---

## Weekly Digest Template

```markdown
# Claude Consultant Digest - [YYYY-MM-DD]

**Issues reviewed:** [count]
**Patterns identified:** [count]
**Recommendations:** [count]

---

## Critical

(Caused real damage or high probability of causing damage if not addressed)

- [ ] [Recommendation + proposed CLAUDE.md change]

## Should Do

(Will cause damage eventually if not addressed)

- [ ] [Recommendation + proposed CLAUDE.md change]

## Nice to Have

(Minor quality improvements)

- [ ] [Recommendation + proposed CLAUDE.md change]

---

## Patterns Found

[List any recurring issues - name the pattern, how many times it appeared]

---

## Issues Included

[List of issue report files included in this digest]
```
