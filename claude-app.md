# Claude App: Getting Started and Going Deeper

> A detailed guide to getting the most out of Claude Enterprise.

This document complements the [AI Resources Guide](ai-resources-guide.md) with deeper coverage of Claude — what it's good at, how to use Projects, and tips for effective use. For Claude Code (the coding tool), see the [Claude Code Guide](claude-code.md).

## What Claude Is Good At

Claude is Anthropic's AI assistant. It has particular strengths in:

- **Long-document analysis** — Claude can process very long documents and maintain context across them
- **Nuanced writing** — strong at matching tone, style, and audience expectations
- **Careful reasoning** — excels at tasks requiring step-by-step logic, analysis, and weighing trade-offs
- **Following complex instructions** — handles multi-part requests with detailed constraints well

## Getting Started with Claude

1. Request access via ConductorOne (through [Okta](https://thg.okta.com)). Note: we have 100 seats and there is currently a waiting list.
2. Once approved, log in at [claude.ai](https://claude.ai) in your browser, or download the native app for [macOS](https://claude.ai/download/mac) or [Windows](https://claude.ai/download/windows)
3. Start a new conversation and try a task from your day-to-day work

## Projects

Projects are self-contained workspaces with their own chat histories and knowledge bases. They let you organise context, files, and instructions so that every conversation within a project starts with the same foundation.

### When to Use Projects

- **Recurring tasks** — You do the same type of work regularly and need the same background context each time (e.g., writing product descriptions, reviewing content against brand guidelines)
- **Shared knowledge** — You want to upload reference documents (brand guidelines, specs, data) that Claude can draw on across multiple conversations
- **Custom instructions** — You need to set specific instructions that apply to all conversations within a project (e.g., "Always write in UK English", "Follow our SEO guidelines")

### How to Create a Project

1. Click **Projects** in the Claude sidebar
2. Give your project a name and description
3. Add **project instructions** to define how Claude should behave (tone, format, focus areas)
4. Upload **knowledge files** — documents, guidelines, data that Claude should reference
5. Start a new conversation within the project

### Sharing Projects

With Claude Enterprise, you can share projects with colleagues:

- Share with specific people by email, or make a project available to everyone in the organisation
- Set permission levels: **Can use** (view and chat) or **Can edit** (modify instructions and add files)
- Shared projects appear under the **Shared with me** tab in the sidebar

### Tips for Projects

- **Keep knowledge focused.** A project with 3 highly relevant documents performs better than one with 30 loosely related ones.
- **Write clear instructions.** Be specific about the role, tone, format, and boundaries. For example: "You are a returns policy specialist for lookfantastic. Only answer questions covered by the uploaded policy documents."
- **Update documents when they change.** A project using last year's brand guidelines will give last year's answers.
- **Create separate projects for distinct tasks.** Don't overload one project — a "Product Descriptions" project and a "Brand Review" project will each work better than a single "Content" project trying to do both.

## Artifacts

Artifacts are standalone pieces of content that Claude creates in a dedicated panel alongside the conversation. Instead of generating a long document inline in the chat, Claude places it in an artifact where you can view, edit, and download it separately.

### What Claude Creates as Artifacts

Claude automatically creates an artifact when content is substantial (typically over 15 lines), self-contained, and something you're likely to reuse or edit. This includes:

- **Documents** — reports, proposals, guides, emails (in Markdown or plain text)
- **Code** — scripts, functions, configuration files
- **Websites and apps** — HTML pages, interactive React components
- **Visual content** — SVG images, diagrams, flowcharts
- **Spreadsheet-ready content** — tables and data formatted for export

### Working with Artifacts

**Iterate through conversation.** Ask Claude to modify an artifact: "Make the introduction shorter", "Add a section on pricing", "Change the tone to be more formal". Claude updates the artifact in place.

**Version history.** You can switch between previous versions to compare changes or go back to an earlier draft.

**Multiple artifacts.** Claude can work with several artifacts in the same conversation. You can tell it which one to update.

**Export.** Copy content to your clipboard, view the underlying code, or download the file for use elsewhere.

### When Artifacts Are Useful

- **Drafting documents** — Ask Claude to write a report or proposal, then refine it through conversation. The artifact keeps the document separate from your back-and-forth discussion.
- **Creating templates** — Build reusable templates for emails, reports, or presentations that you can download and adapt.
- **Prototyping** — Have Claude build a quick interactive prototype or data visualisation you can preview immediately.
- **Generating structured content** — Product descriptions, FAQ pages, or other content that benefits from being viewed as a finished document rather than chat output.

## Cowork

Cowork brings Claude's agentic capabilities to the Claude desktop app for complex, multi-step work. Instead of responding to prompts one at a time, Claude can take on extended tasks and execute them on your behalf — reading and writing files on your machine, creating professional documents, and coordinating multiple workstreams in parallel.

### What Cowork Can Do

- **Work with your local files.** Claude can read from and write to files on your computer directly, without manual uploads or downloads.
- **Create professional deliverables.** Generate Excel spreadsheets with working formulas, PowerPoint presentations, formatted documents, and more.
- **Break down complex tasks.** Claude analyses your request, creates a plan, breaks work into subtasks, and coordinates parallel workstreams to complete them.
- **Run scheduled tasks.** Set up recurring tasks that run automatically while your desktop app is open — daily reports, regular data processing, etc.
- **Work from your phone.** Pro and Max subscribers can message Claude from mobile, with work executing on the desktop using your local files.

### How It Works

Cowork runs in an isolated virtual machine environment on your computer, separate from your operating system. Claude requires your explicit permission before permanently deleting any files.

To use Cowork, open the Claude desktop app and start a Cowork session. You can set standing instructions in **Settings > Cowork** (preferred tone, output formats, role context) and add folder-specific instructions for particular projects.

### Plugins

Plugins bundle skills, connectors, and sub-agents into packages tailored for specific roles or teams — like sales, legal, or finance. They customise how Claude operates within your workflow.

### Things to Know

- Cowork requires the **Claude desktop app** (macOS or Windows) and a paid subscription (Pro, Max, Team, or Enterprise)
- The desktop app must remain open during task execution
- Cowork uses significantly more tokens than standard chat due to its computational intensity
- Cowork activity is currently not captured in Audit Logs, Compliance API, or Data Exports — do not use it for regulated workloads

## Tips for Using Claude Effectively

**Give Claude a role and context.** Start conversations by explaining who you are, what you're working on, and what good output looks like. For example: "I'm a content manager writing product descriptions for lookfantastic. The tone should be warm, aspirational, and beauty-focused."

**Upload reference material.** Claude works best when it has concrete examples, documents, or data to work with. Upload your brand guidelines, previous reports, or sample outputs.

**Use Projects for recurring work.** If you find yourself re-explaining context at the start of every conversation, create a Project with your standard instructions and reference files.

**Break complex tasks into steps.** Rather than asking Claude to do everything at once, work through it in stages — outline first, then draft, then refine.

**Ask Claude to critique its own work.** After getting a first draft, ask "What's weak about this?" or "What would a sceptical reader push back on?" Claude is good at self-critique.

---

## External Resources

### Courses

Anthropic offers free courses at [anthropic.skilljar.com](https://anthropic.skilljar.com/):

- **Claude 101** — Learn how to use Claude for everyday work tasks, understand core features, and explore resources for more advanced learning
- **AI Fluency: Framework & Foundations** — Core AI concepts and frameworks

### Blog and Product Updates

- [Anthropic blog](https://www.anthropic.com/blog) — Product announcements, research, and best practices
- [Anthropic YouTube channel](https://www.youtube.com/@anthropic-ai) — Product demos, tutorials, and talks
