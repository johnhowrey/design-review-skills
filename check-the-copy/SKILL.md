---
name: check-the-copy
description: Per-string critique of interface copy (buttons, errors, empty states, confirmations, notifications, trust language). Use when the user pastes UI strings and wants them reviewed for clarity, tone, and whether the person reading them will know what happens next.
---

# check-the-copy

Interface copy is read in a hurry, by someone in the middle of something else. A string works if that person knows what it means, what it will do, and what to do next.

## Inputs

A list of strings, each tagged with its type: **button**, **error**, **empty state**, **confirmation**, **notification**, **label**, or **trust/consent**. If the user pastes strings with no type, infer it from the wording and say what you inferred. Ask for surrounding context only when a string is unreadable without it.

## What to check, by type

**Buttons and links.** The label should name the outcome, not the mechanism ("Send invoice" beats "Submit"). Check that destructive actions say so, that the primary and secondary labels cannot be confused, and that "Cancel" is not ambiguous between cancelling the dialog and cancelling the order.

**Errors.** Each error should answer three things in order: what happened, why (when the person can act on the why), and what to do now. Flag blame ("You entered an invalid email"), jargon, raw codes with no explanation, and errors that say nothing the red border did not already say. Flag "Something went wrong" unless nothing more is knowable, and in that case it should still say whether the work was saved.

**Empty states.** An empty state is the only chance to teach. It should say what belongs here, why it is empty, and offer the first action. Flag empty states that say only "No results" or "Nothing here."

**Confirmations.** The message should say what was done, to what, and whether it can be undone. Flag confirmations that restate the button the person just pressed.

**Notifications.** Check that the reason for interrupting is clear in the first six words, that it is actionable or purely informational (and says which), and that it would still make sense read two hours late.

**Labels and headings.** Check that the same concept always carries the same noun, that a label still makes sense out of context (in a screen reader's list of controls, in a breadcrumb, in a search result), that nouns and verbs are not swapped ("Setting" and "Settings," "Export" as a button and "Export" as a menu), and that capitalization follows one rule.

**Trust and consent language.** Flag vague data claims ("we may share with partners"), euphemisms for charges, pre-ticked consent wording, and any sentence whose legal meaning differs from its friendly reading.

## Output

Start with the five strings most worth fixing, ranked by how many people see them and how badly they mislead, so a long list does not bury the important ones.

Then, for each string: the original, the problem in one sentence, and a rewrite when you have a better one. A string that works gets "fine," plus a clause only when its fitness depends on context (a bare "Cancel" is fine alone and ambiguous next to a subscription). Keep the product's register; do not flatten everything into the same bright friendly tone. When you give no rewrite, write "no rewrite" and the reason, so the gap reads as a decision.

After the per-string pass, add a short consistency note: any term used for the same concept in two ways (workspace and project and team, for example), any shift in person or politeness, any capitalization or punctuation convention that breaks. If the product model is unknown, name the options and say which you would pick and why, instead of picking silently.

Finish by listing any dependent copy you would need to see before the review is complete: the confirmation dialog behind a destructive button, the success state behind a form, the screen an error links to.

## Rules

- Lead with the person's need. A rewrite should be as short as the original unless the original left out something the reader needs (what failed, what to do next, a date, an undo). When it is longer, say what it added.
- You may rely on convention to read a string (a 403 is a permissions failure; "No results" implies a search), but say that you did, and say what would change the rewrite if the assumption is wrong.
- Use a bracketed placeholder such as [date] where the product has to supply a fact. Never invent the fact.
- Do not add exclamation marks, emoji, or cheerfulness that was not there.
- When you cannot tell what a string refers to, say so and do not guess a rewrite.
- Mention accessibility or localization only when a string creates a specific problem (an icon-only label, a sentence built from fragments), not as a standing checklist.
