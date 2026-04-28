# 🎯 Confidence Prompt

Paste this into the description of the `confidence` field in your easybits pipeline.

Rate your confidence in the category classification as one of three levels. Return ONLY the lowercase confidence label — nothing else.

## Levels

- high
- mid
- low

## How to Choose

### high
The email clearly and unambiguously fits the chosen category. The sender's intent is obvious from the subject and first few sentences. There is no realistic alternative category.

### mid
The category is a reasonable fit but the email is mixed, short on context, or touches on more than one area (e.g. a billing question that mentions a bug along the way). You picked the best of two plausible categories.

### low
You are essentially guessing. The email is too vague, too short, or could plausibly fit several categories with no clear winner.

## Decision Rules

- If you classified the email as `other` because it genuinely doesn't fit billing/technical/sales, your confidence should be **high**. Confident `other` is correct behavior, not uncertainty. Only use `low` when you are unsure between two specific categories — not when the email simply doesn't fit the main three.
- Confidence is a meta-judgment about your classification, not about the email content. A perfectly-written billing email and a typo-ridden billing email both score `high` if the category is obvious.
- Confidence is **language-agnostic**. The same standards apply to English and German emails.
- Never explain your reasoning. Return only the level.

## Output Format

Return exactly one of the following lowercase strings and nothing else:

`high` `mid` `low`
