# Claude & Claude Code: Getting Started and Going Deeper

> A detailed guide to getting the most out of Claude Enterprise and Claude Code.

This document complements the [AI Resources Guide](ai-resources-guide.md) with deeper coverage of Claude and Claude Code — installation, configuration, effective usage tips, and links to learning resources.

## Claude Enterprise

### What Claude Is Good At

Claude is Anthropic's AI assistant. It has particular strengths in:

- **Long-document analysis** — Claude can process very long documents and maintain context across them
- **Nuanced writing** — strong at matching tone, style, and audience expectations
- **Careful reasoning** — excels at tasks requiring step-by-step logic, analysis, and weighing trade-offs
- **Following complex instructions** — handles multi-part requests with detailed constraints well

### Getting Started with Claude

1. Request access via ConductorOne (through [Okta](https://thg.okta.com)). Note: we have 100 seats and there is currently a waiting list.
2. Once approved, log in at [claude.ai](https://claude.ai) in your browser, or download the native app for [macOS](https://claude.ai/download/mac) or [Windows](https://claude.ai/download/windows)
3. Start a new conversation and try a task from your day-to-day work

### Claude Projects

Projects let you organise context, files, and instructions into reusable workspaces. This is useful when you:

- Work on a recurring task that needs the same background context each time
- Want to upload reference documents (brand guidelines, specs, data) that Claude can draw on across conversations
- Need to set custom instructions that apply to all conversations within a project

To create a project, click **Projects** in the Claude sidebar and follow the prompts.

### Tips for Using Claude Effectively

**Give Claude a role and context.** Start conversations by explaining who you are, what you're working on, and what good output looks like. For example: "I'm a content manager writing product descriptions for lookfantastic. The tone should be warm, aspirational, and beauty-focused."

**Upload reference material.** Claude works best when it has concrete examples, documents, or data to work with. Upload your brand guidelines, previous reports, or sample outputs.

**Use Projects for recurring work.** If you find yourself re-explaining context at the start of every conversation, create a Project with your standard instructions and reference files.

**Break complex tasks into steps.** Rather than asking Claude to do everything at once, work through it in stages — outline first, then draft, then refine.

**Ask Claude to critique its own work.** After getting a first draft, ask "What's weak about this?" or "What would a sceptical reader push back on?" Claude is good at self-critique.

---

## Claude Code

Claude Code is an agentic coding tool that reads your codebase, edits files, runs commands, and integrates with your development tools. It's available in your terminal, IDE, desktop app, and browser.

### Before You Start

- Make sure you are on the **corporate network or VPN** — many installation issues are caused by being off-network
- Have your **THG Okta credentials** ready (the same login you use for email)
- The setup takes around 15–20 minutes on Mac, 20–30 minutes on Windows

### Installation via Unbound Gateway

For company-managed access via Unbound Gateway, Claude Code is installed as a custom package. This is the recommended route for most employees.

#### Step 1: Request access to Unbound

1. Go to [thg.conductor.one](https://thg.conductor.one) (or find ConductorOne via [Okta](https://thg.okta.com))
2. Search for **Unbound** and request access — approval is usually instant

#### Step 2: Get your API key

1. Go to [ai.thg.dev](https://ai.thg.dev) and log in with Okta (you can also find it as the **ai.thg.dev** tile in Okta)
2. Copy your personal API key — keep it private, do not share it in Slack, email, or documents

#### Step 3: Install prerequisites

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

#### Step 4: Install Claude Code

```bash
npm install -g unbound-claude-code
```

If you see certificate or SSL errors, run the following fix (common on corporate machines):

```bash
curl -LsSf https://raw.githubusercontent.com/aberoham/fuwarp/main/fuwarp.py -o fuwarp.py && chmod +x ./fuwarp.py && ./fuwarp.py --fix
```

Then retry the install command.

#### Step 5: Launch Claude Code

Always launch from inside a specific project folder — not your home directory:

```bash
cd your-project
unbound-claude-code
```

The first time you run it, paste your API key from Step 2. Claude Code will remember it for future sessions.

### Installation via Claude Max

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

### Other Environments

#### VS Code / Cursor

Search for "Claude Code" in the Extensions view (`Cmd+Shift+X` on Mac, `Ctrl+Shift+X` on Windows/Linux) and install it. Then open the Command Palette (`Cmd+Shift+P` / `Ctrl+Shift+P`), type "Claude Code", and select **Open in New Tab**.

#### JetBrains IDEs

Install the [Claude Code plugin](https://plugins.jetbrains.com/plugin/27310-claude-code-beta-) from the JetBrains Marketplace (works with IntelliJ IDEA, PyCharm, WebStorm, and others).

#### Desktop App

A standalone app for running Claude Code outside your IDE. Download from:

- [macOS](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect) (Intel and Apple Silicon)
- [Windows](https://claude.ai/api/desktop/win32/x64/exe/latest/redirect) (x64)

#### Web

Run Claude Code in your browser with no local setup at [claude.ai/code](https://claude.ai/code).

### Access and Cost

There are two ways to use Claude Code at the company:

- **Light use (via Unbound Gateway):** Capped at \$50/month. Good for occasional use and getting started. Request access to Unbound Gateway via ConductorOne.
- **Heavy use (Claude Max):** If you hit the \$50 cap regularly, request a personal Claude Max account. Start with the 5x plan (\$100/month, with five times the standard usage allowance), get your manager's approval, and expense it via ExpenseIn. Higher tiers are available if needed.

### Configuration

#### CLAUDE.md Files

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

#### Auto Memory

Claude Code automatically builds memory as it works, saving learnings like build commands, debugging insights, and project patterns across sessions. You don't need to configure this — it happens automatically.

#### Custom Commands (Skills)

You can create custom slash commands to package repeatable workflows your team can share. For example, `/review-pr` or `/deploy-staging`. These are defined as markdown files in your project's `.claude/commands/` directory.

#### Hooks

Hooks let you run shell commands before or after Claude Code actions — for example, auto-formatting after every file edit or running lint before a commit.

### Useful Slash Commands

Once inside Claude Code, these built-in commands are worth knowing:

- `/init` — Sets up Claude Code for your project and helps it understand your codebase
- `/model` — Switch between Claude models
- `/cost` — Shows how many tokens you've used in the session
- `/doctor` — Runs a health check to make sure everything is configured correctly
- `/mcp` — Manage integrations with external tools

### Tips for Effective Use

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

### Context Management

Claude Code works best when it has the right context. Here's how to manage it:

**CLAUDE.md for persistent context.** Anything Claude Code needs to know across every session should go in `CLAUDE.md` — build commands, coding standards, project structure.

**Keep conversations focused.** Start a new conversation when switching tasks. Long conversations with many topic changes can dilute context.

**Point Claude Code to relevant files.** If you know where the problem is, tell it: "The issue is in `src/auth/` — look at `login.ts` and `session.ts`."

**Use Projects for shared team context.** If your team has standard CLAUDE.md files or custom commands, commit them to the repo so everyone benefits.

### MCP (Model Context Protocol)

MCP is an open standard for connecting Claude Code to external data sources. With MCP, Claude Code can:

- Read design docs in Google Drive
- Update tickets in Jira
- Pull data from Slack
- Use your own custom tooling

See the [MCP documentation](https://code.claude.com/docs/en/mcp) for setup instructions.

---

## External Resources

### Courses

Anthropic offers free courses at [anthropic.skilljar.com](https://anthropic.skilljar.com/):

- **Claude 101** — Learn how to use Claude for everyday work tasks, understand core features, and explore resources for more advanced learning
- **Claude Code in Action** — Integrating Claude Code into development workflows
- **AI Fluency: Framework & Foundations** — Core AI concepts and frameworks
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
