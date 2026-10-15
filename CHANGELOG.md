# Changelog

All notable changes to this project are documented here. Versions follow [Semantic Versioning](https://semver.org/).

## [0.1.0] - 2026-10-15

### Added
- `gtm-context` skill and `templates/gtm-context.md`: the shared context file every skill reads and writes learnings back to.
- `search-demand`: keyword demand checks via Keyword Planner / Google Trends MCPs, with a CSV-export fallback; never estimates volumes.
- `competitive-landscape`: competitor table, gap analysis, comparable scaling, and "can we win" assessment.
- `seo-blog`: research-to-draft SEO + AEO content pipeline with engagement beats, humanization pass, schema guidance, and a verification checklist.
- `reddit-post`: subreddit-native post drafts; drafts only, never posts.
- `validate-lead`: ICP scoring with no-go rules and a scorecard taken from `gtm-context.md`; single and batch modes.
- `cold-email`: signal-based, pain-first first touches and 4-email sequences; drafts only, never sends.
- Claude Code plugin and marketplace manifests.
