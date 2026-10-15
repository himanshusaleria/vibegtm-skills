---
name: reddit-post
description: Use when drafting a Reddit post or comment, sharing a launch, lesson, or experiment in a subreddit, or adapting content for Reddit without it reading as self-promotion or getting removed as spam.
argument-hint: "[topic] [--subreddit name] [--improve 'learning']"
---

# reddit-post: posts that belong in the subreddit

Draft Reddit posts that read like a community member sharing something useful. Zero marketing. The insight is the post; the product is, at most, context.

**Human gate: this skill drafts only.** Never submit, schedule, or post to Reddit on the founder's behalf, even if a tool for it is available. The founder reads the sub's rules, posts, and replies from their own account.

## Shared context (do this first)

1. Read `gtm-context.md` at the project root. Use: Product one-liner (for the one-line self-mention), Problem (community phrasing), Proof (only items not marked private), Voice, Channels (target subreddits, notes), and `## Learnings` tagged `[reddit-post]`.
2. Missing file: say so and offer to run `/gtm-context`. If the founder declines, ask what they build (one line) and what the post is about, then continue.

## Modes

- `/reddit-post [topic]`: suggest the best-fit subreddit, confirm it, then draft.
- `/reddit-post --subreddit <name> [topic]`: draft for that sub (name without `r/`).
- `/reddit-post --improve "learning"`: append to `## Learnings` tagged `[reddit-post]`. Nothing else.

## Process

### 1. Pick the subreddit
Use the Channels section first. Otherwise suggest from the table below, and confirm with the founder before writing. If a tool to read the subreddit is available, skim recent top posts and the rules; if not, tell the founder to check the rules before posting.

| Subreddit | Tone | What works | What gets downvoted or removed |
|---|---|---|---|
| r/SaaS | founder sharing learnings | transparent metrics, honest failures, systems | self-promo, vague advice, "check out my tool" |
| r/startups | raw, honest | numbers, "here's what actually happened" | humble-brags, success with no messy middle |
| r/Entrepreneur | story + lesson | story-driven lessons, actionable frameworks | guru energy, "$X in Y days" with no substance |
| r/SideProject | maker showing work | build process, what you learned, screenshots | pure promo with no story |
| r/opensource | contributor | project showcase with technical depth | "star my repo" drive-bys |
| r/ClaudeAI, r/ClaudeCode, r/vibecoding | technical builder | workflows, prompts, code, "here's how I use it" | hype, marketing |
| r/GrowthHacking | tactician | specific tactics with results and data | theory with no execution |
| Niche practitioner subs (your ICP's profession) | peer practitioner | real pain, tool comparisons, war stories | vendor pitches; strictest about promotion |

### 2. Write the post

**Title**
- Direct, not clickbait. Patterns that work: "How I [did X] in [timeframe]", "Lessons from [experience]", "[Observation]: here's what I learned".
- No ALL CAPS, no emojis, never the product name.

**Body**
- Write as a member of the community, not as a founder promoting something. Apply the Voice section of `gtm-context.md`.
- Short posts (<300 words): no headers. Long posts: scannable, short paragraphs, occasional bold.
- Specifics build credibility: real numbers, timelines, what broke. Use only numbers the founder has. Never invent metrics.
- Honest failures outperform wins.
- End with an invitation to discuss ("Curious if others have seen this"), not a CTA.

**Self-mention rules**
- At most one line of context for credibility: "I build a tool for X, so I see this a lot."
- Never in the title. No link in the body.
- If someone asks in the comments, the founder shares the link there.
- Test: the post must be fully valuable if the product didn't exist.

### 3. Output

```markdown
## Reddit draft for r/<subreddit>

**Title:** ...

---
<body>
---

## Posting notes
- **Check first:** the sub's rules on self-promotion, flair, and required formats
- **Flair:** <suggestion, if the sub uses flair>
- **Timing:** weekday mornings US Eastern work for most US-heavy tech/business subs; adjust for the sub
- **Comment plan:** how to answer "what's the tool?" without pitching
- **First hour:** reply to every comment; early engagement drives reach
- **Cross-post:** other subs where a rewritten (not copied) version fits
```

### 4. Write back
After the founder posts, ask how it did (upvotes, comments, removed or not). Append 1-3 entries to `## Learnings`, e.g. `- 2026-01-10 [reddit-post] r/SaaS removed a post with a link in body -> link only in comments`.

## Never

- A sentence that sounds like marketing copy
- Product name in the title, product link in the body
- Clickbait titles, emojis
- Opening with "As a founder..."
- "Follow me for more" or similar CTAs
- The same text cross-posted to several subs (each sub gets its own native version)
- Posting, scheduling, or voting on the founder's behalf
