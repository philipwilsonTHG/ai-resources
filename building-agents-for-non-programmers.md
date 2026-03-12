# Building AI Agents for Non-Programmers

> How to create your own AI assistants and automated workflows — no coding required.

This guide shows you how to build AI agents using the tools available at THG. You don't need any programming experience — everything here can be done through web interfaces with plain English instructions.

## What Is an Agent?

An agent is an AI assistant that's been configured for a specific task. Instead of starting from scratch every time you use ChatGPT or Claude, you give the agent its own instructions, knowledge, and focus area so it can perform a particular job well, repeatedly.

There are two levels of agents:

- **Configured assistants** — An AI with custom instructions and uploaded reference documents. It answers questions and generates content based on the context you've given it. Think of it as a specialist colleague who has already read all the relevant documentation.
- **Automated workflow agents** — An AI that can take actions across multiple steps, not just answer questions. It can search company data, follow decision logic, and chain tasks together. Think of it as a specialist colleague who can also go and do things for you.

## No-Code Agent Platforms at THG

You have several options, depending on what you need:

### ChatGPT Custom GPTs

Custom GPTs let you create a specialist ChatGPT assistant with its own instructions, uploaded knowledge files, and conversation starters. They live inside ChatGPT Enterprise and can be shared with colleagues.

**Best for:** Repeatable tasks where you want a consistent assistant — Q&A bots, content generators, analysis tools.

**How to create one:**
1. Open [ChatGPT](https://chat.openai.com) with your enterprise account
2. Click your name in the sidebar, then **My GPTs** > **Create a GPT**
3. Use the **Configure** tab to set a name, instructions, and upload files
4. Save and share with your team

### Claude Projects

Claude Projects let you organise instructions, reference documents, and conversation history into reusable workspaces. While not labelled as "agents", they function as configured assistants — every conversation within a Project inherits the same context and instructions.

**Best for:** Recurring tasks that need consistent context — reviewing content against guidelines, analysing documents with the same criteria, generating outputs in a specific format.

**How to create one:**
1. Open [Claude](https://claude.ai) with your enterprise account
2. Click **Projects** in the sidebar
3. Create a new project, add instructions and upload reference files
4. Every new conversation in the project will have access to your instructions and files

### Gemini Enterprise Agent Designer

Gemini Enterprise includes an agent designer for building AI-powered agents that can search across company data, answer questions, and perform multi-step automated workflows. This is the most capable no-code agent platform available at THG.

**Best for:** Multi-step workflows, agents that need to access company data sources, and tasks that go beyond simple Q&A.

**How to access:** Request Gemini Enterprise via ConductorOne.

### Google NotebookLM

NotebookLM isn't technically an agent builder, but it's a powerful no-code way to create a Q&A assistant over a specific set of documents. Upload your sources and NotebookLM lets you (and anyone you share it with) ask questions and get answers grounded in those documents.

**Best for:** Quickly creating a searchable knowledge base from a set of documents — policy guides, research papers, meeting notes, training materials.

**How to access:** Included with Gemini Enterprise. Request via ConductorOne.

## Building Simple Agents (Configured Assistants)

A configured assistant is the easiest type of agent to build. You write instructions, upload some documents, and you have a specialist AI ready to go.

### Writing Good Instructions

The instructions you give your agent are the most important part. They determine how the agent behaves, what it focuses on, and what quality of output it produces.

**Be specific about the agent's role.** Don't just say "You are a helpful assistant." Say "You are a brand tone-of-voice reviewer for Myprotein. Your job is to review marketing copy and flag anything that doesn't match our brand guidelines."

**Define the output format.** If you want bullet points, tables, or a specific structure, say so. "Always respond with: a summary of the issue, your recommendation, and the relevant section from the guidelines."

**Set boundaries.** Tell the agent what it should and shouldn't do. "Only answer questions related to our returns policy. If someone asks about something else, politely redirect them."

**Include examples.** Show the agent what good output looks like. "Here's an example of a well-written product description for reference: [example]."

**Specify the tone.** "Use a professional but friendly tone. Avoid jargon. Write for someone who has never visited our website before."

### Choosing What Documents to Upload

The documents you upload become the agent's knowledge base. Choose carefully:

- **Upload the most authoritative sources** — official guidelines, approved policies, finalised specs. Avoid drafts or outdated versions.
- **Keep it focused.** An agent with 3 highly relevant documents will perform better than one with 30 loosely related ones.
- **Think about what questions the agent will need to answer**, then make sure the source material covers those topics.
- **Update documents when they change.** An agent using last year's brand guidelines will give last year's answers.

### Example: Returns Policy Q&A Bot

**Platform:** ChatGPT Custom GPT

**Instructions:**
> You are a returns policy specialist for lookfantastic. Your job is to answer questions about our returns and refunds process accurately and helpfully.
>
> Always base your answers on the uploaded returns policy document. If a question isn't covered by the policy, say "I don't have specific guidance on that — please contact our customer service team."
>
> Use a friendly, reassuring tone. Customers asking about returns are often frustrated, so be empathetic.

**Uploaded files:** Current returns policy document, FAQ sheet

### Example: Brand Tone-of-Voice Checker

**Platform:** Claude Project

**Instructions:**
> You are a tone-of-voice reviewer for Myprotein. When I share marketing copy with you, review it against our brand guidelines and provide feedback.
>
> For each piece of copy, provide:
> 1. An overall assessment (on-brand / mostly on-brand / off-brand)
> 2. Specific issues, with quotes from the copy and references to the relevant guideline
> 3. Suggested rewrites for any off-brand sections
>
> Be constructive, not just critical. Explain why something is off-brand and how to fix it.

**Uploaded files:** Brand guidelines, tone-of-voice document, examples of approved copy

### Example: Product Description Generator

**Platform:** ChatGPT Custom GPT or Claude Project

**Instructions:**
> You write product descriptions for the lookfantastic website. Each description should be 150–200 words and follow this structure:
>
> 1. Opening hook (one compelling sentence)
> 2. Key benefits (3–4 bullet points)
> 3. How to use / who it's for
> 4. Call to action
>
> Tone: warm, aspirational, beauty-focused. Avoid clinical or technical language unless it's a skincare active ingredient (e.g., retinol, niacinamide).
>
> Always include relevant SEO keywords naturally — don't keyword-stuff.

**Uploaded files:** Style guide, examples of top-performing product descriptions, SEO keyword list

## Building Multi-Step Workflow Agents

Multi-step agents go beyond Q&A — they can follow decision logic, search across data sources, and chain actions together. These are more powerful but take more thought to set up.

### What Makes a Workflow Agent Different

A configured assistant waits for you to ask a question and then responds. A workflow agent can:

- **Search across multiple data sources** to find relevant information
- **Follow decision trees** — "If the proposal meets criteria X, do A; otherwise, do B"
- **Chain tasks together** — gather data, analyse it, format a report, and send it
- **Take actions** — update records, send notifications, generate documents

### Where to Build Workflow Agents

**Gemini Enterprise agent designer** is the primary no-code platform for multi-step agents at THG. It can connect to company data sources and perform actions across Google Workspace.

For more complex automations, you may want to involve an engineer — but the agent designer can handle a surprising amount without code.

### Example: Supplier Proposal Reviewer

An agent that reviews incoming supplier proposals against a standard set of criteria:

1. Reads the uploaded proposal document
2. Checks it against your evaluation criteria (pricing within budget? Lead times acceptable? Quality certifications present?)
3. Produces a structured assessment with a recommendation
4. Flags any missing information that needs follow-up

### Example: Weekly Report Generator

An agent that produces a recurring report from data sources:

1. Pulls data from a specified Google Sheet or data source
2. Analyses trends and highlights anomalies
3. Generates a formatted summary with charts
4. Shares the report to a specified location

## When to Build an Agent vs. Just Use a Tool Directly

**Build an agent when:**

- You repeat the same task with the same context frequently
- Multiple people on your team need the same capability
- Consistency matters — you want the same quality and format every time
- You find yourself re-explaining the same instructions at the start of every conversation

**Don't build an agent when:**

- It's a one-off task — just use ChatGPT, Claude, or Gemini directly
- The task changes significantly each time
- You're still figuring out what you want — experiment in a regular conversation first, then build an agent once you've nailed the instructions

## Sharing Agents with Your Team

### Sharing Custom GPTs

In ChatGPT Enterprise, you can share Custom GPTs with specific colleagues or make them available to everyone in the organisation:

1. Open your Custom GPT
2. Click **Edit** > **Configure** > **Sharing**
3. Choose who can access it — specific people, or anyone in the THG organisation

### Sharing Claude Projects

Claude Projects can be shared with other Claude Enterprise users:

1. Open your Project
2. Click the share button and add colleagues by email
3. They'll be able to start conversations within the project using your instructions and files

### Sharing NotebookLM Notebooks

NotebookLM notebooks can be shared like any Google document:

1. Click **Share** on your notebook
2. Add colleagues by email or generate a sharing link
