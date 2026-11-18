# Tokens and Components

Use this reference when creating a design system, extending an existing system, translating a visual direction into code, or reviewing consistency across pages.

## Token layers

Use a small, explicit token model. Names should express role and state, not the current appearance.

1. **Reference/primitive**: finite raw values such as palette steps, spacing steps, type sizes, radii, elevation, and motion durations.
2. **Semantic/system**: purpose-based aliases such as `surface.canvas`, `content.primary`, `border.subtle`, `action.primary`, `state.negative`, `focus.ring`, `space.section`, and `type.body`. Components should primarily use this layer.
3. **Component**: local values only when a component contract truly needs them, e.g. `button.primary.min-height`. Do not create a component token for every one-off page difference.

For each token, record name, type, value or alias, intended use, supported states/themes, and owner. Keep the source of truth framework-neutral when the project needs multiple outputs; map it to the existing implementation (CSS custom properties, JSON, native platform constants, etc.).

## Establish a bounded visual system

Define only the decisions needed for the task:

- Typography roles: display, heading, body, label, caption, and code as applicable; specify family/fallback, size, weight, line-height, tracking, and line-length guidance.
- Color roles: canvas/surface, content emphasis, border, action, status, focus, and any brand accent; define light/dark/high-contrast values where required.
- Measurement scales: spacing, containers/grid, radii, elevation, icon sizes, and touch target treatment.
- Interaction: focus ring, hover/pressed, selected, disabled, loading, error, and motion rules.
- Content: heading hierarchy, button verb style, error language, date/number formatting, and placeholder policy.

Prefer a limited scale and meaningful aliases to arbitrary values. If a one-off value is necessary, document the reason and location; do not silently expand the scale.

## Component contract

For each reusable component, document:

- **Anatomy**: parts, slots, icon/media placement, content constraints.
- **API**: purpose-based variants and sizes, not arbitrary color/spacing props.
- **Semantics**: native element, accessible name, role/value/state, and keyboard behavior.
- **States**: default, hover (where available), focus-visible, active/selected, disabled, loading, error, and empty where relevant.
- **Responsive behavior**: what reflows, wraps, stacks, scrolls, or is replaced at narrow widths.
- **Content behavior**: realistic short/long copy, localization, truncation policy, and error/empty message.
- **Tokens**: allowed semantic dependencies and any justified component tokens.
- **Examples and anti-examples**: show correct composition and known misuse.

Use an existing component when its semantics and behavior fit. Promote a pattern into a reusable component or variant when the same meaning recurs in more than one context; otherwise prefer a local composition or slot rather than growing the system prematurely.

## Theme and variation checks

- Components should change with semantic token values, not require structural edits for a theme.
- Check contrast in all supported themes and states, including disabled and focus states.
- Use non-color cues such as text, shape, icon, or pattern for error, selection, and status.
- Keep visible focus indication; never remove outlines without a stronger, tested replacement.
- Ensure icons inherit the correct color and have an accessible name when they are the control's only content.
- Avoid nested radii that visibly conflict; account for padding and optical alignment when a surface is inset.

## Design-system QA

- Lint or inspect for unapproved raw colors, font families, spacing, shadows, and transition values.
- Verify semantic token names describe intent and are not tied to a theme's current value.
- Snapshot the same representative components in their key states, themes, and responsive containers.
- Confirm an existing app can consume the tokens without adding a parallel reset, utility system, or component library.
- Check real text lengths and data extremes before declaring a component stable.

## Useful reference sources

- [Material Design tokens](https://m3.material.io/foundations/design-tokens)
- [U.S. Web Design System tokens](https://designsystem.digital.gov/design-tokens/)
- [Adobe Spectrum design tokens](https://spectrum.adobe.com/foundations/design-data/design-tokens/)
- [UI/UX Pro Max Skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/.claude/skills/ui-ux-pro-max/SKILL.md)
- [ConardLi web-design-engineer Skill](https://github.com/ConardLi/garden-skills/blob/main/skills/web-design-engineer/SKILL.md)
- [GitHub premium-frontend-ui Skill](https://github.com/github/awesome-copilot/blob/main/skills/premium-frontend-ui/SKILL.md)
