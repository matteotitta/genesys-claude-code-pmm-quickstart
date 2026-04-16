# Genesys Claude Code for Product Marketing — quickstart

Get Claude Code running your product marketing research and strategy in 35 minutes. Clone this repo, run two commands, and walk away with competitive intelligence, ICP profiles, positioning, messaging, and a pricing strategy — all built on your actual company data.

---

## Quick start (3 steps)

Already familiar with Claude Code and Git? Here's the fast path:

```bash
git clone https://github.com/matteotitta/claude-code-pmm-quickstart.git
cd claude-code-pmm-quickstart
```

Open in Cursor or VS Code. Click the orange Claude Code icon in the right sidebar.

1. Type `/quickstart` — guided tour + generates your personalized CLAUDE.md
2. Type `/context-loop` — runs 7 research and strategy skills in sequence
3. Type `/health-check` — verify everything worked

**New to all of this?** Keep reading — the full guide covers everything from installing Cursor to pushing your work to GitHub.

---

## Who this is for

B2B product marketers who want to use Claude Code for PMM work — positioning, messaging, pricing, competitive research, ICP development, and win/loss analysis.

You don't need to know how to code. You don't need terminal experience. You don't need to have used GitHub before. This repo is designed for product marketers who want research-to-strategy output without the developer learning curve.

**This is not:**
- A chatbot or prompt library
- A developer tool (though developers can use it too)
- A replacement for strategic thinking (it accelerates your process, it doesn't replace your judgment)

---

## Requirements

- **Claude Max** ($100/mo, recommended) or **Pro** ($20/mo) — get one week on me at [claude.ai](https://claude.ai/referral/vq_wUYBj3A)
- **Mac** computer with admin access
- **Cursor** IDE (free) or **VS Code** (free) — [cursor.com](https://cursor.com) / [code.visualstudio.com](https://code.visualstudio.com)
- **VS Code Extension for Claude Code** — a UI upgrade for your Claude Code experience inside your IDE
- Stable internet connection
- No API keys needed to start (optional upgrades available later)

---

## What you get

This repo is a pre-configured Claude Code workspace for B2B product marketers. Everything is set up: the folder structure, the skills, the commands, the agents, and the templates. You just add your company's inputs and run the skills.

### The PMM context engineering loop

```
company-context → competitor-research (parallel) → win-loss (optional) → icp-research → positioning → product-messaging → pricing-strategy
     (context)              (context)                  (context)          (context)       (strategy)      (strategy)          (strategy)
```

You start with context. Context feeds strategy. Every piece builds on the last.

Prompt engineering is how you ask the question. Context engineering is what Claude knows *before* you ask anything. A great prompt with zero context produces internet-grade marketing copy. A simple prompt with rich context — your positioning against specific competitors, your ICP's actual pain points, your brand voice rules — produces output that sounds like it came from inside your company. That's what this repo sets up.

### Skills (10)

| Skill | Level | What it produces |
|-------|-------|-----------------|
| `/company-context` | Research | Your company's market position, traction, team, funding |
| `/competitor-research` | Research | Deep competitor profiles (one per competitor) |
| `/icp-research` | Research | Ideal customer profiles, personas, buying journey |
| `/win-loss-analysis` | Research | Win/loss patterns from sales call transcripts |
| `/positioning` | Strategy | Category, alternatives, differentiators, positioning statement |
| `/product-messaging` | Strategy | Value props, proof points, messaging blocks |
| `/pricing-strategy` | Strategy | Tier structure, value metrics, packaging, experiments |
| `/tov-guidelines` | Brand | Voice patterns, vocabulary, do/don't guidelines |
| `/brand-guidelines` | Brand | Visual + verbal identity, design tokens |
| `/content-strategy` | Strategy | Channel mix, content pillars, editorial plan |

Each skill folder includes an `example-output.md` so you can see what the skill produces before running it on your own company.

### PMM skill chains

Skills connect in a dependency chain — each one makes the next sharper:

```
Research layer:
  company-context ─────────┐
  competitor-research (x3) ─┤── feeds into ──▶ positioning
  win-loss-analysis ────────┤                      │
  icp-research ─────────────┘                      ▼
                                            product-messaging
                                                   │
                                                   ▼
                                            pricing-strategy
```

**Key insight:** Win/loss analysis is optional but powerful. If you have sales call transcripts, it makes your ICP and positioning significantly sharper because it's grounded in what real buyers actually said.

### Commands

| Command | What it does |
|---------|-------------|
| `/quickstart` | Guided Cursor tour + CLAUDE.md generation |
| `/context-loop` | Run all 7 PMM skills in sequence |
| `/health-check` | Verify system state — CLAUDE.md, skills, outputs |
| `/next-steps` | Post-loop guidance — what to build next |
| `/learn` | Educational deep-dives into Claude Code concepts |

### Agents

| Agent | What it does |
|-------|-------------|
| `competitor-researcher` | Deep competitive analysis across positioning, pricing, features, content |
| `market-researcher` | Company background, traction data, ICP profiling |
| `pmm-strategist` | Synthesizes research into positioning, messaging, and pricing strategy |

---

## Step-by-step setup

### Step 1: Install Cursor (5 min)

1. Go to [cursor.com](https://cursor.com)
2. Download the Mac version (.dmg file)
3. Open the .dmg file from Downloads
4. Drag the Cursor icon into the Applications folder
5. Open Finder, go to Applications, find Cursor
6. **Right-click** Cursor and click **Open** (not double-click — this bypasses the macOS security warning on first launch)
7. Create a Cursor account (free) when prompted

### Step 2: Install the Claude Code extension (3 min)

1. In Cursor, find the **Extensions icon** in the left sidebar (looks like 4 squares)
2. Click it
3. Search for: `Claude Code for VS Code`
4. Click **Install**
5. Look for the **orange Claude icon** in the right sidebar

### Step 3: Authenticate Claude Code (2 min)

1. In the Claude Code panel, write anything (e.g., "Hi") and press Enter
2. You'll be prompted to **"Sign in with Claude subscription"**
3. Your browser opens — log in with your Claude Max or Pro account
4. Approve the connection when prompted
5. Return to Cursor

### Step 4: Clone this repo (3 min)

1. In Claude UI, paste this command and press Enter:

```bash
git clone https://github.com/matteotitta/claude-code-pmm-quickstart.git .
```

2. Wait for cloning to complete
3. You should see files appear in the left sidebar

### Step 5: Run /quickstart (15 min)

Before starting, have these ready:
- Your company website URL
- 2-5 competitor names (and their websites if you know them)
- Your role / title
- 3-5 adjectives that describe your brand voice
- Any words Claude should never use in your content
- Your current pricing model (or "pre-launch")

Type `/quickstart` in the Claude Code panel and press Enter.

### Step 6: Run the context engineering loop (35 min)

Type `/context-loop` and press Enter. Claude runs up to 7 skills in sequence:

1. Researches your company (~5 min)
2. Researches your competitors in parallel (~10 min)
3. Runs win/loss analysis if you provided transcripts (~5 min)
4. Builds your ideal customer profile (~5 min)
5. Synthesizes your positioning strategy (~3 min)
6. Generates your messaging library (~3 min)
7. Develops your pricing strategy (~5 min)

### Step 7: Run /health-check (1 min)

Type `/health-check` to verify everything is set up correctly.

---

## Folder structure

```
claude-code-pmm-quickstart/
├── .claude/
│   ├── commands/          → /quickstart, /context-loop, /health-check, /next-steps, /learn
│   ├── skills/            → 10 skills, each with a SKILL.md and example-output.md
│   ├── agents/            → competitor-researcher, market-researcher, pmm-strategist
│   └── settings.json      → Claude Code configuration
├── context/               → Research outputs, organized by type
│   ├── brand/             → Brand guidelines + TOV
│   ├── competitors/       → Competitor profiles (one per competitor)
│   └── icp/               → ICP research + win/loss analysis
├── product-marketing/     → Strategy outputs
│   ├── positioning/       → Positioning, messaging, pricing
│   └── content/           → Content strategy
├── templates/             → CLAUDE.md + SKILL.md builder prompts
├── examples/              → Redirects to skill-level examples
├── CLAUDE.md              → Your persistent context (personalized by /quickstart)
├── FAQ.md                 → Common questions answered
└── README.md              → You are here
```

**Key principle:** `context/` is research. `product-marketing/` is strategy. Research feeds strategy. The organized subfolders mean Claude automatically understands what kind of work you're doing based on where you are.

---

## After the loop

Run `/next-steps` to see what to build next. The highlights:

1. **Push to GitHub** — back up your work to the cloud
2. **Run brand skills** — `/tov-guidelines` then `/brand-guidelines` (they enrich everything)
3. **Run content strategy** — `/content-strategy` uses your positioning and ICP as input
4. **Add API keys** — Exa (better search, 1,000 free/mo) and Firecrawl (website scraping, 500 free/mo)
5. **Build your own skills** — use `templates/SKILL-MD-TEMPLATE.md`

---

## Part of Genesys' Claude Code programme

This quickstart is the PMM-focused entry point. Everything you build here is real foundation work — not throwaway scaffolding. The programme builds directly on top of it:

```
W1: PMM Quickstart (this repo)   → Foundation: CLAUDE.md, 10 skills, context loop
W2: Skills library               → Depth: custom skills, MCP + API connectors
W3: Automation + Dispatch        → Speed: recurring tasks, mobile access
W4: Full system                  → Scale: agents, hooks, rules, memory, sessions
```

**Ready to go further?** [GTM Engineer School](https://www.gtm-engineer-school.com/) · [Book a call](https://cal.com/matteo-titta/30min)

---

Built by [Matteo Tittarelli](https://www.linkedin.com/in/matteo-titta/), founder at [Genesys Growth](https://genesysgrowth.com).

[Book a call](https://calendly.com/genesys-growth/discovery-call) · [Newsletter](https://newsletter.genesysgrowth.com/) · [Star this repo](https://github.com/matteotitta/claude-code-pmm-quickstart)
