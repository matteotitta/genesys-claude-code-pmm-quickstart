---
name: pricing-strategy
version: "1.0"
description: |
  Designs a pricing model with tier structure, value metrics, and packaging recommendations.
  Produces competitive pricing comparisons, tier recommendations, and pricing page guidance.
  Use when you need to create or optimize pricing for a B2B SaaS product.

dependencies:
  required: []
  recommended:
    - positioning
    - product-messaging
    - competitor-research

outputs:
  - type: pricing-strategy
    feeds_into:
      - product-messaging

output_path: "product-marketing/positioning/"

triggers:
  auto_suggest_when:
    - "user mentions pricing strategy or pricing tiers"
    - "user asks about value metrics or packaging"
  auto_run_when: null

review_gate: 2
---

# Pricing strategy

Develop data-informed pricing strategy for B2B SaaS products through competitive analysis, value metric selection, and structured framework application. Output guides pricing decisions and pricing page optimization.

---

## Process flowchart

```text
+--------------------------------------------------------------+
|                  PRICING STRATEGY PROCESS                     |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 1: INPUT VALIDATION                                     |
| Required: Product name, current pricing (if exists)           |
| Optional: competitor-research output, ICP, messaging          |
| -> If available: Pull competitive pricing context             |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 2: PRICING RESEARCH                                     |
| Step 2.1: Competitive pricing analysis (3-5 competitors)      |
| Step 2.2: Value metric analysis (what to charge for)          |
| Step 2.3: Customer willingness research design                |
| Step 2.4: Feature value ranking (MaxDiff methodology)         |
| Checkpoint: Pricing data collected, value metric identified    |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 3: STRATEGY DEVELOPMENT                                 |
| Step 3.1: Tier structure design (Good-Better-Best)            |
| Step 3.2: Price point recommendations (ranges, not precise)   |
| Step 3.3: Pricing page optimization experiments               |
| Checkpoint: Tiers defined, recommendations documented          |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| SELF-EVALUATION                                               |
| [] All research components addressed?                         |
| [] Price points have rationale? No invented data?             |
| [] Recommendations clearly marked as suggestions?             |
| -> If issues: Flag data gaps, suggest customer research       |
+--------------------------------------------------------------+
```

---

## Input requirements

### Required

| Input | Description | Source |
|-------|-------------|--------|
| **Product name** | Product being priced | User provides |
| **Current pricing** | Existing pricing (if any) | User provides or research |

### Optional (improve quality)

| Input | How it helps |
|-------|--------------|
| Competitor pricing | Provides market anchors |
| ICP research | Identifies willingness to pay by segment |
| Product messaging | Clarifies value proposition for pricing alignment |

---

## Core frameworks

### Good-Better-Best tier framework

| Tier | Purpose | Feature set | Pricing psychology |
|------|---------|-------------|-------------------|
| **Good** | Entry point, land new customers | Core features only | Low friction, trial conversion |
| **Better** | Value tier, default choice | Good + power features | Decoy effect, perceived value |
| **Best** | Premium tier, max value capture | Better + advanced features | Anchoring, enterprise signal |

**Feature fencing principles:**
1. **Usage limits** — Good: 100/month, Better: 1,000/month, Best: Unlimited
2. **Access limits** — Good: 1 seat, Better: 5 seats, Best: Unlimited seats
3. **Feature gates** — Good: Core, Better: +Integrations, Best: +API/SSO
4. **Support levels** — Good: Email, Better: Chat, Best: Dedicated CSM

### Value metric selection

| Value metric | Best when | Watch out for |
|-------------|-----------|---------------|
| **Per seat** | Value scales with team size | Discourages adoption, seat hoarding |
| **Per usage** | Value correlates to usage | Unpredictable bills, budget anxiety |
| **Flat rate** | Simple value prop, low complexity | Leaves money on table with large customers |
| **Feature-based** | Clear feature tiers | Complexity, unclear upgrade path |

**Selection criteria:** Value alignment, predictability, growth-friendly, measurable, competitive context.

### Van Westendorp price sensitivity

Four questions to find the acceptable price range:
1. "At what price would you begin to question quality?"
2. "At what price would this be a bargain?"
3. "At what price would this be getting expensive but still worth it?"
4. "At what price would this be too expensive?"

---

## Output format

```markdown
# Pricing strategy: [Product Name]

- **Research date**: [YYYY-MM-DD]
- **Current pricing**: [Existing pricing or "None"]

---

## Executive summary

[2-3 paragraphs summarizing key findings, recommended pricing structure, and strategic rationale]

---

## 1. Competitive pricing analysis

### Market overview

| Competitor | Model | Entry price | Mid tier | Enterprise | Value metric |
|------------|-------|-------------|----------|------------|--------------|
| [Comp 1] | [Type] | [$X/mo] | [$Y/mo] | [Contact] | [Metric] |

**Market positioning observations:**
- [Insight 1]
- [Insight 2]

**Source**: [URLs] | **Confidence**: High/Medium/Low

---

## 2. Value metric analysis

| Value metric | Alignment | Predictability | Growth-friendly | Recommendation |
|-------------|-----------|----------------|-----------------|----------------|
| Per seat | [1-5] | [1-5] | [1-5] | [Rec/Not rec] |

### Recommended value metric

**Primary metric:** [Metric]
**Rationale:** [2-3 sentences]

---

## 3. Tier structure recommendation

### Good tier: [Name]

**Target user:** [Description]
**Price recommendation:** [$X-Y/mo]
**Features:** [List]
**Upgrade trigger:** [What drives upgrade]

### Better tier: [Name]

[Same structure]

### Best tier: [Name]

[Same structure]

---

## 4. Customer research design

### Van Westendorp survey

**Target respondents:** [Segment]
**Recommended sample size:** [N]
**Questions:** [The 4 standard questions]

---

## 5. Pricing page experiments

| Priority | Experiment | Hypothesis | Success metric |
|----------|------------|------------|----------------|
| 1 | [Experiment] | [Hypothesis] | [Metric] |

---

## 6. Data gaps and next steps

| Data point | Impact | How to obtain |
|------------|--------|---------------|
| [Data] | [Impact] | [Method] |
```

---

## Anti-hallucination guardrails

1. **Never invent price sensitivity data.** Mark "Customer research required" if no data
2. **Never claim exact optimal price.** Provide ranges with confidence levels
3. **Always cite competitive prices.** Include source and access date
4. **Mark recommendations as suggestions.** "Based on analysis, consider..." not "You should..."
5. **Acknowledge data gaps.** Pricing decisions need real customer data

---

## Quality checklist

- [ ] 3-5 competitors' pricing documented with sources
- [ ] Value metric options analyzed with pros/cons
- [ ] Tier structure follows Good-Better-Best framework
- [ ] Each tier has target user, price range, features, upgrade trigger
- [ ] Price recommendations are ranges, not false precision
- [ ] Feature fencing has clear rationale
- [ ] Data gaps section completed
- [ ] Next steps actionable

---

## After this skill, consider

1. Review pricing with your team and customers before implementation
2. Design the Van Westendorp survey for customer validation
3. Update your `/product-messaging` to align messaging with pricing tiers
