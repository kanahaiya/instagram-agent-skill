---
name: ig-carousel
description: >-
  Build an Instagram carousel - the cover that earns the swipe, slide-by-slide
  copy, and the 1080x1350 files to upload. Use when the user says "carousel",
  "slides", "swipe post", "turn this into a carousel", or has a list-shaped or
  step-shaped idea that would die as a single image.
---

# ig-carousel

Carousels are the highest-dwell format on the grid, because a swipe is an
interaction and a scroll is not. They also get a second chance: Instagram can
show a carousel again starting from a later slide to someone who did not engage
the first time, so slide two has to stand on its own as well.

The format rewards one idea broken into steps. It punishes a caption cut into
pieces.

## When to use it instead of a Reel

Use a carousel when the idea has **sequence and needs to be re-read**: steps, a
framework with parts, a before and after, a list worth screenshotting. Use a
Reel when the idea has motion, a face, or a payoff that has to be seen
happening.

If the idea is one claim, it is neither. Hand it to /ig-reel and say so.

## Structure

6 to 10 slides. The cap is 20 and 20 is almost always a book nobody finishes.
Under 5 and the swipe never starts.

```
1         COVER     the hook. 6 words or fewer, at a size that is legible in
                    the grid at thumbnail. One line of promise under it.
2         THE STAKE why this matters, in one sentence. This slide is also a
                    second cover, so it cannot be setup.
3 to N    ONE IDEA PER SLIDE. A headline of 3 to 7 words, at most 25 words
                    under it. If a slide needs a paragraph, it is two slides.
N+1       RECAP     the whole thing as a list. This is the screenshot slide.
LAST      CTA       one action. Save, comment a keyword, or follow. One.
```

## Slide copy rules

- **The cover is 80% of the result.** Six words. Big. Nothing on the deck saves
  a cover nobody swipes.
- **Design for the grid crop.** Build at 1080x1350 and keep the cover text well
  inside the middle, clear of the outer 120 pixels on every side.
- **Number the slides** (3/8). Completion goes up when people can see the end.
- **No slide is a paragraph.** If it cannot be said in 25 words, split it.
- **The recap slide is the one people screenshot and send.** Make it standalone
  and readable with no context.
- **The handle on every slide**, small, bottom corner.
- **Alt text on the cover at minimum.**

## Building the files

Build each slide at 1080x1350 (4:5), JPEG or PNG. Use the existing project
renderer and brand system; do not introduce a new palette or dependency.

## Output

Present the slide-by-slide copy first, then the caption. Run both through
/ig-human. Build the files only after the user approves the copy.

## Required freebie analysis

After drafting the slide copy and caption, invoke /ig-freebie-analyzer on the
complete carousel draft before presenting the final carousel receipt. Pass the
slide copy, caption, target audience (if known), language, and current CTA.
The analyzer must run for every carousel, including posts whose CTA does not
mention a freebie.

Include the analyzer's result in the carousel output:
- If YES: show the recommended freebie, score, why it adds value, suggested
  keyword, and a draft CTA clearly marked "use only after the asset exists".
- If NO: show the short reason and score.
- If REVIEW: show what needs human judgement.
Do not silently omit this step. If the analyzer skill is unavailable, say so
and include a brief provisional assessment rather than claiming it ran.

This is recommendation only. Do not automatically create a PDF, change the
caption, publish the post, or send messages unless the user explicitly asks
for those actions. A freebie CTA must never promise delivery of an asset that
has not been created and reviewed.

## Output receipt

```
CAROUSEL · 8 slides

1 COVER ...
...

Caption: ...

FREEBIE ANALYSIS
decision: YES / NO / REVIEW
score: NN/100
reason: ...
recommended asset: ...
keyword: ...
CTA: draft only until the asset exists and is reviewed

Nothing is posted. The user reviews and posts it.
```
