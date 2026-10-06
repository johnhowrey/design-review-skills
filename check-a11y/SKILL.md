---
name: check-a11y
description: A reasoning pass on accessibility for pasted markup or a screenshot description, covering contrast, labeling, keyboard flow, focus, and ARIA structure. Use when the user wants an accessibility review of a component or page. Not a substitute for an automated scan.
---

# check-a11y

This skill reads markup or a description and reasons about how a person using a screen reader, a keyboard, magnification, or reduced motion would experience it. It does not execute anything, measure anything, or replace a real tool.

**Say this first, every time:** this is a reasoning pass and it can miss issues an automated scanner (axe, Lighthouse, Playwright with axe) would catch, and it cannot replace testing with real assistive technology or people. Run a scanner too.

## Inputs

HTML, JSX, or a component's markup; a screenshot or description of the rendered result; or both. Without markup, say that you can only reason about what is visible and cannot judge semantics, labels, or focus order.

## Method

1. **Structure.** Is there a sensible heading outline, with one top-level heading and no skipped levels? Are landmarks (header, nav, main, footer) present and used once where they should be? Are lists marked up as lists and tables as tables with headers?
2. **Names and labels.** Every control needs an accessible name. Flag icon-only buttons with no label, inputs relying on placeholder text as the label, links whose text is "click here" or "read more" out of context, and images with missing or meaningless alt text. Decorative images should be hidden from assistive technology.
3. **Keyboard.** Can everything that works with a mouse be reached and operated with Tab, Shift+Tab, Enter, Space, and arrow keys where the pattern calls for them? Flag clickable divs, positive tabindex values, keyboard traps, and custom widgets (menus, dialogs, tabs, comboboxes) that lack the expected key handling.
4. **Focus.** Is the focus indicator visible on every interactive element, and does it have enough contrast against its surroundings? Does focus move into a dialog when it opens, stay inside while it is open, and return to the trigger when it closes? Does focus survive a route change or a dynamic update?
5. **Contrast and color.** Estimate contrast for text and for meaningful graphics against the WCAG AA thresholds (4.5:1 for body text, 3:1 for large text and interface components). Treat your numbers as estimates when you are working from a screenshot description. Flag any information carried by color alone.
6. **ARIA.** The first rule applies: native elements beat ARIA. Flag redundant roles, roles that contradict the element, `aria-hidden` on focusable content, missing state attributes (`aria-expanded`, `aria-selected`, `aria-current`), and live regions that would announce too much or nothing.
7. **Motion and timing.** Flag auto-playing or looping motion with no pause control, anything that ignores `prefers-reduced-motion`, and time limits with no way to extend.
8. **Forms.** Check that errors are associated with their fields, announced, and described in text, that required fields are indicated in more than color, and that autocomplete attributes are present where they apply.

## Output

Findings ordered by impact on a real user, each with the element, the problem, the WCAG success criterion in plain terms (cite the number only when you are sure of it), and a fix. Close with a short list of things you could not assess from what you were given.

## Rules

- Never say the page "is accessible" or "passes." The strongest honest claim is "I found no issues in these areas, from this input."
- Prefer fixing with native HTML before suggesting ARIA.
- Do not invent a screen reader's exact spoken output. Describe what it would likely convey.
