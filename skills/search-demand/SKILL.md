---
name: search-demand
description: Use when deciding whether people actually search for a product, topic, or keyword set; when validating an idea, picking blog topics, or sizing a niche needs monthly search volumes or trend direction; or when someone asks "is there demand for X".
argument-hint: "[keywords or topic] [--geo country_code] [--improve 'learning']"
---

# search-demand: is anyone actually searching for this?

Check real search demand for a keyword set using whatever data source is available. The output is a demand map plus a verdict, grounded only in numbers that came from a real tool or export.

**Iron rule: never guess search volumes.** No "roughly 5k/mo", no "probably high". A number in the report came from Keyword Planner, another keyword tool, or a CSV the founder exported. If none is available, the report says "volume: not measured" and the skill asks for an export. A guessed volume is worse than none, because the founder will build on it.

## Shared context (do this first)

1. Read `gtm-context.md` at the project root. Use: Product one-liner, ICP (geography), Problem (customer phrasing), Alternatives (competitor names), Channels (SEO notes), Constraints (tools available), and recent `## Learnings` tagged `[search-demand]`.
2. Missing file: say so and offer to run `/gtm-context`. If the founder declines, ask only for the topic and target country, then continue.

## Modes

- `/search-demand "kw1, kw2, kw3" --geo US`: check these keywords.
- `/search-demand "topic description"`: generate the keyword list first (Step 1).
- `/search-demand --improve "learning"`: append the learning to `## Learnings` in `gtm-context.md` tagged `[search-demand]`. Nothing else.

No `--geo`: use the ICP geography from context, else worldwide.

## Process

### 1. Build the keyword list (if given a topic)
15-20 keywords in four buckets:
- **Core (3-5):** the obvious names for the product.
- **Adjacent (5-7):** what the market actually types, which often differs from founder vocabulary.
- **Competitor / brand (3-5):** names from the Alternatives table.
- **Problem (3-5):** the pain described without naming a solution. Pull phrasing from the Problem section.

### 2. Pick the data source (first match wins)

| Available | Use it for |
|---|---|
| Keyword Planner MCP (e.g. `generate_keyword_ideas`, `get_historical_metrics`) | Absolute monthly volumes, related ideas, competition |
| Another keyword tool the founder has (Ahrefs, Semrush, Bing Webmaster keyword research, etc.) | Absolute volumes |
| Google Trends MCP (e.g. `compare_keywords`, `get_related_queries`, `get_interest_by_region`) | Direction (rising/falling), relative interest, related queries. **Not** volumes. |
| None of the above | **Stop and ask** for a CSV export (Step 3). |

Trends alone never produces a volume. It produces direction and related queries.

### 3. Fallback: ask for an export
Say exactly what to export, then wait:
> I can't measure volumes from here, and I won't estimate them. Fastest route (~10 min): Google Ads → Tools → Keyword Planner → "Get search volume and forecasts" → paste the keywords below → download the CSV. Any keyword tool's CSV export works too. Send it and I'll finish the report.

Then list the keywords from Step 1 in one copy-paste block. You may still deliver the qualitative parts (keyword buckets, intent notes, Trends direction if available), clearly labelled "volumes pending".

### 4. Run the checks
- **Volumes** for all keywords (Keyword Planner or export).
- **Trends, sequentially:** compare core keywords (max 5 per call, 12-month window), then adjacent, then related queries for the top 2-3 core terms, then regional interest for the top term. **One Trends call at a time with a pause between calls.** Parallel calls trigger rate-limit blocks that can last hours.
- **Idea expansion:** seed Keyword Planner ideas with the core keywords; the related ideas are often the real finding.

### 5. Synthesize

```
DEMAND MAP (source: <tool or file>, geo: <geo>, pulled <date>)
HIGH  (>=5,000/mo)   | MEDIUM (500-4,999/mo)
LOW   (<500/mo)      | DECLINING (falling >=20% YoY in Trends or KP trend)
```

Answer these four:
1. What do people actually search for vs what the founder expected?
2. What is rising, what is falling?
3. What do related queries reveal? (Usually the best insight in the report.)
4. Is demand concentrated in one geography?

**Thresholds (defaults, override in gtm-context.md Constraints):**
- Core keywords under ~500/mo → flag "below typical threshold for an SEO-led product".
- Any keyword in the space above ~5,000/mo → the market exists even if your exact terms are small.
- Falling trend beats low volume as a warning sign. Small and growing beats big and shrinking.

### 6. Output
1. Demand map with source and date on every number
2. Four findings
3. Verdict: **strong / workable / weak / unmeasured**, one paragraph
4. Suggested next step (e.g. target the adjacent cluster, run competitive-landscape, write the blog post on the rising related query)

### 7. Write back
Append 1-3 entries to `## Learnings` in `gtm-context.md`, e.g. `- 2026-01-10 [search-demand] buyers search "X alternative" (2.4k/mo) not our category name (90/mo) -> lead pages with "X alternative"`. Show them to the founder first. If a finding changes positioning or channels, suggest a `/gtm-context --refresh` instead of silently editing those sections.

## Reading the data correctly

| Signal | What it means |
|---|---|
| Trends shows 0 | Below Trends' reporting threshold in that geo. **Not** zero searches. Check volumes. |
| Huge % growth on a tiny base | Noise. Check absolute volume before calling it a trend. |
| Date-stamped queries spiking ("X May 2026") | Content demand (people want articles), not tool demand. |
| Keyword Planner volume looks global | KP may ignore geo depending on setup. Check the location setting and say which geo the number is. |
| Small in target market, large in an adjacent market | Compare. If the category is big elsewhere, the gap is market-specific, not category-wide. |

## Tool troubleshooting (tell the founder, don't work around)

- Keyword Planner `CUSTOMER_NOT_ENABLED` / `DEVELOPER_TOKEN_NOT_APPROVED`: Google Ads account setup (test-mode token, manager vs client account, billing). Fix in Google Ads, or use the CSV route.
- `invalid_grant`: expired OAuth refresh token. Re-run the MCP's auth flow.
- Trends `429`: you made parallel or rapid calls. Stop, wait, resume sequentially.

## Red flags: stop and re-read the iron rule

- "I'll give a rough estimate so they can decide tonight"
- "Trends says 60, so roughly 6k/mo"
- "Based on similar keywords, it's probably..."
- Reporting a number without naming its source

All of these mean: report "not measured" and ask for the export.
