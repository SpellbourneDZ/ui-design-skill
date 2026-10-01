# Final UI review

Run this after material UI work. When the task allows edits, fix issues instead of only reporting them.

Use applicable items as acceptance criteria: fix observed in-scope failures and reinspect the affected scenarios before claiming completion. For review-only work, report the failures and their corrections. Mark unavailable visual checks as unverified.

## Product fit

- The surface's primary task is obvious.
- The first important decision or action has clear priority.
- The visual character fits the product rather than a generic template.
- Existing vocabulary and product conventions are preserved.

## Hierarchy and layout

- Major sections have deliberate hierarchy.
- Proximity groups related content before containers do.
- Alignment is consistent.
- Spacing uses the layout contract: equal relationships use equal tokens, and distinct hierarchy levels have deliberate gaps.
- Panel headings, fields, and action rows share the intended inset.
- Gaps between complete field groups match across inputs, uploads, and textareas, including help, counters, validation, and attachment actions.
- There is no accidental card-within-card nesting.
- Dense areas remain scannable.
- Empty space appears intentional rather than unfinished.
- The main task has enough working area; utility chrome is sized for its content, and single-purpose strips or panels have a functional reason to remain separate.

## Components and states

- Existing primitives are reused where appropriate.
- Matching component roles and size variants share heights, internal padding, and icon size/alignment; geometry exceptions have a functional reason and a shared variant.
- Hover, focus, active, and disabled states are intentional.
- Loading, empty, error, success, and validation states exist where relevant.
- Primary, secondary, and destructive actions are distinguishable.
- Same-scope actions occupy one predictable toolbar or panel when they fit; view and field actions remain close to their targets.
- Icons come from the project's established family when possible.

## Typography and copy

- Type roles form a clear hierarchy.
- Each repeated text role uses the same size, weight, and line-height combination.
- Body content remains readable at realistic widths.
- Sentence case follows project conventions.
- Labels are not duplicated unnecessarily.
- Each visible text block helps a decision, action, constraint, or meaningful state; remove those that fail this test.
- No stacked eyebrow/title/subtitle repeats one context, and no persistent prose narrates obvious editor mechanics.
- Necessary field labels, accessible names, recovery guidance, storage limitations, and consequential warnings survive copy reduction.
- CTA text describes the action.
- Empty and error copy help the user proceed.
- Numeric data is aligned and formatted deliberately when relevant.

## Color and surfaces

- Semantic colors use project tokens when available.
- Important content has sufficient contrast.
- Borders communicate structure rather than outlining everything.
- Shadows correspond to elevation, focus, or layering.
- Radius is consistent with component roles.
- Accent color is not scattered across unrelated elements.

## Responsive behavior

- Primary actions stay reachable on mobile.
- Action groups reflow or use accessible overflow without losing scope, order, or the primary action.
- Information order remains sensible after reflow.
- Desktop-only affordances have touch-friendly equivalents where needed.
- Long strings and narrow widths do not break the layout.
- Sticky and fixed elements respect safe areas and viewport constraints.
- The task remains usable at short viewport heights after headers, toolbars, and fixed panels take their space.
- Mobile is treated as a behavior/layout decision, not just a narrower desktop.

## Accessibility

- Semantic elements are used for interaction.
- Keyboard focus is visible.
- Controls are keyboard-operable where applicable.
- Interactive elements have accessible names.
- Color is not the only carrier of important state.
- Reduced-motion preferences are respected.
- Touch targets are appropriate for the platform.

## Motion

- Every motion effect has a purpose.
- Frequent actions feel immediate.
- No blanket `transition: all` is used.
- Decorative reveal animation is not repeated across every section.
- Enter and exit behavior preserves spatial logic.
- Animation does not delay keyboard-driven work.

## Anti-slop

- No unjustified gradient or glow.
- No automatic bento layout.
- No universal pill treatment.
- No unnecessary eyebrow labels.
- No arbitrary monospace metadata.
- No repeated identical cards where layout alone would work.
- No vague AI-marketing copy in ordinary product UI.
- At least one meaningful decision is specific to the product, task, or content.

## Visual verification

When rendering is available:

- inspect desktop;
- inspect mobile;
- compare against source design when provided;
- exercise the relevant realistic-content scenarios in [SKILL.md](../SKILL.md#13-visually-verify-material-ui-changes): long strings, empty/invalid fields, attachment states, and constrained viewport space;
- inspect neighboring fields with and without optional help, counters, validation, and attachment actions; compare the gap from each complete field to the next label;
- check that removing redundant text leaves orientation and necessary guidance intact, and that action groups fit with realistic labels;
- identify the most visible problems, correct observed in-scope failures, and reinspect affected scenarios before stopping.
