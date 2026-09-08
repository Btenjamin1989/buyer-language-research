# Source Catalog — where buyers are visible in public data

Every source below is public, and each one reveals a *situation* (something the buyer is living through), not just a *signal* (something convenient for a seller). For each, the catalog gives: what it reveals, how to extract it, and what to filter on. Always filter with the buyer's own phrases from Stage 1 — never with your product category.

Legend: **free** = no account needed · **free-key** = free API key · **paid** = paid tool or actor · **manual** = read by hand, worth it for small lists.

---

## A. Hiring reqs — the buyer describing their own pain, in writing, with a budget attached

A job posting is a company confessing what is broken and paying to fix it. It is the single highest-yield public source for most B2B sellers, and the buyer's words in the req are almost never the vendor's words on the homepage.

**Public ATS JSON endpoints (free, no key, stable):**

| ATS | Endpoint | Notes |
|---|---|---|
| Greenhouse | `https://boards-api.greenhouse.io/v1/boards/{slug}/jobs?content=true` | slug is usually the company name lowercased; the `content=true` flag returns full descriptions |
| Lever | `https://api.lever.co/v0/postings/{slug}?mode=json` | full description in `descriptionPlain` |
| Ashby | `https://api.ashbyhq.com/posting-api/job-board/{slug}` | returns `jobs[]` with `descriptionHtml` |
| SmartRecruiters | `https://api.smartrecruiters.com/v1/companies/{slug}/postings` | paginated; detail per posting id |
| Workable | `https://apply.workable.com/api/v1/widget/accounts/{slug}` | lighter payload; description needs a second call |

**How to find the slug:** the careers link on the company site usually contains it (`boards.greenhouse.io/acme`, `jobs.lever.co/acme`, `jobs.ashbyhq.com/acme`). Try the slug on each ATS; a 200 with jobs is the answer. Expect roughly one in three mid-size B2B companies on one of these five.

**Liveness traps** (all real, all common): a board that returns jobs from a company that was acquired; a slug that belongs to a different company with a similar name; a posting that has been open for 200+ days (often evergreen, not a live need); a board with zero jobs that is still a valid board. Check `updated_at` where available, and confirm the company name in the payload matches the company you think it is.

**⚠ Coverage limit (tested):** medical practices, clinics, law firms, and most non-tech operators are almost never on these five ATSs — they hire through Paylocity, Workday, ADP, or a careers page. For those buyers the public APIs return nothing; use LinkedIn Jobs search, ZipRecruiter, or an Apify LinkedIn-jobs actor, and expect job-board pages to refuse automated reads (open the req by hand for the date and verbatim).

**Aggregators when the company is not on an ATS API:** LinkedIn Jobs (manual or via a scraping actor), Indeed, Google Jobs (structured data on the company's careers page).

**What to filter on:** the buyer's phrase for the problem (Stage 1), the role that feels the pain, and the tools they name. A req for a "denials specialist" is a situation; a req for a "marketing manager" is noise until the description mentions the pain.

---

## B. Reviews — switching language, in the buyer's units

Reviews of *competitors* are more useful than reviews of you: they contain the sentence a buyer says the day they decide to leave.

| Source | Extract | Filter |
|---|---|---|
| G2 | Apify actor `automation-lab/g2-scraper` (paid, cheap) — `mode: "reviews"` with the product review URL, or `mode: "category"` for the whole landscape | "What do you dislike" answers; 1-3 star reviews; the words after "we switched because" |
| Capterra | Apify actor `getdataforme/capterra-reviews-scraper-bulk` (paid, cheap) by company name | cons; "would have liked"; pricing complaints |
| TrustRadius | manual or generic scraper | long-form; best for enterprise buyers |
| Gartner Peer Insights | manual | enterprise only; gated after a few reviews |
| App marketplaces (HubSpot, Salesforce AppExchange, Shopify, Atlassian) | manual or actor | reviews of integrations reveal the *workflow* the buyer lives in |

**Rule:** pull the verbatim sentence, the star rating, the reviewer's role, and the date. Reviews older than 18 months describe a product that may no longer exist.

---

## C. Communities — the problem described before anyone is selling

| Source | Extract | Notes |
|---|---|---|
| Reddit | Apify Reddit scraper (paid, cheap) or the public JSON: append `.json` to any thread or subreddit URL (free, rate-limited) | role-specific subreddits (r/healthIT, r/sales, r/devops, r/CFO, r/humanresources); search the buyer's phrase, not your category |
| Hacker News | Algolia HN API `https://hn.algolia.com/api/v1/search?query=...` (free) | dev tools, infra, security buyers |
| Slack and Discord communities | manual, respect the community rules | often the richest and least scrapeable; read, do not extract at scale |
| Stack Overflow | public search | technical buyers describing the workaround they built |
| Niche forums (HFMA, RevCycle forums, CU communities, ISACA, trade associations) | manual | usually where the most senior buyers actually talk |

---

## D. Buyers speaking in public — dated, quotable, named

| Source | Extract | Notes |
|---|---|---|
| Podcasts | Listen Notes API (free-key) or Apple Podcasts search (free) → episode → transcript via `youtube-transcript` for video versions, or the show's own transcript page | the buyer executive talking for 40 minutes with no script; the best single quotes come from here |
| Conference speaker lists and session recordings | manual (HIMSS, HFMA, SaaStr, Money20/20, RSA, Dreamforce, industry association annual meetings) | a named buyer with a dated, public position |
| LinkedIn posts by buyer personas | Apify LinkedIn posts actor (paid) or manual | filter to posts by the *buyer's* role, not by vendors talking about buyers |
| Webinar and YouTube recordings | `youtube-transcript` (free) | panels where buyers answer audience questions |
| Trade press interviews | Google News RSS `https://news.google.com/rss/search?q=...` (free) | search the buyer's phrase + the vertical |
| Earnings calls and 10-K risk factors (public companies) | SEC EDGAR full-text search `https://efts.sec.gov/LATEST/search-index?q=...` (free) | the CFO naming the problem in the company's own filing |

---

## E. Company-side situation traces — what changed, and when

| Source | Extract | What it reveals |
|---|---|---|
| Wayback Machine CDX API `http://web.archive.org/cdx/search/cdx?url=example.com&output=json` (free) | diff the homepage across dates | a rewritten hero, a new pricing page, a renamed category = a company mid-change |
| DNS records: SPF, MX, TXT (`dig TXT example.com`, free) | the `include:` entries in SPF name the email and sales tools they pay for | which sending platforms are live, whether outbound is running on the root domain |
| Certificate transparency `https://crt.sh/?q=%.example.com` (free) | new subdomains | new products, new sending domains, new regional launches, often weeks before the announcement |
| Tech stack detectors (BuiltWith, Wappalyzer — paid/free tiers) | the marketing and sales stack | who has a CRM and a marketing automation tool but no visible sequences |
| SEC Form D `https://efts.sec.gov/LATEST/search-index?q=%22Form%20D%22...` (free) | private funding rounds, often before the press release | money arrived; the situation that follows is hiring and tooling |
| State business registries (free) | entity changes, new officers, DBAs | rebrands, mergers, new leadership |
| Press releases (PRNewswire, GlobeNewswire, Business Wire RSS — free) | partnerships, launches, executive hires | the announcement *language* is quotable; the event itself is not a message |
| WARN notices (state labor department pages, free) | layoffs 60 days before they happen | contraction; treat with care and never as an opening line |

**A useful SPF reading list** (verify the record yourself; vendors change these): `_spf.google.com`, `spf.protection.outlook.com` (mailbox providers); `sendgrid.net`, `mailgun.org`, `amazonses.com` (transactional); `servers.mcsv.net` (Mailchimp), `spf.hubspotemail.net` (HubSpot), `mktomail.com` (Marketo), `_spf.salesforce.com` (Salesforce/Pardot), `spf.brevo.com`, `_spf.klaviyo.com`, `customeriomail.com` (Customer.io). A root domain with only a mailbox provider and no marketing includes usually means lifecycle email is not running at all. Outbound tools rarely appear on the root domain; they live on sibling sending domains (check crt.sh and registrar lookups for `get-`, `try-`, `-mail`, `-hq` variants).

---

## F. Vertical databases — the situation in the regulator's own records

These are the sources most sellers never open, and they are where a situation is documented by someone with no reason to spin it.

| Vertical | Database (all free unless marked) | What it reveals |
|---|---|---|
| **Healthcare** | CMS NPPES / NPI registry; CMS Care Compare and hospital quality data; HCRIS cost reports (bad debt, margins); CMS Open Payments; HHS OCR breach portal; HRSA data; state hospital association directories; KLAS (paid); Definitive Healthcare (paid) | which providers are under financial or compliance pressure, in numbers they reported themselves |
| **Fintech / banking** | FDIC BankFind and call reports; NCUA credit union data; FFIEC; CFPB consumer complaint database (searchable, verbatim complaints); FinCEN MSB registry; SEC EDGAR | institutions under margin pressure; the *complaint database is buyer language in its purest form* |
| **HR / workforce** | BLS JOLTS; WARN notices; EEOC data; Glassdoor and Indeed reviews (the employee's version of the situation) | churn, hiring surges, the internal experience behind the HR buyer's req |
| **Cybersecurity** | CISA KEV catalog; state attorney general breach notification lists; HHS OCR breach portal; SEC 8-K Item 1.05 filings; CVE databases | who just had the bad quarter, in a filing they were legally required to make |
| **Dev tools / infra** | GitHub issues and discussions; Stack Overflow; HN; npm and PyPI download stats; Product Hunt; status pages and incident postmortems | the workaround the buyer built because your category failed them |
| **Martech / GTM tech** | BuiltWith / Wappalyzer; G2 category pages; app marketplaces; DNS as above | the stack, the gaps in the stack, the tools bought and not used |
| **Legal** | PACER (paid per page); state bar directories; court dockets | firms in specific practice-area surges |
| **Construction / real estate** | municipal permit databases; county assessor records | projects starting; the operator who just took on more than the team can handle |
| **Logistics** | FMCSA registry and safety data; port and customs data (partly paid) | fleet size, safety events, growth |
| **Any vertical** | USPTO and Google Patents; state SOS registries; SEC EDGAR; the Wayback Machine | what they are building, who runs it, what they told regulators |

---

## G. Tools for scale (all optional)

- **Apify** — actors for most of the above; budget ten times your estimate for the first run and call it research.
- **Clay** — enrichment and people lookup once you have company names; not a source of situation, a way to attach a person to one.
- **Public APIs first, actors second, custom scrapers last.** Check the site's network tab before writing anything; most "scraping" problems are an undocumented JSON endpoint.

---

## H. What is NOT a source

- Firmographic filters (industry, headcount, revenue band, funding stage) on their own. They describe a company's shape, not its day.
- "Intent data" you cannot see the underlying evidence for. If the vendor cannot show the page view or the search, treat it as a rumor.
- Anything behind a login, anything that violates a site's terms, and any personal data beyond a business contact's public professional presence.
