---
name: web-design-master
description: "End-to-end web design and frontend delivery: art direction, UI and design systems, responsive implementation, interaction and motion, visual QA, interface review, and accessibility. Use when creating, implementing, improving, or auditing websites, web apps, landing/pricing pages, or design systems from a brief, reference, mockup, or existing code."
---

# Web Design Master

Use this skill to carry a web experience from brief to verified implementation. Treat design, content, code, interaction, responsive behavior, and accessibility as one system; do not stop at a polished static mockup when the task calls for a working page.

## Choose a mode

- **Create**: establish the experience, design direction, system, implementation, and verification.
- **Implement a reference**: inspect the existing project and supplied design/reference, preserve its intent, then implement and compare.
- **Improve**: identify the highest-impact usability, visual, responsive, performance, or accessibility issue; change only what serves the request.
- **Review/audit**: inspect the requested code or experience, separate new regressions from pre-existing issues, and report actionable findings. Do not modify unless asked.

## Non-negotiable working rules

1. Inspect the current project, routes, stack, existing design system, assets, content, and test/build commands before choosing an implementation. Extend existing conventions; do not introduce a second styling system or replace architecture for cosmetic convenience.
2. Convert vague goals such as “premium,” “modern,” or “clean” into observable decisions: audience, task, content order, typography, color roles, layout, imagery, interaction, and acceptance checks.
3. Design around real content and complete states. Include loading, empty, error, disabled, selected/focus, long-copy, sparse/dense data, and recovery behavior where relevant. Never invent product claims, testimonials, prices, or metrics.
4. Use native semantics first and ARIA only to fill real gaps. Keep core content and tasks available without animation or successful JavaScript initialization.
5. Prefer a distinct, coherent visual direction over generic SaaS/AI-template styling. Add a few deliberate, reusable identity cues; do not compensate for weak hierarchy with gradients, glass cards, shadows, or decoration.
6. Verify in a real browser or equivalent runtime when available. A successful build is necessary, not proof of visual, responsive, interaction, or accessibility quality.
7. Separate implementation from evaluation. Use the acceptance criteria and actual browser evidence to critique the result; do not treat the generator's own praise as review.

## End-to-end workflow

1. **Inspect and scope.** Identify mode, affected routes/components, existing stack and conventions, references, content/data, supported input methods, constraints, and available validation tools. For review work, fix the baseline and read the complete relevant diff, including removals.
2. **Write a design contract.** Record audience, primary task, conversion goal/primary CTA, brand personality, trust evidence, required content, constraints, success criteria, supported viewports, and accessibility target. See [intake and contract](references/01-intake-and-contract.md).
3. **Set art direction and content order.** For new work, compare two or three genuinely distinct directions, choose one, and record the reason. Define the page narrative and content-first wireframe before detailed components. See [art direction and content](references/02-art-direction-and-content.md).
4. **Define the smallest useful system.** Reuse existing tokens/components where possible. Otherwise establish semantic tokens, typography and spacing scales, containers, component contracts, and required states before multiplying patterns. See [tokens and components](references/03-tokens-and-components.md).
5. **Build the semantic core.** Implement the actual primary task and content first with links, buttons, headings, form labels, and native layout. Keep the interface understandable in its static/no-motion state.
6. **Add responsive behavior.** Start with the narrow layout; use content/container needs to choose reflow points. Test intermediate widths and realistic content, not only named devices. See [responsive and content resilience](references/04-responsive-and-content-resilience.md).
7. **Add interactions and motion deliberately.** Treat controls as state machines. Use CSS for simple state transitions; introduce a timeline library only for genuine sequencing or scroll-linked complexity. Respect keyboard, touch, reduced motion, and failure fallbacks. See [motion and interaction](references/05-motion-and-interaction.md).
8. **Build and runtime-check.** Run the project's existing type, lint, test, and production-build checks. Inspect console/network errors, loading and recovery behavior, URL state, assets, and layout stability. See [build and runtime verification](references/07-build-and-runtime-verification.md).
9. **Run an accessibility pass.** Target WCAG 2.2 AA unless the task specifies a stricter standard. Combine automated checks with keyboard, zoom/reflow, contrast, and assistive-technology checks appropriate to the experience. See [accessibility](references/06-accessibility.md).
10. **Review visually and regressions.** Fix viewport, browser, fonts, content, locale, DPR, scroll position, and animation state before comparing screenshots. Classify findings as introduced, regression, or pre-existing; prioritize by user impact. See [visual QA and release](references/08-visual-qa-and-release.md).
11. **Close the loop.** Apply high-priority fixes, rerun impacted checks, and report what changed, what was verified, and any material unverified states. Do not claim coverage that was not tested.

## Decision rules

- Keep the existing framework and design conventions unless they block a requirement; if they do, make the smallest isolated change.
- Use art direction to create identity, and tokens/components to keep recurring decisions coherent. Do not turn every one-off layout difference into a new design-system variant.
- Prefer fluid layout, intrinsic sizing, Grid/Flex, and container-aware rules. Use JavaScript measurement only when browser-native layout cannot meet a demonstrated need.
- Prefer CSS for simple visual state changes. Use GSAP or another timeline tool only when sequencing, scroll progress, pinning, or coordinated timelines justify the dependency.
- Preserve native document scrolling by default. Use pin/snap only for a clear narrative or task reason, with mobile, keyboard, reduced-motion, and no-script fallbacks.
- Choose accessible behavior over a conflicting visual spec. Document the deviation and keep the design's intent where possible.
- Use real evidence for product content. Use visibly marked placeholders when facts are unavailable; never make up social proof or pricing.
- For a review-only request, return prioritized findings rather than silently fixing them. Keep pre-existing defects separate from defects introduced by the requested change.

## Definition of done

Do not call the work complete until all applicable gates pass or the remaining gaps are explicit:

- **Intent**: audience, primary task, content hierarchy, unique primary CTA, and visual direction are clear.
- **Identity and craft**: the result has at least two deliberate identity decisions beyond a stock component-library default; typography, spacing, color, imagery, icons, and states are coherent.
- **Responsive**: narrow phone, tablet, desktop, ultra-wide, and an intermediate width have been checked; no unintended overflow, clipping, overlap, or broken order.
- **Function**: primary flows work with real controls; loading, empty, error, disabled, and recovery states are handled where applicable.
- **Accessibility**: semantic names/roles, keyboard path, visible unobscured focus, contrast, zoom/reflow, and reduced motion have been reviewed; automated tooling is not the sole evidence.
- **Engineering**: existing checks/build pass; no new console, hydration, or network errors; obvious layout shift and avoidable animation jank are addressed.
- **Evidence**: visual comparisons use fixed conditions; each significant finding has a reproduction and acceptance condition; untested areas are named.

## Load references as needed

Read only the references relevant to the current task; each is directly linked here to keep the core workflow lean.

- [01 — Intake and design contract](references/01-intake-and-contract.md): requirements, repo reconnaissance, scope, and acceptance criteria.
- [02 — Art direction and content](references/02-art-direction-and-content.md): distinctive direction, prompting, landing/pricing narrative, and content rules.
- [03 — Tokens and components](references/03-tokens-and-components.md): design tokens, typography, components, themes, and state contracts.
- [04 — Responsive and content resilience](references/04-responsive-and-content-resilience.md): mobile-first layout, breakpoints, real content, and viewport matrix.
- [05 — Motion and interaction](references/05-motion-and-interaction.md): CSS vs timeline tools, scroll animation, performance, and fallbacks.
- [06 — Accessibility](references/06-accessibility.md): WCAG 2.2 AA implementation and manual review.
- [07 — Build and runtime verification](references/07-build-and-runtime-verification.md): build, browser, interaction, performance, and failure testing.
- [08 — Visual QA and release](references/08-visual-qa-and-release.md): screenshot comparison, review findings, prioritization, and release gates.
- [09 — Source map](references/09-source-map.md): source families incorporated and selected primary references for deeper lookup.
