# Final UI review

Run this after material UI work. When the task allows edits, fix issues instead of only reporting them.

## Product fit

- The surface's primary task is obvious.
- The first important decision or action has clear priority.
- The visual character fits the product rather than a generic template.
- Existing vocabulary and product conventions are preserved.

## Hierarchy and layout

- Major sections have deliberate hierarchy.
- Proximity groups related content before containers do.
- Alignment is consistent.
- Spacing follows a visible rhythm.
- There is no accidental card-within-card nesting.
- Dense areas remain scannable.
- Empty space appears intentional rather than unfinished.

## Components and states

- Existing primitives are reused where appropriate.
- Hover, focus, active, and disabled states are intentional.
- Loading, empty, error, success, and validation states exist where relevant.
- Primary, secondary, and destructive actions are distinguishable.
- Icons come from the project's established family when possible.

## Typography and copy

- Type roles form a clear hierarchy.
- Body content remains readable at realistic widths.
- Sentence case follows project conventions.
- Labels are not duplicated unnecessarily.
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
- Information order remains sensible after reflow.
- Desktop-only affordances have touch-friendly equivalents where needed.
- Long strings and narrow widths do not break the layout.
- Sticky and fixed elements respect safe areas and viewport constraints.
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
- test realistic content extremes;
- identify and fix the three most visible problems before stopping.
