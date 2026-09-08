# Buyer Language Research

A research method for B2B teams, packaged as a Claude skill. It answers two questions before anyone writes outbound, a homepage, or a sequence:

1. What do our buyers actually say, in their own words?
2. Where are they visible right now, in public data, in the situation we solve?

It produces three files: a **Buyer Voice File** (12–15 dated verbatim quotes), a **Source Map** (5–8 public databases and how to pull from each), and a **Situation Ledger** (companies with a dated, quotable reason to contact them, scored).

## Install

**Claude Code (terminal):** copy the `buyer-language-research/` folder into `~/.claude/skills/` (or into your project's `.claude/skills/`). Then type `/buyer-language-research` or just describe what you need — it triggers on "where do I find my buyers," "what databases," "buyer language," and similar.

**claude.ai (web/desktop):** zip the `buyer-language-research/` folder and upload it under Settings → Capabilities → Skills. Available on Pro, Max, Team, and Enterprise plans.

**No Claude, or no skills enabled:** open `PASTE-IN-PROMPT.md`, copy everything below the line, and paste it into any capable model. Same method, no install.

## What's inside

```
buyer-language-research/
  SKILL.md                         the method: 5 stages, 4 tests, rules, worked example
  references/
    source-catalog.md              every public database by trace type and vertical, with extraction recipes
    language-mining.md             how to pull verbatim buyer language and keep it intact
    output-templates.md            the three deliverables + the scoring rubric
  PASTE-IN-PROMPT.md               the no-install version
  README.md                        this file
```

## Rules it enforces

Public data only. Verbatim quotes only, always dated. Verify at the source or flag it. Target by situation (what the buyer is living through), not by signal (what is convenient for the seller). Flag gaps instead of filling them.

## Cost

The method is free. Some sources have paid tiers (review scrapers, LinkedIn post actors, Definitive Healthcare, PACER). The catalog marks each one; none are required.

---

Built by Ben Watkins · thisiscopy.com · This is the research stage of the method I use before writing anything for a client. It is yours to use. If it turns up something you'd like a second set of eyes on, you know where I am.
