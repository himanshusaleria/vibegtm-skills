---
name: gtm-context
description: Use when a project has no gtm-context.md, when the founder wants to set up or refresh their ICP, positioning, voice, or channels, or when another VibeGTM skill reports the context file is missing, stale, or contradicted by new results.
argument-hint: "[--refresh section] [--review]"
---

# gtm-context: interview the founder, write the shared context

Every VibeGTM skill reads one file, `gtm-context.md` at the project root, and appends what it learns to its `## Learnings` section. This skill creates and maintains that file. One file means the cold email, the blog post, and the Reddit draft all describe the same buyer with the same words.

## Modes

| Invocation | What happens |
|---|---|
| `/gtm-context` | No file yet: full interview, write the file. File exists: show gaps and offer to fill them. |
| `/gtm-context --refresh <section>` | Re-interview one section (e.g. `icp`, `positioning`, `voice`). |
| `/gtm-context --review` | Read `## Learnings`, propose which learnings to promote into the main sections, and which to prune. Edit only after the founder agrees. |

## Process

1. **Look before asking.** Check for `gtm-context.md` at the project root. Also skim what already exists: README, landing page copy, pricing page, existing blog posts, a CLAUDE.md or AGENTS.md. Pre-fill answers from these and ask the founder to confirm, instead of asking from scratch.
2. **Interview in batches of 2-4 questions**, one section at a time, in this order: Product → ICP → Problem → Alternatives → Positioning → Proof → Voice → Channels → Constraints. Start from `template.md` in this skill's directory (same file as `templates/gtm-context.md` in the repo).
3. **Push for specifics, accept "unknown".** Use the probes below. If the founder doesn't know, write `unknown` and move on. Never fill a gap with a plausible guess: a wrong ICP poisons every downstream skill.
4. **Write the file** with the template's headings, bullets not prose. Add `Last reviewed: <today>` in the header comment. Keep an empty `## Learnings` section at the bottom.
5. **Show the founder the file**, then list the 3 biggest `unknown`s and which skills they will weaken (e.g. "no ICP scorecard → validate-lead will ask you each time").

## Probes that get real answers

| Section | Weak answer | Probe |
|---|---|---|
| ICP | "SMBs", "startups" | "Name the last 3 people who paid or seriously evaluated. What did they have in common: size, role, trigger?" |
| Problem | "They need better X" | "What were they doing the day before they looked for a fix? What broke?" |
| Alternatives | "No competitors" | "What do they use today, including a spreadsheet, a hire, or ignoring it?" |
| Positioning | A feature list | "If a buyer could only remember one sentence about you vs the alternative, what is it?" |
| Proof | Round numbers with no source | "Where would a skeptic verify this? If nowhere, mark it private or drop it." |
| Voice | "Professional but friendly" | "Paste 2-3 things you wrote that sound like you. Which words make you cringe?" |
| No-go rules | none | "Which leads looked good and wasted your time? Why?" |

## Rules

- **The founder owns the content.** You draft and structure; they confirm every section before it is written.
- **Proof must be verifiable.** No invented metrics, logos, customer names, or quotes. Mark unpublished proof as private so public-facing skills don't use it.
- **Keep it under ~250 lines.** It is read on every skill run. Promote stable learnings into sections; delete stale ones.
- **Don't store secrets.** No API keys, passwords, private sheet IDs, or personal contact data in this file. It often ends up in git.

## The Learnings section (shared by all skills)

Every VibeGTM skill appends entries in this format:

```
- YYYY-MM-DD [skill-name] what happened -> what to do next time
```

During `--review`, group entries by theme. A learning that has held up 2-3 times belongs in its home section (e.g. a reply-rate pattern goes into Voice or Channels). Remove the original entries after promoting.
