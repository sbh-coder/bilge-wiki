# Bootstrap Prompt

Copy everything below the line into Claude Code to generate your wiki. Customize the sections marked with `<!-- CUSTOMIZE -->` before running.

---

You are doing a one-time bootstrap job. You will populate this repo with a structured knowledge wiki based on my operational history.

## STEP 1 — CONFIGURE

<!-- CUSTOMIZE: Set your data source -->
**Primary source:** Slack channel `DEB7CQKU6`
**Date range:** Fetch all messages from `YYYY-MM-DD` onwards
**Source type:** Daily paid channel briefings, ad dashboard updates, campaign performance notes
**Owner:** Bilge Hasekioglu — Digital Marketing Team Leda, Justlife

## STEP 2 — CREATE FOLDER STRUCTURE

```bash
mkdir -p workstreams people experiments decisions metrics
```

## STEP 3 — FETCH SOURCE MATERIAL

Use the Slack MCP tool to read channel `DEB7CQKU6`. Fetch all messages using pagination until you have everything from your start date onwards. These are your source of truth. Do not invent or assume anything not explicitly stated in these messages.

## STEP 4 — CREATE ARTICLES

For each category below, extract everything relevant from the source history and write structured articles. Use only what appears in the source. Be specific. Include real numbers. Every article must have YAML frontmatter, content body, and a Backlinks section.

### Workstreams

**workstreams/meta-ads.md** — Include: campaign status, spend, ROAS, CPA, active ad sets, creative performance, budget pacing, blockers. Key people: Bilge.
**workstreams/google-ads.md** — Include: campaign status, spend, ROAS, CPA, keyword performance, quality scores, budget pacing, blockers. Key people: Bilge.
**workstreams/tiktok-ads.md** — Include: campaign status, spend, CPA, creative performance, audience performance, budget pacing. Key people: Bilge.
**workstreams/snapchat-ads.md** — Include: campaign status, spend, CPA, creative performance, budget pacing. Key people: Bilge.
**workstreams/dashboard-reporting.md** — Include: current dashboard status, data sources connected, metrics tracked, open issues, requested improvements.

### People

**people/bilge.md** — Include: role (Digital Marketing, Paid Channels), ownership areas (Meta, Google, TikTok, Snapchat ads, dashboards), all open items, decisions made.

### Experiments

**experiments/[name].md** — Include: hypothesis, channel tested (Meta/Google/TikTok/Snapchat), mechanic (creative variant, audience, bid strategy, budget), result (with CPA/ROAS/CTR numbers), status (Active / Resolved), next steps.

### Decisions Log

**decisions/log.md** — Format every entry as:

```
## DD.MM.YYYY

**Decision title**
What was decided, one to three sentences max. Source: [which message/meeting].
```

Extract every clear decision from all source messages in chronological order.

### Metrics

**metrics/definitions.md** — Define every metric mentioned across all source messages. For each: name, definition as used at your company, current benchmark or target.

**metrics/weekly-benchmarks.md** — Extract every number mentioned as a target or threshold. Format as a table: Metric | Target/Threshold | Source | Date mentioned.

## STEP 5 — CREATE INDEX

Write `index.md` as a full catalog of every article created:

```markdown
# Wiki Index

Last updated: [today's date DD.MM.YYYY]
Source: [your source description]

## Workstreams
* [[workstreams/name]] - [one-line summary] | [status]

## People
* [[people/name]] - [one-line summary] | Active

## Experiments
* [[experiments/name]] - [one-line summary] | [status]

## Decisions
* [[decisions/log]] - Chronological log of all decisions

## Metrics
* [[metrics/definitions]] - Metric definitions and benchmarks
* [[metrics/weekly-benchmarks]] - Current targets and thresholds
```

## STEP 6 — CREATE LOG

Write `log.md`:

```markdown
# Wiki Log

## [today's date] bootstrap

Initial wiki created from [source description], covering [date range].
Articles created: [count per folder]. Source messages processed: [count].
```

## STEP 7 — GENERATE state.md

Using all articles you just created, generate the initial state.md. This is a compressed snapshot of current state for token-efficient loading.

Populate:
- CRITICAL/URGENT/HIGH sections: extract any items with hard deadlines or marked as urgent in the source
- Workstream Status table: one row per workstream article you created, current status from the article
- Open Items table: every open item across all workstream and people articles, with owner and estimated days open
- Active Experiments: any experiment with status Active or Pending decision
- People Watch List: people with open items assigned to them
- Key Metrics: every metric with a current known value from metrics/weekly-benchmarks.md

state.md is always a full rewrite. Generate it fresh from the wiki you just built.

## STEP 8 — COMMIT AND PUSH

```bash
git add .
git commit -m "bootstrap: initial wiki from [source] [date range]"
git push -u origin main
```

## STEP 9 — FINAL OUTPUT

After pushing, print:
1. GitHub repo URL
2. Article count per folder
3. Any gaps where source data was thin or missing
4. The raw base URL for fetching articles: `https://raw.githubusercontent.com/USERNAME/REPO/main/`
5. The Step 0 line to add to your agent prompts, with the real index.md URL
