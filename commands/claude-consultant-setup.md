---
description: Set up the Claude Consultant project in this workspace
allowed-tools: Write, Bash, Read
---

Set up a Claude Consultant quality control project in the current workspace.

Step 1: Check whether `Claude Consultant/` already exists. If it does, tell the user and ask if they want to continue (it will not overwrite existing files).

Step 2: Create this folder structure:
- `Claude Consultant/`
- - `Claude Consultant/issue-reports/`
  - - `Claude Consultant/outputs/`
    - - `Claude Consultant/outputs/weekly-digests/`
     
      - Step 3: Read the CLAUDE.md template from `${CLAUDE_PLUGIN_ROOT}/skills/claude-consultant/references/templates.md` under the "CLAUDE.md Template" heading. Create `Claude Consultant/CLAUDE.md` with that content.
     
      - Step 4: Create `Claude Consultant/issue-reports/.gitkeep` as an empty placeholder so the folder persists in version control.
     
      - Step 5: Tell the user what was created. Keep it to one short paragraph. Mention:
      - - The project is ready
        - - Use /claude-consultant-report-issue any time Claude gets something wrong
          - - Use /claude-consultant-digest to run a weekly self-audit and get improvement recommendations
            - - They can edit Claude Consultant/CLAUDE.md at any time to add rules specific to their setup
