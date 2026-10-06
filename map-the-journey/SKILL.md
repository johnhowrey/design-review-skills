---
name: map-the-journey
description: Breaks a user objective into a full journey by user maturity (first use, occasional, habitual, expert) and flags unhandled entry points, exit paths, and interruptions. Use when the user describes a goal such as "people need to set up billing" and wants to know what the experience around it must cover.
---

# map-the-journey

A flow diagram shows the path the designer imagined. A journey shows the paths people take. Your job is to find the distance between the two.

## Inputs

A stated objective, in the user's words ("a new customer connects their store and publishes a first product"). Optionally the product's type, the audience, and any existing flow. If the objective is vague, restate it as a testable sentence and ask the user to confirm before going further.

## Method

1. **Define done.** What observable thing is true when the person has succeeded? Write one sentence. If there are two plausible definitions (the form is submitted versus the product is live), list both and note which the journey below assumes.
2. **Break the objective into stages**, each a thing the person does or decides, not a screen. Name the decision at each stage and what the person needs to know to make it.
3. **Run the stages four times**, once for each maturity level:
   - first use: no context, no vocabulary, no trust yet
   - occasional: remembers roughly, forgot the details, needs reorientation
   - habitual: wants the shortest path and resents confirmation
   - expert: wants to batch, script, or skip
   Note where the same stage must look different, and where one design cannot serve all four.
4. **Entry points.** List every way a person can arrive in the middle of this journey: a deep link, an email, a notification, a search result, a shared URL, a returning session, a handoff from another person or device. For each, say what the person needs to see to orient themselves.
5. **Exit paths.** List every way a person can leave: finish, cancel, give up, get interrupted, lose connection, be pulled away by something urgent. For each, say what happens to their progress and how they get back.
6. **Interruption and resumption.** Which stages can be paused safely, and which lose state? A person who returns after a day, a week, or a quarter should land somewhere sensible.

## Output

The stage list, the maturity table (stages down, levels across, with a short note in each cell that differs), then two flagged lists: **entry points with no designed arrival** and **exit paths with no designed recovery**. End with the single stage where most journeys are likely to fail and the reason.

Tag claims as **stated** (the user told you), **inferred** (you derived it from the objective), or **assumed** (a guess you could not support). A journey map made mostly of assumptions is worth saying so about.

## Rules

- Describe behavior, not screens. If the output reads like a sitemap, start over.
- Do not invent user research. If you describe what people "typically" do, say that it is a general pattern and not evidence about this product's users.
