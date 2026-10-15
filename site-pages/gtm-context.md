---
name: gtm-context
summary: Interviews you once and writes gtm-context.md, the single file every VibeGTM skill reads before it works and writes learnings back to after.
pillar: context-and-positioning
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Set up your ICP, problem, positioning, and voice before running any other GTM skill
  - Refresh one section after customer calls change your view of the buyer
  - Review accumulated learnings and promote the ones that held up
---

## What it does

`gtm-context` builds the one file the rest of VibeGTM depends on. It first reads what already exists in your project (README, landing copy, pricing page, blog posts) and pre-fills what it can. Then it interviews you a few questions at a time: product, ICP, problem, alternatives, positioning, proof, voice, channels, and constraints. The result is `gtm-context.md` at your project root, with an empty `## Learnings` section that every other skill appends to.

It pushes back on vague answers. "Startups" becomes "name the last three people who paid, and what they had in common." When you don't know something, it writes `unknown` instead of guessing, and tells you which skills that gap will weaken.

## When to use it

- Before your first run of any other VibeGTM skill
- When a skill says your context is missing or out of date
- Every few weeks, with `--review`, to turn repeated learnings into rules

## Example

**Input:** `/gtm-context`

**Output:** a `gtm-context.md` with sections for Product, ICP (including a 0/1 scorecard that `validate-lead` uses), Problem in the customer's words, an Alternatives table, Positioning, Proof marked public or private, Voice, Channels, Constraints, and Learnings. It ends with a short list of the biggest unknowns to fill next.
