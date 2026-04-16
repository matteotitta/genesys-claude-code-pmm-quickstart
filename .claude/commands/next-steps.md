---
name: next-steps
description: Post-loop guidance — what to build next after the PMM context loop
---

# What to build next

You've completed the PMM context engineering loop. Here's what to do next, in recommended order.

---

## Immediate next steps

### 1. Push to GitHub

Back up your work to a private GitHub repository. Ask Claude to walk you through the process if you haven't done this before.

```bash
git add .
git commit -m "Add PMM context engineering outputs"
git push
```

### 2. Run brand and voice skills

These weren't in the context loop but they enrich everything:

- `/tov-guidelines` — Analyzes your brand voice patterns and creates do/don't guidelines. Makes all future output sound like your company.
- `/brand-guidelines` — Visual + verbal identity, design tokens, CSS variables. Useful for design briefs and landing pages.

**Recommended order:** TOV first (it informs brand guidelines).

### 3. Run content strategy

- `/content-strategy` — Channel mix, content pillars, editorial plan. Uses your positioning, ICP, and messaging as input.

### 4. Review and refine

Open each output file and review it. The context loop produces strong first drafts, but your insider knowledge makes them better:

- **Positioning:** Does the category feel right? Are the differentiators what you'd actually say in a sales call?
- **Messaging:** Do the value props resonate? Would your best customer nod at these?
- **Pricing:** Are the tier recommendations realistic for your market?
- **ICP:** Do the personas match the people who actually buy from you?

Edit any file directly — Claude reads the updated versions in future sessions.

---

## Build your own skills

When you find yourself explaining the same task to Claude more than twice, it's a skill candidate.

Open `templates/SKILL-MD-TEMPLATE.md` — it walks you through building a custom skill in 7 questions. Common first skills product marketers build:

- A competitive battlecard generator
- A launch brief template
- A case study writer
- A landing page copy generator
- A sales enablement asset creator

Save your skill to `.claude/skills/[skill-name]/SKILL.md` and invoke it by name.

---

## Add API keys for stronger research

Sign up for free tiers to make research skills more powerful:

- **Exa** (1,000 free searches/month) — [exa.ai](https://exa.ai) — better web search for competitive research
- **Firecrawl** (500 free credits/month) — [firecrawl.dev](https://firecrawl.dev) — website scraping for deeper competitor analysis

Add keys to a `.env` file in your project root:

```
EXA_API_KEY=your-exa-key-here
FIRECRAWL_API_KEY=your-firecrawl-key-here
```

The `.gitignore` already protects `.env` from being uploaded to GitHub.

---

## Going further

This quickstart builds your PMM foundation — company context, competitive intelligence, ICP, positioning, messaging, and pricing. The full Claude Code programme adds layers on top:

- **Quality gates** — hooks that catch brand voice violations and fabricated metrics before output ships
- **Automation** — recurring tasks on schedule (competitive digests, content calendars)
- **Agents** — parallel execution across competitors, transcripts, and content channels
- **Team scale** — `git clone` gives every team member the whole system

**Ready to go further?** [GTM Engineer School](https://www.gtm-engineer-school.com/) · [Book a call](https://cal.com/matteo-titta/30min)
