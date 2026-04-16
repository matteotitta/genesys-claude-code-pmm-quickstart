---
name: win-loss-analysis
version: "1.0"
description: |
  Analyzes sales call transcripts to extract win/loss patterns, objection themes, and competitive intelligence.
  Produces aggregate insights with verbatim quotes, pattern frequencies, and strategic recommendations.
  Use when you have sales call transcripts and want to understand why deals are won or lost.

dependencies:
  required: []
  recommended:
    - company-context

outputs:
  - type: win-loss-analysis
    feeds_into:
      - icp-research
      - positioning
      - product-messaging

output_path: "context/icp/"

triggers:
  auto_suggest_when:
    - "user provides sales call transcripts"
    - "user mentions win/loss analysis or lost deals"
  auto_run_when: null

review_gate: 2
---

# Win/loss analysis

Analyze sales call transcripts to extract actionable insights on why deals are won, lost, retained, or churned. Cross-reference findings with ICP, firmographics, and competitive context to produce strategic recommendations.

---

## Process flowchart

```text
+--------------------------------------------------------------+
|                  WIN/LOSS ANALYSIS PROCESS                     |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 1: INPUT VALIDATION                                     |
| Required: Sales call transcripts with outcome (Win/Loss)      |
| Optional: Website URL per customer, competitors, sales notes  |
| -> If missing: Ask for transcripts                            |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 2: TRANSCRIPT PROCESSING                                |
| Step 2.1: Classify outcome (Win/Loss/Retention/Churn)         |
| Step 2.2: Identify speakers (prospect vs sales rep)           |
| Step 2.3: Extract customer context (company, role, deal)      |
| Step 2.4: Extract verbatim quotes for 6 dimensions            |
| Checkpoint: All transcripts classified, quotes extracted       |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 3: PATTERN AGGREGATION                                  |
| Step 3.1: Group by outcome (Wins vs Losses)                   |
| Step 3.2: Count frequency per insight (X of Y calls)          |
| Step 3.3: Identify top patterns (3+ mentions = confirmed)     |
| Step 3.4: Cross-reference with ICP, competitor, persona       |
| Checkpoint: Patterns grouped, frequency counts calculated      |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| PHASE 4: INSIGHT SYNTHESIS                                    |
| Step 4.1: State each pattern (1-2 sentence summary)           |
| Step 4.2: Provide evidence (verbatim quotes + frequency)      |
| Step 4.3: Identify opportunities (actionable recommendations) |
| Step 4.4: Generate executive summary                          |
| Checkpoint: All patterns have evidence, exec summary complete  |
+--------------------------------------------------------------+
                              |
                              v
+--------------------------------------------------------------+
| SELF-EVALUATION                                               |
| [] Every insight traces to verbatim quote?                    |
| [] Frequency counts provided (X of Y calls)?                  |
| [] No invented patterns (single mentions flagged)?            |
| [] All 6 dimensions addressed or marked "Not discussed"?      |
+--------------------------------------------------------------+
```

---

## Input requirements

### Required

| Input | Description | Source |
|-------|-------------|--------|
| **Transcripts** | Sales call transcripts with customer name and outcome | User provides |
| **Outcome** | Win/Loss/Retention/Churn for each call | User specifies or infer |

### Optional (improve quality)

| Input | How it helps |
|-------|--------------|
| Website URL per customer | Firmographics cross-reference |
| Competitor names | Pre-identify competitors to watch for |
| Sales notes | Additional context (stage, deal size) |

---

## 6 analysis dimensions

| # | Dimension | Win signals | Loss signals |
|---|-----------|-------------|--------------|
| 1 | **Product** | "Exactly what we need," feature praised | "Missing [feature]," "Doesn't do [X]" |
| 2 | **Messaging** | "Now I understand why this matters" | "What does it actually do?" |
| 3 | **GTM/Sales** | "You really understand our problem" | "Demo didn't address our needs" |
| 4 | **Pricing** | "Fair price," "good value" | "Too expensive," "over budget" |
| 5 | **Competition** | "Chose you over [competitor]" | "Going with [competitor]" |
| 6 | **Customer context** | "Need this now," deadline-driven | "No rush," "maybe next year" |

---

## Confidence scoring

| Level | Definition | When to apply |
|-------|------------|---------------|
| **High** | 3+ calls with consistent pattern | Clear recurring theme |
| **Medium** | 2 calls or inferred from strong signals | Emerging pattern |
| **Low** | Single mention or indirect reference | Possible outlier |

---

## Output format

```markdown
# Win/loss analysis report

**Analysis date:** [YYYY-MM-DD]
**Transcripts analyzed:** [N]
**Outcome breakdown:** [X wins / Y losses]

---

## Executive summary

[3-5 sentences on key findings and strategic recommendations]

---

## Win/loss reasons matrix

| Dimension | Win reasons | Loss reasons | Evidence (calls) |
|-----------|-------------|--------------|------------------|
| Product | [1-3 reasons] | [1-3 reasons] | [X of Y calls] |
| Messaging | [1-3 reasons] | [1-3 reasons] | [X of Y calls] |
| GTM/Sales | [1-3 reasons] | [1-3 reasons] | [X of Y calls] |
| Pricing | [1-3 reasons] | [1-3 reasons] | [X of Y calls] |
| Competition | [1-3 reasons] | [1-3 reasons] | [X of Y calls] |
| Customer context | [1-3 reasons] | [1-3 reasons] | [X of Y calls] |

---

## Insights by dimension

### 1. Product

**Pattern:** [One-sentence summary]

**Evidence:**
> "[Verbatim quote]"
> — [Speaker role], [Customer name], [Outcome]

**Frequency:** [X of Y calls] | **Confidence:** High/Medium/Low

**Opportunity:** [Actionable recommendation]

---

[Continue for all 6 dimensions]

---

## Cross-reference analysis

### By competitor

| Competitor | Head-to-head | Why we win | Why we lose |
|------------|--------------|------------|-------------|
| [Competitor 1] | [X wins / Y losses] | [Reasons] | [Reasons] |

---

## Verbatim evidence library

### Win quotes by dimension

**Product:**
> "[Quote]" — [Speaker], [Customer], [Outcome]

### Loss quotes by dimension

[Same structure]

---

## Data gaps

| Gap | Impact | Suggested follow-up |
|-----|--------|---------------------|
| [What's missing] | [Impact] | [How to fill] |
```

---

## Anti-hallucination guardrails

1. **Quote verbatim.** All insights must trace to specific transcript quotes.
2. **Never invent patterns.** If a pattern appears in only one call, label it "Single mention — pattern unconfirmed."
3. **State frequency.** Always note how many calls support each finding (e.g., "4 of 7 calls").
4. **Acknowledge gaps.** If a dimension has no data, mark "Not discussed in transcripts."
5. **Distinguish roles.** Tag who said what — prospect vs. sales rep vs. champion.

---

## Quality checklist

- [ ] Every insight traces to verbatim quote with speaker attribution
- [ ] Frequency counts provided (X of Y calls)
- [ ] Confidence levels assigned to all patterns
- [ ] No invented patterns — all findings grounded in transcript text
- [ ] All 6 dimensions addressed or marked "Not discussed"
- [ ] Executive summary is actionable
- [ ] Data gaps documented with suggested follow-ups

---

## After this skill, consider

1. `/icp-research` — Win patterns reveal who your best customers actually are
2. `/positioning` — Loss reasons show where you need stronger differentiation
3. `/product-messaging` — Win quotes become proof points in your messaging
