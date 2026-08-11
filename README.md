# Sales AI Prompt Pack by WireForge

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](./LICENSE) [![Prompts](https://img.shields.io/badge/Prompts-8-orange?style=flat-square)](./system-prompts/) [![GitHub stars](https://img.shields.io/github/stars/srmcguirt/sales-ai-prompt-pack?style=flat-square)](https://github.com/srmcguirt/sales-ai-prompt-pack)

> **8 system prompts that turn any LLM into a senior sales professional.** Prospect research, cold emails, discovery prep, demo scripts, objection handling, proposals, win/loss analysis, and follow-up sequences — each with few-shot examples and structured output schemas for Claude, GPT-4, Cursor, and any OpenAI-compatible API.
>
> *Part of the [WireForge](https://srmcguirt.github.io) AI tooling collection.*

> 💎 **Full pack** with all 8 prompts, few-shot examples, output schemas, and future updates → **[Get it on Gumroad ($49) →](https://srmcguirt.gumroad.com)**
>
> 📬 **Free sample prompt** — [subscribe at srmcguirt.github.io](https://srmcguirt.github.io)

---

## What's Inside

| # | Prompt | What It Does |
|---|--------|-------------|
| 1 | **Prospect Research Analyst** | Transforms account data into a structured intelligence brief: ICP fit, trigger events, stakeholder map, pain hypotheses, and outreach frame |
| 2 | **Cold Email Writer** | Generates 3 personalized cold email variants with subject lines, objection-safe opening hooks, and A/B testing guidance |
| 3 | **Discovery Call Prep** | Produces a complete call brief: hypothesis, agenda, question bank by category, objection handlers, and qualification checkpoint |
| 4 | **Demo Script Builder** | Builds a persona-tailored demo script in three acts: their world → product proof → future state |
| 5 | **Objection Handler** | Decodes the real concern behind any stated objection and produces exact response language with next-step scripts |
| 6 | **Proposal Writer** | Generates a complete proposal document: executive summary, business case with ROI, implementation plan, pricing, and next steps |
| 7 | **Win/Loss Analyzer** | Transforms deal records and interview data into structured win/loss analysis with actionable recommendations |
| 8 | **Follow-Up Sequence Writer** | Creates a complete post-meeting sequence (6 emails) tailored to meeting type, commitments, and deal stage |

### What Makes These Different from Free Prompts

- **800+ words each** — comprehensive system prompts with role definitions, behavioral constraints, output format specifications, and edge case handling.
- **Real few-shot examples** — each prompt includes 3 realistic input/output pairs with actual research briefs, cold emails, discovery questions, and proposals.
- **Structured output schemas** — JSON Schema files for every prompt, ready to use with OpenAI's structured output, Claude's tool use, or any JSON-mode API.
- **Edge case coverage** — each prompt handles the hard cases: enterprise vs. SMB, competitive bake-offs, executive buyers, inbound vs. outbound, no-budget responses.

---

## ⚡ The WireForge Prompt Architecture

Every WireForge prompt follows our **4-Layer Prompt Architecture**:

```
┌─────────────────────────────────────────────┐
│  Layer 1: IDENTITY                          │
│  Senior sales professional + specific       │
│  experience scope and domain expertise      │
├─────────────────────────────────────────────┤
│  Layer 2: GUARDRAILS                        │
│  10-15 behavioral constraints that prevent  │
│  common AI failure modes in sales output    │
│  "Never send a 'just checking in' email"    │
├─────────────────────────────────────────────┤
│  Layer 3: OUTPUT BLUEPRINT                  │
│  Exact section-by-section format with       │
│  tables, scripts, and structure the AI      │
│  must follow — no freeform output           │
├─────────────────────────────────────────────┤
│  Layer 4: EDGE CASE LIBRARY                 │
│  7-8 specific scenarios (enterprise,        │
│  SMB, inbound, competitive, no-budget)      │
│  that trip up generic prompts               │
└─────────────────────────────────────────────┘
```

**The Stakeholder Test™:** Every output from these prompts goes directly into your sales workflow without rewriting. Research briefs go straight to the AE. Follow-up emails send as-is. Proposals circulate to economic buyers without revision.

---

## 📦 File Structure

```
sales-ai-prompt-pack/
├── system-prompts/
│   ├── 01-prospect-research-analyst.md
│   ├── 02-cold-email-writer.md
│   ├── 03-discovery-call-prep.md
│   ├── 04-demo-script-builder.md
│   ├── 05-objection-handler.md
│   ├── 06-proposal-writer.md
│   ├── 07-win-loss-analyzer.md
│   └── 08-followup-sequence-writer.md
├── few-shot-examples/
│   ├── 01-prospect-research-analyst.json
│   ├── 02-cold-email-writer.json
│   └── ... (8 total)
├── output-schemas/
│   ├── 01-prospect-research-analyst.json
│   └── ... (8 total)
├── README.md
├── LICENSE
└── CHANGELOG.md
```

---

## 🚀 Quick Start

### Method 1: Copy-Paste (Fastest)

1. Open any file in `system-prompts/`
2. Copy the full content
3. Paste into Claude, ChatGPT, or any AI tool as the system prompt
4. Send your sales request ("Research [Company] for cold outreach" / "Write a cold email to [Name] at [Company]")

### Method 2: Claude Projects / Custom GPT

Set as the system prompt in a Claude Project or Custom GPT. Then interact naturally — "Prep me for my discovery call with Acme Corp's VP of Engineering on Thursday."

### Method 3: API Integration

```python
import anthropic

client = anthropic.Anthropic()

with open("system-prompts/02-cold-email-writer.md") as f:
    system_prompt = f.read()

message = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=2048,
    system=system_prompt,
    messages=[{
        "role": "user",
        "content": """
        Account: Acme Corp (B2B SaaS, 300 employees, Series B)
        Contact: Sarah Chen, VP Engineering
        Trigger: Just raised $40M Series B (announced 2 weeks ago)
        Product: Our multi-agent orchestration platform
        Pain signal: 3 open ML Ops engineer roles posted in last 60 days
        """
    }]
)
```

### Method 4: Cursor / VS Code

Add to `.cursorrules`:

```
[paste content of any system-prompts/*.md file]
```

---

## 💡 Workflow Chaining

The full sales cycle covered end-to-end:

```
Account identified → Prospect Research Analyst
         ↓
Intel brief → Cold Email Writer
         ↓
Reply received → Discovery Call Prep
         ↓
Call completed → Follow-Up Sequence Writer
         ↓
Demo scheduled → Demo Script Builder
         ↓
Objection raised → Objection Handler
         ↓
Demo completed → Proposal Writer
         ↓
Deal closed (won or lost) → Win/Loss Analyzer
```

---

## 📊 Prompt Quick Reference

| Prompt | Input | Output |
|--------|-------|--------|
| Prospect Research | Company name + context | Intelligence brief with ICP fit, triggers, stakeholder map, outreach frame |
| Cold Email | Contact + trigger + product | 3 email variants with subject lines, A/B guidance |
| Discovery Prep | Account + contact + known info | Agenda, question bank, objection handlers, qualification checklist |
| Demo Script | Discovery notes + persona | 3-act demo script with transitions, check-ins, objection handlers |
| Objection Handler | Exact objection text | Psychology, clarifying questions, response language, next step |
| Proposal | Deal details + pricing | Full proposal doc with business case, ROI, implementation plan |
| Win/Loss | Deal records + interview data | Pattern analysis, competitive intel, actionable recommendations |
| Follow-Up | Meeting notes + commitments | 6-email sequence with timing, subject lines, break-up email |

---

## 🎯 Before / After

### Without WireForge

**You type:** "Write a follow-up email after my sales demo"

**You get:**
> "Hi [Name], thank you for taking the time to meet with me today. I really enjoyed our conversation and I'm excited about the possibility of working together. Please let me know if you have any questions. Best, [Name]"

This email will be ignored.

### With WireForge Follow-Up Sequence Writer

**You provide:** Meeting notes (3 bullet points about what was discussed, commitments made, next step agreed)

**You get:** A 6-email sequence with specific subject lines, opening hooks that reference exact things said in the meeting, a structured recap, resources tailored to their stated concerns, a stakeholder multi-thread email, and a break-up email that creates closure without desperation.

---

## 🛒 Other WireForge Products

| Product | Description | Link |
|---------|-------------|------|
| **Product Management AI Prompt Pack** | 8 prompts for PRDs, user stories, sprint planning, competitive analysis, metrics | [GitHub](https://github.com/srmcguirt/product-management-ai-prompt-pack) |
| **DevOps AI Prompt Pack** | 8 prompts for Terraform, K8s, CI/CD, security, monitoring | [GitHub](https://github.com/srmcguirt/devops-ai-prompt-pack) |
| **Marketing AI Prompt Pack** | 8 prompts for SEO, social, email, ads, content strategy | [GitHub](https://github.com/srmcguirt/marketing-ai-prompt-pack) |
| **MCP Server Starter Kit** | Production-ready MCP server boilerplate (TypeScript + Python) | [GitHub](https://github.com/srmcguirt/mcp-server-starter-kit) |
| **Claude Agent Boilerplate** | Agent framework with memory, tools, structured conversations | [GitHub](https://github.com/srmcguirt/claude-agent-boilerplate) |
| **Multi-Agent Orchestration Kit** | Pipeline, fan-out, and supervisor patterns for multi-agent systems | [GitHub](https://github.com/srmcguirt/multi-agent-orchestration-kit) |

---

## License

MIT — see [LICENSE](./LICENSE)

## Changelog

See [CHANGELOG.md](./CHANGELOG.md)

---

**Built by [WireForge](https://srmcguirt.github.io)** — AI developer tools that actually work.
