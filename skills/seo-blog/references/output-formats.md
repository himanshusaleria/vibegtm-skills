# Output formats

Match the existing blog. Read one existing post's frontmatter first and mirror its fields; the templates below are defaults when there is nothing to mirror.

## Research brief (`--research-only`)

```markdown
## Research brief: [topic]

### Search demand (source: [tool or CSV], pulled [date])
- Primary: [keyword] ([volume]/mo, or "not measured")
- Secondary: [keywords with volumes]
- Trend: rising / stable / declining

### Related queries
- ...

### Forum questions (exact wording, with links)
- [question] ([source link])

### Competitor content (top 3-5)
- [URL]: [length, structure, gaps]

### Citable data
- [figure], [source], [year], [link]

### Recommended content type
[type]: [why, by funnel position and intent]

### Recommended angle
[1-2 sentences: the POV competitors miss]
```

## Format A: MDX / framework blog

```mdx
---
title: '[Title]'
description: '[Meta description]'
date: 'YYYY-MM-DD'
dateModified: 'YYYY-MM-DD'
author: '[Author from gtm-context.md Voice]'
authorRole: '[Role / credential]'
authorUrl: '[Author profile URL]'
reviewedBy:            # only if a named expert reviewed it, with written permission
  - name: '[Reviewer]'
    role: '[Role]'
    url: '[Profile URL]'
tags: ['Tag1', 'Tag2']
keywords: ['keyword-1', 'keyword-2']
readingTimeMinutes: [words / 200]
---

*Published YYYY-MM-DD · Last updated YYYY-MM-DD · N-minute read*

## TL;DR
- ...

> **[Direct-answer block, 40-60 words.]**

[Intro, 2-3 sentences]

## [Question H2]?
[First sentence answers the H2.] [Engagement beat in sentences 2-4.] ...

> ### Key takeaways
> - ...

## Frequently asked questions
### [Researched question]?
[40-60 words; first sentence answers.]

---

## About the author
**[Name]**, [role]. [One-line credential.] [Profile link].

<!-- JSON-LD at end of file: FAQPage, Article (author, datePublished, dateModified, image),
     BreadcrumbList, Person for author (+ each named reviewer), DefinedTerm for coined terms -->
```

## Format B: plain Markdown

```markdown
---
title: "[Title]"
description: "[Meta description]"
date: "YYYY-MM-DD"
author: "[Author]"
keywords: [keyword1, keyword2]
---

[Same body structure as Format A]

<!-- JSON-LD blocks for the developer to paste into the page head -->
```

## Always attach
- Image generation prompts for each suggested image
- The verification checklist with pass/fail per row
- Publish-hygiene reminders (sitemap, llms.txt, banner image path the blog expects)
