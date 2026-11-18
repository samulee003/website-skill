# Build and Runtime Verification

Use this reference when implementing a page or making code changes. Adapt checks to the existing project rather than inventing a new test stack.

## Before editing

1. Read the project manifest, entry points, routes, rendering model, style configuration, token/component conventions, assets, and existing tests.
2. Find the documented or existing commands for install, type checking, lint, unit/integration tests, and production build. Do not run a package install or modify lockfiles unless required.
3. Trace the affected pages and shared components. Identify existing data, API, authentication, and error-handling patterns. Preserve public contracts unless the request authorizes a change.
4. Define the smallest set of screenshots, routes, states, viewports, and input methods needed to verify the change.

## Implement through the real task

- Build the semantic structure and primary task first. Use the project's routing, data, and component model; avoid a static mock that cannot complete the requested interaction.
- Use real supplied content and assets. For missing factual content, use marked placeholders and keep the layout resilient.
- Implement empty/loading/error/success/disabled states that are relevant to the task. Make failures recoverable and avoid duplicate submissions.
- For shareable filters, tabs, pagination, or expanded sections, persist state in the URL/history where that matches product behavior.
- Avoid `transition: all`, uncontrolled layout measurement, hard-coded heights, and dependencies added only for cosmetic convenience.

## Run the existing checks

Run the relevant project commands in a useful order: formatting/lint, type check, unit or integration tests, then production build. When a command fails, determine whether the failure is introduced by the change or existed in the baseline. Do not hide a failure by weakening tests or replacing the project's tooling.

Inspect the running experience when browser access is available:

- Console: uncaught errors, hydration mismatch, warnings introduced by the change, failed or duplicated requests.
- Network/assets: missing fonts, images, APIs, incorrect caching, and unnecessary large assets.
- Layout: content shift from fonts/media, unexpected scrollbars, overlays that cover content or focus, and missing safe-area handling.
- Interaction: real form submission, CTA destination, loading duration, error recovery, keyboard and touch behavior, browser Back/Forward, and refresh/deep-link behavior.
- Performance: image dimensions/loading strategy, long tasks, layout/paint work during animation, dropped frames, and avoidable JavaScript on the critical path.

## Runtime resilience tests

Test relevant failures, not only the happy path: slow or unavailable network, empty response, invalid data, rejected submission, expired/unauthorized state if applicable, delayed font/media, and JavaScript/animation initialization failure. Confirm that the user sees a clear state, entered data is retained where appropriate, and a safe recovery action exists.

For motion-heavy pages, test on at least one lower-powered or touch device when possible. Inspect `prefers-reduced-motion`, resize/orientation changes, and route unmount/remount to ensure listeners, observers, and animation triggers are cleaned up.

## Delivery record

State which commands passed, which browser/device/viewport and interaction paths were checked, and any known unverified cases. A passing build only proves the code compiled; do not claim visual equivalence, accessibility conformance, or browser coverage without separate evidence.

Useful references:

- [OpenAI frontend-app-builder Skill](https://github.com/openai/plugins/blob/main/plugins/build-web-apps/skills/frontend-app-builder/SKILL.md)
- [OpenAI frontend coding with GPT-5](https://developers.openai.com/cookbook/examples/gpt-5/gpt-5_frontend)
- [Vercel Web Interface Guidelines](https://vercel.com/design/guidelines)
