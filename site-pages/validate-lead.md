---
name: validate-lead
summary: Researches a company and scores it against your own ICP scorecard and no-go rules before you spend an email on it.
pillar: outbound
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Check one company, optionally from a job posting, before outreach
  - Triage a CSV or sheet of unreviewed leads in batch
  - Turn wasted-meeting lessons into no-go rules that stick
---

## What it does

`validate-lead` looks up what a company actually sells, its headcount, location, hiring, funding, and stack. A job posting or source URL makes the research sharper. It checks your no-go rules first, and any match ends the review with the evidence attached. Otherwise it scores each criterion in the ICP scorecard from your `gtm-context.md` as 0 or 1, with one line of evidence each. The total maps to Core ICP, Broader ICP, or Not ICP, alongside a one-line verdict.

It handles the usual judgment calls. A services firm hiring for a role your product supports is often a false positive. A company name with "Solutions" in it is a hint, not a verdict. When the research leaves real doubt, it says go ahead with caveats, because reviewing a maybe costs less than missing a fit. Facts it can't verify are marked "not found".

In batch mode it reads unreviewed rows from a CSV or sheet and returns values you can paste straight back in.

## When to use it

- Before every cold email
- When a lead list has grown faster than you can review it

## Example

**Input:** `/validate-lead "Example Corp" https://example.com/careers/role`

**Output:** a verdict table, a research summary with sources, the scorecard, bonus signals, caveats, and paste-ready values for your sheet. Your feedback goes into `gtm-context.md`.
