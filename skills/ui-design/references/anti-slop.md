# Anti-slop reference

Use this as a diagnostic reference, not as a universal ban list.

The key question is not whether a pattern is popular. Ask whether the choice is justified by this product, task, content, or design system.

## Common generated-interface tells

### 1. Cardification

Symptoms:

- nearly every section is placed inside the same rounded rectangle;
- cards are nested inside cards;
- border, radius, padding, and shadow stay identical across unrelated hierarchy levels;
- whitespace that could group content is replaced by containers.

Corrections:

- remove containers that do not communicate grouping, interaction, selection, or elevation;
- let page-level layout and spacing create structure;
- vary treatment according to semantic role rather than visual habit.

### 2. Decorative gradients and glow

Symptoms:

- blurred color orbs added behind content;
- gradient text on a heading without brand justification;
- random blue or purple glow behind dashboards;
- gradients introduced because the layout otherwise feels empty.
- glassmorphism added without a meaningful layered surface or a product convention.

Corrections:

- establish hierarchy through type, spacing, content, imagery, or product-specific visual material first;
- retain gradients only when they belong to the brand, data, state, or spatial model.
- use translucent surfaces only when layering helps orientation; preserve text contrast over realistic backgrounds.

### 3. Generic hero recipe

Symptoms:

- centered badge;
- oversized centered headline;
- muted explanatory paragraph;
- two rounded CTAs;
- floating product screenshot;
- gradient background.

Corrections:

- derive the opening composition from the product's actual subject, content, workflow, or signature interaction;
- show the characteristic thing instead of generic startup chrome.

### 4. Bento by reflex

Symptoms:

- features placed in an arbitrary mosaic;
- unrelated items receive equal visual weight;
- the grid exists to look designed rather than communicate a model or priority.

Corrections:

- use the sequence, comparison, workflow, hierarchy, timeline, or data relationship that actually fits the content.

### 5. Universal pill treatment

Symptoms:

- buttons, filters, badges, navigation, and inputs all use maximum radius;
- shape stops carrying semantic information because everything looks alike.

Corrections:

- use shape to distinguish roles and interaction patterns;
- inherit the product's geometry instead of defaulting every control to a capsule.

### 6. Excessive micro-labels

Symptoms:

- uppercase eyebrow text above most headings;
- tiny monospace labels used as atmosphere;
- artificial numbering where no real sequence exists;
- headings that repeat context already obvious from the layout.

Corrections:

- remove labels that do not help navigation, hierarchy, state, or meaning.

### 7. Fake sophistication

Symptoms:

- random monospace typography;
- arbitrary `01 / 02 / 03` numbering;
- unnecessary charts or statistics;
- technical vocabulary exposed to users for visual texture;
- punctuation used as decoration rather than language.

Corrections:

- get sophistication from clarity, behavior, precision, content, and product-specific detail.

### 8. Generic AI copy

Symptoms:

- vague words such as "Unlock", "Elevate", "Seamless", or "Powerful" inside ordinary utility UI;
- headings that do not describe a concrete object or outcome;
- repeated subtitle patterns;
- explanatory copy for controls whose meaning is already clear.

Corrections:

- use concrete nouns and verbs from the user's task;
- remove copy that does not change understanding or action.

### 9. Motion everywhere

Symptoms:

- every section fades upward;
- every card lifts or scales on hover;
- routine navigation waits for page transitions;
- looping decoration competes with content.

Corrections:

- keep motion for state change, feedback, spatial continuity, or explanation;
- reduce motion as interaction frequency increases.

### 10. Design-system amnesia

Symptoms:

- a new gray palette appears beside an existing one;
- a second modal, toast, or button primitive is introduced;
- arbitrary spacing values multiply;
- icon styles become inconsistent;
- nearly identical component variants accumulate.

Corrections:

- inspect and reuse the existing system before creating a new pattern.

### 11. Dashboard-by-default

Symptoms:

- metrics are promoted into large stat cards whether or not they drive decisions;
- a sidebar is added to a product that has only a few destinations;
- charts are shown because dashboards are expected to have charts;
- page structure follows an admin template rather than the workflow.

Corrections:

- design around the user's decision or sequence of work;
- introduce navigation, metrics, and visualization only when they reduce cognitive or operational cost.

### 12. Decorative emptiness

Symptoms:

- large blank regions are filled with illustration, glow, slogans, or cards because the composition feels sparse;
- visual filler gets added instead of reconsidering density and information architecture.

Corrections:

- decide whether the surface should actually be sparse;
- if not, fix structure or content rather than decorating the absence of it.

## Distinctiveness test

Before finalizing a new surface, ask:

- If the logo and product name disappeared, would the structure or interaction still reveal what kind of product this is?
- Is hierarchy derived from the user's task or from a familiar template?
- What is the most product-specific visual or interaction decision on this surface?
- Which decoration could disappear without losing meaning?
- Did the implementation create a new pattern where an established project pattern already existed?

If the interface could plausibly belong to almost any SaaS product, revisit the visual thesis, content structure, or interaction model before adding more polish.
