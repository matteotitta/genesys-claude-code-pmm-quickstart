# Frequently asked questions

## What is this repo?

A pre-configured Claude Code workspace specifically for B2B product marketers. It includes 10 skills, 3 agents, organized folders, and a context engineering loop that builds your positioning, messaging, and pricing strategy from research.

## What is Claude Code?

Claude Code is a tool that runs Claude inside your project folder. It reads your files, creates new ones, searches the web, and follows structured processes (skills). Unlike chatbots, Claude Code works with your actual files and remembers your context across sessions via CLAUDE.md.

## Do I need to know how to code?

No. This repo is designed for marketers who want the power of Claude Code without the developer learning curve. You'll type commands like `/context-loop` and Claude does the rest.

## What's the difference between this and the GTM quickstart?

The GTM quickstart is broad — it covers all GTM roles (demand gen, content, brand, etc.). This PMM quickstart goes deeper on product marketing specifically:
- Adds win/loss analysis and pricing strategy skills
- Organizes context by type (brand, competitors, ICP)
- Has a 7-step context loop (vs 5 in GTM)
- Focused on the research → strategy pipeline that PMMs live in

## What is CLAUDE.md?

CLAUDE.md is a file that Claude Code loads automatically at the start of every session. It tells Claude who you are, what your company does, who your competitors are, what your voice sounds like, and what your quality standards are. The `/quickstart` command generates yours.

## What are skills?

Skills are reusable prompt templates saved as files. Instead of re-explaining competitive analysis every session, you build a skill once and run `/competitor-research Acme` forever. Each skill handles the process, output format, and quality checks.

## What does the context engineering loop produce?

Up to 7 outputs in sequence:
1. Company context (your market position, traction, team)
2. Competitor profiles (one per competitor, researched in parallel)
3. Win/loss analysis (optional — requires sales call transcripts)
4. ICP research (who buys from you and why)
5. Positioning strategy (category, differentiators, statement)
6. Product messaging library (value props, proof points, blocks)
7. Pricing strategy (tiers, value metrics, experiments)

## How long does the context loop take?

About 35 minutes total. Competitor research (10 min) is the longest step because it runs deep analysis on each competitor. The rest average 3-5 minutes each.

## Can I run skills individually?

Yes. The context loop runs them in sequence, but you can run any skill on its own:
```
/company-context
/competitor-research [name]
/win-loss-analysis
/icp-research
/positioning
/product-messaging
/pricing-strategy
```

The order matters — later skills use earlier outputs as context. Run them in the sequence above for best results.

## What if I don't have sales call transcripts?

The context loop skips win/loss analysis automatically if you don't have transcripts. You can run it later anytime you have transcripts available. The loop still produces strong output without it — win/loss just makes ICP and positioning sharper.

## How do I update my context?

Edit any output file directly, or re-run the skill. Claude reads the latest versions automatically. When your competitors change, re-run `/competitor-research`. When your ICP evolves, re-run `/icp-research`. Each new run overwrites the previous output (previous versions are preserved in git history).
