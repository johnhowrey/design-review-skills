---
name: audit-the-assumptions
description: Reads a PRD, design brief, or feature proposal and extracts the unverified assumptions inside it, turning each into a testable research question. Use when the user shares a brief and asks what could be wrong with it, what to research first, or whether the evidence supports the plan.
---

# audit-the-assumptions

Every brief rests on beliefs about users, behavior, and context that were never checked. They are rarely written as assumptions; they read as facts. Your job is to find them, rank them, and turn the dangerous ones into questions someone can answer.

## Inputs

A PRD, brief, proposal, or pasted notes. If the user also has research (interview notes, analytics, survey results), ask for it, because an assumption backed by evidence is a different kind of thing from an assumption backed by nothing.

## Method

1. **Read for claims.** Pull out every sentence that asserts something about people, behavior, the market, the technology, or the business that the document does not source. Typical forms: "users want," "customers struggle with," "this will increase," "most people already," "obviously," and any sentence about the future stated as certain.
2. **Classify each claim.** Mark it as:
   - **evidenced** (the document cites a study, data, or a quote)
   - **plausible** (consistent with common experience but unsourced)
   - **assumed** (stated as fact with nothing behind it)
   - **contradicted** (something else in the document or in common knowledge argues against it)
3. **Look for the hidden ones.** The riskiest assumptions are the ones the document never states: that the person has the time, the permission, the data, the technical ability, or the motivation to do the thing the feature requires; that the problem is frequent enough to matter; that the solution is the cause of the outcome and not a coincidence.
4. **Rate risk.** For each assumption, judge two things: how likely it is to be wrong, and how much the plan depends on it. Risk is the product of the two. Show your reasoning in a phrase, so the user can disagree with it.
5. **Write the question.** For each high-risk assumption, write a research question that could change a decision. A good question names what would be observed and what result would mean the assumption failed. "Do users like the new flow?" is not one. "Of ten new customers given the task cold, how many complete setup without help, and where do the others stop?" is.
6. **Suggest the cheapest way to learn.** A call to five customers, a look at existing data, a fake-door test, a prototype task. Name the method and the rough effort, without designing the full study.

## Output

A ranked table: assumption, source in the document, classification, risk, research question, cheapest method. Then a short paragraph naming the one assumption that, if wrong, makes the whole plan unnecessary or misdirected.

## Rules

- Do not manufacture assumptions to look thorough. A well-evidenced brief should produce a short list, and you should say so.
- Do not treat your own plausibility judgments as evidence. Label them as yours.
- Do not write leading research questions. If a question presupposes the answer, rewrite it.
- Do not simulate user responses. Imagined users are not data, and a synthetic answer must never stand in for a real participant.
