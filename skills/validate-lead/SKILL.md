---
name: validate-lead
description: Use when deciding whether a company or lead fits the ICP before outreach, qualifying or scoring a prospect list, reviewing a job posting or company as a buying signal, or triaging unreviewed rows in a lead sheet or CSV.
argument-hint: "[company] [job_or_source_url] | --batch [file] | --improve 'learning'"
---

# validate-lead: is this company worth an email?

Research a company and score it against the founder's ICP: no-go rules first, then a 0/1 scorecard, then a tier and a one-line verdict. Cheap to run before every outreach, and it keeps cold-email from burning sends on bad fits.

## Shared context (do this first)

1. Read `gtm-context.md` at the project root. Use: ICP (good-fit signals, no-go rules, the **ICP scorecard** and tier thresholds), Product (what it is NOT), and `## Learnings` tagged `[validate-lead]`. Learnings override default scoring.
2. Missing file, or no scorecard: say so and offer to run `/gtm-context --refresh icp`. If the founder declines, ask for 4-6 yes/no fit criteria and their no-go rules, use them for this session, and offer to save them.

## Modes

- `/validate-lead <company> [url]`: one company. A job posting or source URL improves accuracy.
- `/validate-lead --batch [file]`: unreviewed rows from a CSV or a sheet the founder points to.
- `/validate-lead --improve "learning"`: append to `## Learnings` tagged `[validate-lead]`. Nothing else.

## Single-company flow

### 1. Research (parallel where possible)
- URL given: fetch it. For a job posting extract role, stack, requirements, and how the company describes itself.
- Search "<company> product" → what they actually sell, to whom.
- Search "<company> employees" / company profile pages → headcount estimate.
- Note location, funding news, hiring activity, tech stack.
Record "not found" for anything you can't verify. Don't infer headcount from vibes.

### 2. No-go rules (check FIRST)
Apply every no-go rule from `gtm-context.md`. Any match → verdict **No go** with the rule and the evidence. Skip scoring.

Common no-go rules founders use (suggest them if the context has none; apply only what the founder adopts):
- Services, consulting, or agency business when you sell to product companies
- Far too large to buy from a startup, or too early (no launched product)
- A competitor, or a company that sells your category as a service
- No surface your product works on (e.g. no web app when you need one)
- A signal that matches the keyword but not the need (e.g. a role adjacent to yours that your product doesn't serve)

### 3. Score
Each scorecard criterion scores 0 or 1, with one line of evidence. Sum it and apply the tier thresholds from context:
- **Core ICP** → Go ahead
- **Broader ICP** → Go ahead, list caveats
- **Not ICP** → No go

Note **bonus signals** separately (not scored): strong positives and negatives from the good-fit signals list.

### 4. Output

```
## <Company>: lead validation

| Verdict | Action | Summary |
|---|---|---|
| Core / Broader / Not ICP / No-go | Go ahead / No go | <one line> |

**Research:** what they do · headcount · geography · product type · signals (with source links)

**Scorecard (X/N)**
| # | Criterion | Score | Evidence |
|---|---|---|---|

**Bonus signals:** ...
**Caveats:** ...
```

If the founder tracks leads in a sheet, end with paste-ready values ("Paste into your sheet: fit=Yes, action=Go ahead, comment=..."). Treat sheet access as read-only unless the founder says otherwise.

### 5. Feedback and write-back
Ask: "Any feedback on this verdict? I'll save it." Append to `## Learnings`, e.g. `- 2026-01-10 [validate-lead] IT-services firms hiring for our role staff client projects, not their own product -> no-go`.

## Batch flow

1. Read the CSV/sheet. Rows with empty verdict and action columns are unreviewed. Ask which column holds the company and the source URL if unclear.
2. Show the unreviewed list; ask which to run (all or a subset).
3. Validate sequentially, pausing between web searches to stay rate-limit friendly.
4. Summary table: `Company | Score | Tier | Action | Comment`, followed by paste-ready values.
5. One combined write-back of patterns seen across the batch.

## Judgment calls

| Situation | Call |
|---|---|
| Uncertain after research | **Go ahead with caveats.** Reviewing a maybe costs less than missing a fit. |
| Company name suggests services ("Solutions", "Technologies", "Labs") | A hint, not a verdict. Check what they sell. |
| Services firm hiring for a role your product supports | Usually a false positive: they staff client projects. Confirm before scoring. |
| Company does mobile AND has a web product | Score the part your product serves; don't reject on the mobile part. |
| Name sounds like media/gaming ("Interactive", "Studios") | Check whether there is a software product before scoring. |
| Learnings contradict the default criteria | Learnings win. Say which learning you applied. |
