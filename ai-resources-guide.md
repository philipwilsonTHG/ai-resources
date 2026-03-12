# AI Resources Guide

> Your guide to the AI tools available across the company, how to access them, and how to put them to work.

## Introduction

AI tools are changing how we work — and they're available to you right now. Whether you're writing product copy, debugging code, analysing data, or preparing for a board meeting, there's an AI tool that can help you do it faster and better.

This guide covers what's available, how to get access, and how to start using these tools in your day-to-day work. You don't need a technical background to benefit — the tools covered here range from coding assistants to AI built into the Office and Google apps you already use.

Our approach to AI is simple: **use it, but own the output.** AI is a powerful assistant, not a replacement for your judgement. Every piece of AI-generated work should be reviewed by a human before it's used. With that principle in mind, we encourage everyone to experiment and find the workflows that make you most productive.

## Data Sensitivity & Responsible Use

AI tools can dramatically improve your productivity, but you are always responsible for the output. Treat AI as a capable assistant, not an authority — everything it produces should be reviewed, verified, and owned by you before it goes anywhere.

### Human in the Loop

Always review AI-generated content before using it in your work. AI can hallucinate facts, invent citations, and produce plausible-sounding nonsense. This is especially important for:

- **Marketing and product claims** — AI-generated copy should go through your normal review and approval processes
- **Financial reporting** — AI can help with analysis and drafting, but figures and conclusions must be verified
- **Customer-facing content** — Always proofread and fact-check before publishing

### What You Can and Can't Put Into AI Tools

**Never input into any AI tool, including enterprise versions:**

- Customer personally identifiable information (PII) — names, email addresses, phone numbers, delivery addresses, payment information
- Customer order data that could identify individuals — if you need to analyse order data, ensure it is aggregated or fully anonymised (no names, emails, or addresses attached) before using it in any AI tool
- Employee personal data — salaries, performance reviews, personal contact details

**OK in enterprise tools (ChatGPT Enterprise, Claude Enterprise, Gemini Enterprise, Microsoft 365 Copilot), but avoid in free or personal-tier tools:**

- Financial data — revenue figures, margins, supplier pricing
- Proprietary information — product formulations, unreleased product plans, supplier contracts
**No restrictions:**

- Internal source code — fine to use in any AI tool, including free and personal-tier versions

Enterprise tools have data protection agreements in place and do not use your inputs to train their models. Free and personal-tier versions of the same tools may not offer these protections — this is why the distinction matters.

**Use enterprise tools for work.** As a general rule, always use the company-provided enterprise versions of AI tools rather than free or personal accounts. If you already have a personal ChatGPT, Gemini, or Claude account, avoid using it for work tasks — use the enterprise version instead.

### When in Doubt

If you're unsure whether something is appropriate to share with an AI tool, err on the side of caution and check with your manager or the team administering these tools. These guidelines will evolve as our AI usage matures — when they do, this document will be updated.

## Available Tools & How to Access Them

### How to Request Access via ConductorOne

Several tools below require you to request access through **ConductorOne**, our software access management platform. To find it:

1. Log in to **Okta** (our single sign-on portal)
2. Search for **ConductorOne** in the Okta app catalogue
3. Open ConductorOne and search for the tool you need (e.g., "ChatGPT Enterprise")
4. Submit your request — most are auto-approved and you'll receive access within minutes

If you're unfamiliar with Okta, it's the company portal where you access all your work applications. You can reach it at [thg.okta.com](https://thg.okta.com).

---

### ChatGPT Enterprise

ChatGPT is a general-purpose AI assistant from OpenAI. It's a strong all-rounder for writing, brainstorming, summarisation, data analysis, and research. You can upload files (spreadsheets, PDFs, images) and ask it to analyse them, generate charts, or extract insights. It also supports Custom GPTs — pre-configured assistants tailored to specific tasks.

ChatGPT Enterprise is the company-approved version with full data protection. Your conversations are not used to train OpenAI's models.

**Access:** Request via ConductorOne (see [How to request access via ConductorOne](#how-to-request-access-via-conductorone) below). Most requests are auto-approved.

---

### Claude Enterprise

Claude is Anthropic's AI assistant. It excels at long-document analysis, nuanced writing, careful reasoning, and tasks that require following complex instructions. The Projects feature lets you organise context, files, and instructions into reusable workspaces.

Claude Enterprise provides full data protection — your conversations are not used to train Anthropic's models.

**Access:** Request via ConductorOne. We have 100 seats total and they are currently fully subscribed, so there is a waiting list. If you need access, submit your request and you'll be added to the queue.

For a deeper dive into Claude and Claude Code, see the [Claude & Claude Code Guide](claude-and-claude-code.md).

---

### Microsoft 365 Copilot

Copilot is Microsoft's AI assistant integrated directly into the Office 365 apps you already use — Word, Excel, PowerPoint, Outlook, and Teams. It can draft documents, summarise email threads, generate presentations from notes, analyse spreadsheet data, and recap meetings you missed.

Because it works inside your existing tools, Copilot is one of the easiest AI tools to start using immediately.

**Access:** Available to all employees through Office 365. No additional request needed.

---

### Gemini Enterprise

Gemini is Google's AI assistant. It offers a chat interface at [gemini.google.com/app](https://gemini.google.com/app) similar to ChatGPT and the Claude app, where you can have conversations, upload files, and get help with writing, analysis, and research tasks. It is also integrated with Google Workspace — helping you draft and edit in Google Docs, analyse data in Google Sheets, compose emails in Gmail, and summarise content across Google's productivity suite. Gemini Enterprise also includes an agent designer for building AI-powered agents and automated workflows that can search across company data and perform multi-step tasks.

Gemini Enterprise provides data protection — your conversations are not used to train Google's models.

**Access:** Request via ConductorOne. Gemini Enterprise also includes access to NotebookLM.

#### Google AI Studio

Google AI Studio at [aistudio.google.com](https://aistudio.google.com) is a web-based playground for experimenting with Google's AI models. It's a good place to prototype ideas, test different prompts, and explore what Google's models can do before building something more formal.

**Access:** Available to all employees. Log in with your work Google account.

#### GCP Vertex AI

Vertex AI is Google's machine learning platform for building, training, and deploying models at scale. It provides access to Google's foundation models as well as tools for custom model development and MLOps.

This is primarily for engineering teams working on ML/AI-powered features and services.

**Access:** Contact a GCP administrator or InfoSec, who will set up a project for you.

#### Google NotebookLM

NotebookLM is an AI-powered research and note-taking tool from Google. You upload documents — PDFs, articles, notes — and it helps you synthesise information, answer questions about your sources, and generate summaries. It's particularly useful when you need to quickly get across a large body of material.

**Access:** Included with Gemini Enterprise. Request Gemini Enterprise via ConductorOne.

## CLI Tools for Programmers

These tools run in your terminal and are designed for writing, editing, running, and debugging code. They are most useful for software engineers, data analysts, and anyone comfortable working on the command line.

### Claude Code

Claude Code is an AI coding assistant from Anthropic that works in your terminal and IDE. It can write and edit code, run commands, search your codebase, and handle multi-step development tasks autonomously. For installation, configuration, and detailed usage tips, see the [Claude & Claude Code Guide](claude-and-claude-code.md).

There are two ways to use Claude Code:

- **Light use (via Unbound Gateway):** Capped at \$50/month. Good for occasional use and getting started. Request access to Unbound Gateway via ConductorOne.
- **Heavy use (Claude Max):** If you find yourself hitting the \$50 cap regularly, request a personal Claude Max account. Start with the 5x plan (\$100/month, with five times the standard usage allowance), get your manager's approval, and expense it via ExpenseIn (our expense management system). Higher tiers are available if your usage grows beyond this.

Installation instructions are available on the [Claude Code GitHub page](https://github.com/anthropics/claude-code).

---

### Codex CLI

OpenAI's Codex CLI is an AI-powered coding assistant that runs in your terminal. It can write, edit, run, and debug code, as well as explain existing code, automate scripting tasks, and work with files on your machine. It uses your ChatGPT Enterprise account, so it has the same data protections.

**Access:** Uses your ChatGPT Enterprise account. Install the CLI tool and authenticate with your enterprise credentials. Installation instructions are available on the [Codex GitHub page](https://github.com/openai/codex).

---

### Gemini CLI

Gemini CLI is Google's AI-powered coding assistant that runs in your terminal. It can write, edit, run, and debug code, automate tasks, and work with files on your machine.

Gemini CLI connects to Google's models via a Vertex AI project, or via an API key generated through Unbound Gateway.

**Access:** Either use a GCP Vertex AI project, or request access to Unbound Gateway via ConductorOne to generate an API key. Installation instructions are available on the [Gemini CLI GitHub page](https://github.com/google-gemini/gemini-cli).

---

### GitHub Copilot

GitHub Copilot is an AI pair-programming tool that provides code suggestions directly in your IDE as you type. It can autocomplete functions, suggest implementations, and help you write boilerplate code faster.

**Access:** Must be enabled by your GitHub organisation administrator. Contact your org admin to request access.

## Which Tool Should I Use?

If you're not sure where to start, **Gemini Enterprise** is a good default — it's available to everyone and integrated with the Google Workspace tools you already use.

For more specific tasks, use this quick-reference table:

| Task | Recommended Tool(s) |
|------|---------------------|
| General writing & editing (emails, reports, proposals) | Gemini Enterprise / Copilot |
| Brainstorming & ideation | ChatGPT Enterprise / Gemini Enterprise |
| Analysing spreadsheet data | Copilot (Excel) / Gemini (Sheets) / Claude / ChatGPT |
| Summarising long documents | Claude Enterprise / NotebookLM |
| Research & synthesis from multiple sources | NotebookLM / Claude Enterprise |
| Writing & editing code | Claude Code / Codex CLI / Gemini CLI / GitHub Copilot |
| Debugging & code review | Claude Code / Codex CLI / Gemini CLI / ChatGPT Enterprise |
| Terminal & scripting automation | Claude Code / Codex CLI / Gemini CLI |
| Email management & drafting | Copilot (Outlook) / Gemini (Gmail) |
| Meeting summaries & recaps | Copilot (Teams) |
| Creating presentations | Copilot (PowerPoint) / Gemini (Slides) / Claude / ChatGPT |
| Data analysis & visualisation | ChatGPT Enterprise / Vertex AI |
| Marketing copy & content | ChatGPT Enterprise / Claude Enterprise |
| Prototyping AI ideas | Google AI Studio |
| Building AI agents & workflows | Gemini Enterprise (agent designer) / Vertex AI |
| Quick question, not sure where to start | Gemini Enterprise |

Many of these tools have overlapping capabilities. Don't worry about picking the "perfect" one — try a couple and see what feels most natural for your workflow. The best tool is the one you'll actually use.

## Sample Use Cases by Role

These are practical examples to get you started. Each includes a sample prompt you can adapt to your own work.

### Software Engineers

**Scaffold a new service from a spec**
Use Claude Code to turn a technical spec into working code with tests.

> *Prompt:* "Read the spec in `docs/payment-retry-spec.md` and scaffold a new service that implements it. Include unit tests, error handling, and a README. Use the same patterns as the existing services in `src/services/`."

**Debug a failing CI pipeline**
Paste a CI error log into Claude Code and let it trace the root cause.

> *Prompt:* "Here's the error output from our failing CI build. Identify the root cause and suggest a fix. The relevant code is in `src/checkout/`."

**Write a one-off migration script**
Use Codex CLI to quickly generate a script for a data migration or cleanup task.

> *Prompt:* "Write a Python script that reads all records from the `products` table where `category` is null, looks up the correct category from the `product_catalogue` table, and updates them. Add dry-run mode and logging."

---

### Data Analysts

**Identify trends in a dataset**
Upload a CSV to ChatGPT Enterprise and ask it to explore the data.

> *Prompt:* "Here's 12 months of order data for lookfantastic. Identify the top trends — seasonality, product category shifts, average order value changes. Generate charts for the most interesting findings."

**Extract data model implications from a requirements doc**
Use Claude Enterprise to analyse a long business requirements document.

> *Prompt:* "Read this requirements document for the new loyalty programme. Identify all the data entities, relationships, and attributes implied by the requirements. Flag anything that's ambiguous or contradictory."

**Prototype a classification prompt**
Use Google AI Studio to test whether an AI model can categorise something before investing in a full pipeline.

> *Prompt:* "I'm going to give you customer support tickets. Classify each one into: Order Issue, Product Question, Returns, Account Problem, or Other. Here are 10 examples — how accurately can you classify them?"

---

### Marketers

**Generate ad copy variants for A/B testing**
Use ChatGPT Enterprise to quickly produce multiple options.

> *Prompt:* "Write 5 variants of a Facebook ad for Myprotein's Impact Whey Protein. Target audience: gym-goers aged 20-35. Each variant should take a different angle — price, taste, protein content, convenience, social proof. Keep each under 90 words."

**Analyse competitor positioning**
Use Claude Enterprise to review competitor pages and summarise how they position themselves.

> *Prompt:* "Here are the landing pages for [competitor A] and [competitor B]'s protein powder ranges. Compare their positioning, key claims, pricing strategy, and tone of voice against our Myprotein Impact Whey page. Summarise the differences and suggest opportunities."

**Draft email campaign copy**
Use Gemini directly in Google Docs to write and refine campaign emails.

> *Prompt:* "Draft a 3-email welcome sequence for new lookfantastic subscribers. Email 1: welcome and brand story. Email 2: top-rated products by category. Email 3: first-purchase offer. Tone should be warm, aspirational, and beauty-focused."

---

### Supply Chain Managers

**Identify reorder patterns from inventory data**
Upload inventory data to ChatGPT Enterprise for analysis.

> *Prompt:* "Here's 6 months of inventory and sales data for our top 200 SKUs. Identify which products are at risk of stockout in the next 30 days, which are overstocked, and recommend reorder quantities based on the trends you see."

**Build demand forecasting formulas**
Use Copilot in Excel to create forecasting models without writing formulas from scratch.

> *Prompt:* "Using the sales data in columns A-F, create a 3-month demand forecast for each product using a weighted moving average. Add a column highlighting products where forecast demand exceeds current stock."

**Draft supplier communications**
Use Gemini to draft professional supplier emails and RFP responses.

> *Prompt:* "Draft an email to our whey protein supplier requesting a quote for a 20% volume increase for Q3. Reference our current contract terms, ask about lead times, and request tiered pricing options."

---

### Content Managers

**Generate SEO-optimised product descriptions**
Use Claude Enterprise to write product copy that ranks well and converts.

> *Prompt:* "Write a product description for the new lookfantastic Exclusive Beauty Box (Summer Edition). Include target keywords: 'summer beauty box', 'lookfantastic beauty box', 'skincare gift set'. The description should be 150-200 words, highlight the included products, and include a compelling call to action."

**Bulk-generate image alt text**
Use ChatGPT Enterprise to produce accessible alt text at scale.

> *Prompt:* "I'm going to upload 20 product images. For each one, write descriptive alt text suitable for an e-commerce site. Keep each under 125 characters. Focus on the product, its colour/shade, and packaging."

**Synthesise brand guidelines into a quick reference**
Upload brand and tone-of-voice documents to NotebookLM.

> *Prompt:* "Here are our brand guidelines, tone-of-voice document, and style guide. Create a one-page quick reference that a freelance copywriter could use to write on-brand content for Myprotein. Include dos and don'ts with examples."

---

### Finance & Accounting

**Automate reconciliation checks**
Use Copilot in Excel to spot discrepancies across large datasets.

> *Prompt:* "Compare the transactions in Sheet 1 (bank statement) with Sheet 2 (general ledger). Flag any transactions that appear in one but not the other, and highlight any amount mismatches greater than £1. Summarise the total discrepancy."

**Draft variance commentary**
Use ChatGPT Enterprise to write first drafts of monthly reporting narratives.

> *Prompt:* "Here's our P&L for February vs. budget. Revenue was 8% above plan driven by a strong Myprotein promotion. COGS were 3% over due to shipping cost increases. Draft the variance commentary for the monthly finance pack — keep it factual, concise, and focused on the key drivers."

**Summarise regulatory updates**
Use Gemini to quickly digest lengthy compliance documents.

> *Prompt:* "Summarise the key changes in this updated HMRC guidance on digital services VAT. Focus on what's changed from the previous version and what actions our team needs to take. Keep it under 500 words."

---

### Executives

**Catch up on missed meetings**
Use Copilot in Teams to get a structured recap with action items.

> *Prompt:* "Summarise this meeting recording. What were the key decisions made? What are the open action items, and who owns each one? Flag anything that needs my input."

**Quickly digest briefing documents**
Upload a stack of documents to NotebookLM before a board meeting or strategy session.

> *Prompt:* "Here are the board pack documents for next week's meeting. For each document, give me a 3-bullet summary of the key points, any decisions required from me, and any red flags I should be aware of."

**Draft talking points from strategic documents**
Use Gemini to prepare for presentations or town halls.

> *Prompt:* "Based on this quarterly strategy update, draft 5 talking points I can use in the all-hands meeting. Focus on progress against our top 3 priorities, one challenge we're navigating, and one thing to celebrate. Keep the tone confident but honest."

## Getting Started

### Pick a Task and Try It Today

Don't overthink it. Look at the [quick-reference table](#which-tool-should-i-use), pick one task that's relevant to your work, and give it a go. Start with something low-stakes — drafting an email, summarising a document, exploring a dataset — so you can build confidence without pressure.

### Tips for Better Prompts

The quality of what you get out of an AI tool depends heavily on what you put in. Here are a few principles that work across all the tools:

**Be specific.** Vague questions get vague answers. Instead of "Write me some ad copy," try "Write 3 variants of a Facebook ad for Myprotein Impact Whey targeting gym-goers aged 20-35, each under 90 words."

**Give context.** Tell the AI who you are, who the audience is, and what good looks like. "I'm a finance analyst writing variance commentary for the monthly board pack. Tone should be factual and concise" gives the AI much more to work with.

**Show your work.** Paste in examples, existing drafts, data, or reference material. AI works best when it has something concrete to build on rather than starting from a blank page.

**Iterate.** Your first prompt rarely gives the perfect answer. Follow up with refinements: "Make it shorter," "Focus more on the pricing angle," "Now rewrite it for a UK audience." Treat it as a conversation, not a single query.

**Ask it to explain.** If the output seems off, ask the AI why it gave that answer. This often reveals misunderstandings you can correct, and helps you write better prompts next time.

**Always check the output.** Verify facts, figures, and any links or citations. AI tools can sound confident while being completely wrong. You are responsible for everything you use.

### Experiment Across Tools

Try the same task in two different tools and see which gives better results for your workflow. The tools have overlapping capabilities but different strengths — the best way to discover what works for you is to experiment.

### Share What Works

[TBD — feedback channel to be confirmed. When you discover a great use case or prompt, we'd love to hear about it so we can share it with the wider team.]

### Get Help

[TBD — support channel to be confirmed. If you're stuck, have questions, or want guidance on which tool to use for a specific task, reach out here.]
