# Claude Consultant Plugin

A quality control layer for Claude Cowork. Track mistakes, enforce verification protocols, and run weekly self-audits to make Claude measurably more reliable over time.

Built by [Sourav Ghosh](https://x.com/souravghosh).

---

## The problem

Claude doesn't remember its mistakes across sessions. Without a feedback loop, the same wrong answers keep coming up. Most users have no system for catching and fixing this — and the longer you ignore it, the more your setup drifts.

## What this plugin does

Creates a dedicated Claude Consultant project in your workspace that gives Claude three jobs:

- **Fix** — diagnose and resolve setup, memory, and performance issues specific to your workspace
- - **Update** — track Claude ecosystem changes and assess what actually requires action
  - - **Protect** — enforce a verification protocol so Claude can't give confident-but-unverified technical recommendations
   
    - ## Installation
   
    - Download `claude-consultant.plugin` from the [Releases](../../releases) page and drag it into Claude Cowork's plugin settings.
   
    - Then open a new chat and run:
   
    - ```
      /claude-consultant-setup
      ```

      This creates the folder structure and `CLAUDE.md` in your workspace. Done.

      ## Commands

      | Command | What it does |
      |---------|-------------|
      | `/claude-consultant-setup` | Creates the Claude Consultant project folder and CLAUDE.md in your workspace |
      | `/claude-consultant-report-issue` | Logs a Claude mistake as a structured issue report |
      | `/claude-consultant-digest` | Reviews pending reports, identifies patterns, proposes CLAUDE.md rule additions |

      ## Daily workflow

      **When Claude gets something wrong:**
      Type `/claude-consultant-report-issue` (optionally add a brief description). Claude writes a structured report to `Claude Consultant/issue-reports/`.

      **Weekly:**
      Type `/claude-consultant-digest`. Claude reads every pending report, identifies patterns, and gives you a prioritised list of rule additions. You review, pick what applies, Claude applies it with your confirmation.

      **Over time:**
      Your `CLAUDE.md` becomes a personalised instruction set built from your actual corrections. Claude gets more reliable for your context — not because the model changed, but because you built a feedback loop.

      ## Customisation

      Edit `Claude Consultant/CLAUDE.md` in your workspace at any time to add rules specific to your setup. The plugin does not overwrite this file after initial setup.

      ## No external services required

      No MCP connections, no API keys, no external dependencies. Works entirely within your Claude Cowork workspace.

      ## Contributing

      Issues and PRs welcome. If you improve the setup — tighter prompts, better digest format, additional commands — open a PR or share what changed.

      See [CHANGELOG.md](CHANGELOG.md) for version history.

      ## License

      MIT — use freely, no attribution required.
