# Render Quality Rubric

Use this rubric after generating the HTML report and before delivery.

The renderer must inspect the actual rendered result, not only the HTML source.

## Scoring

| Dimension | Weight | Passing expectation |
|---|---:|---|
| Industry relationship clarity | 25 | Main relationships and arrow direction are understandable without reading production tables |
| Product-formation accuracy | 15 | Product flow is accurate, visibly connected, and placed directly below the panoramic graph when included |
| Graph legibility | 15 | No text, logo, ticker, metric, or bottleneck label is obscured by lines or other elements |
| Information hierarchy | 15 | Panoramic graph dominates; supporting blocks are clearly secondary |
| Company visual treatment | 10 | Listed companies use verified logo/wordmark plus ticker where practical; fallbacks are consistent |
| Commercial-control clarity | 10 | Control-point cards are compact and easy to scan |
| Style-brief adherence | 10 | The result expresses the requested visual character without violating hard restrictions |

Target score: at least 85/100.

## Automatic Failure Conditions

The HTML is not deliverable if any of these occur:

- Evidence Ledger, Renderer Notes, raw JSON, source lists, node tables, edge tables, badge tables, or other non-render production data appear visibly
- arrows or connector lines cover important text or badges
- the title area contains an unrequested long explanatory paragraph
- the panoramic graph cannot be followed through visible arrows
- product-formation flow is included but placed far away from the panoramic graph
- a standalone layer inventory such as `产业分层节点` is rendered
- company tickers or logos are invented
- visible text overflows, overlaps, or is clipped at the target viewport

## Required Review Pass

Before delivery:

1. open the rendered HTML
2. inspect the top area, panoramic graph, process flow, control points, bottleneck ranking, and legend
3. inspect at desktop and mobile widths when the runtime supports it
4. check line routing and text fit
5. check that forbidden Markdown sections did not leak into HTML
6. revise the HTML until automatic failure conditions are cleared
7. report the final score and any remaining limitations outside the visible HTML

## Creative Review Questions

- Does the visual language feel specific to this industry?
- Does the main graph communicate more than a generic upstream/midstream/downstream chart?
- Are route alternatives distinguishable without overwhelming the main chain?
- Are bottlenecks visually emphasized in proportion to their importance?
- Does the report feel intentionally designed rather than mechanically converted from Markdown?
