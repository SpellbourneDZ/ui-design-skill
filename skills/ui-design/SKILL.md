---
name: ui-design
description: Design, build, redesign, polish, or review product UI with a product-specific visual direction and a high craft bar. Use for frontend pages, components, dashboards, forms, responsive web surfaces, design-system work, screenshot or Figma-driven implementation, UI cleanup, interaction and animation decisions, or whenever an interface risks looking generic, templated, or AI-generated. Skip for backend-only work or mechanical frontend changes that do not materially affect the user experience.
---

# UI Design

Act as a product-minded design engineer, not a generic interface generator.

The goal is not to make a screen merely look polished. Make it feel intentional, specific to the product, coherent with the existing system, and complete across states and breakpoints.

## 1. Establish design authority

Follow applicable project instructions, including `AGENTS.md`, throughout. The order below resolves visual decisions; it does not override project requirements.

Before changing UI, use this order of authority:

1. User-provided Figma, screenshots, specifications, or explicit visual instructions.
2. Existing project design system, tokens, components, and visual language.
3. Product patterns already used consistently in the codebase.
4. Project documentation such as `AGENTS.md`, `DESIGN.md`, component docs, or frontend conventions.
5. This skill's defaults when no stronger direction exists.

Do not replace a provided design with your own taste unless the user explicitly asks for redesign or critique.

If the project defines a fallback design system, use it. If it does not, do not silently introduce a new one just because it is familiar.

## 2. Understand the product before styling

Before material UI work, determine from the brief, code, docs, screenshots, or existing product:

- what the product does in plain language;
- who the primary user is;
- the main task on the current surface;
- the first decision or action the user should understand;
- what success looks like;
- important empty, loading, error, disabled, and recovery states;
- the product temperament: utilitarian, calm, premium, playful, dense, editorial, technical, or another specific direction;
- vocabulary already used by the product;
- components and tokens that should be reused.

Infer these from available context when the answers are clear. Do not turn obvious context into ceremonial discovery questions.

## 3. Choose a visual thesis when direction is missing

If no design direction is already specified, form a compact visual thesis before implementing substantial new UI.

A useful thesis covers:

- visual character;
- dominant hierarchy principle;
- intended density;
- typography behavior;
- surface, border, and elevation behavior;
- motion temperament;
- at most one memorable visual idea.

Example:

`Calm utilitarian finance UI with dense information, strong numeric hierarchy, flat surfaces, restrained borders, and motion used only to explain state changes.`

Do not begin with effects such as gradients, glass, large radii, or shadows. Begin with the product and task.

## 4. Run the anti-slop gate

Read [references/anti-slop.md](references/anti-slop.md) before accepting a substantial new visual direction or when reviewing UI that feels generic.

A useful test: if a visual decision could move unchanged into several unrelated SaaS products, it may be a template habit rather than a product decision.

Do not mechanically ban popular styles. Cards, gradients, glass, pills, bento layouts, dark themes, serif type, bold radii, and expressive motion can all be correct when the product or design system gives them a reason to exist.

## 5. Structure before decoration

Resolve these in roughly this order:

1. information hierarchy;
2. grouping and proximity;
3. alignment;
4. spacing rhythm;
5. content density;
6. primary and secondary actions;
7. responsive behavior;
8. interaction and system states;
9. accessibility;
10. visual expression.

Do not use decoration to compensate for unclear structure.

## 6. Build components for real behavior

Prefer established project components over bespoke replacements.

When creating or changing components:

- support realistic content ranges, not only demo data;
- include hover, focus-visible, active, disabled, loading, error, success, and empty states where relevant;
- preserve semantic HTML and keyboard behavior;
- keep touch targets appropriate for the platform;
- express differences through existing tokens and component APIs when possible;
- do not hand-roll mature primitives when an established project dependency already solves the problem;
- do not add a dependency for a trivial behavior that CSS or existing code already handles well.

When several component APIs are plausible, prefer the smallest coherent system.

## 7. Treat typography as structure

- Follow the project's type system when it exists.
- Do not add a typeface merely to make the interface feel designed.
- Prefer sentence case unless the product language says otherwise.
- Create hierarchy through type size, weight, spacing, contrast, and placement before adding extra labels.
- Avoid decorative eyebrow labels and arbitrary monospace metadata.
- Keep long-form text readable.
- For data-heavy products, handle numeric alignment, units, precision, and tabular figures deliberately.

## 8. Use color, surfaces, and elevation semantically

- Use semantic tokens when available.
- Color should communicate hierarchy, state, brand, or meaning.
- Borders should separate or group something, not outline every rectangle by reflex.
- Shadows should communicate elevation or focus, not decorate every container.
- Radius should reflect component role and product language rather than one universal value.
- Do not create a second near-identical neutral palette inside an existing system.
- Keep state colors consistent across surfaces.

## 9. Design responsive behavior, not just smaller screenshots

- Preserve the primary task and important context across breakpoints.
- Do not simply stack every desktop panel vertically and call it mobile.
- Decide what reorders, collapses, becomes sticky, moves into a sheet or menu, or can disappear.
- Avoid controls that are unnecessarily full-width on large screens or unusably compressed on small screens.
- Test realistic long labels, validation messages, empty values, and dense content.

## 10. Use motion as feedback and explanation

Before adding animation, ask:

1. Does the change need animation?
2. What does the motion explain or confirm?
3. How often will the user see it?
4. Can CSS handle it simply?
5. Does it respect reduced-motion preferences?

Prefer immediate feedback for direct manipulation and short, restrained transitions for frequent actions. Reserve expressive motion for rare or meaningful moments.

Avoid:

- `transition: all`;
- animating every card or section on page load;
- repeated fade-and-slide reveals without a product reason;
- slow animation on high-frequency actions;
- motion that delays keyboard workflows;
- scale-from-zero entrances for ordinary UI;
- animation whose only purpose is to make the screen feel more designed.

## 11. Treat copy as part of the interface

Use product vocabulary rather than implementation vocabulary.

- CTA labels should name the real action.
- Keep the same action name across buttons, results, toasts, and history when possible.
- Empty states should help the user move forward.
- Error messages should explain recovery when possible.
- Avoid marketing language inside utility surfaces unless the product requires it.
- Do not add filler headings or subtitles only to balance a composition.

If the project has a dedicated writing skill, use it for longer copy while preserving the product vocabulary established here.

## 12. Keep implementation disciplined

While coding:

- reuse existing tokens and primitives;
- preserve architectural conventions unless they prevent the requested result;
- keep visual constants centralized where the project already centralizes them;
- avoid repeated magic numbers;
- do not refactor unrelated code under the label of UI polish;
- do not replace working interaction behavior merely to simplify styling;
- keep DOM structure semantic and reasonably shallow;
- verify that visual work does not regress forms, loading, errors, keyboard use, or mobile behavior.

## 13. Visually verify material UI changes

Do not stop at a successful build when rendering or browser inspection is available.

For material UI changes:

1. render the changed surface;
2. inspect a primary desktop width;
3. inspect a realistic mobile width;
4. compare with source Figma or screenshots when provided;
5. identify the three most visible weaknesses;
6. fix them;
7. run [references/ui-review.md](references/ui-review.md).

If rendering or browser inspection is unavailable, perform the checks that are possible and state which visual checks remain unverified. Do not claim a visual review from a successful build alone.

Prefer one meaningful correction pass over adding more decoration.

## 14. When existing UI looks AI-generated

Do not repaint it first. Diagnose in this order:

1. hierarchy;
2. excessive containerization;
3. spacing rhythm;
4. typography;
5. primary action clarity;
6. repetitive component geometry;
7. decorative effects;
8. generic copy;
9. purposeless motion.

Fix the earliest structural problem that explains the largest amount of visual noise.

## 15. Final response

For build tasks, summarize meaningful UI decisions and important tradeoffs rather than narrating every CSS edit.

For review tasks, order findings by impact. Each finding should identify:

- what is wrong;
- where it appears;
- why it hurts the experience;
- the concrete correction.
