---
name: extract-design-system
description: Reads pasted CSS, design-token JSON, or a component prop list and extracts the design system it implies (scales, tokens, patterns), flagging inconsistencies, near-duplicates, and values that bypass the system. Use when the user pastes styles or tokens and asks what system they actually have, or where it is inconsistent.
---

# extract-design-system

Most codebases have a design system that nobody wrote down, built from decisions repeated often enough to become habit. Your job is to read the evidence, state the system that is really there, and mark where the code disagrees with itself.

This version works on text the user pastes. It does not connect to Figma, a repository, or a running site, so it only knows what it has been shown. Say how much you were shown (one file, a token list, a fragment) and treat conclusions from a small sample as provisional.

## Inputs

Any of: a CSS or SCSS file, CSS custom properties, a token export (JSON or YAML), a Tailwind config, a styled-components theme, or a list of component props. Ask for more files when a single file cannot answer the question being asked.

## Method

1. **Inventory.** Collect every distinct value for color, font family, font size, font weight, line height, spacing, radius, border width, shadow, z-index, breakpoint, and motion duration. Count how often each appears.
2. **Find the scales.** Look for the pattern behind the values: a 4 or 8 point spacing grid, a type scale with a ratio, a short list of radii. State each scale as you reconstruct it, and give the share of values that fit it.
3. **Find the roles.** Group colors by apparent job (surface, text, border, accent, status), not by hue. Name the roles the code seems to use, even when it never named them.
4. **Find the drift.** List values that sit just off a scale (15px beside 16px, `#333` beside `#323232`), near-duplicate colors, one-off magic numbers, and hard-coded values sitting next to a token that already covers them. Report each with its count, since a value used once is different from one used forty times.
5. **Check the components.** For props, look for the same concept under different names (`variant`, `kind`, `type`), booleans that should be an enum, and components that overlap in purpose.
6. **Check accessibility-relevant tokens.** Flag text and surface color pairs that fall under AA contrast by arithmetic, and focus styles that are removed without replacement.

## Output

1. The system as you reconstruct it: scales, roles, and naming conventions, each stated in a line or two.
2. A drift report ordered by how often the offending values occur.
3. A proposed token set, kept small, which collapses the drift onto the scales you found. Mark every proposed merge as **safe** (visually identical) or **needs a designer** (a visible change).
4. What you could not determine from the input.

## Rules

- Report counts, not impressions. "Fourteen distinct grays" is a finding; "lots of grays" is not.
- Describe the system that exists. Do not substitute the one you would prefer.
- Do not merge two values you have not proven equivalent. When contrast is borderline, show the ratio.
- If the input is too small to support a conclusion, say that, and name the file that would settle it.
