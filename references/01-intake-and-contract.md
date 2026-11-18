# Intake and Design Contract

Use this reference before creating, implementing, or reviewing a web experience. The purpose is to turn an ambiguous request into a bounded, testable contract without slowing down on choices that can be safely inferred.

## Inspect the context first

- Identify the requested mode: create, implement a supplied reference, improve, or review/audit.
- Inspect the existing routes, framework, rendering model, styling system, tokens, shared components, asset conventions, content/data model, and available test/build commands.
- Identify what is in scope, shared dependencies that may be affected, immutable APIs, existing brand guidance, supported languages/locales, and required browsers or input methods.
- For implementation from a design, record the design version, reference viewport, key measurements, exact content, asset sources, and any known intentional deviations.
- For review, establish the base/head or other comparison baseline, read the complete relevant diff including deleted lines, and expand shared-token changes to their consumers.

Do not introduce a new framework, CSS system, package, or architecture before checking whether the existing project already provides the needed capability. Ask only when a missing choice blocks safe execution or would materially change the result; otherwise state a reasonable assumption and proceed.

## Write a one-page contract

Capture the following in a short working note. Keep it close to the task artifacts when appropriate; do not create a report file unless one is requested.

| Field | What to specify |
|---|---|
| Audience and context | Who is using this, where, and with what knowledge or constraints? |
| Primary task | What is the most important action or answer the interface must enable? |
| Success signal | What observable behavior proves the task succeeded? |
| Primary CTA | What is the single main next step, and what happens after activation? |
| Brand direction | Personality, emotional register, trust signals, and two or three specific visual cues. |
| Content and evidence | Required sections, real copy/data/assets, sources of claims, and unavailable facts. |
| Constraints | Existing stack, browser support, performance, brand/legal rules, delivery scope, and deadlines. |
| Accessibility target | Default to WCAG 2.2 AA unless the user or product specification sets a higher target. |
| Validation | Routes, widths, input modes, states, assistive technology, build checks, and visual evidence needed. |
| Out of scope | Explicitly name adjacent systems or changes that must remain untouched. |

Replace vague adjectives with observable outcomes. Examples:

- “Premium” → restrained palette with one accent, deliberate type scale, aligned grid, consistent spacing, authentic evidence, and no unmotivated decoration.
- “Modern” → name the relevant behaviors, e.g. fluid layout, clear focus, responsive navigation, persistent shareable filters, and reduced-motion-safe transitions.
- “Beautiful” → specify hierarchy, typography, image treatment, whitespace, contrast, and the evidence by which the result will be judged.

## Set the review boundary

For code review, label each finding:

- **Introduced**: directly caused by the current change.
- **Regression**: a previously working behavior is now broken.
- **Pre-existing**: visible in the baseline and not caused by the change.

Report pre-existing issues separately; do not silently broaden a scoped fix. For a shared token or primitive, trace at least its direct consumers and rerun their relevant checks.

## When information is missing

1. Separate blocking unknowns (e.g. required legal copy, actual pricing, supported browser, irreversible architectural choice) from non-blocking preferences (e.g. exact radius, icon stroke, breakpoint value).
2. Use project conventions, content needs, and inclusive behavior for non-blocking choices.
3. Use clearly labeled placeholder content for unknown facts; do not invent claims, prices, testimonials, certifications, or metrics.
4. Ask a concise question only if no safe default exists and the answer would materially change scope, user trust, or implementation.
5. Record assumptions and remaining unknowns in the delivery note.

## Contract quality check

Before implementation, confirm that a reviewer can answer in one pass: who is the user, what is their main task, what must be visible first, what is the primary action, what makes this experience distinct, which constraints are fixed, and how will success be tested? If not, refine the contract before polishing visuals.
