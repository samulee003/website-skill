# Motion and Interaction

Use this reference when adding interactive behavior, transitions, scroll-linked storytelling, GSAP, or any movement that may affect performance or accessibility.

## Model each interaction as a state machine

For every control, define: initial state, trigger, changed state, loading/disabled behavior, success result, error/recovery, keyboard behavior, touch equivalent, URL/history behavior if shareable, and reduced-motion result. Do not implement only the visual default state.

Use native links for navigation and buttons for actions. Provide visible keyboard focus. Never require hover, precise dragging, or motion perception to discover or complete the core task.

## Choose the simplest suitable animation system

- Use CSS transitions/keyframes for a small number of known visual states, hover/focus feedback, and simple enter/exit effects.
- Use a timeline library such as GSAP only when the task genuinely needs coordinated sequences, multiple synchronized elements, scroll progress mapping, pinning, scrubbing, snapping, or complex interruption/reversal.
- Assign one owner to each animated property. Do not let CSS utilities and a JS timeline race to set the same transform/opacity; use a documented CSS custom property if handoff is necessary.
- Keep the final content present in normal document flow. A no-JavaScript path or failed animation initialization must not leave meaningful content at `opacity: 0`, off-screen, or inaccessible.

## Motion and scroll guardrails

- Use motion to explain causality, hierarchy, feedback, or a deliberate narrative. Reduce decorative movement that competes with reading.
- Preserve native scrolling by default. Pin/snap only when users benefit from a clear storyboard or bounded step sequence; do not hijack the entire page.
- Start with one purposeful motion variable per section. Define scroll trigger, start/end point, duration/progress mapping, interruption, and cleanup.
- Prefer `transform` and `opacity`. Avoid per-frame layout changes such as `width`, `height`, `top`, `left`, or `margin`; do not use `transition: all`.
- Use `will-change` sparingly and only where profiling shows benefit. Inspect layout, paint, layers, dropped frames, and long tasks in browser performance tools.
- In development, enable timeline/scroll markers to verify trigger boundaries; remove them before delivery and check the footer and final section afterward.

## Responsive and reduced-motion behavior

- Treat viewport/input preference as animation states. A desktop pinned sequence may become ordinary stacked content on mobile.
- Respect `prefers-reduced-motion`. Remove or simplify decorative transforms, parallax, rotation, looping, and large-distance movement. Preserve functional outcomes with a static result, brief opacity/color feedback, or immediate state change.
- For GSAP, use context and `gsap.matchMedia()` (or an equivalent media-query lifecycle) so triggers and listeners revert when conditions change. Avoid duplicate triggers after resize or route changes.
- Reduced motion is not just duration zero: remove motion that can cause discomfort while keeping meaning, result, reading order, and focus intact.
- Test at least one touch device. Hover-only effects need focus/tap alternatives and must not reveal core information exclusively on pointer hover.

## Motion acceptance checklist

- With JavaScript or the animation library unavailable, content remains visible and operable.
- With reduced motion enabled, the task remains complete and decorative motion is removed or minimized.
- Keyboard users can reach, activate, and leave every control; focus remains visible and unobscured.
- Touch users do not need hover or precise drag; tap targets and alternative controls are available.
- Animation does not introduce unacceptable jank, layout shift, focus loss, duplicated announcements, or scroll traps.
- Timeline triggers are verified at narrow and wide sizes, after resize/route changes, and at the final page section.

Useful references:

- [GSAP accessible animation](https://gsap.com/resources/a11y/)
- [GSAP matchMedia](https://gsap.com/docs/v3/GSAP/gsap.matchMedia/)
- [GSAP ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/)
- [Tailwind CSS animation and motion variants](https://tailwindcss.com/docs/animation)
- [web.dev: high-performance CSS animations](https://web.dev/articles/animations-guide)
- [MDN: CSS and JavaScript animation performance](https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/CSS_JavaScript_animation_performance)
