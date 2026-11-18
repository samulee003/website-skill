# Responsive and Content Resilience

Use this reference when choosing layout rules, building a page that must work across device sizes, or checking a design that looks correct only at its reference viewport.

## Let content and containers set the rules

- Start with the narrow, fully functional layout. Add a breakpoint only when content or task density requires a structural change; do not treat device names as layout rules.
- Prefer intrinsic sizing, Grid/Flex, `minmax()`, `min-width: 0`, `max-width`, fluid type, and container-aware logic over fixed widths and JavaScript viewport measurement.
- Let reusable components respond to their available container when possible. A card in a sidebar, dialog, or embedded panel may be narrower than the viewport suggests.
- At each structural change, define what reorders, stacks, wraps, scrolls, becomes a different control, or is intentionally hidden. Do not merely shrink desktop values.
- Preserve the same content meaning and action order across viewports. If dense content must scroll in two dimensions, name the exception, provide a usable label/instruction, and ensure the scroll region itself is operable.

## Test a viewport matrix

At minimum, test:

| Range | Example check |
|---|---|
| Narrow mobile | 320–375 CSS px; text wraps, controls fit, no unintended horizontal scroll |
| Larger mobile | portrait/landscape, dynamic browser chrome, safe-area insets, on-screen keyboard |
| Tablet | compact navigation, multi-column transitions, touch targets |
| Desktop | reference width around 1366 CSS px; visual hierarchy and dense layouts |
| Ultra-wide | constrained content width, balanced whitespace, no stretched paragraphs |
| Intermediate width | drag continuously or test a breakpoint-adjacent value to catch gaps |

Use the project's actual browser support and design constraints; these are representative checks, not a claim that every exact size is universally required.

## Stress realistic content and states

Test with:

- Long headings, button labels, validation messages, URLs, and translated strings.
- Different date/number/currency formats and large values.
- Empty, sparse, typical, dense, loading, error, and success data.
- Multiple locales and right-to-left direction when supported.
- Larger user text and browser zoom; do not disable zoom.
- Dynamic viewport height, safe areas, keyboard opening, and rotation on mobile.

Avoid fixed heights that clip content. Define whether text wraps, truncates with an accessible full value, or expands; never assume placeholder copy is the final maximum length. Skeletons should match the geometry of the eventual content to avoid layout shift.

## Responsive page patterns

- **Navigation**: preserve access to primary destinations; any collapsed menu must be operable by keyboard and touch, announce expanded state, and manage focus correctly.
- **Forms**: use readable single-column grouping on narrow widths, correct input types and autocomplete, and keep labels/errors visible with the software keyboard open.
- **Pricing**: make plan and billing selection explicit; stack readable plan summaries or provide an accessible selector instead of squeezing comparison columns into tiny text.
- **Tables/data**: preserve headers and relationships; when horizontal scrolling is necessary, expose it as a clearly named region, retain keyboard access, and do not hide critical columns without an alternative.
- **Hero/media**: keep the primary promise and CTA visible, choose responsive sources/aspect ratios, and preserve a useful focal point when cropping.
- **Sticky/fixed UI**: account for focus visibility, browser chrome, safe areas, zoom, and the fact that an overlay can obscure content or error messages.

## Responsive acceptance

A page passes when the primary task works at narrow, intermediate, and wide sizes; information order remains clear; text and controls are not clipped or covered; there is no unintended horizontal overflow; and responsive changes do not remove keyboard, screen-reader, or reduced-motion support.

Useful reference: [Tailwind CSS responsive design and container queries](https://tailwindcss.com/docs/responsive-design).
