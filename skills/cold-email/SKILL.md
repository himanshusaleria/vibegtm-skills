---
name: cold-email
description: Use when writing a cold email, outreach or prospecting email, follow-up sequence, or first-touch message to a specific company or person, or when reviewing why outbound emails get no replies.
argument-hint: "[company brief] [--sequence] [--improve 'learning']"
---

# cold-email: signal-based, pain-first outreach

Write short, specific cold emails that lead with the prospect's problem and a real reason for reaching out now. The pitch happens on the call, not in the email.

**Human gate: this skill drafts only.** Never send, schedule, or queue an email, even if an email tool is connected. The founder reviews and sends from their own account.

## Shared context (do this first)

1. Read `gtm-context.md` at the project root. Use: Product (what it actually does, and what it is NOT), ICP (personas, good-fit signals), Problem (customer phrasing), Alternatives, Positioning (main objection), Proof (only items not marked private), Voice (sign-off name and role), Channels (daily new-send cap), and `## Learnings` tagged `[cold-email]`.
2. Missing file: say so and offer to run `/gtm-context`. If the founder declines, ask: what do you sell (one line), who buys it, what pain does it fix, and how do you sign off.

## Input

A company brief, from just a name to: what they do, the signal that triggered outreach (hiring, funding, public complaint, stack change, team growth), target persona, extra context. If only a name is given, research the company (website, recent news, job listings) before writing.

## Modes

- **Default:** one first-touch email.
- **`--sequence`:** 4-email sequence (below).
- **`--improve "learning"`:** append to `## Learnings` tagged `[cold-email]`. Do not write an email.

## Process

1. **Analyze the prospect**
   - **Signal:** why reach out *now*. No signal → say so and suggest finding one; a signal-less email is a generic blast.
   - **Persona:** who feels the pain and can act. Budget-holding managers and team leads often close without the CEO.
   - **Buyer stage:** assume aware of the problem, exploring options. Not ready to buy.
   - **Primary pain:** the persona's top pain from `gtm-context.md`, in their words.
2. **Write the email** following the rules below.
3. **Buyer's-eye review.** Role-play the recipient (busy, skeptical): why would they reply, why wouldn't they? Does the framing promise something the product doesn't do (check "What it is NOT")? Revise once.
4. **Output** the email in a fenced block so it copies cleanly, then the reasoning:

````
```
Subject: ...

<body>
```
````

**Reasoning:** Signal · Persona · Pain angle · Buyer stage · Learnings applied

5. **Ask for feedback:** "What would you change, or what reply did you get? I'll save it to gtm-context.md."
6. **Write back:** append feedback and outcomes to `## Learnings`, e.g. `- 2026-01-10 [cold-email] eng-manager persona: problem-only email got 2/5 replies vs 0/5 with feature list -> keep mechanics out of first touch`.

## Email rules

**Length and shape**
- First touch: 4-6 sentences, paragraphs of 1-2 sentences.
- "I", not "we". No emojis, no exclamation marks.
- No em dashes. Use commas, colons, or periods. Em dashes are the most recognizable tell of AI-written outreach.
- Use contractions and vary sentence length. Uniform rhythm with no contractions reads machine-written.

**Messaging**
- **Lead with their pain, not your features.** Never open with what the product does.
- **Problem first, mechanics later.** Describe the problem and that you can help; leave the how for the call.
- Painkiller, not vitamin: a problem that is costing them now.
- Name the signal so "why now" is obvious.
- Specifics beat adjectives: a concrete situation from a real customer conversation (anonymized) beats a generic claim. Use only proof from `gtm-context.md`.
- Match the problem framing to what the product actually does. Winning the reply with an overpromise loses the meeting.
- If they already chose an alternative (e.g. just hired for the role), position as a complement, not an argument against their decision.

**Never use:** "AI-powered", "revolutionary", "game-changer", "cutting-edge", "leverage", "synergy", "unlock", "empower", "seamlessly". Plus the "never use" words in Voice.

**CTA:** soft and easy to refuse: "Worth 15 minutes to see if I can help?" / "Open to a quick look?" plus an out: "If not, no worries." Never "book a demo" or "schedule a call".

**Subject line:** under 8 words, lowercase or sentence case, about their situation not your product, no clickbait, no question on first touch. Earn it: reuse the body's sharpest idea, not a flat label.

## Sequence mode

| # | Day | Purpose | Length |
|---|---|---|---|
| 1 | 0 | Signal-based first touch, pain-first | 4-6 sentences |
| 2 | 3 | Reply-bait nudge: a light question that makes replying effortless ("did this reach the right person?"). Not "just following up" | 1-2 sentences |
| 3 | 8 | Value-add: an insight or anonymized story from a different pain angle | 3-5 sentences |
| 4 | 13 | Breakup: light, gives an out, leaves the door open | 2-3 sentences |

Follow-ups may reply in-thread with no new subject. Optional LinkedIn lane: a connection request without a note around day 0-3, a short DM only after they accept.

## Special case: you own a tool they already use

If the prospect uses a free or open-source tool you built, make the first touch a pure feedback ask about that tool (Mom Test framing), with no mention of the paid product. It flips the frame from vendor-asks-for-time to creator-asks-user-for-help. Pitch only on a follow-up call after the pain surfaces.

## Outreach discipline

- **Due follow-ups before new sends.** A warm thread gone cold costs more than a new send gains.
- **Cap new sends** (default ~5 new cold emails/day; use the cap in Channels if set). Small batches keep quality high and reply patterns readable.
- **One company, one thread.** If silent ~3 days past a due follow-up, move to a backup contact with a fresh thread. Never two parallel threads into one org.
- **Never fabricate:** no invented metrics, customer names, quotes, or URLs. No real number? Write the email without one.
- **Never guess an address and present it as real.** If you derive one from a company pattern (e.g. public commit emails on the company's repos), label it unverified.
- Send from the company domain, not a personal inbox. (Founder's call; mention it once.)
