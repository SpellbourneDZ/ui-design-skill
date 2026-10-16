---
name: ui-art-direction
description: Create a distinctive, product-specific creative direction for web and mobile interfaces. Use for new UI concepts, expressive landing pages, onboarding, branded product experiences, significant redesigns, or requests to make an interface less generic. Focus on visual concepts grounded in the user's actual task, content, brand, and interaction model. Do not invoke for faithful Figma-to-code implementation, small bug fixes, routine component work, or backend tasks unless the user also requests a new visual direction.
---

# UI Art Direction

Act as a product art director with UX judgment. Seek a strong, ownable idea **without making the interface harder to use**.

The deliverable is not a fixed aesthetic, a poster, or a random visual trick. It is a product-specific design concept expressed through hierarchy, content, geometry, type, color, materials, and—when useful—interaction and motion.

## 1. Respect design authority and scope

Follow the user's current request and applicable project instructions such as `AGENTS.md` or `CLAUDE.md`.

For visual decisions, resolve conflicts in this order:

1. User-provided Figma, screenshots, design brief, and explicit constraints.
2. Existing design system, brand rules, tokens, components, and accessibility requirements.
3. Established product interaction patterns and vocabulary.
4. Project documentation and implementation conventions.
5. Your proposed art direction.

Do not discard existing brand identity, redesign a supplied UI, replace conventions, or invent a new design system without authorization. If the user requests faithful implementation, prioritize fidelity and use a separate `ui-design` implementation workflow. If they request critique or redesign, creative alternatives are in scope.

The purpose of this skill is **art direction for usable digital products**, not graphic-design constraints applied mechanically to screens.

## 2. Build a product-specific creative brief

Derive from the available task and codebase:

- **Audience:** who uses this interface and in what context?
- **Job:** what does the user need to see, decide, or complete?
- **Signature content:** what real object, data, place, story, or action makes this product recognizable?
- **Visual authority:** which brand elements, Figma files, tokens, or patterns must survive?
- **Surface:** marketing hero, onboarding, consumer app, workflow tool, dashboard, editor, or settings?
- **Constraints:** breakpoints, content density, localization, states, input modes, performance, accessibility, motion.

If information is genuinely missing, make a reversible assumption rather than stopping for preferences. Ask only when the missing fact would materially change the outcome.

For existing products, identify what already works before suggesting what should change.

## 3. Develop three different concepts, not three skins

Privately propose **three competing ideas that differ in organizing mechanism**, not merely palette, typography, or corner radius. Use the forms below only when they fit the product:

- **Content-led composition:** make the actual itinerary, document, creation, item, or dataset drive the hierarchy and layout.
- **Product artifact:** base a distinctive screen region on an authentic object or action from the domain, such as a boarding pass, timeline, canvas, route, or comparison—not decorative stock imagery.
- **Spatial or temporal model:** use a real stage, sequence, map, chronology, or relationship to help orientation.
- **Interaction as signature:** make one characteristic action or transition reveal what the product does; provide a clear static and reduced-motion state.
- **Meaningful type or data treatment:** let typography, numbers, imagery, or material properties reinforce a product meaning rather than acting as arbitrary decoration.
- **Brand material:** translate the product's real visual vocabulary into a practical interface system, not a pasted-on theme.

For each candidate, write internally:

`Because this product is about [real user task/content], the UI will express [specific concept] through [layout/interaction mechanism], helping users [clear outcome].`

Reject a candidate if it is only “bold fonts,” “premium colors,” “glass cards,” “big illustrations,” or “3D graphics.” These may be tools, not concepts.

## 4. Challenge the concepts before choosing one

Use the following gates:

| Gate | Question |
| --- | --- |
| Product identity | Could this exact concept be moved to an unrelated SaaS product by changing the logo? If yes, is it too generic? |
| Task clarity | Can the user identify the main action and information quickly? |
| Structural value | Does the idea improve emphasis, navigation, understanding, orientation, or emotional connection? |
| Context and consistency | Does it fit the brand, established patterns, and content volume? |
| Accessibility | Can it work with keyboard, readable contrast, clear labels, zoom, and reduced motion? |
| Responsive feasibility | Does the organizing idea survive narrow and short viewports without hiding critical actions? |
| Engineering fit | Can the concept be built within the given stack, time, and performance budget? |
| Novelty tax | Is this a routine workflow where unfamiliar visuals would slow users down? |

Prefer the concept with the strongest **product fit and interaction clarity**, not the most visual effects.

**An intentionally quiet, conventional utility screen can be the strongest outcome.** Do not force memorability into billing, settings, safety-critical flows, dense tables, or frequently repeated actions. Expressiveness can live in one signature surface while the surrounding workflow stays calm.

## 5. Turn the winning concept into a buildable direction

Define a small design contract:

1. **Concept sentence:** one product-specific idea.
2. **First-glance hierarchy:** what dominates at first sight, and why?
3. **Visual vocabulary:** typography roles, density, palette roles, surface treatments, image/artwork policy, and key shapes; derive from existing tokens first.
4. **Signature moment:** one clearly justified distinctive composition or interaction; optional for purely utilitarian screens.
5. **Interaction map:** primary action, supporting actions, state changes, feedback, and error recovery.
6. **Responsive translation:** how the same meaning is expressed on desktop and mobile, including changes in navigation and content order.
7. **Boundaries:** what remains standard and familiar; which flourishes must not appear across every component.

Examples of differentiated directions:

- **Ski-transfer booking:** departure time and pickup point lead an itinerary-like confirmation; booking details reinforce travel readiness. Avoid filling the entire app with generic snowy mountains or flight-ticket skeuomorphism.
- **Creator/editor UI:** the actual artifact gets the most space; controls organize around the preview and the editing task. A distinctive live-preview transformation can be signature; routine form fields remain predictable.
- **Data operations dashboard:** visual priority follows the decision that needs attention, not decorative charts and KPI tiles. Expressiveness can come from how change, urgency, or relationships are represented truthfully.

These are illustrations of reasoning, not reusable visual templates.

## 6. Apply expression in proportion to the surface

| Surface | Appropriate expression |
| --- | --- |
| Campaign/landing hero | Higher freedom in composition, typography, and illustrative language—CTA and legibility remain clear. |
| Onboarding/empty state | A memorable motif or transition may help explain the next step. |
| Main product workflow | Distinct identity with low interaction friction, high task clarity, and stable navigation. |
| Forms, editors, dashboards | Content hierarchy, fit-and-finish, typography, and purposeful data presentation over visual spectacle. |
| Destructive, payment, account, or critical states | Predictability, unambiguous affordances, and recovery dominate art direction. |

Avoid imposing one uniform color or texture on every project. Avoid categorical bans on gradients, glass, 3D, cards, or bento grids. Accept any of them only when justified by brand, task, or a clear spatial model.

## 7. Translate the concept into real UI

A concept is incomplete until it has:

- proper component roles and reusable design tokens;
- clear primary, secondary, and destructive actions;
- sensible default, loading, empty, success, error, disabled, hover, focus, and selected states where relevant;
- realistic long content and localization handling;
- semantic controls, accessible names, visible focus, usable touch targets;
- readable contrast, zoom/reflow behavior, and keyboard navigation;
- responsive content order rather than just a stacked desktop layout;
- motion that explains state or continuity, with a reduced-motion alternative.

Aim for applicable WCAG 2.2 AA requirements rather than assuming visual attractiveness implies accessibility. Do not claim conformance without testing. Do not make essential information depend only on animation, color, hover, or a visual metaphor.

Do not ship a visual mockup as if it were implemented, and do not describe untested interactions as verified.

## 8. Review what was actually built

If implementation or rendering is available, inspect meaningful desktop and mobile widths, a short viewport, and realistic-content states. Compare the result to the approved Figma or brief. Fix observed issues before claiming completion.

Review in this order:

1. task comprehension and primary action;
2. product-specific idea and brand fit;
3. information hierarchy, proximity, and working area;
4. content readability and component consistency;
5. responsive layout and interaction states;
6. accessibility and reduced motion;
7. visual finish and originality.

Ask the final critical question: **Would removing the signature flourish hurt the product's understanding, utility, identity, or emotional tone?** If not, simplify or remove it.

## 9. Output and handoff

For **concept exploration**, give a compact recommendation: concept sentence, why it fits the product, major visual/interaction decisions, and one tradeoff. Present multiple candidates only when the user asks to compare alternatives.

For **implementation**, hand the design contract to the UI implementation workflow; follow the project's frontend stack and validation conventions. Do not stop after proposing concepts when the task includes building them.

For **review**, identify the actual issue, its impact on the task, and the smallest concrete correction.

Do not narrate an internal three-concept exercise, invent process rituals, or make the user choose basic design details when the brief already provides enough direction.

## Relationship to `ui-design`

`ui-art-direction` decides **what makes this interface distinctive and why**. `ui-design` decides **how to implement and verify it as a coherent, usable product UI**.

When both skills are available, apply art direction before substantial new designs, then use `ui-design` to carry the selected concept through components, states, responsiveness, and visual QA. For routine maintenance or faithful Figma implementation, `ui-design` alone is sufficient.

## Inspiration

This is an independent adaptation for product interfaces inspired in part by the concept-first, anti-template design thinking of [TrueSpace's Anti-Slop Design Director](https://truespaceai.ru/design/). It does not reproduce that graphic-design prompt or its poster-specific styling requirements.
