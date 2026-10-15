# Engagement beats: the technique library

Every post needs at least one engagement beat per 300-400 words of body prose. A 2,500-word post needs 6 or more; a 5,000-word pillar needs 12 or more.

**Why:** SEO structure (TL;DR, question H2s, FAQ) is necessary but produces commodity prose. Readers bounce when the writing reads like every other generated blog. Beats make prose sound like someone who has been in the room, without breaking extractability.

**Hard constraint:** the first sentence of each H2 section stays a standalone answer to the heading. Beats go in sentences 2-4.

> All examples below are illustrative, set in a fictional B2B support-software context. The numbers are made up to show the shape of the technique. In a real post, every number must come from a real source.

---

## The 7 techniques

### 1. Expectation → denial, with concrete contrast
Set up what the reader expected, deny it, anchor the denial with two specific contrasting examples.
> We expected the large support teams to be different. They weren't: a 60-agent team at a public SaaS company and a 4-person team at a seed-stage startup both spent about a quarter of their week on tickets that a help-center article already answered.

The contrast (60 vs 4, public vs seed) does the work and gives the reader something to picture.

### 2. A specific scene in industry shorthand
Drop the reader into a real moment, using vocabulary that only insiders use.
> A support lead told us her team clears the macro backlog on Friday afternoons. The Friday before a pricing change is the one nobody forgets.

### 3. Opinion stated as fact, no hedging
> Help centers go stale because products change, and products change because that's the job.

Conviction reads human; hedging reads machine. Pair the opinion with the data that backs it so it lands as a judgment, not a hot take.

### 4. Parenthetical aside
> Most teams have a tagging taxonomy. (Half of them call it that. The other half call it "the tags" and hope nobody asks.)

Use once or twice per 1,000 words or it becomes a tic.

### 5. Cost framed as something people buy
> That's roughly one full-time hire a year, paid in backlog instead of salary.

Managers think in headcount and quarters, not percentages.

### 6. Setup across sentences, payoff at the end
> One team rewrote their onboarding docs in three weeks. They felt good. Then they spent the next two months answering tickets about the old screens, because the product shipped a redesign the week after. The docs weren't the problem. The release calendar was.

The payoff earns its place because the setup did the work.

### 7. A line that requires lived experience
> Anyone who has run support through a launch week knows which dashboard nobody trusts on Monday.

Readers either nod or don't. The ones who nod are the buyers.

---

## AI tells: block these

Any draft containing these must be rewritten before it passes.

**Sentence-level**
- One-word paragraphs ("Wrong." "Except.")
- Single-sentence paragraphs for emphasis more than twice in a post
- Em dash + fragment combos in succession
- "It's not X. It's Y." reveal constructions (replace with a specific example)

**Phrase-level**
- "Here's where it gets weird/interesting/wild."
- "Spoiler:", "Plot twist:", "The catch?", "And that's the rub."
- "We did the math." as a sign-off
- "Welcome to [X]." as a section opener
- "Here's the part nobody wants to admit:"

**Rhythm-level**
- Denial stacks of 3+ short sentences ("Not at X. Not at Y. Not at Z.")
- Three or more sentences of 8 words or fewer in a row
- More than one paragraph opening with a one-sentence line
- Sections ending in rhetorical questions

**Vocabulary** (on top of the banned list in `playbook.md`): wild, brutal / brutally honest, reality check, the hard truth, game-changer, sea change, inflection point.

### The em dash rule
Em dashes are a common machine-writing fingerprint. Replace them with a comma (most cases), a colon (before a list or definition), a period (independent clauses), or parentheses (true asides). At most 2 per 2,500 words; 3 or more is a fail.

---

## Anonymization: protect people and companies

Without explicit written permission:

- **People:** use a role + sector ("a support lead at a US fintech") or an obviously placeholder first name. Never the real first name, even with "let's call him X".
- **Companies:** describe by sector + scale + region ("a 40-person European HR SaaS"). Never name the employer, even if the individual agreed to be named: permission covers the person, not their company.
- **Internal systems:** never expose internal project IDs, database names, or dashboard IDs in public copy. Use descriptive labels ("our product analytics"). If readers need to verify, link a public artifact.

---

## Sentence-length variance

Human prose has wide variance, but not a mechanical short-short-long pattern. Aim for:
- 60% of sentences at 12-22 words
- 25% at 6-11 words
- 10% over 25 words
- 5% under 6 words

Avoid uniform 15-word blocks, uniform 6-word "punchy" blocks, mechanical alternation, and paragraphs where every sentence starts the same way.

## The bar

Read the first and last 200 words aloud. A peer explaining something over coffee: pass. A content intern paraphrasing a chatbot: rewrite.
