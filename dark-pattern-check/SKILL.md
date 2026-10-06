---
name: dark-pattern-check
description: Reasons over a described flow (signup, checkout, cancellation, billing, consent) for dark patterns such as forced continuity, obstruction, hidden costs, asymmetric cancellation, and confirm-shaming. Use when the user describes or pastes a flow and wants to know whether it manipulates people or would draw regulatory attention.
---

# dark-pattern-check

A dark pattern is a design choice that works against the person using it, to the benefit of the business, in a way the person would object to if they saw it plainly. Keyword matching misses most of them, because the manipulation lives in the structure of the flow and not in any one string. Your job is to read the flow as a whole.

This is a design review and not legal advice. Say so once, and recommend counsel for anything that touches billing law, consumer protection, or privacy regulation.

## Inputs

A flow described step by step, with the copy on each screen where possible. The most useful flows to check are signup, free trial, upgrade, cancellation, refund, account deletion, data export, and consent. If the user gives only the sign-up side of a subscription, ask for the cancellation side, since the asymmetry between the two is the most common finding.

## What to look for

- **Forced continuity.** A trial or free tier that converts to paid with weak notice, or a card requested for a "free" product with no reminder before the charge.
- **Obstruction and asymmetry.** Easy to enter, hard to leave. Compare the step count, the time, the channel (self-serve versus phone or chat), and the emotional load of signing up versus canceling. A large gap is a finding on its own.
- **Hidden or late costs.** Fees, taxes, shipping, or auto-added items that appear only at the last step, or a price shown at a different billing interval than the one charged.
- **Confirm-shaming.** Decline buttons phrased to make the person feel foolish ("No thanks, I don't like saving money").
- **Visual interference.** The preferred option is large and colored, and the other is a faint link; a close button that is hard to see; a pre-selected option the person is likely to miss.
- **Nagging and interruption.** Repeated prompts after a refusal, with no way to say "stop asking."
- **Misdirection and trick wording.** Double negatives, toggles where "on" means opting out, checkboxes where checked means declining.
- **Sneaking.** Items added to a cart, a plan upgraded, or consent assumed without an explicit act.
- **False urgency and scarcity.** Countdown timers that reset, "only 2 left" with no basis, activity notices that are not real.
- **Roach motel for data.** Data collected easily and deletion or export that is hard to find or incomplete.
- **Consent coercion.** A cookie or data banner where accepting is one click and refusing takes several.

## Output

For each finding: the step, the pattern's name, what the flow does, who is harmed, and a fix that preserves the business goal where one exists (a clear reminder email before a trial converts costs little and removes the finding). Rate each as **likely harmful**, **borderline**, or **defensible with changes**.

Finish with a symmetry table for any subscription or account flow: steps, time, and channel to start versus to stop.

## Rules

- Judge from the description. If a key step is missing, say that the finding is conditional on it.
- Do not accuse. Describe the effect on the person, since intent cannot be seen in a flow.
- Do not recommend removing a business model. Recommend making its terms plain.
