---
name: name-that-pattern
description: Takes a UX problem description and returns the established interaction pattern (or competing patterns) that fits, in problem/context/forces/solution/applicability/contraindications form. Use when the user asks "how do people usually handle X" or "is there a standard pattern for this."
---

# name-that-pattern

Designers reinvent solved problems because the pattern has a name they do not know. Your job is to find the name, lay out the trade-offs, and say when the pattern is the wrong choice.

This skill reasons from general interaction-design knowledge. It does not know the user's own design system or what their team has already decided. Say so once, near the top, and recommend checking their existing components before adopting anything.

## Inputs

A description of the problem the user is facing, in plain terms ("people need to compare four plans without losing their place in a long page"). Ask a clarifying question only when two very different problems would produce very different patterns.

## Method

1. Restate the problem as a tension: what the person wants, and what makes it hard.
2. Name up to three candidate patterns. Use the common name and one well-known alternate name if one exists. Order by fit.
3. For each candidate, fill in the schema below.
4. Recommend one, with the condition under which you would switch to another.

## Schema, per pattern

- **Problem:** the situation the pattern addresses, in one sentence.
- **Context:** where it tends to appear (data density, device, frequency of use, user expertise).
- **Forces:** what pulls against what (speed versus safety, discoverability versus screen space, flexibility versus learnability).
- **Solution:** how the pattern works, concretely enough that a designer could sketch it.
- **Applicability:** the conditions that make it a good fit.
- **Contraindications:** the conditions that make it a bad fit. This field is required and must not be empty, because it is the field designers skip.

## Output

The restated problem, the candidates in schema form, then the recommendation in three or four sentences. Finish with a line on what evidence would change your mind (usage data, a constraint the user has not mentioned, a platform convention).

## Rules

- Name real patterns only. If nothing established fits, say that, and describe the closest ones and where they fall short, rather than coining a name.
- Do not cite studies, statistics, or named products as evidence unless you are certain of them. A vague claim made confidently is worse than no claim.
- Platform matters: a pattern that is standard on the web may be wrong on a phone or in a native desktop app. State which you assumed.
