---
name: competitive-landscape
summary: Maps who already serves your market, covering direct tools, indirect options, and DIY workarounds, with pricing, traction signals, and the gaps worth attacking.
pillar: context-and-positioning
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Size up a market before entering it
  - Fill in the Alternatives table in gtm-context.md
  - Find the angle for comparison and alternative pages
  - Decide whether a gap is an opportunity or a trap
---

## What it does

`competitive-landscape` researches a space on three tracks: direct competitors, indirect and DIY alternatives (spreadsheets, agencies, a feature inside a bigger product, doing nothing), and comparable products that succeeded in other markets. For each competitor it collects what they do, pricing, a traffic estimate with a confidence level, strengths and weaknesses taken from real reviews and forum threads, business model, trend, and funding.

It then sorts the market into well-served, underserved, and unserved areas, and asks why each gap exists. A gap can be hard to fill, too small to bother with, kept open on purpose by incumbents, or simply overlooked. It closes with a plain "can we win?" judgment against the wedge in your `gtm-context.md`.

Fields it can't verify are marked "not found". Traffic numbers are always labeled directional.

## When to use it

- Before positioning work or a pricing decision
- Before writing comparison or "alternatives to X" pages
- When someone says "there are no competitors" (it treats that as a red flag)

## Example

**Input:** `/competitive-landscape "scheduling tools for independent tutors"`

**Output:** a competitor table, a 2-3 sentence landscape summary, a gap analysis, an optional comparable-market ceiling with its inputs shown, proposed updates to your Alternatives table, and learnings appended to `gtm-context.md`.
