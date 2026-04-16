---
name: context-loop
description: Run the full PMM context engineering loop — company context, competitors (parallel), win-loss (optional), ICP, positioning, messaging, pricing
---

# PMM context engineering loop

You are running the full PMM context engineering loop for a product marketer. This loop builds their foundational knowledge base — everything downstream depends on these outputs.

**Read the CLAUDE.md first** to get the company name, website, and competitor list.

---

## Phase 0: Verify inputs

Before starting any research, confirm you have everything needed. Read CLAUDE.md and check:

1. **Company name and website** — Is the `## Who I am` section personalized (not the starter placeholder)?
2. **Competitors** — Does `## Competitive landscape` list actual competitor names?
3. **Voice and audiences** — Is `## Voice and style` populated with real adjectives and preferences?

If ANY of these are still placeholder/generic:
- Tell the user: "Your CLAUDE.md hasn't been personalized yet. Run `/quickstart` first to set up your company context, then come back to `/context-loop`."
- Stop here. Do not proceed.

If CLAUDE.md is personalized, confirm the inputs with the user:

"Before I start, let me confirm what I'm working with:

- **Company:** [name] ([website])
- **Competitors:** [list from CLAUDE.md]

I'll research your company first, then all competitors in parallel, then build your ICP, positioning, messaging, and pricing strategy — each step feeding the next.

**One question before we begin:** Do you have any sales call transcripts or recordings (won or lost deals)? If yes, paste them or point me to the files — I'll run a win/loss analysis that makes your ICP and positioning significantly sharper.

Anything you'd like to add or change before I begin?"

Wait for confirmation before proceeding.

---

## Overview

After confirmation, present this:

"Starting the PMM context engineering loop for [Company Name].

This will generate up to 7 outputs in sequence:

1. **Company context** — your market position, traction data, team, funding (~5 min)
2. **Competitor research** — deep profiles for [list competitors] (~10 min)
   (these run in parallel — one agent per competitor)
3. **Win/loss analysis** (if transcripts provided) — why deals are won and lost (~5 min)
4. **ICP research** — who buys from you and why (~5 min)
5. **Positioning** — how you differentiate from alternatives (~3 min)
6. **Product messaging** — your messaging library (~3 min)
7. **Pricing strategy** — tier structure, value metrics, packaging (~5 min)

Each step feeds the next. Everything saves to the right folder automatically.
Let's begin."

---

## Phase 1: Company context

Run the `/company-context` skill on the user's company.

- Read `.claude/skills/company-context/SKILL.md` and follow its process
- Use the company URL from CLAUDE.md
- Show key findings as they emerge (traction signals, team size, funding, customers)
- Save output to `context/MMYY-company-context.md` (where MMYY is current month/year)

After saving, show a brief summary:
"Done. Key findings: [2-3 bullet highlights]. Saved to context/MMYY-company-context.md"

---

## Phase 2: Competitor research (parallel)

Dispatch one competitor-researcher agent per competitor listed in CLAUDE.md. Run them in parallel.

For each competitor:
- Launch an agent with subagent_type "competitor-researcher"
- The agent should read `.claude/skills/competitor-research/SKILL.md` and run the full analysis
- Each agent saves its output to `context/competitors/MMYY-competitor-[name].md`

Show progress as agents complete:
"Dispatching research agents...
→ Agent 1: Researching [Competitor A]...
→ Agent 2: Researching [Competitor B]...
→ Agent 3: Researching [Competitor C]..."

As each completes:
"Done: [Competitor A] → context/competitors/MMYY-competitor-[name].md"

Wait for ALL agents to complete before moving to Phase 3.

After all complete, show: "All competitor research complete."

---

## Phase 3: Win/loss analysis (optional)

**Only run this phase if the user provided sales call transcripts in Phase 0.**

If transcripts were provided:
- Read `.claude/skills/win-loss-analysis/SKILL.md` and follow its process
- Use transcripts as primary input, company context as supporting context
- Save output to `context/icp/MMYY-win-loss-analysis.md`

After saving: "Done. Key patterns: [2-3 findings]. Saved to context/icp/MMYY-win-loss-analysis.md"

If no transcripts were provided:
- Skip this phase
- Show: "Skipping win/loss analysis (no transcripts provided). You can run `/win-loss-analysis` anytime later when you have transcripts."

---

## Phase 4: ICP research

Run the `/icp-research` skill.

- Read `.claude/skills/icp-research/SKILL.md` and follow its process
- Use the company context AND competitor research outputs as input (read them from context/)
- If win/loss analysis was run, use it as additional input — it sharpens the personas
- Save output to `context/icp/MMYY-icp-research.md`

After saving: "Done. Key segments identified: [2-3 segment summaries]. Saved to context/icp/MMYY-icp-research.md"

---

## Phase 5: Positioning

Run the `/positioning` skill.

- Read `.claude/skills/positioning/SKILL.md` and follow its process
- Use company context + competitor research + ICP research as input
- Save output to `product-marketing/positioning/MMYY-positioning.md`

After saving:
"Done. Positioning summary:
- Category: [category]
- Primary alternative: [what they'd use instead]
- Key differentiators: [2-3 bullets]
- Statement: '[one-line positioning statement]'

Saved to product-marketing/positioning/MMYY-positioning.md"

---

## Phase 6: Product messaging

Run the `/product-messaging` skill.

- Read `.claude/skills/product-messaging/SKILL.md` and follow its process
- Use positioning + ICP research as primary input
- Save output to `product-marketing/positioning/MMYY-product-messaging.md`

After saving:
"Done. Messaging library includes:
- Positioning statement
- Value propositions
- Key differentiators
- Proof points
- Core messaging blocks

Saved to product-marketing/positioning/MMYY-product-messaging.md"

---

## Phase 7: Pricing strategy

Run the `/pricing-strategy` skill.

- Read `.claude/skills/pricing-strategy/SKILL.md` and follow its process
- Use positioning + competitor research + ICP research as input
- Save output to `product-marketing/positioning/MMYY-pricing-strategy.md`

After saving:
"Done. Pricing strategy includes:
- Competitive pricing analysis
- Recommended value metric
- Tier structure (Good-Better-Best)
- Pricing page experiments
- Customer research design (Van Westendorp)

Saved to product-marketing/positioning/MMYY-pricing-strategy.md"

---

## Phase 8: Summary + commit

After all phases complete, show the summary table:

"--- PMM context engineering loop complete ---

| # | Output | File | Status |
|---|--------|------|--------|
| 1 | Company context | context/MMYY-company-context.md | Done |
| 2 | Competitor: [A] | context/competitors/MMYY-competitor-[a].md | Done |
| 3 | Competitor: [B] | context/competitors/MMYY-competitor-[b].md | Done |
| ... | ... | ... | ... |
| N | Win/loss analysis | context/icp/MMYY-win-loss-analysis.md | Done / Skipped |
| N+1 | ICP research | context/icp/MMYY-icp-research.md | Done |
| N+2 | Positioning | product-marketing/positioning/MMYY-positioning.md | Done |
| N+3 | Product messaging | product-marketing/positioning/MMYY-product-messaging.md | Done |
| N+4 | Pricing strategy | product-marketing/positioning/MMYY-pricing-strategy.md | Done |

These files are now your persistent context. Every future skill you run draws from this foundation."

Then commit all outputs:

```bash
git add context/ product-marketing/
git commit -m "Add PMM context engineering loop outputs — [Company Name]"
```

"Committed all outputs to git. Your work is saved.

Run `/next-steps` to see what to build next."
