---
name: stress-test-locale
description: Simulates how UI copy and layouts break under German expansion, Japanese density, right-to-left scripts, pluralization, dates, currencies, and names. Use when the user pastes interface copy or describes a layout and asks whether it will survive localization or international users.
---

# stress-test-locale

English copy in a tight layout is the best case, and it is the only case most designs are tested against. Your job is to find what breaks before a translator does.

## Inputs

UI strings, a layout description, or both. Useful extras: the font in use, which components have fixed widths, and which markets matter. If the user names no markets, run the full set below and say which findings matter only if that market is in scope.

## What to test

**Expansion.** German and Finnish routinely run 30 to 40 percent longer than English; short strings (buttons, tabs, labels) can double. Flag every fixed-width container, truncated label, and single-line control that holds text. For each, estimate whether the longer string fits and what happens when it does not (wrap, clip, overflow, ellipsis that hides meaning).

**Density.** Japanese, Chinese, and Korean pack more meaning into fewer characters and need taller line height and different line-breaking. Check for layouts that depend on word spaces, on letter-spacing for emphasis, or on italic and uppercase for hierarchy, since none of those exist in CJK scripts.

**Right-to-left.** Arabic and Hebrew mirror the layout: navigation, progress, back and forward, icon direction, and text alignment all flip, while numerals, brand names, and some icons (a clock, a play button, a checkmark) do not. List which elements in this design must mirror and which must not, and flag any hard-coded left or right.

**Plurals.** English has two forms. Russian and Polish have three or four, Arabic has six. Flag every string built by concatenation or by "item(s)", and every sentence with a number embedded in it.

**Sentence assembly.** Flag strings composed from fragments ("You have " + count + " new " + noun), because word order differs between languages and the fragments cannot be translated separately.

**Dates, times, numbers, currency.** Flag hard-coded formats (MM/DD/YYYY), 12-hour assumptions, decimal and thousands separators, currency symbol position, and phone or address fields that assume one country's structure.

**Names and identity.** Flag first/last name splits, required middle initials, fixed character limits, ASCII-only validation, and any place a person's name is inserted into a sentence that assumes a grammatical case.

**Culture.** Flag idioms, humor, color meanings, gestures, imagery, and metaphors (sports, weather, food) that may mean something else or nothing elsewhere.

## Output

Group findings by the market or script that triggers them. For each: the string or component, what breaks, how likely it is, and the fix (flexible container, message-format syntax, locale-aware formatting library, rewrite). End with the three changes that remove the most risk for the least work.

## Rules

- Estimate, and say that you are estimating. You are not a translation engine, and expansion ratios are ranges, not guarantees.
- Do not translate the strings unless the user asks. When you illustrate, use one short example and mark it as illustrative.
- Do not claim certainty about any language you cannot reason about reliably. Say where a native-speaker review is needed.
