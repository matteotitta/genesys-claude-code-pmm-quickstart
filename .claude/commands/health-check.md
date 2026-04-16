---
name: health-check
description: Verify PMM quickstart setup — CLAUDE.md, skills, agents, outputs
---

# PMM health check

Run a diagnostic on the PMM quickstart workspace. Check every component and report status.

---

## Checks to run

### 1. CLAUDE.md

Read the CLAUDE.md file in the project root. Check:

- [ ] File exists
- [ ] `## Who I am` section is personalized (not placeholder text)
- [ ] `## Competitive landscape` lists actual competitors
- [ ] `## Voice and style` has real adjectives (not defaults)
- [ ] `## Output routing` table is intact
- [ ] `## Workspace structure` section is intact

**Status:** If all pass → "CLAUDE.md is personalized and complete"
**If any fail:** "CLAUDE.md needs attention — run `/quickstart` to set it up"

### 2. Skills (10 required)

Check that each skill folder exists with a SKILL.md file:

| Skill | Path | Status |
|-------|------|--------|
| company-context | `.claude/skills/company-context/SKILL.md` | |
| competitor-research | `.claude/skills/competitor-research/SKILL.md` | |
| icp-research | `.claude/skills/icp-research/SKILL.md` | |
| win-loss-analysis | `.claude/skills/win-loss-analysis/SKILL.md` | |
| positioning | `.claude/skills/positioning/SKILL.md` | |
| product-messaging | `.claude/skills/product-messaging/SKILL.md` | |
| tov-guidelines | `.claude/skills/tov-guidelines/SKILL.md` | |
| brand-guidelines | `.claude/skills/brand-guidelines/SKILL.md` | |
| content-strategy | `.claude/skills/content-strategy/SKILL.md` | |
| pricing-strategy | `.claude/skills/pricing-strategy/SKILL.md` | |

**Status:** "[X] of 10 skills available"

### 3. Agents (3 required)

Check that each agent file exists:

| Agent | Path | Status |
|-------|------|--------|
| competitor-researcher | `.claude/agents/competitor-researcher.md` | |
| market-researcher | `.claude/agents/market-researcher.md` | |
| pmm-strategist | `.claude/agents/pmm-strategist.md` | |

**Status:** "[X] of 3 agents available"

### 4. Context outputs

Check for research outputs in the context folders:

| Output | Path pattern | Status |
|--------|-------------|--------|
| Company context | `context/*company-context*` | |
| Competitor research | `context/competitors/*competitor*` | |
| ICP research | `context/icp/*icp-research*` | |
| Win/loss analysis | `context/icp/*win-loss*` | |
| TOV guidelines | `context/brand/*tov*` | |
| Brand guidelines | `context/brand/*brand*` | |

**Status:** "[X] context outputs found"

### 5. Product marketing outputs

Check for strategy outputs:

| Output | Path pattern | Status |
|--------|-------------|--------|
| Positioning | `product-marketing/positioning/*positioning*` | |
| Product messaging | `product-marketing/positioning/*messaging*` | |
| Pricing strategy | `product-marketing/positioning/*pricing*` | |
| Content strategy | `product-marketing/content/*content-strategy*` | |

**Status:** "[X] product marketing outputs found"

---

## Report format

Present results as a summary table:

"--- PMM quickstart health check ---

| Component | Status | Action needed |
|-----------|--------|---------------|
| CLAUDE.md | [Personalized / Needs setup] | [None / Run /quickstart] |
| Skills | [X/10 available] | [None / List missing] |
| Agents | [X/3 available] | [None / List missing] |
| Context outputs | [X found] | [None / Run /context-loop] |
| PMM outputs | [X found] | [None / Run /context-loop] |

[Overall assessment: one sentence]"

If everything is green: "All systems go. Your PMM workspace is fully operational."

If context loop hasn't been run: "Foundation is set up. Run `/context-loop` to generate your research and strategy outputs."

If CLAUDE.md isn't personalized: "Start with `/quickstart` to personalize your workspace."
