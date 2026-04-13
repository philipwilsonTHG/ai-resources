# Claude App: Getting Started and Going Deeper

> A detailed guide to getting the most out of Claude at THG.

This document complements the [AI Resources Guide](ai-resources-guide.md) with deeper coverage of Claude — the chat interface, Projects, Artifacts, Research, connectors, and more. For Claude Code (the coding tool), see the [Claude Code Guide](claude-code.md).

## What Claude Is Good At

Claude is Anthropic's AI assistant. It has particular strengths in:

- **Long-document analysis** — Claude can process very long documents (up to 200,000 tokens — roughly 500 pages) and maintain context across them
- **Nuanced writing** — strong at matching tone, style, and audience expectations
- **Careful reasoning** — excels at tasks requiring step-by-step logic, analysis, and weighing trade-offs
- **Following complex instructions** — handles multi-part requests with detailed constraints well

## Getting Started with Claude

1. Request access via ConductorOne (through [Okta](https://thg.okta.com)). Note: we have 100 seats and there is currently a waiting list.
2. Once approved, log in at [claude.ai](https://claude.ai) in your browser, or download the native app for [macOS](https://claude.ai/download/mac), [Windows](https://claude.ai/download/windows), [iOS](https://apps.apple.com/app/claude-by-anthropic/id6473753684), or [Android](https://play.google.com/store/apps/details?id=com.anthropic.claude)
3. Start a new conversation and try a task from your day-to-day work

## The Chat Interface

Claude works through a conversational interface — you type a message, Claude responds, and you can continue the conversation to refine the results. Each conversation maintains context, so Claude remembers what you've discussed earlier in the same chat.

If you're new to Claude, begin with a simple conversation to get a feel for it. Then try uploading a document and asking Claude to analyse it. Once you're comfortable, explore Projects for recurring work and Artifacts for creating documents and prototypes.

### What You Can Do in a Conversation

- **Ask questions** — from simple lookups to complex analysis
- **Upload files** — documents, spreadsheets, images, and data for Claude to read and work with
- **Search the web** — Claude can search the web mid-conversation for current information, and will include citations so you can verify sources. You can prompt it explicitly ("search the web for...") or let it decide when a search would help. You can also give Claude a URL and ask it to read the page directly. For deeper investigations, see the [Research](#research) section.
- **Use voice** — on the mobile apps, tap the sound wave icon to speak to Claude and hear voice responses. You can switch between text and voice within the same conversation. Hands-free mode responds to natural pauses; push-to-talk gives you more control in noisy environments.
- **Switch models** — paid plan users can choose between different Claude models using the model selector below the text input. Opus is the most capable, Sonnet balances speed and quality, and Haiku is the fastest for simpler tasks.
- **Start fresh** — begin a new conversation when switching topics, as this helps Claude focus on the task at hand

### Tips for Prompting

**Talk naturally.** Speak to Claude like you would a knowledgeable colleague — conversationally and in plain language.

**Be specific.** The more detail you give, the better the result. Instead of "Write me a report", try "Write a one-page summary of Q3 sales performance for the UK market, highlighting the top 3 growth categories and any areas of concern."

**Give Claude a role and context.** Start by explaining who you are and what you need. For example: "I'm a content manager writing product descriptions for lookfantastic. The tone should be warm, aspirational, and beauty-focused."

**Break complex tasks into steps.** Rather than asking Claude to do everything at once, work through it in stages — outline first, then draft, then refine.

**Upload reference material.** Claude works best when it has concrete examples to work from. Upload your brand guidelines, previous reports, sample outputs, or data.

**Iterate through conversation.** Treat Claude's first response as a draft. Follow up with refinements: "Make the introduction shorter", "Add a section on pricing", "Change the tone to be more formal."

**Ask Claude to critique its own work.** After getting a first draft, ask "What's weak about this?" or "What would a sceptical reader push back on?" Claude is good at self-critique.

**Use Projects for recurring work.** If you find yourself re-explaining the same context at the start of every conversation, create a Project (see below) with your standard instructions and reference files.

### Keep in Mind

Claude is powerful but not infallible. It can occasionally present plausible-sounding information that is incorrect (sometimes called "hallucination"), so always verify important facts — especially numbers, dates, and claims about specific people or events. Claude's training data has a knowledge cutoff, so it may not know about very recent events unless it searches the web. And without connectors set up, Claude has no access to THG's internal systems or data — you'll need to provide that context yourself or connect the relevant tools.

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

For more details, see Anthropic's guide to [creating and managing Projects](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects).

## Memory

Claude automatically builds memory from your conversations, summarising key insights and retaining context across chats. This means Claude can recall what you've discussed before — you don't need to re-explain your role, preferences, or ongoing work every time you start a new conversation.

- **Automatic summaries** — Claude creates a synthesis of key insights from your chat history, updated every 24 hours, which provides context for every new standalone conversation
- **Chat search** — On paid plans, you can ask Claude to search your previous conversations: "What did we decide about the pricing model last week?"
- **Project-specific memory** — Each project maintains its own separate memory, so context stays focused and relevant
- **Privacy controls** — Use incognito chats for temporary conversations that aren't saved to your history or memory. You can manage memory settings in **Settings > Capabilities**.

Memory differs from Projects in that it's automatic and personal — Claude learns from your conversations over time, while Projects are intentionally curated workspaces with uploaded documents and instructions that can be shared with colleagues.

For more details, see Anthropic's guide to [memory and chat search](https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context).

## Artifacts

Artifacts are standalone pieces of content that Claude creates in a dedicated panel alongside the conversation. Instead of generating a long document inline in the chat, Claude places it in an artifact where you can view, edit, and download it separately.

### What Claude Creates as Artifacts

Claude automatically creates an artifact when content is substantial, self-contained, and something you're likely to reuse or edit. This includes:

- **Documents** — reports, proposals, guides, emails (in Markdown or plain text)
- **Code** — scripts, functions, configuration files in any language
- **Websites and apps** — HTML pages, interactive React components with real functionality
- **Visual content** — SVG images, illustrations, icons
- **Diagrams** — flowcharts, sequence diagrams, Gantt charts, and org charts (using Mermaid)
- **Spreadsheet-ready content** — tables and data formatted for export

### Working with Artifacts

**Iterate through conversation.** Ask Claude to modify an artifact: "Make the introduction shorter", "Add a section on pricing", "Change the tone to be more formal". Claude updates the artifact in place.

**Version history.** You can switch between previous versions to compare changes or go back to an earlier draft.

**Multiple artifacts.** Claude can work with several artifacts in the same conversation. You can tell it which one to update.

**Export.** Copy content to your clipboard, view the underlying code, or download the file for use elsewhere.

**Sharing.** With Claude Enterprise, you can share artifacts with colleagues within the organisation. Shared artifacts require team authentication to access — your chat conversation remains private.

### Code Execution and File Creation

When code execution is enabled (**Settings > Capabilities**), Claude can run Python code in a secure sandboxed environment to produce more sophisticated outputs. This powers several practical capabilities:

- **Data analysis** — Upload a CSV or spreadsheet and ask Claude to analyse it, find trends, or build a machine learning model
- **Charts and visualisations** — Generate charts and graphs from your data as downloadable images
- **Professional documents** — Create polished Excel spreadsheets with working formulas, PowerPoint presentations, Word documents, and PDFs
- **File processing** — Transform, clean, or restructure data files

Code execution is enabled by default on free, Pro, and Max plans. On Enterprise plans, organisation owners must enable it in Admin settings first.

### When Artifacts Are Useful

- **Drafting documents** — Ask Claude to write a report or proposal, then refine it through conversation. The artifact keeps the document separate from your back-and-forth discussion.
- **Creating templates** — Build reusable templates for emails, reports, or presentations that you can download and adapt.
- **Prototyping** — Have Claude build a quick interactive prototype or data visualisation you can preview immediately.
- **Data analysis** — Upload a dataset and ask Claude to analyse it, generate charts, or build a model — the results appear as downloadable files.
- **Generating structured content** — Product descriptions, FAQ pages, or other content that benefits from being viewed as a finished document rather than chat output.

### Tips for Artifacts

- **Be specific about what you want.** "Build a budget tracker" is good, but "Build a monthly budget tracker where I can input expenses by category, see a pie chart breakdown, and get a warning when I'm over budget" is better.
- **Describe the end user.** Telling Claude who will use the artifact helps it make appropriate design choices — "this flowchart is for new employees" leads to different results than "this flowchart is for the engineering team."
- **Iterate incrementally.** Add one feature or make one change at a time to catch issues early.
- **Request artifacts when needed.** If Claude responds in the chat instead of creating an artifact, say "Please create that as an artifact."

## Skills

Skills are packages of instructions, scripts, and resources that Claude loads dynamically to improve its performance on specialised tasks. Think of them as expertise packages — they teach Claude how to complete specific tasks in a repeatable way.

### How Skills Work

Claude handles skill selection automatically based on your request. When you ask Claude to create an Excel spreadsheet or a PowerPoint presentation, it loads the relevant skill behind the scenes — you don't need to do anything special. You'll see skills mentioned in Claude's chain of thought as it works.

### Types of Skills

- **Anthropic Skills** — Built-in skills maintained by Anthropic for document creation (Excel, Word, PowerPoint, PDF). These are available to all paid users and invoked automatically.
- **Partner Skills** — Professionally built integrations from partners like Notion, Figma, and Atlassian, available through the Skills Directory.
- **Custom Skills** — Skills you or your organisation create for specific workflows — for example, a skill that applies Myprotein's brand tone of voice to product descriptions, or one that structures meeting notes in a particular format.
- **Organisation-provisioned Skills** — On Team and Enterprise plans, owners can distribute approved skills to all members.

### Creating Custom Skills

The easiest way to create a custom skill is through conversation with Claude itself — no coding required for simple skills:

1. Start a new chat and describe what you want: "I want to create a skill for writing quarterly business reviews"
2. Answer Claude's questions about your workflow, what good output looks like, and any constraints
3. Upload reference materials if you have them — templates, style guides, or examples
4. Download the skill as a ZIP file when Claude has finished
5. Upload it in **Settings > Capabilities > Skills**

Your custom skill will appear alongside Anthropic's built-in skills and Claude will invoke it automatically when relevant. Skill creation is often iterative — expect to test, refine, and re-upload a few times before the skill works exactly as you want.

### Enabling Skills

To use skills, you need **Code execution and file creation** enabled in **Settings > Capabilities**. On Enterprise plans, organisation owners must first enable both code execution and skills in Admin settings before individual members can access them.

### Skills vs Projects

Both features give Claude additional context, but they serve different purposes:

- **Projects** store knowledge — reference materials, specs, and documents that Claude draws on across conversations within that project
- **Skills** define processes — step-by-step procedures that Claude executes consistently whenever the task comes up, across all conversations

The two complement each other. A skill can reference knowledge stored in a project — for example, a "customer call prep" skill might pull from customer profiles uploaded to a project's knowledge base.

For more details, see Anthropic's guide to [working with Skills](https://support.claude.com/en/articles/12512176-what-are-skills).

## Connectors

Connectors let Claude access your apps and services directly — retrieving data, searching documents, and taking actions without you needing to copy and paste information into the conversation. Instead of starting from scratch every time, Claude can work with the same tools and data you use every day.

### Types of Connectors

- **Web connectors** — Link Claude to cloud services like Google Drive, Slack, Gmail, Notion, Asana, Linear, Jira, Stripe, and many more. Available across Claude web, desktop, and mobile.
- **Desktop extensions** — Run locally on your computer through the Claude desktop app, giving Claude access to local files and native applications like Figma.
- **Custom connectors** — Connect Claude to any service via remote MCP servers. Useful for internal tools and APIs. Available on free (limited to one), Pro, Max, Team, and Enterprise plans.

### Setting Up a Connector

1. In any chat, click the **+** button, hover over **Connectors**, and select **Manage connectors** — or go to **Settings > Customize > Connectors**
2. Browse the [Connectors Directory](https://claude.ai/directory) and select the connector you want
3. Click **Connect** or **Install** and complete authentication with the service
4. Review and grant the requested permissions
5. Test the connection with a simple request like "Can you access my Google Drive?"

### What You Can Do with Connectors

**Project management (Asana, Linear, Jira)** — "What are my highest priority tasks due this week?", "Create a new task for reviewing the Q4 budget proposal"

**Communication (Slack, Gmail)** — "Find the email thread where we discussed the vendor contract", "What did the team decide about the timeline in yesterday's Slack discussion?"

**Documentation (Notion, Google Drive, Confluence)** — "Search our documentation for our brand voice guidelines", "Summarise the meeting notes from last week's product review"

**Business tools (Stripe, Salesforce)** — "Show me revenue trends for the past quarter", "List recent transactions over \$1,000"

### Permissions and Security

- **Scoped access** — Permissions are specific to what the connector needs, and you can toggle individual permissions on or off
- **Claude sees what you see** — Claude can only access data you have permission to access; connecting your work email doesn't give Claude access to colleagues' private messages
- **Revocable at any time** — Disconnect a service through Claude's settings or through the third-party service's security settings

On Enterprise plans, organisation owners must enable connectors before individual members can use them. Connectors are limited to private projects, and chats with synced content cannot be shared. Check with your admin which connectors are currently enabled for THG.

For more details, see Anthropic's guide to [using connectors](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities) and browse available integrations in the [Connectors Directory](https://claude.ai/directory).

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
- **Important:** Cowork activity is currently not captured in Audit Logs, Compliance API, or Data Exports — do not use it for regulated workloads

## Research

Research transforms Claude from a conversational assistant into a systematic investigator. Instead of running a single search, Claude conducts multiple searches that build on each other — exploring different angles, cross-referencing sources, and pursuing leads as they emerge. The result is a comprehensive, cited report delivered in minutes rather than the hours it would take manually.

### How It Works

1. **Claude plans its approach** — it breaks down your question, identifies what information it needs, and plans how to investigate from different angles
2. **Claude conducts multiple searches** — it searches the web and any connected integrations (Gmail, Google Drive, Slack, etc.), with each search building on what it has already found
3. **Claude synthesises findings** — it compiles everything into a well-organised report
4. **Claude provides citations** — every claim links back to its source, making it easy to verify and dig deeper

Most reports complete in 5–15 minutes, though more complex investigations can take up to 45 minutes.

### How to Use Research

1. Find the **Research** button in the bottom left of the chat interface
2. Click to enable it — the button turns blue when active
3. Enter your prompt and submit
4. Claude works in the background, showing progress indicators as it searches and analyses

Web search must be enabled for Research to work. Research is available on Pro, Max, Team, and Enterprise plans, and works across Claude web, desktop, and mobile.

### When to Use Research

Research is best for tasks that require pulling together information from multiple sources:

- Comprehensive reports comparing options (vendors, competitors, technologies)
- In-depth analysis that would typically require hours of manual research
- Investigations that combine web research with your connected tools — e.g., "Summarise what's been discussed about Project X in Slack, then research industry best practices for similar initiatives"

For quick factual lookups, standard web search is faster. For complex reasoning that doesn't need external information (debugging, analysis, logic problems), use Claude's normal conversation.

### Tips for Research Prompts

- **Be specific about your goals.** Instead of "Tell me about the EV market", try "Analyse the electric vehicle battery market — identify the top three manufacturers, compare their technology approaches, and summarise recent developments in solid-state batteries."
- **Specify the structure you want.** Claude will organise its findings around the structure you provide. For example: "Include sections for cost, capacity, catering options, and AV capabilities."
- **Include constraints.** Budget ranges, timelines, geographic requirements, and other parameters help Claude focus on what's relevant.

For more details, see Anthropic's guide to [using Research](https://support.claude.com/en/articles/11088861-using-research-on-claude-ai).

## Other Ways to Use Claude

Beyond the main chat interface, Claude is available as add-ins and extensions that meet you where you already work.

### Claude for Excel

Claude for Excel is a Microsoft add-in that brings Claude directly into Excel as a sidebar. You can ask questions about your workbook, build and modify models, and debug errors — all through conversation while staying in your spreadsheet.

- **Understand your workbook** — Ask questions about formulas, calculation flows, and data across multiple tabs, with cell-level citations in the answers
- **Modify and build** — Update assumptions while preserving formula dependencies, populate templates with data, or build new financial models from scratch
- **Debug errors** — Trace `#REF!`, `#VALUE!`, circular references, and other errors to their source
- **Apply Excel operations** — Create pivot tables and charts, apply conditional formatting, set data validation, and format workbooks for printing

Install "Claude by Anthropic for Excel" from the [Microsoft Marketplace](https://appsource.microsoft.com/). Works on Excel for the web, Windows (Microsoft 365), Mac, and iPad. Does not support macros, VBA, or data tables. **Only use with trusted spreadsheets** — untrusted files may contain hidden prompt injection attacks. See Anthropic's guide to [Claude in Excel](https://support.claude.com/en/articles/12650343-use-claude-in-excel).

### Claude for Word

Claude for Word is a Microsoft add-in that brings Claude into your document workflow as a sidebar. You can ask questions about your document, edit text, and draft content — all while staying in Word.

- **Ask and understand** — Ask questions about your document and get answers with clickable section citations
- **Edit with tracked changes** — Edit selected text while maintaining formatting, styles, and numbering, with tracked changes mode so you can review edits before accepting
- **Process comments** — Respond to comment threads with contextual, document-aware replies
- **Fill templates** — Draft content that matches your document's existing styles and structure
- **Semantic search** — Find thematic provisions through meaning rather than keyword matching

Install "Claude for Word" from the [Microsoft Marketplace](https://appsource.microsoft.com/). Works on Word for the web, Windows (Microsoft 365), and Mac. Not available on iPad, Android, or older standalone versions of Word. Currently in beta. **Only use with trusted documents** — untrusted files may contain hidden prompt injection attacks. See Anthropic's guide to [Claude for Word](https://support.claude.com/en/articles/14465370-use-claude-for-word).

### Claude for PowerPoint

Claude for PowerPoint is a companion add-in that brings Claude into your presentation workflow. You can create slides from templates, edit specific slides without regenerating entire decks, convert bullet points into native charts and diagrams, and build full deck structures from natural language descriptions.

Claude can also work across the Office add-ins — for example, reading data from an Excel workbook and creating charts in a PowerPoint presentation without you switching between apps.

Install "Claude by Anthropic for PowerPoint" from the [Microsoft Marketplace](https://appsource.microsoft.com/). Works on PowerPoint for the web, Windows (Microsoft 365), and Mac. Not available on iPad. See Anthropic's guide to [Claude in PowerPoint](https://support.claude.com/en/articles/13521390-use-claude-in-powerpoint).

### Claude in Chrome

Claude in Chrome is a browser extension that adds Claude as a sidebar in Google Chrome. Claude can read, click, and navigate websites alongside you — summarising content, drafting responses, filling forms, and automating multi-step browser tasks.

- **Summarise web content** — Summarise articles, research papers, or web pages as you browse
- **Draft and manage email** — Help compose responses and manage your inbox
- **Automate browser tasks** — Fill out forms, navigate multi-step workflows, and test website features
- **Work across tabs** — Drag tabs into Claude's tab group and it can see and work across all of them simultaneously
- **Schedule recurring tasks** — Set browser tasks to run automatically on a daily, weekly, or monthly schedule

Install the extension from the [Chrome Web Store](https://claude.ai/chrome). Currently in beta. Only works in Google Chrome — not other Chromium-based browsers or mobile devices. Pro plans are limited to the Haiku model; Max, Team, and Enterprise plans can choose the model. Anthropic recommends using it for low-risk tasks on trusted websites. See Anthropic's guide to [Claude in Chrome](https://support.claude.com/en/articles/12012173-get-started-with-claude-in-chrome).

### Availability

The Office add-ins and Chrome extension are available on Pro, Max, Team, and Enterprise plans. Sign in with your Claude account after installation. Data is automatically deleted within 30 days.

## Enterprise Search

Enterprise Search is a dedicated workspace that lets you search across your organisation's connected tools — Google Drive, Gmail, Slack, Microsoft 365, and more — directly from Claude. Instead of switching between apps to find information, you can ask Claude questions like "What did the team decide about the Q3 timeline?" and it will search across your connected sources for the answer.

Enterprise Search appears as a pre-configured "Ask Your Org" project in the sidebar, with system prompts optimised by Anthropic for effective searching. Organisation owners set up the data sources, and all members can then use it.

> **Note:** Enterprise Search is not yet configured for THG. This section will be updated when it becomes available.

For more details, see Anthropic's guide to [Enterprise Search](https://support.claude.com/en/articles/12489464-use-enterprise-search).

---

## External Resources

### Courses

Anthropic offers free courses at [anthropic.skilljar.com](https://anthropic.skilljar.com/):

- **Claude 101** — Learn how to use Claude for everyday work tasks, understand core features, and explore resources for more advanced learning
- **AI Fluency: Framework & Foundations** — Core AI concepts and frameworks

### Documentation

- [Claude Help Centre](https://support.claude.com) — Feature guides, troubleshooting, and account management
- [Use Case Gallery](https://claude.com/resources/use-cases) — Step-by-step guides for common tasks organised by role (sales, marketing, finance, HR, legal, research)
- [Prompt engineering guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) — Techniques for getting the best results from Claude (aimed at developers but useful for anyone)

### Blog and Product Updates

- [Anthropic blog](https://www.anthropic.com/blog) — Product announcements, research, and best practices
- [Anthropic YouTube channel](https://www.youtube.com/@anthropic-ai) — Product demos, tutorials, and talks
