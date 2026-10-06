# Design review skills for Claude

Ten Claude Skills that review product design the way a sharp, slightly hard-to-please colleague would. Paste a screenshot, a flow, some interface copy or a brief, run the slash command, and get findings ranked by how badly they hurt a real user.

They are plain markdown. No API key, no server, no install step beyond copying a folder.

## The ten

| Command | You give it | You get back |
|---|---|---|
| `/grill-my-design` | A screenshot or frame description, optionally a PRD | Ranked findings on hierarchy, density, affordance and composition, plus the six hard questions (first use, 500th use, zero data, huge data, no permission, irreversible) |
| `/find-missing-states` | A feature or form description | The states the description covers and the ones it forgot, across data, loading, permission, network, account, content, time and concurrency |
| `/map-the-journey` | A user objective | The journey by maturity (first use to expert), with unhandled entry points and exit paths flagged |
| `/check-the-copy` | Interface strings tagged by type | A per-string critique with rewrites, plus a terminology consistency note |
| `/name-that-pattern` | A UX problem | Established patterns in problem/context/forces/solution/applicability/contraindications form |
| `/stress-test-locale` | Copy or a layout | What breaks under German expansion, CJK density, right-to-left, plurals, dates, names |
| `/check-a11y` | Markup or a screenshot description | A reasoning pass on structure, labels, keyboard, focus, contrast and ARIA |
| `/dark-pattern-check` | A flow (signup, cancel, billing, consent) | Manipulative structure, with a side-by-side of the effort to start versus stop |
| `/audit-the-assumptions` | A PRD or brief | The unverified assumptions, ranked, each turned into a testable research question |
| `/extract-design-system` | CSS, tokens or props | The system your code implies, and every place it contradicts itself |

## Install

Copy the folders you want into your skills directory.

```sh
# one project
cp -R grill-my-design find-missing-states .claude/skills/

# everywhere
cp -R grill-my-design find-missing-states ~/.claude/skills/
```

Then invoke by name inside Claude Code, for example `/grill-my-design` followed by your screenshot.

## How they behave

Every skill separates what it saw from what it is guessing. Findings are tagged observed, inferred or assumed, so you know how much weight each carries. None of them pretend to know your users, your analytics or your design system; where a conclusion would need that, the skill says so and tells you what it would take to know.

`/check-a11y` is a reasoning pass. It is not a scanner and will say so every time. Run axe or Lighthouse alongside it.

`/audit-the-assumptions` will not simulate user answers. Imagined participants are not evidence.

## What these do not do

They do not read Figma, Storybook, analytics or research repositories. They work on what you paste. A version that connects to those sources is in development; until it exists, paste.

## License

MIT. See `LICENSE`.
