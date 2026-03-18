# Claude Code: Getting Started and Going Deeper

> A detailed guide to getting the most out of Claude Code at THG.

This document complements the [AI Resources Guide](ai-resources-guide.md) with deeper coverage of Claude Code — installation, configuration, effective usage tips, and links to learning resources. For the Claude app (the chat assistant), see the [Claude App Guide](claude-app.md).

## What Is Claude Code?

Claude Code is an agentic coding tool that reads your codebase, edits files, runs commands, and integrates with your development tools. It's available in your terminal, IDE, desktop app, and browser.

## Before You Start

- You need to be using a **THG-managed laptop** — many of these instructions won't work correctly on a personal device
- Have your **THG Okta credentials** ready (the same login you use for email)
- The setup takes around 15–20 minutes on Mac, 20–30 minutes on Windows

## Installation via Unbound Gateway

For THG-managed access via Unbound Gateway, Claude Code is installed as a custom package. This is the recommended route for most employees.

### Step 1: Request access to Unbound

1. Go to [thg.conductor.one](https://thg.conductor.one) (or find ConductorOne via [Okta](https://thg.okta.com))
2. Search for **Unbound** and request access — approval is usually instant

### Step 2: Get your API key

1. Go to [ai.thg.dev](https://ai.thg.dev) and log in with Okta (you can also find it as the **ai.thg.dev** tile in Okta)
2. Copy your personal API key — keep it private, do not share it in Slack, email, or documents

### Step 3: Install prerequisites

**Mac:**

Install Homebrew (if you don't have it), then Node.js:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install node
```

**Windows:**

Windows requires Windows Subsystem for Linux (WSL). Open PowerShell as Administrator and run:

```powershell
wsl --install
```

Restart your computer, then set up your Linux username and password when Ubuntu opens. Install VS Code with the WSL extension for the best experience, then install Node.js inside WSL using nvm:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
# Close and reopen the terminal, then:
nvm install --lts
```

### Step 4: Install Claude Code

```bash
npm install -g unbound-claude-code
```

If you see certificate or SSL errors (common on corporate machines due to TLS inspection), run [fumitm](https://github.com/aberoham/fumitm) to automatically detect and fix certificate trust issues:

**macOS / Linux / WSL:**

```bash
python3 <(curl -LsSf https://raw.githubusercontent.com/aberoham/fumitm/main/fumitm.py) --fix --yes
source ~/.zshrc  # or ~/.bashrc
```

**Windows (PowerShell):**

```powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/aberoham/fumitm/main/fumitm_windows.py" -OutFile "fumitm_windows.py"
python fumitm_windows.py --fix
```

Then retry the install command.

### Step 5: Launch Claude Code

Always launch from inside a specific project folder — not your home directory:

```bash
cd your-project
unbound-claude-code
```

The first time you run it, paste your API key from Step 2. Claude Code will remember it for future sessions.

## Installation via Claude Max

If you have a Claude Max account, you can install Claude Code directly using the standard installer:

**macOS / Linux / WSL:**

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Homebrew:**

```bash
brew install --cask claude-code
```

Then launch with:

```bash
cd your-project
claude
```

You'll be prompted to log in with your Claude account on first use.

## Other Environments

### VS Code / Cursor

Search for "Claude Code" in the Extensions view (`Cmd+Shift+X` on Mac, `Ctrl+Shift+X` on Windows/Linux) and install it. Then open the Command Palette (`Cmd+Shift+P` / `Ctrl+Shift+P`), type "Claude Code", and select **Open in New Tab**.

### JetBrains IDEs

Install the [Claude Code plugin](https://plugins.jetbrains.com/plugin/27310-claude-code-beta-) from the JetBrains Marketplace (works with IntelliJ IDEA, PyCharm, WebStorm, and others).

### Desktop App

A standalone app for running Claude Code outside your IDE. Download from:

- [macOS](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect) (Intel and Apple Silicon)
- [Windows](https://claude.ai/api/desktop/win32/x64/exe/latest/redirect) (x64)

### Web

Run Claude Code in your browser with no local setup at [claude.ai/code](https://claude.ai/code).

## Access and Cost

There are two ways to use Claude Code at THG:

- **Light use (via Unbound Gateway):** Capped at \$50/month. Good for occasional use and getting started. Request access to Unbound Gateway via ConductorOne.
- **Heavy use (Claude Max):** If you hit the \$50 cap regularly, request a personal Claude Max account. Start with the 5x plan (\$100/month, with five times the standard usage allowance), get your manager's approval, and expense it via ExpenseIn. Higher tiers are available if needed.

## Configuration

### CLAUDE.md Files

`CLAUDE.md` is a markdown file you add to your project root that Claude Code reads at the start of every session. Use it to set:

- Coding standards and conventions (e.g., "Use TypeScript strict mode", "Follow our REST API naming conventions")
- Architecture decisions and project structure
- Preferred libraries and frameworks
- Build and test commands
- Review checklists

Example `CLAUDE.md`:

```markdown
# Project Guidelines

## Build & Test
- Run tests with `npm test`
- Lint with `npm run lint`
- Build with `npm run build`

## Coding Standards
- Use TypeScript strict mode
- Prefer functional components with hooks
- All API endpoints must have input validation
- Write unit tests for all new functions

## Architecture
- Services go in `src/services/`
- API routes go in `src/routes/`
- Shared types go in `src/types/`
```

### Auto Memory

Claude Code automatically builds memory as it works, saving learnings like build commands, debugging insights, and project patterns across sessions. You don't need to configure this — it happens automatically.

### Custom Commands (Skills)

You can create custom slash commands to package repeatable workflows your team can share. For example, `/review-pr` or `/deploy-staging`. These are defined as markdown files in your project's `.claude/commands/` directory.

### Hooks

Hooks let you run shell commands before or after Claude Code actions — for example, auto-formatting after every file edit or running lint before a commit.

## Useful Slash Commands

Once inside Claude Code, these built-in commands are worth knowing:

- `/init` — Sets up Claude Code for your project and helps it understand your codebase
- `/model` — Switch between Claude models
- `/cost` — Shows how many tokens you've used in the session
- `/doctor` — Runs a health check to make sure everything is configured correctly
- `/mcp` — Manage integrations with external tools

## Tips for Effective Use

**Start with context.** When you open Claude Code in a new project for the first time, ask it to explore the codebase: "Read the README and explore the project structure. Summarise how this project is organised."

**Be specific about what you want.** Instead of "fix this bug", try "The checkout flow throws a 500 error when the cart has more than 10 items. The error log shows a null pointer in `src/checkout/CartProcessor.ts`. Investigate and fix it."

**Let it run commands.** Claude Code can run tests, linters, and build tools. Let it verify its own work: "Write tests for this function, run them, and fix any failures."

**Use it for tedious tasks.** Claude Code excels at the work you keep putting off: writing tests for untested code, fixing lint errors across a project, resolving merge conflicts, updating dependencies, and writing release notes.

**Work with git.** Claude Code can stage changes, write commit messages, create branches, and open pull requests: "Commit my changes with a descriptive message" or "Create a PR for this feature."

**Pipe data in.** Claude Code follows the Unix philosophy — you can pipe logs, diffs, and other data into it:

```bash
# Review changed files for security issues
git diff main --name-only | claude -p "review these changed files for security issues"

# Analyse error logs
tail -f app.log | claude -p "alert me if you see any anomalies"
```

## Context Management

Claude Code works best when it has the right context. Here's how to manage it:

**CLAUDE.md for persistent context.** Anything Claude Code needs to know across every session should go in `CLAUDE.md` — build commands, coding standards, project structure.

**Keep conversations focused.** Start a new conversation when switching tasks. Long conversations with many topic changes can dilute context.

**Point Claude Code to relevant files.** If you know where the problem is, tell it: "The issue is in `src/auth/` — look at `login.ts` and `session.ts`."

**Use Projects for shared team context.** If your team has standard CLAUDE.md files or custom commands, commit them to the repo so everyone benefits.

## MCP (Model Context Protocol)

MCP is an open standard for connecting Claude Code to external data sources. With MCP, Claude Code can:

- Control a browser using [Playwright](https://github.com/microsoft/playwright-mcp)
- Query databases in GCP [link](https://cloud.google.com/blog/products/databases/managed-mcp-servers-for-google-cloud-databases/)
- Use your own custom tooling (talking to internal APIs for example)

See the [MCP documentation](https://code.claude.com/docs/en/mcp) for setup instructions.

## CLI Tools

Claude is good at writing and using command line interface tools, this is often a good way to access APIs and in many cases preferable to MCP. CLI tools can be used in custom skills.

---

## External Resources

### Courses

Anthropic offers free courses at [anthropic.skilljar.com](https://anthropic.skilljar.com/):

- **Claude Code in Action** — Integrating Claude Code into development workflows
- **Introduction to Model Context Protocol** — MCP fundamentals
- **Model Context Protocol: Advanced Topics** — Advanced MCP techniques

### Documentation

- [Claude Code documentation](https://code.claude.com/docs/en/overview) — Installation, configuration, workflows, and reference
- [Claude Code quickstart](https://code.claude.com/docs/en/quickstart) — Walk through your first real task
- [Claude Code best practices](https://code.claude.com/docs/en/best-practices) — Patterns for getting the most out of Claude Code
- [Common workflows](https://code.claude.com/docs/en/common-workflows) — Practical workflow examples
- [CLAUDE.md and memory](https://code.claude.com/docs/en/memory) — Setting up persistent instructions
- [Claude Code settings](https://code.claude.com/docs/en/settings) — Customisation options

### Blog and Product Updates

- [Anthropic blog](https://www.anthropic.com/blog) — Product announcements, research, and best practices
- [Claude Code product page](https://code.claude.com/) — Demos, pricing, and product details

### Video

- [Anthropic YouTube channel](https://www.youtube.com/@anthropic-ai) — Product demos, tutorials, and talks
- [Claude Code introduction](https://youtu.be/Yf_1w00qIKc) — Official getting-started video
- [Advanced Claude Code use cases](https://youtu.be/AJpK3YTTKZ4) — Tips and advanced workflows
- [Matt Pocock's YouTube channel](https://www.youtube.com/@mattpocockuk) — Practical Claude Code tutorials and developer workflows

### Community

- [Simon Willison's Claude Code write-ups](https://simonwillison.net/tags/claude-code/) — Practical insights and experiments from a well-known developer

### Internal Resources

- [THG custom Claude commands](https://github.com/THJoe/claude-commands) — Shared custom commands for THG workflows
- [GCP access guide](https://thehut.atlassian.net/wiki/spaces/DSP/pages/5490081816/AI+Engineering#Access-to-GCP) — For teams using dedicated GCP projects

### GitHub

- [Claude Code repository](https://github.com/anthropics/claude-code) — Installation, issues, and release notes
