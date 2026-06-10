# Visual Reference And Asset Library

Use this file to improve consistency through reference materials without forcing a fixed HTML template.

## Reference Types

Organize available references by purpose:

| Reference type | What to learn | What not to copy blindly |
|---|---|---|
| Hero/title reference | hierarchy, spacing, tag treatment | exact wording or decorative clutter |
| Panoramic graph reference | lane structure, edge routing, node density | incorrect industry relationships |
| Product-flow reference | sequence clarity, merge/split treatment | oversimplified product logic |
| Control-point reference | information compression, badge layout | paragraph-heavy cards |
| Bottleneck-ranking reference | scan order, heat encoding, row density | unsupported rankings |
| Company badge reference | logo/ticker scale and placement | guessed logos or tickers |
| Full-report reference | overall rhythm and section transitions | exact page structure |

## How To Use References

- Study references before rendering and extract 3-6 useful visual principles.
- Add those principles to the non-render Render Style Brief.
- State which parts are anti-references or known failures.
- Recreate the design logic, not the source image pixel-for-pixel.
- Preserve the industry-map content contract even when a reference uses a different information structure.

## Asset Guidance

Useful assets include:

- official company logos or wordmarks
- verified ticker labels
- domain-relevant icons for materials, equipment, components, integration, testing, customers, and demand
- subtle background textures tied to the industry
- small explanatory illustrations that reveal real products or processes

Asset rules:

- prefer official or reliable logo sources
- do not invent company logos, tickers, or listing status
- use a consistent fallback wordmark badge when a logo is unavailable
- keep logos subordinate to product and process nodes
- avoid stock-like decorative images that do not explain the chain
- do not let missing assets block rendering; degrade to consistent text badges

## External Design Capability References

External design libraries may be studied or selectively used for motion, interaction, backgrounds, and visual polish.

- Use [external-design-libraries.md](external-design-libraries.md) for the approved-use guidance.
- React Bits is an optional reference for restrained React-based text animation, backgrounds, card interactions, and metric reveals.
- External libraries must not determine the graph structure, node placement, edge routing, or industry relationships.
- Prefer a lightweight static equivalent when the report does not otherwise need React.
- Record the chosen library, effect, fallback, and license note in the non-render Render Style Brief.

## Anti-Pattern Library

Treat these as explicit failures:

- arrows or lines cover text, logos, tickers, metrics, or bottleneck tags
- every section becomes the same-size card grid
- the title area contains a long explanatory paragraph
- the main graph is replaced by a standalone layer inventory
- raw node, edge, badge, evidence, JSON, or renderer-note tables appear in HTML
- company lists appear as long comma-separated text when badges are practical
- decorative effects reduce graph readability
- the product-formation sequence appears far away from the panoramic graph
- route branches are visually different but semantically unlabeled

## Adding New References

When the user provides a strong HTML report, screenshot, or infographic:

1. identify the useful visual principles
2. identify visible failures and anti-patterns
3. update the relevant style profile or reference guidance
4. do not encode one example as a mandatory universal template
