# Visual QA and Release

Use this reference for design-to-code comparison, interface review, visual regression, and final release decisions.

## Fix comparison conditions

Before capturing a baseline and the implementation, match the browser/version where possible, viewport and device pixel ratio, fonts loaded, content/data, locale and timezone, color scheme, authentication state, scroll position, and animation progress. Keep animation and time-dependent content deterministic or disable it for the capture. Record any condition that cannot be matched.

Use screenshots, overlays, pixel differences, and browser inspection as complementary evidence. Pixel diffs can be noisy because of antialiasing, font rasterization, or platform rendering; inspect the actual hierarchy and interaction rather than blindly fixing every pixel.

## Review the whole surface

For each changed route or component, check:

- Hierarchy and content order: one clear primary heading and action, headings/sections answer user questions, long copy is not clipped.
- Geometry and craft: container/grid alignment, spacing rhythm, typography, line lengths, imagery crop, icon size/stroke, nested radii, focus/hover/disabled states.
- Responsive behavior: narrow, intermediate, desktop, and ultra-wide; no unintended overflow, overlap, clipping, or broken ordering.
- Functional states: default, hover, focus-visible, active/selected, disabled, loading, success, empty, error, and any domain-specific state.
- Interaction semantics: keyboard order, focus visibility/management, links vs buttons, labels and errors, touch hit area, and status announcements.
- Runtime: console, network, hydration, URL/history, media, and layout stability.

## Classify and prioritize findings

For code changes, label findings as **Introduced**, **Regression**, or **Pre-existing**. For each finding, record:

| Field | Include |
|---|---|
| Severity | Blocker, high, medium, or low, based on user/task impact |
| Location | Route, component, viewport, and state |
| Reproduction | Exact steps, input, and browser/device condition |
| Current vs expected | Observable behavior, not a subjective label |
| Evidence | Screenshot, recording, console, accessibility tree, or test output |
| Fix | Specific change that fits the current stack |
| Acceptance | How to confirm the fix and avoid regression |

Suggested priority order: task blocker/data loss; accessibility or security risk; cross-viewport/state breakage; misunderstanding or broken content; system inconsistency; low-impact visual polish. Keep pre-existing issues separate unless the user also authorized broader remediation.

## Iterate without polishing the wrong direction

1. Rank findings by severity and scope.
2. Fix root causes before local patches; a shared token or component may affect multiple routes.
3. Re-run the relevant viewport/state matrix after each meaningful fix.
4. For subjective visual iteration, change one major variable at a time and save before/after evidence.
5. If design quality or distinctiveness does not improve after two iterations, reconsider the direction instead of adding decorative effects.

## Release gate

Release only when all applicable high-priority issues are closed, existing project checks pass, key tasks work by keyboard and touch, responsive and accessibility checks have evidence, and screenshots show no unexplained material mismatch. Name any remaining unverified route, viewport, state, browser, or assistive technology. Do not imply full conformance or pixel-perfect coverage unless those checks were performed.

## Compact review output

For a review request, use this flexible format:

```text
# Interface review

## Highest-priority findings
1. [Severity] [Introduced/Regression/Pre-existing] — [route/component/state]
   Reproduce: ...
   Expected: ...; observed: ...
   Evidence: ...
   Fix and acceptance: ...

## Verified
- [Build/test/browser/device paths actually checked]

## Not verified / remaining risk
- [Specific route, width, state, or assistive technology]
```

Useful references:

- [jakubkrehel interface-review Skill](https://github.com/jakubkrehel/skills/blob/main/skills/interface-review/SKILL.md)
- [jakubkrehel Skills repository](https://github.com/jakubkrehel/skills)
- [Vercel Web Interface Guidelines](https://vercel.com/design/guidelines)
