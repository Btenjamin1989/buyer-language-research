# Language Mining — how to pull the buyer's words and keep them intact

## Fidelity order

Work sources in this order. Stop early only if you have enough; never skip a higher source because a lower one is easier.

1. **Recorded sales and discovery calls** — the buyer explaining the problem to a stranger. Highest fidelity. Pull from the *prospect's* turns only.
2. **Win/loss notes and lost-deal debriefs** — the sentence that ended the deal, in the buyer's words if anyone wrote it down.
3. **Support tickets, churn reasons, cancellation surveys** — the problem after the sale.
4. **Replies to past outbound** — including the annoyed ones. "Not interested, we already use X" is a competitor name and a moment.
5. **Reviews of competitors** — switching language (see source catalog §B).
6. **Community threads** — the unsold version of the problem (§C).
7. **Buyers speaking in public** — podcasts, panels, posts (§D).
8. **Hiring reqs** — the problem with a budget attached (§A). Note: reqs are also a *targeting* source; here they are a *language* source.

## What to pull

- The **verbatim sentence**. Not the gist. If the buyer said "we're throwing bodies at it," the file says "we're throwing bodies at it," not "they rely on manual headcount."
- The **speaker's role**, the **source**, the **date**.
- The **moment**: before / evaluating / after / when a vendor pitches them.
- The **unit** the buyer used, if any: hours, days, dollars, headcount, claims, tickets, seats. Units are the most reusable part of the sentence.

## What to ignore

- Vendor voice quoted inside a buyer source (a review that repeats the product's tagline).
- Anything a marketer wrote *about* buyers.
- Compliments without a mechanism ("great tool, love it"). Keep the sentence that says *why*.

## Clustering

1. Put every phrase on one line with its tags.
2. Group by the underlying complaint, not by the words used. "Three people on the denial queue" and "throwing bodies at it" are one cluster.
3. Count. The cluster size is the prior for how often a cold reader will recognize themselves.
4. Within each cluster, keep the two or three most specific phrasings. Specific beats representative.
5. Name each cluster in the buyer's words, never yours. If the cluster is "operational inefficiency," you have not read closely enough.

## The four moments, and what each one is for

| Moment | What it sounds like | What it writes |
|---|---|---|
| Before | "We didn't even have a name for it. It was just Tuesday." | the opening line of any cold message |
| Evaluating | "Everyone says AI. Show me the claim it caught." | the objection section, the FAQ, the proof block |
| After | "Went from four days to same-day. Two people back on real work." | every result claim, in their units |
| When a vendor pitches them | "The last one opened with 'I noticed you're hiring.' Deleted." | the never-do list, and the best first line by contrast |

The fourth moment is the one almost no team collects, and it is the one that most reliably prevents the message everyone else sends.

## The vendor-word check

Take the twenty most common nouns and verbs on the seller's homepage. Take the twenty most common nouns and verbs across the reqs and reviews. Put them side by side. The words that appear only on the seller's side are the words the buyer does not use. That list is usually the entire messaging problem, and it is the first thing to show the seller.

## The Buyer Voice File (output)

12 to 15 verbatim quotes, organized by moment, each with role, source, date, and unit. One page. Every quote passes the swap test. Nothing paraphrased. Template in `output-templates.md`.

## Gaps

If a moment has fewer than three quotes, write the gap into the file: "*Evaluating*: thin — only two quotes, both from reviews; no call transcripts available. Objection language will be weaker until calls are added." A visible gap is worth more than a filled one.
