---
name: buyer-language-research
description: Find where your buyers are visible in public data and what they say when nobody is selling to them. Use when someone asks "where do I find my audience," "what databases should I look at," "what words do our buyers actually use," "build a target list from situation not firmographics," or wants a source map, a buyer voice file, or a situation ledger before writing any outbound, homepage, or sequence.
---

# Buyer Language Research

Two questions every outbound and messaging effort has to answer before a single word gets written:

1. **What do our buyers say** when they describe the problem in their own words, to each other, with no vendor in the room?
2. **Where are those buyers visible right now**, in public data, in the exact situation we solve?

Most teams answer the first with a persona doc someone wrote from memory, and the second with a firmographic filter (industry, headcount, funding). Both produce messages that could have been sent to anyone. This skill replaces them with evidence.

The idea underneath: **target by situation, not by signal.** A signal is something convenient for the seller ("they just raised, they have budget"). A situation is something the buyer feels on a Tuesday ("denials are up and the only fix anyone has proposed is more staff"). Situations leave public traces. Those traces are findable, dated, and quotable.

## Inputs

Ask for, or infer from what's provided:

- **Who you sell to** — the buyer's job title, the role that signs, and the role that feels the pain if different.
- **What breaks in their day** — one sentence, in plain words. If the user can only describe their product, that is itself the first finding.
- **What you have** — any of: recorded sales calls or transcripts, win/loss notes, support tickets, churn reasons, replies to past outbound, review pages (yours and competitors'), a list of competitors.
- **Vertical** — so the source catalog can be narrowed.

Work with whatever exists. Flag what's missing and what it would have added. Never fabricate a quote to fill a gap.

## Workflow

### Stage 1 — Mine the language (what they say)

Load `references/language-mining.md`. Work through the sources in fidelity order — recorded calls first, public reviews last — and pull **verbatim** phrases. Not paraphrases. The exact words are the product.

Tag every phrase by **moment**:
- *Before* — how they describe the problem before they think a product exists
- *Evaluating* — what they compare, what they fear, what they ask
- *After* — what changed, in their units (hours, dollars, headcount, days)
- *When a vendor pitches them* — what they say about the last pitch that annoyed them. This is the page almost nobody builds and the one that writes the best first line.

Cluster, count, and keep the top phrases with their source and date. Output the **Buyer Voice File** (template in `references/output-templates.md`).

### Stage 2 — Build the source map (where they are visible)

Load `references/source-catalog.md`. For the buyer identified in Stage 1, work down the catalog and pick every source where **their situation** leaves a public trace. For each source, write one row:

| Source | What it reveals about the situation | How to extract | Filter phrase (from Stage 1) |

The filter phrase is the bridge between the two halves: the buyer's own words from Stage 1 become the search terms in Stage 2. A hiring req that contains the buyer's phrase for the problem is worth ten reqs that contain your product category.

Aim for 5 to 8 sources. Fewer than 5 means the situation is too vague; more than 8 means you are collecting instead of targeting.

### Stage 3 — Extract and score

Run the extraction recipes from the catalog. Every row that comes back goes into the **Situation Ledger** with:

- the company
- the exact evidence (a quote, a req title, a review line, a record)
- the source URL
- the date
- which Stage 1 phrase it matched
- a score (rubric in `references/output-templates.md`)

Cut below the score threshold. What survives is a list of companies that are *in the situation*, with a dated, quotable reason for each. That is the list.

### Stage 4 — Run the four tests

Before anything from this research goes into a message, page, or sequence:

1. **The swap test** — could a competitor paste this sentence and have it still be true? If yes, it is not evidence, it is category language. Cut it.
2. **The buyer's-day test** — is the sentence about the buyer's customer or the buyer's day, in the buyer's units? "Reduce operational inefficiency" fails. "Your billers know the payors by first name and the denials still climb" passes.
3. **The vendor-word check** — compare the words on your own site against the words in the reqs and reviews. Where they differ, the reqs and reviews win. List the differences; that list is usually the whole messaging problem.
4. **Freshness** — quotes under 90 days, situation traces under 60. Older evidence goes in the file with a date, never in a message.

### Stage 5 — Hand off

Deliver three files: the Buyer Voice File, the Source Map, and the Situation Ledger. Then, and only then, write anything.

## Rules

- **Public data only.** No scraping behind logins, no purchased personal data, respect every site's terms and robots file. If a source requires a paid tool, say so; do not pretend it is free.
- **Verify or skip.** Every fact that will be used in a message gets checked at the source URL first. An unverifiable claim is a flagged claim, never a used one.
- **Verbatim means verbatim.** Never compress, tidy, or "improve" a quote. Keep their punctuation and their hyphens.
- **Date everything.** A quote without a date is a rumor.
- **Flag gaps out loud.** "No call transcripts — objection language will be thin" beats an invented objection every time.
- **Never present the source list as a finished target list.** The ledger is evidence. Judgment about who to contact still belongs to a person.

## Worked example (abbreviated)

**Seller:** a healthcare SaaS that automates claim denial workflows.
**Buyer:** revenue cycle director at a mid-size hospital; the CFO signs.

*Stage 1 — language.* Competitor G2 reviews: "we still have three people working the denial queue by hand." Reddit r/healthIT thread: "leadership's answer to denials is always another FTE." Becker's panel quote (dated): "denials are a staffing problem we keep solving with more staff." Vendor-word check: the seller's homepage says "streamline revenue cycle operations" — a phrase that appears in zero reviews and zero reqs.

*Stage 2 — sources.* Hospital job boards via ATS APIs (filter: "denial", "appeals specialist", "AR follow-up"); CMS cost report data (rising bad debt); Becker's and HFMA speaker lists (named directors, dated quotes); G2/Capterra reviews of the three main competitors (switching language); state hospital association news (mergers, EHR migrations — the moments denial queues break).

*Stage 3 — ledger.* 412 hospitals scanned → 61 with a live req containing a Stage 1 phrase → 23 with a second trace (a dated quote, a competitor review, or a migration) → score ≥ 3.

*Stage 4 — tests.* "Streamline revenue cycle operations" fails the swap test. "Your denial queue has three people in it and a req for a fourth" passes the buyer's-day test.

*Stage 5.* Twenty-three companies, each with a dated reason. Now write.
