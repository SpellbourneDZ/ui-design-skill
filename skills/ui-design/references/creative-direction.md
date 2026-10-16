# Product-specific creative direction

Use this reference when the request involves a **new visual direction**, a significant redesign, an expressive product experience, or a complaint that an interface looks generic. For faithful Figma implementation, routine component changes, accessibility fixes, and small layout corrections, use the existing design authority and ordinary `ui-design` workflow instead.

This is a concept-generation and judgment layer, **not** a replacement for the core layout, copy, state, component, responsive, and visual-review rules in [SKILL.md](../SKILL.md).

## The UI concept loop

### 1. Locate the real product signal

Identify the user's main job, the screen's signature content or artifact, the strongest brand cue already available, and the action that matters most. Distinctiveness should come from these, not from random colors or effects.

### 2. Consider three fundamentally different organizing ideas

Privately explore three ways to make the UI specific to this product:

- **Content as identity:** the itinerary, document, map, product, preview, or dataset itself drives composition.
- **Workflow as form:** a true sequence, relationship, comparison, or spatial model informs grouping, navigation, or transitions.
- **One signature moment:** one piece of brand character, revealing interaction, or distinctive data/typographic treatment supports the product story.

These are categories, not recipes. For each candidate, explain in one sentence how the concept helps a **specific user task**. If the explanation is only a mood or a styling choice, revise it.

### 3. Reject generic or costly concepts

Question each idea:

- Would it still make sense for an unrelated SaaS product after replacing the logo and copy?
- Does it make a user action, choice, hierarchy, or relationship easier to understand?
- Does it fit existing Figma, brand assets, tokens, and product patterns?
- Will it survive real content, narrow mobile layouts, long translations, and short viewports?
- Can it preserve accessible controls, keyboard use, focus visibility, readable contrast, and reduced motion?
- Is the novelty worth its learning curve and engineering/performance cost?

The best answer may be a quiet, conventional interface. Do not add a motif just to pass the distinctiveness test.

### 4. Commit to one practical visual thesis

The selected direction should identify:

1. **Concept:** one sentence tying visual direction to domain and task.
2. **Hierarchy:** which content dominates and which actions remain immediate.
3. **Visual decisions:** role-based typography, density, layout, surfaces, color use, imagery, and tokens.
4. **Signature expression:** at most one justified high-impact moment, if appropriate.
5. **Interaction:** states, feedback, and recovery.
6. **Responsive behavior:** what reorders, compresses, collapses, or stays persistent.

A concept can be expressed without any visual effects. Do not make typography, oversized numbers, card shapes, gradients, glass, or motion the idea itself.

## Expression budget by screen type

| Screen | Guidance |
| --- | --- |
| Landing / campaign | Allow more expressive composition while keeping the real offer and CTA legible. |
| Onboarding / empty state | Use illustration or motion when it helps meaning, guidance, or character. |
| Core product workflow | Favor clarity, accessible affordances, efficient actions, and recognizable content. |
| Editors / forms / dashboards | Treat working space, data relationships, and meaningful information hierarchy as the art direction. |
| Critical actions | Favor predictability, confirmation, state clarity, and recovery over novelty. |

A distinctive landing page should not turn every internal settings screen into a poster.

## Cross-check with UI craft

Keep the implementation requirements from the main skill: structural hierarchy before decoration; reusable components; meaningful copy; consistent spacing by role; realistic data, empty/error/loading states; responsive behavior; semantic controls; and visual inspection.

No category bans: cards, bento layouts, bright colors, glass, gradients, and 3D are acceptable when they are defensible **product decisions**, not defaults.

Before finishing, ask: **Does the signature treatment earn its space by improving product comprehension, clarity, confidence, or brand fit?** If not, remove it.

## Output

When building, implement the selected idea and verify actual screens rather than only pitching a concept. When brainstorming, briefly state the proposed concept and why it fits; show multiple directions only if the user asks for options. When reviewing, give concrete issue → impact → correction guidance.

The optional companion `ui-art-direction` skill in this repository expands this concept loop into a full art-direction workflow. This reference remains self-contained so `ui-design` still works when installed alone.

### Background

The concept-first / anti-template approach was informed in part by [TrueSpace's Anti-Slop Design Director](https://truespaceai.ru/design/). These are original UI/UX-specific rules, not the source's graphic-design prompt or its stylistic bans.
