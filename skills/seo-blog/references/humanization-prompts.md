# Humanization and image prompts

Copy-paste prompts used by seo-blog, also usable on their own. They are consistent with `engagement-beats.md`; if a prompt and that file disagree, the file wins.

## 1. Rewrite for a human voice

```
Rewrite this so it reads like a knowledgeable practitioner with a clear point of view, not an AI assistant.
- Open each section with a sentence that directly answers its heading.
- Vary sentence and paragraph length; never three similar-length sentences in a row.
- Active voice. Second person (you/your) where it fits. Contractions everywhere.
- Remove: delve, tapestry, pivotal, furthermore, moreover, in conclusion, it's worth noting, it's important to note, in today's digital landscape, leverage, robust, seamless.
- Replace em dashes with commas, colons, periods, or parentheses.
- No one-word paragraphs, no "Here's the thing", no rhetorical-question section endings.
- Keep every fact and number exactly as given. Do not add new numbers.
```

## 2. Two-pass editor

```
Edit this as a human editor would:
- Cut any sentence that sounds machine-written.
- Replace at least 3 generic phrases with something only someone with real experience would say (use only the facts provided).
- Make the opening more specific and the ending less neat.
- Check: would a person actually say this out loud? If not, rewrite that part.
```

## 3. Experienced-skeptic pass

```
Rewrite from the perspective of a highly experienced practitioner who has seen every trend come and go. Respect the reader's intelligence, skip the obvious, get to what matters, allow one dry observation per section, never use buzzwords unironically. Do not change facts or numbers.
```

## 4. Voice profile (run once, store the result in gtm-context.md → Voice)

```
Here are 3-5 pieces of my writing. Build a voice profile: sentence rhythm, words I favor, words I never use, how I structure arguments, how I open and close, my relationship with the reader, and rules another writer could follow. Compress it into a 150-200 word voice prompt.
```

## 5. Section independence check

```
For each section: (1) does the first sentence answer the heading? (2) does it make sense read alone? (3) any "as mentioned above" or "we'll cover later"? Flag failures and rewrite them to stand alone.
```

---

## Image prompts (any image model)

**Blog banner (1200×675)**
```
A modern, minimal illustration for a blog post titled "[TITLE]". Flat design, muted palette with one accent color, clean negative space. Concept: [VISUAL CONCEPT]. Landscape 1200x675. No text, logos, or watermarks.
```

**Data visual**
```
A clean, minimal infographic showing [DATA OR COMPARISON]. 2-3 colors, flat design, large readable numbers, simple icons. Include exactly these figures: [FIGURES FROM THE POST]. Vertical, for embedding in a blog post. No logos.
```

**Comparison graphic (1200×800)**
```
A side-by-side comparison of "[A] vs [B]". Split layout; abstract icons for each attribute, no logos or screenshots. Neutral palette with one accent for the recommended option per use case.
```

**Process diagram**
```
A horizontal flow diagram: [STEP 1] → [STEP 2] → [STEP 3] → [STEP 4]. Minimal, connected arrows, a simple icon and 2-3 word label per step, monochrome with one accent on the final step.
```

**Inline illustration (600×400)**
```
A simple abstract illustration of "[CONCEPT]". Flat design, single accent color, metaphorical rather than literal.
```

**Screenshot annotation**
```
Annotate this screenshot of [WHAT]: highlight [AREA] with a box, add numbered callouts to [FEATURE 1], [FEATURE 2], [FEATURE 3] with 3-5 word labels. Clean, uncluttered.
```
