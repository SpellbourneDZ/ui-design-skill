# UI Design Skill

A product-minded UI design skill for AI coding agents.

It helps agents build interfaces that feel intentional and product-specific instead of converging on the same generic AI-generated patterns: nested cards, decorative gradients, oversized pills, arbitrary bento grids, vague copy, and motion added for decoration.

The skill treats UI work as a sequence of product understanding, hierarchy, visual direction, implementation, and visual review.

## Install

Use Node.js 22.20.0 or newer for the current `skills` CLI.

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill
```

To install only this skill explicitly:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design
```

For Codex:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design -a codex
```

For Codex across projects:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design -a codex -g
```

These options are documented by the [skills CLI](https://github.com/vercel-labs/skills#options).

## Why use it?

Coding agents can build functional interfaces quickly, but without strong constraints they often converge on familiar visual recipes instead of making decisions from the product itself.

`ui-design` adds a design-engineering layer that asks the agent to:

- understand the product, user, task, and existing design language before styling;
- respect Figma, screenshots, existing components, and tokens as sources of truth;
- define a compact visual thesis when no design direction exists;
- fix hierarchy and structure before adding decoration;
- apply a consistent UI system for copy, spacing, component geometry, action grouping, and working space;
- detect common AI-looking UI patterns without blindly banning popular styles;
- treat responsive behavior, states, accessibility, copy, and motion as part of the design;
- render and visually review material UI changes with realistic content and treat applicable checks as acceptance criteria when the environment allows it.

The goal is not a specific aesthetic. The goal is deliberate UI that belongs to the product it was made for.

## UI system

The skill turns visual preferences into implementation rules and acceptance checks:

| Area | Rule |
| --- | --- |
| Useful copy | Keep text that clarifies a decision, action, constraint, or meaningful state. Remove repeated headings and descriptions of obvious mechanics. Preserve labels, recovery guidance, and consequential warnings. |
| Spacing | Use one spacing contract by relationship. A field includes its label, control, help, counter, error, and attachment actions; gaps between complete fields stay consistent. |
| Component geometry | Matching roles and size variants share heights, padding, icon alignment, and text styles. Functional differences use deliberate variants. |
| Actions | Keep related actions in one toolbar or panel when they fit. Keep document, view, and field controls near the object they affect. |
| Working space | Give the main task enough usable area. Size supporting chrome for its contents and reconsider separate strips that contain only one hint or secondary action. |
| Realistic content | Check long strings, empty and invalid fields, attachment states, narrow widths, and short viewport heights where relevant. |

Existing designs and project tokens take precedence. When spacing tokens are absent, the skill supplies a compact `4 / 8 / 16 / 24 / 32` px fallback mapped to layout roles.

For build and polish tasks, applicable checks are acceptance criteria: fix observed in-scope failures and reinspect affected scenarios before claiming completion. Review-only tasks report failures and concrete corrections. If visual inspection is unavailable, mark those checks as unverified.

## Reference

- **[ui-design](./skills/ui-design/SKILL.md)** — Main product UI design and implementation skill.
- **[anti-slop](./skills/ui-design/references/anti-slop.md)** — Diagnostic reference for generic AI-looking interface patterns.
- **[ui-review](./skills/ui-design/references/ui-review.md)** — Final quality gate for product fit, hierarchy, states, responsive behavior, accessibility, motion, and visual verification.

## How it works

```text
Understand the product
        ↓
Respect existing design authority
        ↓
Choose a visual thesis if needed
        ↓
Structure before decoration
        ↓
Define spacing, geometry, action locations + working space
        ↓
Implement states + responsive behavior
        ↓
Anti-slop check
        ↓
Render with realistic content and review
        ↓
Fix failed acceptance checks and reinspect
```

## Usage

Agents should be able to select the skill automatically for material UI work based on its description.

You can also invoke it explicitly:

```text
Use the ui-design skill to redesign this settings page without changing product behavior.
```

```text
Use ui-design to review this frontend for generic AI-looking patterns and fix the highest-impact issues.
```

```text
Use ui-design to clean up this editor: remove redundant explanatory text, unify spacing and control geometry, group document actions, and preserve useful preview space. Verify realistic field values and validation states at desktop and mobile widths.
```

```text
Build this page from the provided Figma. Treat the design as the source of truth and use ui-design for implementation quality and responsive behavior.
```

## Design authority

Follow applicable project instructions, including `AGENTS.md`, throughout. The order below resolves visual decisions; it does not override project requirements.

The skill follows this order when visual sources disagree:

1. user-provided design/specification;
2. project design system and tokens;
3. established product patterns;
4. project documentation and agent instructions;
5. the skill's own defaults.

It does not redesign supplied work unless redesign or critique was requested.

## Compatibility

The repository follows the Agent Skills directory convention used by the `skills` CLI. It contains no runtime dependencies and does not require a specific frontend framework.

## Repository structure

```text
ui-design-skill/
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
└── skills/
    └── ui-design/
        ├── SKILL.md
        └── references/
            ├── anti-slop.md
            └── ui-review.md
```

## Philosophy

Improve execution without imposing a universal style. Start with the product's task, preserve its design system, and fix structure before decoration. Popular visual patterns are useful when they have a concrete purpose.

## Acknowledgements

This project is informed by the broader public work around design-focused agent skills, including [Emil Kowalski's skills](https://github.com/emilkowalski/skills), [Anthropic's frontend-design skill](https://github.com/anthropics/skills), and [Vercel's agent skills](https://github.com/vercel-labs/agent-skills).

Those projects are not bundled here. `ui-design` is an independent skill with its own workflow and rules.

## License

[MIT](./LICENSE), copyright 2026 SpellbourneDZ.
