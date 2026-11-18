# Accessibility

Use this reference when creating or reviewing any web interface. Treat accessibility as an input to structure and interaction design, not as a final styling pass. Use WCAG 2.2 AA as the default target unless the product specifies a stricter target.

## Semantics, names, and structure

- Use native HTML controls and landmarks first: headings in a meaningful hierarchy, navigation/main/footer landmarks, skip link, links for navigation, buttons for actions, labels for form controls, and appropriate table structure.
- Every interactive control needs a programmatically determinable name, role, value, and state. Give icon-only controls a descriptive accessible name. Do not expose decorative media as meaningful content.
- Provide equivalent text for informative images; describe the image's purpose in context. Use empty alt or hide purely decorative images from assistive technology. For complex charts, provide the underlying values or a meaningful long description.
- Use ARIA only when native semantics are insufficient. If a custom widget is necessary, implement the relevant keyboard pattern and state management rather than adding a role alone.

## Keyboard and focus

- Complete the primary task using only a keyboard. Test Tab and Shift+Tab through the whole page, plus the widget-specific keys (Enter, Space, arrows, Home/End, Escape) that the component requires.
- Keep focus order aligned with reading and visual order. Keep a clearly visible focus indicator; do not remove it without a stronger, tested replacement.
- Ensure sticky elements and overlays do not obscure the focused control. On dialog open, move focus to an appropriate dialog control; contain focus only when the dialog requires it; on close, return focus to the trigger.
- When content changes, move focus only when necessary. Announce asynchronous status and errors without unexpectedly stealing focus.
- Provide keyboard alternatives for drag, swipe, and other pointer gestures.

## Visual and reflow checks

- Meet WCAG contrast criteria: normal text at least 4.5:1, large text at least 3:1, and essential non-text UI components/graphics at least 3:1 against adjacent colors. Check every theme and state that ships.
- Do not convey error, selection, success, or required status by color alone.
- Preserve browser zoom. Test text enlarged to 200% and reflow at a width equivalent to 320 CSS px (often reached at 400% zoom on a desktop viewport); except for content that genuinely requires two-dimensional layout, the user should not need horizontal and vertical scrolling for the same content.
- A 44×44 CSS px target is a strong mobile usability recommendation, not the WCAG 2.2 AA minimum in every case. WCAG 2.2 AA Target Size (Minimum) generally sets a 24×24 CSS px floor with defined exceptions and spacing alternatives. Prefer the larger target where the layout permits.
- Test forced-colors/high-contrast mode where applicable. Confirm focus, selected, required, and error cues remain visible without depending on subtle color differences.

## Forms and dynamic content

- Associate each input with a visible label and provide instructions before input when needed. Use correct `type`, `autocomplete`, `name`, and `inputmode` values.
- Identify errors in text, associate them with the affected field, and explain how to fix them when possible. On submission, provide a useful error summary or focus the first invalid field without losing entered data.
- Announce loading, success, error, and asynchronous updates through an appropriate status/live region when the information is not otherwise immediately available. Avoid duplicate or excessively chatty announcements.
- Respect user-entered data; do not clear form values on error or prevent paste/password-manager use without a necessary, justified reason.
- For high-impact transactions, destructive actions, or legal/financial data, provide review, correction, confirmation, or reversibility as appropriate.

## Motion and time

- Respect `prefers-reduced-motion`. Remove or simplify nonessential parallax, large-distance movement, rotation, looping, and auto-playing effects while preserving functional outcomes and content order.
- Avoid flashing content and provide pause/stop controls when movement or auto-updating content runs long enough to affect reading or safety.
- Do not make information or task completion depend on animation timing, precision, or color perception.

## Test methods

Automated scanners are useful for catching detectable issues and preventing regressions, but a clean scan is not proof of conformance. Combine them with:

1. Keyboard-only completion of the primary flow and all custom widgets.
2. Browser zoom/text enlargement, responsive reflow, and forced-colors review.
3. At least one real screen-reader/browser pairing appropriate to the audience (e.g. NVDA or JAWS on Windows; VoiceOver on Apple platforms; TalkBack on Android).
4. Checks of accessible names, reading order, landmarks, headings, form errors, focus transitions, dialogs, tables, and live announcements.
5. An automated scan (e.g. axe or Lighthouse) on representative routes and relevant states, with findings documented by WCAG criterion and reproduction steps.

Record the tested assistive technology and browser, task completed, uncovered problems, and any untested combinations. Do not claim a specific conformance level solely because automated tooling passed.

Useful sources:

- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)
- [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)
- [Intopia accessibility resources](https://intopia.digital/resources-for-developing-for-web-accessibility/)
- [Anthropic accessibility-review Skill](https://github.com/anthropics/knowledge-work-plugins/blob/main/design/skills/accessibility-review/SKILL.md)
- [Vercel Web Interface Guidelines](https://vercel.com/design/guidelines)
- [mgifford manual testing Skill](https://github.com/mgifford/accessibility-skills/blob/main/skills/manual-testing/SKILL.md)
