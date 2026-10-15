# VibeGTM skills

**Go-to-market the way you vibe-code.** You set the intent (who it's for, why it wins, your taste) in one file. Claude skills do the repeatable work. You review anything that goes public. Results get written back into that file, so the next run is better than the last.

This repo is a Claude Code plugin with seven skills for solo founders and small teams doing their own GTM.

## The loop

```
gtm-context.md  (ICP, problem, positioning, proof, voice, channels)
      │
      ▼
 skill runs  ── search-demand, competitive-landscape, seo-blog,
      │         reddit-post, validate-lead, cold-email
      ▼
 human gate  ── you review; you publish, post, and send
      │
      ▼
 ship → measure → append to ## Learnings in gtm-context.md → repeat
```

## Why a shared context file

Most skill libraries treat each skill as a standalone prompt, so you re-explain your product every time and each skill drifts toward its own idea of your buyer. Here every skill:

1. reads `gtm-context.md` at your project root before doing anything (and offers to create it if it's missing),
2. uses only the proof you've marked as citable, in the voice you've described,
3. appends what it learned to the file's `## Learnings` section, tagged with the skill name.

Your cold email, blog post, and Reddit draft describe the same buyer in the same words, and the system gets sharper with use.

## Skills

| Skill | Use it when | Needs (optional) |
|---|---|---|
| `gtm-context` | Setting up or refreshing your ICP, positioning, voice, channels | – |
| `search-demand` | Checking whether people actually search for something | Keyword Planner MCP, Google Trends MCP, or a keyword CSV export |
| `competitive-landscape` | Mapping who serves a market, their pricing, traction, and gaps | Web search / fetch |
| `seo-blog` | Writing blog posts, pillars, comparisons, glossary entries that rank and get cited by AI search | Web search; keyword MCPs |
| `reddit-post` | Drafting a subreddit post that doesn't read as promotion | – |
| `validate-lead` | Scoring a company against your ICP before outreach | Web search; a lead CSV or sheet for batch mode |
| `cold-email` | Writing a signal-based first touch or a 4-email sequence | – |

Every tool dependency is optional. When a tool is missing, skills fall back to asking you for an export or for the missing input. They don't guess. In particular, `search-demand` never estimates search volumes.

**Human gate:** no skill posts, publishes, or sends anything. Drafts only.

## Install

### Option 1: Claude Code plugin marketplace

In Claude Code:

```
/plugin marketplace add himanshusaleria/vibegtm-skills
/plugin install vibegtm@vibegtm
```

Skills are then available as `/vibegtm:gtm-context`, `/vibegtm:cold-email`, and so on. Claude also picks them up automatically when your request matches a skill's description.

### Option 2: manual copy

```bash
git clone https://github.com/himanshusaleria/vibegtm-skills.git
cp -r vibegtm-skills/skills/* ~/.claude/skills/
```

Restart Claude Code. Skills are then available as `/gtm-context`, `/cold-email`, and so on. To install for one project only, copy into `<project>/.claude/skills/` instead.

## Quick start

1. Open Claude Code in your product's repo (or any folder you use for GTM work).
2. Run `/gtm-context` (or `/vibegtm:gtm-context`). It reads what it can from your repo and interviews you for the rest, about 10-15 minutes. The result is `gtm-context.md` at the project root. A blank copy is in [`templates/gtm-context.md`](templates/gtm-context.md) if you'd rather fill it in by hand.
3. Run any skill, for example `/search-demand "notion invoice template, freelance invoice tracker" --geo US`.
4. After results come in (replies, rankings, upvotes), tell the skill. It appends a dated learning to `gtm-context.md`. Run `/gtm-context --review` now and then to promote stable learnings into the main sections.

Every skill also takes `--improve "learning"` to record a lesson directly.

`gtm-context.md` is meant to be committed to your own repo. Keep secrets out of it: no API keys, passwords, or private contact data.

## Repo layout

```
.claude-plugin/       plugin.json + marketplace.json
skills/<name>/        SKILL.md (+ references/ where needed)
templates/            gtm-context.md template
site-pages/           one page per skill for the VibeGTM website
```

## Contributing

Issues and PRs are welcome, especially new GTM skills and field-tested learnings.

- **One skill per directory** under `skills/`, with a `SKILL.md` that has `name` and `description` frontmatter. Descriptions start with "Use when..." and describe triggers, not the workflow.
- **Every skill reads `gtm-context.md`** and writes learnings back to `## Learnings` as `- YYYY-MM-DD [skill-name] what happened -> what to do next time`.
- **Human gate:** skills draft; people publish, post, and send.
- **No invented data:** no made-up volumes, metrics, quotes, customers, or URLs in skills or examples. Illustrative examples are labeled as such.
- **Tools optional:** if a skill uses an MCP server or API, it must degrade gracefully when that tool isn't installed.
- **Nothing private:** no company names, customer data, personal paths, or credentials.
- If you change `templates/gtm-context.md`, copy it to `skills/gtm-context/template.md` too.
- Run `claude plugin validate .` before opening a PR, and add a line to `CHANGELOG.md`.

## License

[MIT](LICENSE) © Himanshu Saleria
