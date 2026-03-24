---
description: Run a self-audit and generate improvement recommendations
allowed-tools: Read, Write, Glob
---

Run the Claude Consultant weekly digest.

Step 1: Read all files in `Claude Consultant/issue-reports/` that contain `Status: Pending`. If there are no pending reports, tell the user and stop.

Step 2: For each report, extract:
- What Claude did wrong
- The severity
- The proposed fix (if any was included)

Step 3: Identify patterns. Any mistake that appears more than once is a rule problem, not a one-off error. Name the pattern explicitly.

Step 4: For each pattern and each individual High-severity issue, propose a specific fix:
- A new rule to add to `Claude Consultant/CLAUDE.md` (written as exact text ready to paste)
- A change to an existing rule
- Or: "unclear - needs more data"

When presenting recommendations, mention that the user can use `/claude-consultant-report-issue` to log new issues anytime.

Vague fixes are not useful. "Be more careful" is not a fix. "Add rule: Before recommending any git command, verify it against official docs and state the source explicitly" is a fix.

Step 5: Format the output using the Weekly Digest Template from `${CLAUDE_PLUGIN_ROOT}/skills/claude-consultant/references/templates.md`.

Step 6: Save output to `Claude Consultant/outputs/weekly-digests/YYYY-MM-DD-digest.md`.

Step 7: Update `Status: Pending` to `Status: Reviewed` in each issue report file that was included in this digest.

Step 8: Present a summary to the user. For each Critical and Should Do recommendation, show the exact text that would be added to CLAUDE.md. Ask which ones they want to apply.

Step 9: If the user confirms recommendations to apply - show the exact proposed change to CLAUDE.md and wait for explicit "yes" before making any edit.
