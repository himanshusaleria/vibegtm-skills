---
name: search-demand
summary: Checks whether people actually search for your product, topic, or keyword set, using real keyword data only. It never estimates volumes.
pillar: seo
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Validate demand for a product idea before building it
  - Pick which blog topics and landing pages are worth writing
  - Find the words buyers actually search for instead of your category name
  - Compare demand across countries
---

## What it does

`search-demand` turns a topic or keyword list into a demand map: high, medium, low, and declining keywords, each with its source and the date it was pulled. Given a topic, it first builds 15-20 keywords across four buckets: core terms, adjacent terms, competitor names from your `gtm-context.md`, and problem phrasing.

It uses Google Keyword Planner for volumes and Google Trends for direction and related queries when those MCP servers are installed. Trends calls run one at a time, because parallel calls trigger long rate-limit blocks. With no keyword tool available, it stops and tells you exactly which CSV to export from Keyword Planner, then finishes the report from that file. It won't fill the gap with a guess.

## When to use it

- Before committing to an idea, a niche, or a content plan
- When you suspect your category name isn't what buyers type
- When a Trends chart shows zero and you need to know whether that means zero

## Example

**Input:** `/search-demand "notion invoice template, freelance invoice tracker" --geo US`

**Output:** a demand map with a volume and source on every keyword (or "not measured"), what's rising and falling, related queries worth targeting, a verdict (strong, workable, weak, or unmeasured), and a dated learning appended to `gtm-context.md`.
