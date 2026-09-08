# Output Templates

Three deliverables, in this order. Nothing gets written for the market until all three exist.

---

## 1. Buyer Voice File

```
BUYER VOICE FILE — [buyer role] at [company type]
Built [date] · Sources: [list] · Gaps: [list or "none"]

BEFORE (how they describe it with no product in mind)
1. "[verbatim]" — [role], [source], [date] · unit: [x]
2. ...

EVALUATING (what they compare, fear, ask)
1. "[verbatim]" — [role], [source], [date]
2. ...

AFTER (what changed, in their units)
1. "[verbatim]" — [role], [source], [date] · unit: [x]
2. ...

WHEN A VENDOR PITCHES THEM (what they say about the last pitch)
1. "[verbatim]" — [role], [source], [date]
2. ...

VENDOR-WORD CHECK
Words only on our site:      [list]
Words only in reqs/reviews:  [list]
Verdict: [one sentence]
```

Rules: 12–15 quotes total. Every quote verbatim. Every quote dated. Every quote passes the swap test. Fewer than three in a moment = flag the gap.

---

## 2. Source Map

| # | Source | What it reveals about the situation | How to extract | Filter phrase (from the Voice File) | Cost | Freshness |
|---|---|---|---|---|---|---|
| 1 | | | | | free / key / paid | days |

5 to 8 rows. The filter phrase column must contain the buyer's words, never the product category. If a row's filter phrase is "revenue cycle software," delete the row and try again.

---

## 3. Situation Ledger

| Company | Evidence (verbatim) | Source URL | Date | Matched phrase | Trace type | Score |
|---|---|---|---|---|---|---|

**Scoring rubric** (adjust the weights to the seller; keep the shape):

| Trace | Points |
|---|---|
| Live hiring req containing a Voice File phrase | +2 |
| Competitor review complaint under 18 months, matching a cluster | +2 |
| Named buyer quote under 90 days (podcast, panel, post, filing) | +2 |
| Company-side change under 60 days (homepage rewrite, new subdomain, funding, migration) | +1 |
| Stack evidence consistent with the situation (SPF shows tools with no visible use; no marketing sends at all) | +1 |
| Regulator or public-record evidence of the pressure (cost report, complaint database, breach filing) | +1 |
| Second independent trace of the same situation | +1 |

**Cut at 3.** Below 3, the company is a guess. At 3 or above, there is a dated, quotable reason to write to them, and the reason is already in the row.

**Identity check before anything ships:** confirm the company in each row is the company you think it is. Shared words are not identity (a "Particle" in health tech and a "Particle" in IoT are two companies). Match on the registrable domain or the exact legal name, never on a substring.

---

## 4. Optional: the first line

Once the ledger exists, each row can produce the first sentence of a message — the buyer's own situation, in the buyer's own units, dated:

> "Your board has a req for a fourth denials specialist, posted Tuesday. Three people are already working that queue by hand."

Whether to write it is a separate decision. The research is finished when the three files above exist.
