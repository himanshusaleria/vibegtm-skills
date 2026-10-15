# SEO + AEO playbook

Rules for content that ranks in classic search and gets cited by AI search.

## A. Research before writing

**Keywords**
- Volumes: Keyword Planner (or another keyword tool, or a founder-exported CSV). Never estimate.
- Direction and real phrasing: Google Trends (`compare_keywords`, `get_related_queries`, `get_trending_searches`), one call at a time.
- Output: 1 primary keyword, 3-5 secondary, 5-8 long-tail questions.

**Forum mining:** Reddit, Stack Overflow, Quora, niche forums. Extract exact questions, pain points, misconceptions, vocabulary. These become H2s and FAQs.

**Competitor content:** top 3-5 ranking pages. Structure, length, headings, data, and what they miss. The gap is your angle.

**Data:** 3+ citable numbers with source, year, and exact figure. Research papers (Google Scholar, arXiv), official docs, analyst and industry reports, public benchmarks. Pillars need at least one first-party number (own survey, telemetry, or customer data, as listed in `gtm-context.md` Proof).

**Semantic check:** ask AI assistants what they recommend for the topic; note the sources they cite. Your page should be better than those.

**Funnel classification**

| Position | Content types | Effort | Keywords |
|---|---|---|---|
| Top | glossary, broad educational, listicles with a real POV | light | high volume, low intent |
| Middle | how-tos, guides, use cases | moderate | specific, problem-focused |
| Bottom | comparisons, alternatives, case studies | deep | high intent, low volume |

## B. Structure

**Every page**
1. TL;DR: 3-5 bullets, <100 words, before the intro
2. Short intro: 2-3 sentences of tension, not a preamble
3. Question H2s from real searches. Good: "How much does X cost?", "Should I use X or Y?" Bad: "Pricing Considerations".
4. Self-contained sections: first sentence answers the heading; no "as mentioned above"; extractable on its own
5. Tables for comparisons, pricing, pros/cons, feature matrices
6. FAQ at the bottom: 5-7 researched questions, 40-60 words each
7. 1+ image with alt text (include a generation prompt)
8. 5+ interlinks, 2+ authoritative outlinks
9. 3+ data citations (source + year)
10. Editorial footer: one line on how you research plus a link to a methodology page if the site has one
11. Changelog block on actively maintained pages (pillars, comparisons, evergreen guides)
12. Brand consistency: the brand name spelled exactly as on the rest of the site; site-wide `Organization` schema present. AI engines build the brand entity from cross-page consistency.

**Schema by page type (JSON-LD)**

| Page | Schemas |
|---|---|
| Blog post (cluster) | `Article` + `BreadcrumbList` + `FAQPage` (if FAQ) + `Person` (author, `sameAs`) |
| Pillar | `Article` + `BreadcrumbList` + `FAQPage` + `DefinedTermSet` (if coining terms) + `Person` |
| Comparison | `Article` + `BreadcrumbList` + `Product` (`aggregateRating` only with real review-site data) + `FAQPage` + `Person` |
| Glossary term | `DefinedTerm` + `DefinedTermSet` + `BreadcrumbList` |
| How-to | `HowTo` with numbered `HowToStep` + `BreadcrumbList` + `Person` |
| Feature/product page | `SoftwareApplication` or `Product` + `Organization` + `BreadcrumbList` |

**Pillar ↔ cluster links:** cluster posts link UP to their pillar with inline anchor text (mandatory). Pillars link DOWN to every cluster. Siblings link laterally where it helps. A pillar without down-links is just a long post; a cluster without an up-link is an orphan.

**By type**
- Cluster post: TL;DR → intro → 4-7 question H2s → FAQ → CTA
- Comparison: TL;DR → why compare → scannable feature/price/use-case table near the top → one section per differentiator → **verdict naming a winner per use case with a number-based contrast** → FAQ. AI engines lift verdicts verbatim; "it depends" doesn't get cited.
- Glossary: one-line definition → explanation → why it matters → examples → related terms → FAQ
- Pillar: TL;DR → overview → 8-12 H2s each linking down to a cluster → resources → FAQ → changelog
- FAQ section: 5-7 Q&As with schema, embedded on a host page

## C. Writing

**Banned words:** delve, tapestry, pivotal, furthermore, moreover, in conclusion, leverage, robust, comprehensive, seamless, utilize, harness, navigate, "in today's digital landscape", "it's important to note", "it's worth noting", "without further ado", "let's dive in". Plus the "never use" list in `gtm-context.md` Voice.

**Rhythm:** vary sentence length (see `engagement-beats.md`). Starting a sentence with "And", "But", "Because", or "So" is fine.

**Point of view:** take a position. "In our experience" beats "some say". "I" for personal insight, "we" for team actions, "you" constantly.

**Real over hypothetical:** "from 12 failing checks to 2", not "significant improvement". Named public examples over "a company might". Exact citations ("<Report>, <year>, found <figure>"), not "studies show".

**Non-commodity:** first-hand experience, proprietary data, expert depth, real case studies. If you can't add any of these, the post shouldn't exist.

**Two passes:** pass 1 for completeness (structure, data, links); pass 2 to humanize (voice, rhythm, specifics, banned words).

**Never:** "In this article, I will...", recap conclusions, "Moving on...", listicle headers ("5 Things I Learned"), "What do you think?" endings, long comma-spliced sentences, passive voice, three same-length paragraphs in a row.

## D. Publish hygiene (same change as the post)

1. Add the URL to the blog sitemap with the correct `lastmod`.
2. If the site ships `/llms.txt`, add the URL + one-line summary (and full text to `llms-full.txt` if it exists).
3. Confirm the root sitemap or sitemap index references the blog sitemap. An orphaned sitemap means crawlers, including AI crawlers, may never find the post.
4. Bump `dateModified` on any pillar or comparison page that now links to this post.

## E. After publishing

What tends to matter for AI search, per Google's public guidance on AI features: a unique point of view, non-commodity content, clear organization, good media, technical fundamentals (crawlable, fast, semantic HTML), and no scaled content abuse.

Often overhyped: FAQ schema as an AI-search lever (it helps classic rich results), chopping content into tiny chunks, "AI-specific" writing styles, manufactured mentions. `llms.txt` is cheap to add even though search engines don't require it.

Still worth doing: comparison pages, freshness (update stats and "last updated" dates), video, genuine community participation (AI answers cite Reddit and forums often), guest posts in trade publications, glossary terms (clean definitions get cited).
