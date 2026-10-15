---
name: reddit-post
summary: Drafts Reddit posts that read like a community member sharing something useful rather than a founder promoting a product. You do the posting.
pillar: communities
install: "/plugin marketplace add himanshusaleria/vibegtm-skills && /plugin install vibegtm@vibegtm"
use_cases:
  - Share a build lesson or experiment in r/SaaS, r/SideProject, or r/startups
  - Turn a blog post into a native post for a niche practitioner subreddit
  - Plan how to answer "what's the tool?" in the comments without pitching
---

## What it does

`reddit-post` picks the right subreddit for your topic, or uses the one you name, and writes a post in that community's style. It knows what tends to work and what gets removed in common founder and builder subs, and it reminds you to check each sub's rules before you post.

The rules are strict. The product name never appears in the title, there's no link in the body, and the product gets at most one line of context. The post has to be worth reading even if your product didn't exist. Titles are direct, with no emojis and no "As a founder..." opener. Posts end by inviting discussion rather than with a call to action. Specifics come only from the proof in your `gtm-context.md`, and it won't invent metrics.

It is draft-only by design. It never posts, schedules, or votes for you. When you report back how a post did, it records what it learned in `gtm-context.md`.

## When to use it

- You have a real lesson, number, or failure worth sharing
- You're adapting one piece of content to several subreddits (each one gets its own version)

## Example

**Input:** `/reddit-post --subreddit SideProject "what I learned shipping a free tool before the paid product"`

**Output:** a title, the post body, and posting notes: rules to check, flair, timing, a plan for answering comments, and cross-post options.
