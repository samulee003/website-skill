# Art Direction and Content

Use this reference when creating a new page, responding to a visual prompt, or deciding whether an existing page needs a new direction rather than more polish.

## Choose direction before components

1. Read the design contract and inspect existing brand/product cues.
2. Propose two or three mutually distinct routes. For each, state the audience fit, emotional register, typography roles, palette proportions, grid/composition, image/illustration strategy, materials, interaction/motion character, and one or two risks.
3. Select one route and record why it serves the task. Do not blend all routes into an incoherent compromise.
4. Define two or three reusable identity cues, such as an editorial asymmetry, a data-driven graphic vocabulary, a distinctive image crop, a characteristic typographic pairing, a recognizable accent ratio, or a restrained purposeful motion.
5. State negative constraints: generic or unwanted styles, unsupported claims, unnecessary decoration, inaccessible contrast, or image treatments that conflict with the brand.

A direction is incomplete if it says only “premium,” “clean,” “modern,” or “beautiful.” Express decisions in observable terms: scale, placement, proportion, hierarchy, materials, content order, and measurable checks.

## Design prompt / handoff template

Use this compact contract for an internal implementation prompt or design handoff:

```text
GOAL: [audience, primary task, success outcome]
FORMAT: [page/screen, route, viewport or responsive range]
LAYOUT: [grid, container, alignment, section order, density, fold behavior]
TYPE: [font roles/fallbacks, scale, weights, line-height, max line length]
COLOR + MATERIAL: [semantic roles and proportions, surface treatment, contrast]
IMAGERY / UI: [authentic assets, crop, illustration, product evidence, component rules]
COPY: [voice, exact content, primary CTA, factual constraints]
INTERACTION: [states, triggers, keyboard/touch equivalent, motion behavior]
CONSTRAINTS: [existing stack, tokens, accessibility, performance, things to preserve]
NEGATIVE: [specific unwanted patterns or claims]
ACCEPTANCE: [observable checks at required widths and states]
```

Use real copy and assets where available. If unknown, mark placeholders explicitly and make the layout resilient to longer text.

## Avoid generic output without banning useful conventions

- Do not default automatically to a centered SaaS hero, purple/blue gradient, identical rounded cards, stock icon rows, and repeated testimonial blocks.
- Reuse familiar interaction patterns where they improve comprehension; differentiate the visual language, content, evidence, and composition rather than making basic controls novel.
- Avoid decoration that adds no information, hierarchy, brand recognition, or feedback. A visual hook should recur with restraint, not compete with the primary task.
- Do not use fake customer logos, awards, metrics, quotes, prices, savings, or scarcity language. Mark placeholders until facts are supplied.
- Do not add arbitrary images because a page feels empty. Choose media that explains the product, builds trust, or supports the narrative; specify crop, aspect ratio, focal point, and loading behavior.

## Content-first page structure

### Landing page

Construct a path from understanding to action. A useful default is:

1. **Hero**: audience/problem or outcome, one concise promise, evidence or product context, one primary CTA; secondary CTA is visually secondary.
2. **Proof of product**: real interface, workflow, result, or data that makes the promise concrete.
3. **Capabilities**: organize by user outcome or task, not a generic feature grid.
4. **Trust and objections**: real customer evidence, security/accessibility/process facts, limitations, or answers to likely concerns.
5. **Decision support**: explain who the product fits and what the next step entails.
6. **Closing CTA**: restate the next step and any relevant conditions.

Each section should answer one question. Remove sections that do not add a reason to continue, evidence, or clarity.

### Pricing page

Answer these before encouraging purchase:

- Who is each plan for?
- What is the billing unit, and how do monthly and annual prices compare?
- What is included, limited, or billed as overage?
- Are tax, trial, cancellation, refund, and renewal terms clear?
- What happens after each CTA?

Use consistent comparison fields and a clear but non-coercive recommended plan. Make the selected billing interval explicit. On mobile, use readable stacked plan summaries or an accessible selector; do not shrink a wide comparison table into illegible text. Keep the terms and limitations close to the price and CTA.

## Evaluate separately

Score each from 1–5 and write one concrete reason for every score:

- **Design quality**: hierarchy, coherence, legibility, fit to audience.
- **Originality**: recognizable choices beyond library defaults, without novelty harming usability.
- **Craft**: spacing, alignment, typography, imagery, state design, detail quality.
- **Functionality**: the actual user task and CTA work across inputs and states.

Capture a browser screenshot and test the task before scoring. Change one main variable per iteration. If quality/originality does not improve for two rounds, reconsider the whole direction instead of adding shadows, gradients, or animation.
