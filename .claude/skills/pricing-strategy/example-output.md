<!--
EXAMPLE OUTPUT: This is what the /pricing-strategy skill produces.
Company: DataPulse (fictional B2B SaaS analytics platform, used as example)
Generated: April 2026
Purpose: Show students what "good output" looks like before they run the skill on their own product
-->

# Pricing strategy: DataPulse

- **Research date**: April 2026
- **Current pricing**: Free tier + $14/seat/mo (single paid plan)

---

## Executive summary

DataPulse's current single-paid-tier model leaves money on the table with larger teams and creates a gap between free and $14/seat. The analytics market is converging on usage-based pricing (events/month) layered with seat-based access, but DataPulse's core differentiator — no SQL required — makes per-seat pricing more natural than usage-based.

Recommendation: Move to a three-tier Good-Better-Best structure. Entry tier at $8/seat/mo targets small teams currently on free, mid tier at $14-18/seat/mo (current anchor) adds collaboration features, and enterprise tier at custom pricing unlocks SSO/audit logs that currently block enterprise deals. The mid tier becomes the default — decoy effect makes it the obvious choice.

---

## 1. Competitive pricing analysis

### Market overview

| Competitor | Model | Entry price | Mid tier | Enterprise | Value metric |
|------------|-------|-------------|----------|------------|--------------|
| Amplitude | Usage-based | Free (10M events) | $49/mo (growth) | Custom | Events/month |
| Mixpanel | Usage-based | Free (20M events) | $24/mo (growth) | Custom | Events/month |
| Heap | Usage-based | Free (10K sessions) | Custom | Custom | Sessions/month |
| PostHog | Usage-based | Free (1M events) | Pay-as-you-go | Custom | Events/month |

**Source:** Competitor pricing pages, accessed April 2026 | **Confidence:** High

**Market positioning observations:**
- All major competitors use usage-based pricing (events or sessions) — DataPulse is the outlier with per-seat
- Free tiers are generous — competing on free tier limits is a race to the bottom
- Enterprise pricing is universally "contact us" — SSO/audit logs are the gate
- Amplitude's growth plan at $49/mo is the highest mid-tier anchor in the market

---

## 2. Value metric analysis

| Value metric | Alignment | Predictability | Growth-friendly | Recommendation |
|-------------|-----------|----------------|-----------------|----------------|
| Per seat | 4/5 | 5/5 | 3/5 | Recommended (primary) |
| Per event | 3/5 | 2/5 | 4/5 | Not recommended |
| Flat rate | 2/5 | 5/5 | 2/5 | Not recommended |
| Hybrid (seat + usage) | 4/5 | 3/5 | 4/5 | Consider for Best tier |

### Recommended value metric

**Primary metric:** Per seat
**Rationale:** DataPulse's differentiation is "analytics without SQL" — the value scales with how many team members can self-serve. Per-seat pricing aligns with this: more people using it = more value delivered. Usage-based pricing (events) would create anxiety for marketing teams who can't predict event volume, undermining the "easy" positioning.

**Confidence:** Medium — recommend validating with Van Westendorp survey before implementation.

---

## 3. Tier structure recommendation

### Good tier: Starter

**Target user:** Small teams (1-3 people) getting started with product analytics
**Price recommendation:** $8-10/seat/mo
**Features:**
- Up to 5 seats
- Core analytics dashboards
- 10,000 events/month
- 30-day data retention
- Email support

**Upgrade trigger:** Team grows beyond 5, need longer retention, want saved reports

**Rationale:** Entry price undercuts Amplitude Growth ($49/mo) and anchors below the current $14/seat. Low enough to convert free users. 5-seat limit creates natural expansion moment.

### Better tier: Team (default recommended tier)

**Target user:** Growth-stage teams (5-25 people) who need collaboration and deeper analysis
**Price recommendation:** $14-18/seat/mo
**Features:**
- Everything in Starter, plus:
- Unlimited seats
- 100,000 events/month
- 90-day data retention
- Saved reports and shared dashboards
- Slack/email alerts
- Priority chat support

**Upgrade trigger:** Need SSO, audit logs, custom retention, dedicated support

**Rationale:** Anchored at current pricing ($14/seat). Adding Starter below makes this feel like better value (decoy effect). Collaboration features (shared dashboards, alerts) justify the premium over Starter.

### Best tier: Enterprise

**Target user:** Larger teams (25+) with compliance and security requirements
**Price recommendation:** Custom pricing (estimated $25-35/seat/mo based on competitive analysis)
**Features:**
- Everything in Team, plus:
- SSO (SAML/OIDC)
- Audit logs
- Custom data retention (1yr+)
- API access
- Dedicated CSM
- SLA guarantee

**Upgrade trigger:** Security review requirements, compliance needs, large team deployment

**Rationale:** SSO and audit logs are the #1 loss reason in enterprise deals (3 of 3 losses cite this). Gating behind enterprise tier captures value while solving the biggest sales blocker. Custom pricing allows flexibility for large deployments.

---

## 4. Customer research design

### Van Westendorp survey

**Target respondents:** Current free users + trial users in mid-market segment
**Recommended sample size:** 100+ respondents
**Segment by:** Team size (1-5, 5-25, 25+) and current analytics tool

**Questions:**
1. "At what monthly price per seat would you begin to question DataPulse's quality?"
2. "At what monthly price per seat would DataPulse be a bargain — a great buy for the money?"
3. "At what monthly price per seat would DataPulse be getting expensive, but you'd still consider it?"
4. "At what monthly price per seat would DataPulse be too expensive to consider?"

**Deployment:** In-app survey to free users with 14+ days of activity. Email survey to trial users who converted and churned.

---

## 5. Pricing page experiments

| Priority | Experiment | Hypothesis | Success metric |
|----------|------------|------------|----------------|
| 1 | Add Starter tier below current plan | Three options increase mid-tier selection via decoy effect | Mid-tier conversion rate |
| 2 | Default toggle to annual pricing | Annual default increases annual plan selection by 15-25% | Annual plan % |
| 3 | Add "Most popular" badge to Team tier | Badge guides 60%+ of signups to target tier | Team tier selection % |
| 4 | Show "vs Amplitude" price comparison | Competitive anchor increases perceived value | Conversion rate |

### Copy recommendations

**Headline:** "Analytics your whole team can use"
**Tier names:** Starter / Team / Enterprise (avoid jargon — "Growth" and "Scale" are overused)
**CTA text:** Starter: "Start free" | Team: "Start 14-day trial" | Enterprise: "Talk to us"

---

## 6. Data gaps and next steps

| Data point | Impact | How to obtain |
|------------|--------|---------------|
| Customer willingness to pay by segment | Critical for validating price points | Run Van Westendorp survey (above) |
| Feature importance ranking | Needed for tier fencing validation | Run MaxDiff study with 50+ users |
| Annual vs. monthly preference | Affects cash flow and retention | Add to Van Westendorp survey |
| Price sensitivity by company size | Enterprise pricing calibration | Segment survey results by team size |

### Recommended next steps

1. Deploy Van Westendorp survey to validate $8-10 and $14-18 ranges
2. Add SSO and audit logs to product roadmap (enterprise deal blocker)
3. A/B test three-tier pricing page vs. current single tier
4. Train sales on Good-Better-Best positioning and upgrade triggers
