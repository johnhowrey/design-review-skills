---
name: find-missing-states
description: Generates the state space and edge cases for a feature, form, or screen, and reports which states the description covers and which it leaves out. Use when the user describes a feature and asks what they forgot, what could go wrong, or whether they have covered the edge cases.
---

# find-missing-states

Most shipped bugs in interface work are not logic errors. They are states nobody drew. Your job is to enumerate the states a feature can be in and compare that list against what the user has described.

## Inputs

A feature, form, or screen described in prose, a spec, or a list of designed screens. Ask for the feature if none is given. If the description is thin, proceed anyway and mark what you had to assume.

## Method

Walk the feature through each dimension below. For each one, list the states that apply to this feature and ignore the dimensions that do not apply (and say which you skipped and why, in a single line).

- **Data:** none yet, one item, a few, very many, a single item with an absurdly long value, malformed or partial data, data that changes while the person is looking at it.
- **Loading:** first load, reload, slow load, load that never finishes, partial load where some regions arrive and others fail.
- **Permission:** signed out, signed in without rights, rights revoked mid-session, read-only, an admin acting for someone else.
- **Network:** offline, flaky, request succeeded but the response was lost, duplicate submission from a double tap, request that completes after the person navigated away.
- **Account:** new, trial, expired, over quota, suspended, deleted, a user belonging to several organizations.
- **Content:** empty strings, maximum lengths, emoji and combining characters, right-to-left text, pasted rich text, names with one word or six.
- **Time:** stale session, expiry during a long form, time zones, daylight-saving boundaries, scheduled actions that fire while the app is closed.
- **Concurrency:** two tabs, two people editing the same record, an action that races with its own result.
- **Dependencies:** every outside service the feature leans on (an identity provider, a payment processor, an email sender, a third-party API). For each one: down, slow, rate-limited, returning something new, revoking access, or delivering an event twice or late.
- **Money:** whenever a price is involved: failed payment, refund, proration, tax, currency, a charge that succeeds while the app never hears about it, and what the person keeps access to in each case.
- **Consistency:** wherever the same fact lives in two places (a count in the app and a quantity at the billing provider, a user in your database and in an identity provider). List how the copies can disagree, which one wins, and what the person sees while they differ.
- **People:** who can do what. Invitations, removal, a person leaving the organization while holding access, and the difference between someone who can see a thing and someone who can change what it costs.

Then check recovery: for every error state you named, can the person get back to a good state without losing their work?

## Output

Begin with the assumptions you made about the feature, in a short list, so the reader can correct them. Then, for each applicable dimension, one line naming what the description already covers, followed by the gaps in that dimension. Do not make a table of "covered" against "not covered"; when the description is thin, the covered side is empty and the table only pads. Say "nothing stated" in one line and go straight to the gaps.

End with a ranked list of the five gaps most likely to cause real harm. Rank by the product of how likely the state is and how bad the outcome is when it goes unhandled; a rare state that destroys data or money outranks a common state that is merely ugly.

Tag every gap in the ranked list as **stated** (the description names the state) or **inferred** (you derived it from the feature's nature), with a one-line reason for each inference. Where a gap needs a product decision, put it as a question for the user. When you notice a risk that spans several dimensions (two systems of record, an outside service the whole feature depends on), say so explicitly and rank it as one item rather than scattering it.

## Rules

- Do not pad. Ten real gaps beat forty generic ones.
- Skip states the feature structurally cannot reach.
- When a state needs a product decision (what should happen when quota runs out mid-upload?), write it as a question for the user and do not decide for them.
