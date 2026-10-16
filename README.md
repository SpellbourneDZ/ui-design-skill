# UI Design Skill

A product-minded UI design skill for AI coding agents.

It helps agents build interfaces that feel intentional and product-specific instead of converging on the same generic AI-generated patterns: nested cards, decorative gradients, oversized pills, arbitrary bento grids, vague copy, and motion added for decoration.

The core skill treats UI work as a sequence of product understanding, hierarchy, visual direction, implementation, and visual review.

**New:** `ui-art-direction` is an optional companion skill for distinctive concepts and substantial visual redesigns. It adapts concept-first anti-template thinking to *real product interfaces*, balancing visual identity with UX, accessibility, responsive behavior, and implementation feasibility. `ui-design` also includes a smaller creative-direction reference, so it works independently.

## Install

Use Node.js 22.20.0 or newer for the current `skills` CLI.

The repository contains two skills:

- `ui-design`: product UI implementation, components, states, responsive behavior, and review.
- `ui-art-direction`: concept-first, product-specific visual direction for new interfaces and substantial redesigns.

Both follow the Agent Skills `SKILL.md` format and can be installed in **Claude Code** and **Codex**. No separate Claude-specific package is needed.

### Claude Code

Install **both skills** in the current project:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design --skill ui-art-direction -a claude-code -y
```

Install both **globally** for Claude Code (all your local projects):

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design --skill ui-art-direction -a claude-code -g -y
```

Install only the core UI skill:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design -a claude-code
```

Install only the art-direction skill:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-art-direction -a claude-code
```

With the CLI's default project scope, Claude Code finds the skills in `.claude/skills/`. With `-g`, the target is `~/.claude/skills/`.

### Codex

Install both skills in the current project:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design --skill ui-art-direction -a codex -y
```

Install both globally for Codex:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design --skill ui-art-direction -a codex -g -y
```

### Claude Code + Codex

Install both skills for **both agents**, globally, with one command:

```bash
npx skills@latest add SpellbourneDZ/ui-design-skill --skill ui-design --skill ui-art-direction -a claude-code -a codex -g -y
```

Remove `-g` to install within the current project instead. `-y` skips installation prompts.

Verify the installation with:

```bash
npx skills@latest ls -a claude-code -a codex
```

These flags and installation paths are documented by the [skills CLI](https://github.com/vercel-labs/skills#options).

## Why use it?

Coding agents can build functional interfaces quickly, but without strong constraints they often converge on familiar visual recipes instead of making decisions from the product itself.

`ui-design` adds a design-engineering layer that asks the agent to:

- understand the product, user, task, and existing design language before styling;
- respect Figma, screenshots, existing components, and tokens as sources of truth;
- define a compact visual thesis when no design direction exists;
- explore genuinely different product-grounded concepts for expressive new designs without forcing decorative novelty into utility workflows;
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
- **[ui-art-direction](./skills/ui-art-direction/SKILL.md)** — Optional concept-first art direction for distinctive product interfaces.
- **[anti-slop](./skills/ui-design/references/anti-slop.md)** — Diagnostic reference for generic AI-looking interface patterns.
- **[creative-direction](./skills/ui-design/references/creative-direction.md)** — Lightweight concept exploration embedded in `ui-design` when installed alone.
- **[ui-review](./skills/ui-design/references/ui-review.md)** — Final quality gate for product fit, hierarchy, states, responsive behavior, accessibility, motion, and visual verification.

## How it works

```text
Understand the product
        ↓
Respect existing design authority
        ↓
Explore product-grounded concepts when needed
        ↓
Choose a visual thesis
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

For concept-first work, use the companion skill explicitly:

```text
Use ui-art-direction to create a distinctive visual direction for this booking experience. Keep the existing design tokens and make the primary flow easy to use. Then apply ui-design during implementation.
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

The repository follows the Agent Skills directory convention used by the `skills` CLI and is compatible with Claude Code and Codex. Claude Code can load skills from `.claude/skills/` (project) or `~/.claude/skills/` (global). The skills contain no runtime dependencies and do not require a specific frontend framework. Agent instructions such as `CLAUDE.md` or `AGENTS.md` remain authoritative.

## Repository structure

```text
ui-design-skill/
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
└── skills/
    ├── ui-art-direction/
    │   └── SKILL.md
    └── ui-design/
        ├── SKILL.md
        └── references/
            ├── anti-slop.md
            ├── creative-direction.md
            └── ui-review.md
```

## Philosophy

Improve execution without imposing a universal style. Start with the product's task, preserve its design system, and fix structure before decoration. Popular visual patterns are useful when they have a concrete purpose.

## Acknowledgements

This project is informed by the broader public work around design-focused agent skills, including [Emil Kowalski's skills](https://github.com/emilkowalski/skills), [Anthropic's frontend-design skill](https://github.com/anthropics/skills), and [Vercel's agent skills](https://github.com/vercel-labs/agent-skills).

The concept-first direction also draws inspiration from [TrueSpace's Anti-Slop Design Director](https://truespaceai.ru/design/), adapted for interactive, accessible UI rather than graphic design.

Those projects are not bundled here. The skills in this repository have their own independent workflow and rules.

## License

[MIT](./LICENSE), copyright 2026 SpellbourneDZ.
