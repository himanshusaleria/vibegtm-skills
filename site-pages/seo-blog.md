---
name: seo-blog
summary: A research-to-draft pipeline for blog posts, pillars, comparisons, glossary entries, and FAQs that rank in Google and get cited by AI search.
pillar: seo
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Write a blog post grounded in real search demand and real forum questions
  - Build a comparison page with a verdict AI search can quote
  - Outline a pillar page and its cluster posts
  - Produce a research brief before deciding what to write
---

## What it does

`seo-blog` covers the whole job. It researches keywords (with real volumes only), mines Reddit and forums for the exact questions people ask, audits the pages that already rank, and gathers citable data. Then it outlines and drafts.

Drafts follow a fixed structure built for both search and AI answers. There's a TL;DR, a 40-60 word direct-answer block, and question-based headings where the first sentence of every section answers the heading on its own. Tables, an FAQ drawn from real questions, and the matching JSON-LD schema complete the page.

A second pass fixes the voice. It adds an "engagement beat" every 300-400 words (a concrete contrast, a specific scene, a stated opinion) and strips a blocklist of common AI-writing tells, including em-dash habits. A verification checklist runs last, and any failed row blocks the draft. Product facts, proof, and voice come from your `gtm-context.md`, and private customer details are anonymized.

## When to use it

- You know the topic and want a publish-ready draft
- You want only research or an outline first (`--research-only`, `--outline`)
- You need a specific format (`--type comparison`, `glossary`, `pillar`, `howto`, `faq`)

## Example

**Input:** `/seo-blog --type comparison "spreadsheet vs dedicated tool for tracking freelance invoices"`

**Output:** an MDX or Markdown draft in your blog's format, image prompts, schema blocks, a pass/fail checklist, and publish-hygiene reminders (sitemap, llms.txt).
