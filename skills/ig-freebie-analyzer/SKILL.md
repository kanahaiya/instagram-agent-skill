---
name: ig-freebie-analyzer
description: >-
  Analyze a generated Instagram carousel, caption, or existing post and decide
  whether a genuinely useful freebie should accompany it. Recommend the best
  asset type, explain audience value, score the opportunity, and prepare a
  keyword CTA and manual delivery brief. Run automatically after /ig-carousel
  and also when the user invokes /ig-freebie-analyzer directly.
---

# ig-freebie-analyzer

Decide whether a post deserves a freebie. Do not assume every post does, and do
not create an asset merely to fill a slot. The goal is a useful resource that
solves the next problem left open by the post, not a PDF copy of the slides.

## When to run

- **Automatic:** Run after /ig-carousel has drafted its slides and caption,
  before the final carousel receipt/approval. Analyze the generated content,
  even if the post's existing CTA does not mention a freebie.
- **Manual:** Run when the user invokes /ig-freebie-analyzer with a post,
  carousel, caption, or pasted slide copy. If some fields are missing, analyze
  what is available and state the limitation; ask only if the post itself is
  unavailable or the audience/topic cannot reasonably be inferred.
- This skill analyzes and recommends. It does not render a PDF, publish a post,
  send a DM, or alter files unless the user explicitly requests that work.

## Inputs

Use available fields:
- Post topic and intended audience
- Slide-by-slide copy and cover
- Caption and current CTA
- Language and brand voice, including templates/voice.md if available
- Existing claims, examples, links, templates or resources in the post

Do not require a particular JSON schema. Accept plain text, a structured post
object, or content passed by the carousel skill.

## Decision rubric

Score each dimension from 0 to 5, then calculate a weighted score out of 100:
- Audience problem and topic relevance: 25%
- Incremental value beyond the carousel: 25%
- Practical usefulness / likelihood someone would request it: 20%
- Ease of consuming and applying it: 15%
- Accuracy and verifiability: 15%

Weighted score = sum of (dimension score / 5 * dimension weight).

Interpretation:
- 75–100: recommend a freebie.
- 55–74: recommend only if a focused, lightweight asset clearly adds value;
  otherwise say skip or review.
- Below 55: do not recommend a freebie.

These are decision heuristics, not predictions of engagement or conversion.
Apply hard stops regardless of score:
- If the proposed resource merely repeats or repackages the slides without
  meaningful extra utility, recommend NO FREEBIE.
- If material claims cannot be responsibly verified, recommend human review
  or remove those claims.
- Do not invent statistics, testimonials, research, pricing, URLs or outcomes.
- For high-risk or sensitive topics, flag the need for appropriate expert review.
- Do not suggest collecting personal data as a condition of receiving a freebie.

## Select the smallest useful format

Choose one primary format:
1. Checklist / quick-reference sheet
2. Mini guide (usually 3–8 pages)
3. Template, swipe file or prompt pack
4. Worksheet / planner
5. Curated resource directory
6. Comparison sheet
7. Decision tree

Prefer a checklist, template or one-page guide when it solves the problem.
Recommend a longer PDF only when the topic genuinely needs it. A freebie should
answer the next practical question that remains after reading the carousel.

## CTA and delivery rules

When recommending a freebie, include:
- A specific title and one-sentence promise
- The audience problem it solves
- What sections/items it should contain
- Why it is more useful than the carousel alone
- A simple one-word comment keyword (uppercase, easy to spell)
- One optional caption CTA
- A short public comment reply
- A manual DM template with a placeholder for the approved share link
- Any sources or verification needed before the asset is created

Never claim the file is already created or ready when only a brief has been
produced. Do not insert a CTA promising a resource that does not yet exist.
Mark the CTA as **use only after the freebie is created and reviewed**.
Preserve an existing CTA if changing it would create competing asks; recommend
one clear action, not multiple CTAs.

The existing /ig-dm skill can be used for message tone and manual delivery
conventions. Do not send messages or automate delivery.

## Output format

Always return a concise, scannable report:

### Freebie decision
- Recommendation: YES / NO / REVIEW
- Score: NN/100
- Confidence: HIGH / MEDIUM / LOW
- One-sentence rationale

### If YES
- Best format and suggested title
- Target audience and problem solved
- Contents / outline (specific, not generic)
- Incremental value over the carousel
- Suggested keyword
- Suggested CTA, labelled as draft until the asset exists
- Public reply and manual DM template
- Validation/source checks
- Next action: create and review the asset

### If NO or REVIEW
- Explain the specific reason
- If useful, name one change that could make a freebie worthwhile
- Do not invent a weak freebie just to avoid saying no

End with a compact status line suitable for the carousel receipt:
FREEBIE: YES — [format/title] ([score]/100)
or FREEBIE: NO — [short reason] ([score]/100)
or FREEBIE: REVIEW — [short reason] ([score]/100)

## Examples

Post: "5 mistakes people make when writing AI prompts."

Good recommendation:
- YES, 86/100 — an AI Prompt Repair Kit with a reusable prompt formula,
  10 before/after prompt rewrites, and a copyable starter pack. This helps
  readers apply the advice instead of repeating the slides.
- Keyword: PROMPTS.
- CTA draft: "Comment PROMPTS for the free AI Prompt Repair Kit."
- Label the CTA as a draft until the asset is created and reviewed.

Bad recommendation:
- A generic 20-page "Complete AI Guide" that repeats the same five mistakes.

Post: "A single motivational quote with no actionable topic."

Good recommendation:
- NO — the post does not reveal a specific audience problem that a separate
  resource would solve. Keep the post simple.
