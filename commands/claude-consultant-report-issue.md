---
description: Log a Claude mistake as a structured issue report
allowed-tools: Write, Read
argument-hint: [optional: brief description of what went wrong]
---

Log a Claude mistake as a structured issue report in the Claude Consultant project.

Step 1: Gather context.
- If $ARGUMENTS is provided, use it as the starting description.
- If the issue is already clear from the current conversation, infer as much as possible without asking.
- Only ask the user for what is genuinely unclear - one message, all questions at once.

What to gather:
- What Claude did (the specific wrong behavior)
- What should have happened (the correct behavior)
- Severity: High (caused rework, wrong output used, decision made on bad info) / Medium (caught before damage) / Low (minor annoyance or style issue)

Step 2: Create the report file at `Claude Consultant/issue-reports/YYYY-MM-DD-[3-word-slug].md`.

Use today's date. The slug should describe the issue in 3-5 words (lowercase, hyphens). Example: `2026-03-19-wrong-technical-recommendation.md`

Use this exact format:

```
# Issue Report: [descriptive title]

**Date:** YYYY-MM-DD
**Session context:** [what task was in progress, or "unspecified"]
**Severity:** High / Medium / Low
**Status:** Pending

---

## What Claude Did

[Concrete description of the actual behavior]

## What Should Have Happened

[The correct behavior]

## Impact

[Actual consequence. If caught before any damage, say so explicitly.]

## Proposed Fix

[Specific CLAUDE.md rule to add, SOP change, or "unclear - investigate in next digest"]
```

Step 3: Confirm in one sentence that the report was saved. Include the filename.

Do not ask for feedback on the report. Do not offer suggestions on prompting. Do not pad the response.
