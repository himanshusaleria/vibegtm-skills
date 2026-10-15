---
name: cold-email
summary: Writes short, signal-based cold emails and follow-up sequences that open with the prospect's problem rather than your features. You review and send.
pillar: outbound
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Write a first-touch email triggered by a hiring, funding, or stack-change signal
  - Generate a 4-email sequence with a nudge, a value-add, and a breakup
  - Diagnose why outbound emails get no replies
---

## What it does

`cold-email` starts from a company brief, which can be as short as a name. It works out the signal (why now), the persona, and that persona's main pain, using the ICP, problem wording, and proof in your `gtm-context.md`. The draft runs four to six sentences. It names the signal, describes the problem, offers help, and closes with a soft, easy-to-decline ask. How the product works is saved for the call.

Before showing you the draft, it reads it as a skeptical recipient would. It checks whether the framing promises something your product doesn't do and whether there's a real reason to reply. Hard rules apply: no em dashes, no hype words, no invented metrics or customer names, and no guessed email addresses presented as real. The sequence mode follows a set cadence: first touch, a short nudge, a value-add from a new angle, and a breakup email.

It never sends. You review and send from your own inbox, and reply outcomes go back into `gtm-context.md` as learnings.

## When to use it

- You have a validated lead and a real signal
- You want a sequence, not a one-off email (`--sequence`)

## Example

**Input:** `/cold-email "Example Corp, just posted its first ops-manager role, 30 people, B2B SaaS"`

**Output:** a subject line and email in a copy-ready block, followed by its reasoning: signal, persona, pain angle, buyer stage, and which learnings it applied.
