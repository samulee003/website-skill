# Source Map and Further Reading

This reference maps the source families named in the design brief to the integrated workflow. The skill expresses their concerns as one operational process; it is not a verbatim copy of any upstream skill. Read the relevant source and verify current details when a task depends on a particular framework, library, or source-specific procedure.

| Named source family | Integrated in |
|---|---|
| Anthropic Claude Code `frontend-design` | [02 Art direction and content](02-art-direction-and-content.md), [08 Visual QA and release](08-visual-qa-and-release.md): distinct visual choices, craft, browser evidence, and iterative critique. |
| OpenAI `frontend-app-builder` | [01 Intake and contract](01-intake-and-contract.md), [07 Build and runtime verification](07-build-and-runtime-verification.md): design intent, existing project context, implementation, and verification. |
| UI/UX Pro Max | [02 Art direction and content](02-art-direction-and-content.md), [03 Tokens and components](03-tokens-and-components.md): style selection, page patterns, and coherent system decisions. |
| ConardLi `web-design-engineer` | [01 Intake and contract](01-intake-and-contract.md), [03 Tokens and components](03-tokens-and-components.md), [04 Responsive and content resilience](04-responsive-and-content-resilience.md). |
| GitHub Awesome Copilot `premium-frontend-ui` | [02 Art direction and content](02-art-direction-and-content.md), [03 Tokens and components](03-tokens-and-components.md), [05 Motion and interaction](05-motion-and-interaction.md). |
| uizze `ui-design` | Interface composition and design-first decisions are incorporated in [02](02-art-direction-and-content.md) and [03](03-tokens-and-components.md). |
| Meng To design-first prompting, high-quality websites, landing/pricing pages, GSAP, Tailwind, and scroll animation | [02 Art direction and content](02-art-direction-and-content.md), [03 Tokens and components](03-tokens-and-components.md), [04 Responsive and content resilience](04-responsive-and-content-resilience.md), [05 Motion and interaction](05-motion-and-interaction.md). |
| Vercel Web Interface Guidelines | Cross-cutting implementation, state, semantics, keyboard, responsive, and motion checks in [04](04-responsive-and-content-resilience.md), [05](05-motion-and-interaction.md), [06](06-accessibility.md), [07](07-build-and-runtime-verification.md), and [08](08-visual-qa-and-release.md). |
| jakubkrehel interface, UI, typography, color, layout, writing, accessibility, design implementation, and interface-review Skills | [01](01-intake-and-contract.md), [02](02-art-direction-and-content.md), [03](03-tokens-and-components.md), [06](06-accessibility.md), [08](08-visual-qa-and-release.md). |
| akillness `design-system` | Token layering, reusable component contracts, and consistency checks in [03 Tokens and components](03-tokens-and-components.md). |
| Intopia web accessibility | [06 Accessibility](06-accessibility.md): semantic structure, forms, dynamic content, assistive-technology testing, and practical exercises. |
| Anthropic `accessibility-review` | [06 Accessibility](06-accessibility.md), [08 Visual QA and release](08-visual-qa-and-release.md): structured WCAG review and actionable findings. |
| Everything Claude Code accessibility | [06 Accessibility](06-accessibility.md): accessibility checks integrated into implementation and review. |
| mgifford accessibility-focused Skills | [06 Accessibility](06-accessibility.md), [08 Visual QA and release](08-visual-qa-and-release.md): manual testing, governance, regression prevention, and release evidence. |

## Selected primary references

These sources were opened during synthesis and provide directly useful implementation or verification guidance:

- [Anthropic Claude Code frontend-design plugin](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design)
- [Anthropic design harness research](https://www.anthropic.com/research/harness-design-long-running-apps)
- [Meng To design-first UI prompting](https://www.ui-skills.com/skills/mengto/design-first-ui-prompting)
- [OpenAI frontend-app-builder Skill](https://github.com/openai/plugins/blob/main/plugins/build-web-apps/skills/frontend-app-builder/SKILL.md)
- [UI/UX Pro Max Skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/.claude/skills/ui-ux-pro-max/SKILL.md)
- [ConardLi web-design-engineer Skill](https://github.com/ConardLi/garden-skills/blob/main/skills/web-design-engineer/SKILL.md)
- [GitHub Awesome Copilot premium-frontend-ui Skill](https://github.com/github/awesome-copilot/blob/main/skills/premium-frontend-ui/SKILL.md)
- [Vercel Web Interface Guidelines](https://vercel.com/design/guidelines)
- [jakubkrehel interface-review Skill](https://github.com/jakubkrehel/skills/blob/main/skills/interface-review/SKILL.md)
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [Intopia accessibility resources](https://intopia.digital/resources-for-developing-for-web-accessibility/)
- [Anthropic accessibility-review Skill](https://github.com/anthropics/knowledge-work-plugins/blob/main/design/skills/accessibility-review/SKILL.md)
- [mgifford manual accessibility testing Skill](https://github.com/mgifford/accessibility-skills/blob/main/skills/manual-testing/SKILL.md)

Some named projects are not individually linked here because the brief provided a skill name without a stable canonical source or the specific source page could not be confirmed. The operational guidance remains framed as integrated practice rather than an unsupported attribution to that project.
