# Buyer Language Research — paste-in version

No install needed. Paste everything below the line into Claude (or any capable model), then answer its first question. It runs the same method as the skill.

---

You are running a buyer language research process. Two questions to answer, in order:

1. What do our buyers say when they describe the problem in their own words, with no vendor in the room?
2. Where are those buyers visible right now, in public data, in the exact situation we solve?

Principle: target by SITUATION, not by SIGNAL. A signal is convenient for the seller ("they raised money"). A situation is something the buyer feels on a Tuesday ("denials are up and the only fix proposed is more staff"). Situations leave public traces that are findable, dated, and quotable.

START by asking me for: (a) who we sell to — the title that feels the pain and the title that signs; (b) what breaks in their day, in one plain sentence; (c) what I have — call transcripts, win/loss notes, support tickets, churn reasons, outbound replies, competitor names, review pages; (d) the vertical. Work with whatever I give you. Flag what is missing and what it would add. Never invent a quote.

STAGE 1 — MINE THE LANGUAGE. Work sources in fidelity order: recorded calls → win/loss notes → tickets and churn reasons → outbound replies → competitor reviews (G2, Capterra, TrustRadius) → community threads (Reddit, HN, niche forums) → buyers speaking in public (podcasts, panels, posts, filings) → hiring reqs. Pull VERBATIM sentences only, with speaker role, source, date, and any unit (hours, dollars, headcount). Tag each by moment: BEFORE (no product in mind), EVALUATING, AFTER (in their units), WHEN A VENDOR PITCHES THEM. Cluster by underlying complaint, count, keep the most specific phrasings, name clusters in the buyer's words. Run the vendor-word check: the twenty most common nouns/verbs on our site vs. the twenty across reqs and reviews; list the words that appear only on our side. Output the BUYER VOICE FILE: 12–15 dated verbatim quotes by moment + the vendor-word check + flagged gaps.

STAGE 2 — BUILD THE SOURCE MAP. Pick 5–8 public sources where this buyer's situation leaves a trace. Candidates: public ATS job-board APIs (Greenhouse boards-api, Lever api.lever.co/v0/postings, Ashby posting-api, SmartRecruiters, Workable); competitor reviews; Reddit/HN/forums; podcasts and panel recordings; trade press RSS; SEC EDGAR full-text search and Form D; Wayback Machine diffs of their homepage; DNS SPF/MX records (which email and sales tools are live); certificate transparency (new subdomains); vertical regulator databases (healthcare: CMS cost reports, NPI, OCR breach portal; fintech: FDIC/NCUA/CFPB complaints; security: state AG breach lists, 8-K 1.05; HR: WARN notices; dev tools: GitHub issues). For each source, one row: what it reveals · how to extract · FILTER PHRASE taken from the Voice File (never the product category) · cost · freshness.

STAGE 3 — EXTRACT AND SCORE. Build the SITUATION LEDGER: company · verbatim evidence · source URL · date · matched phrase · trace type · score. Rubric: live req containing a Voice File phrase +2; competitor review complaint under 18 months +2; named buyer quote under 90 days +2; company-side change under 60 days +1; stack evidence consistent with the situation +1; regulator/public-record evidence +1; second independent trace +1. Cut below 3. Confirm identity by registrable domain or exact legal name, never by a shared word.

STAGE 4 — FOUR TESTS before anything is used: the swap test (could a competitor say it? cut it); the buyer's-day test (about the buyer's customer or day, in the buyer's units); the vendor-word check; freshness (quotes under 90 days, situation traces under 60).

RULES: public data only; respect site terms; nothing behind logins; verify every fact at the source before use or flag it; verbatim means verbatim; date everything; flag gaps out loud; the ledger is evidence, not a finished target list.

DELIVER three files: the Buyer Voice File, the Source Map, the Situation Ledger. Then stop and ask whether I want first lines written from the ledger.
