---
name: competitive-landscape
description: Use when mapping who already serves a market, before entering a space, writing positioning or comparison pages, or when a founder asks who the competitors are, how they price, how much traffic they get, or where the gaps are.
argument-hint: "[market or space description] [--improve 'learning']"
---

# competitive-landscape: who is here, who is winning, what is missing

Map direct, indirect, and DIY alternatives in a space, with pricing, traction signals, strengths, weaknesses, and a gap analysis. Every claim carries a source and a confidence level.

## Shared context (do this first)

1. Read `gtm-context.md` at the project root. Use: Product, ICP, Problem, the Alternatives table (start from it, don't rediscover it), Positioning, and `## Learnings` tagged `[competitive-landscape]`.
2. Missing file: say so and offer to run `/gtm-context`. If the founder declines, ask for the space description, the target buyer, and any competitors they already know.

## Modes

- `/competitive-landscape "space description"`: full map.
- `/competitive-landscape --improve "learning"`: append to `## Learnings` tagged `[competitive-landscape]`. Nothing else.

## Process

### 1. Find competitors (three parallel tracks; use subagents if available)
- **Direct:** web search "[space] tools", "best [space] software [year]", "[space] alternatives"; Product Hunt launches; GitHub repos (open-source alternatives).
- **Indirect / DIY:** what people use today without a purpose-built tool: spreadsheets, templates, a hire, an agency, a feature bundled in a bigger product, doing nothing. Search Reddit/forums for "how do you [job]".
- **Comparables elsewhere:** the equivalent product in another country or vertical, and how big it got.

### 2. Research each competitor

| Field | How to find | Notes |
|---|---|---|
| Name + URL | search | |
| What it does | fetch homepage | their words, one line |
| Pricing | fetch pricing page | note free tier, floor price, per-seat vs usage |
| Traffic | public estimates (SimilarWeb snippets, etc.) | **directional only**; mark confidence |
| Strengths | reviews, feature pages, praise on Reddit/forums | |
| Weaknesses | complaints in reviews, forums, support threads | quote real phrasing, link the source |
| Model | freemium / subscription / usage / ads / services | |
| Trend | traffic trend, review recency, release cadence, hiring | growing, flat, or declining |
| Funding | press, Crunchbase snippets | |

If a field isn't findable, write "not found". Never fill it with a plausible guess.

### 3. Compile the table

```markdown
| Competitor | What it does | Pricing | Traffic (conf.) | Strength | Weakness | Trend |
|---|---|---|---|---|---|---|
```

### 4. Gap analysis
1. **Well-served:** strong competition, happy users. Don't enter head-on.
2. **Underserved:** users complain or hack together workarounds.
3. **Unserved:** nobody does it.
4. **Why is the gap a gap?** Hard (data access, regulation), small (not worth it), structural (incumbents are paid not to fix it, e.g. a broker keeps its screener basic to drive trades), or overlooked. The answer decides whether it's an opportunity.

### 5. Comparable scaling (if a comparable exists)
```
Comparable: <tool> in <market>: traffic X/mo, addressable population Y
Your market: population Z → ceiling ≈ Z × (X / Y)
```
Label it an order-of-magnitude estimate and show the inputs and their sources.

### 6. Output
1. Competitor table
2. Landscape in 2-3 sentences: crowded or thin, who is winning, what's missing
3. Gap analysis
4. Comparable scaling (if any)
5. **Can we win?** Based on the gaps and the wedge in `gtm-context.md`. Name the one gap the founder's wedge fits, or say plainly that it fits none.

### 7. Write back
- Propose updates to the **Alternatives** table in `gtm-context.md` (new rows, corrected weaknesses). Edit only after the founder agrees.
- Append 1-3 entries to `## Learnings`, e.g. `- 2026-01-10 [competitive-landscape] incumbents all price per seat; solo buyers complain -> lead with flat pricing`.

## Reading the signals

| Signal | Interpretation |
|---|---|
| "No competitors" | Red flag, not green. Usually the market is tiny or the problem isn't painful. Look harder at DIY alternatives. |
| Declining incumbent | Ask why: shrinking market or bad product? The answer flips the conclusion. |
| Well-funded players in a small market | Danger. |
| Demand exists, nobody raised money | Likely a solid bootstrapped business, not a venture-scale one. Cross-check with search-demand. |
| GitHub stars / active open-source libraries | Proxy for developer interest. Zero repos can mean nobody is building. |
| App store: few apps, low ratings | Mobile gap, or no mobile demand. Check which. |
| Traffic from search snippets | Directional. Never present as precise. |
