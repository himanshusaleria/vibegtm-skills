---
name: seo-blog
description: Use when writing or outlining a blog post, pillar guide, comparison or alternatives page, glossary entry, how-to, or embedded FAQ meant to rank in Google and be cited by AI search (ChatGPT, Perplexity, AI Overviews), or when researching what content to write next.
argument-hint: "[topic] | --outline [topic] | --research-only [topic] | --type [blog|faq|glossary|comparison|pillar|howto] [topic] | --improve 'learning'"
---

# seo-blog: research-to-publish SEO + AEO content

Full pipeline: keyword research → forum mining → competitor audit → outline → draft → humanization pass → verification checklist. Output is a publish-ready draft for the founder to review. The founder publishes; this skill never pushes content live on its own.

## Voice north star

Every post reads like a senior practitioner explaining something to a peer: calm, specific, opinionated. Not a guru, not a hot take, not a textbook. Two hard tests, both must pass:

1. **The first sentence of every H2 section is a standalone answer to the heading question.** Featured snippets and LLM citations lift that sentence.
2. **Every 300-400 words of body prose contains an engagement beat** (see `references/engagement-beats.md`). The beat lives in sentences 2-4, never sentence 1.

## Shared context (do this first)

1. Read `gtm-context.md` at the project root. Use: Product, ICP, Problem (real phrasing becomes H2s), Alternatives (comparison targets), Positioning, Proof (first-party data; skip items marked private), Voice, Channels (blog directory, pillar pages, SEO notes), and `## Learnings` tagged `[seo-blog]`.
2. Missing file: say so and offer to run `/gtm-context`. If the founder declines, ask for: what the product does, who reads the blog, where blog files live, and the author name/role.
3. List existing posts in the blog directory (titles + slugs) for interlinks.

## Modes

| Mode | Output |
|---|---|
| `/seo-blog [topic]` | Full pipeline, blog post |
| `--outline [topic]` | Research + outline, no prose |
| `--research-only [topic]` | Research brief only |
| `--type <blog\|faq\|glossary\|comparison\|pillar\|howto> [topic]` | That content type's template |
| `--improve "learning"` | Append to `## Learnings` tagged `[seo-blog]`; nothing else |

**Token discipline:** load each reference file at the step that needs it, not up front. `--improve` loads nothing.

## Process

### 1. Research (parallel where possible)
- **Keywords:** if a Keyword Planner or Google Trends MCP is available, get volumes, related queries, and trend direction (Trends calls one at a time; parallel calls get rate-limited). If the `search-demand` skill is installed, follow its rules. **Never invent volumes.** No tool → report "volume: not measured" and offer the CSV-export route.
- **Forum mining:** search `"<topic> site:reddit.com"`, Stack Overflow, Quora, niche forums. Extract 5-8 questions in people's exact words. These become H2s and FAQs. Never assume FAQ questions.
- **Competitor content:** top 3-5 ranking pages: structure, length, data, and what they miss. That gap is the angle.
- **Data:** 3+ citable numbers with source, year, and link. Prefer first-party data from `gtm-context.md` Proof.
- **AI citation check:** which sources do AI assistants currently cite for this topic? Beat those.
- **Classify:** funnel position and content type (`references/content-architecture.md`).

`--research-only` stops here and outputs the brief in `references/output-formats.md`.

### 2. Outline
Title (<60 chars, primary keyword) · meta description (<155 chars) · content type · TL;DR bullets · 4-7 question H2s, each with its first-sentence answer · FAQ candidates from forums · 5+ interlinks · 2+ outlinks · table placements · image placements with generation prompts (`references/humanization-prompts.md`) · data citations.

`--outline` stops here.

### 3. Draft (read `references/playbook.md` §B-C and `references/engagement-beats.md` first)
Structure, in order:
1. Reading time (200 wpm) and visible published/updated dates
2. TL;DR: 3-5 bullets, <100 words
3. Direct-answer block: 40-60 words answering the title question
4. Short intro (2-3 sentences, a hook, not a preamble)
5. Question H2s; each section self-contained, first sentence answers the heading
6. An engagement beat every 300-400 words
7. Key Takeaways callout after the first 3-4 H2s (3-5 bullets, <80 words)
8. Tables wherever data is structured; 1+ image with alt text
9. 1-2 citation-ready quote boxes: `> "Stat with context." (Source, year) [link]`
10. FAQ: 5-7 researched questions, 40-60-word answers
11. Author bio (name, role, one-line credential, profile link) from Voice in context

Non-commodity or don't publish: a clear point of view and at least one insight competitors don't have.

### 4. Humanization pass (HUMANS)
- **H**ear it aloud: rewrite anything that sounds like a textbook.
- **U**nique stance: add one if missing.
- **M**ix sentence lengths per the distribution in `engagement-beats.md`.
- **A**necdotes: replace generic examples with specific ones (role + sector + moment), anonymized.
- **N**atural language: strip banned words (`playbook.md`) and AI tells (`engagement-beats.md`).
- **S**tory beats: count them; add beats to the longest flat stretches if short.

### 5. Output
Use the format in `references/output-formats.md` that matches the project (MDX/Markdown frontmatter per the existing blog). Include image prompts and JSON-LD schema blocks.

### 6. Verify
Run every row of `references/verification-checklist.md` and report pass/fail. Any FAIL blocks the draft until fixed or explicitly waived by the founder.

### 7. Feedback and write-back
Ask for feedback on structure, voice, and content. After publishing, ask how the page performs (impressions, clicks, AI citations) when data exists. Append 1-3 entries to `## Learnings`, e.g. `- 2026-01-10 [seo-blog] comparison verdicts naming a winner per use case got cited by AI search; "it depends" pages didn't -> always name a winner`.

## Never

- Hardcode product details: everything comes from `gtm-context.md` or the founder
- Invent statistics, customer names, quotes, or URLs; every number has a source
- Name a person or company from a customer conversation without written permission (see anonymization rules in `engagement-beats.md`)
- Skip the humanization pass or the checklist
- Bury the answer below sentence 1 of a section; write "as mentioned above"
- Publish a standalone `/faq` page (FAQs are embedded sections)
- Commodity "7 tips for X" content with no unique angle
