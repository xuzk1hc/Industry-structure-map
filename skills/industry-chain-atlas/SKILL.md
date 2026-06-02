---
name: industry-chain-atlas
description: Use when the user wants a structured industry-chain atlas for a product or sector such as HBM, EV batteries, semiconductors, robotics, energy storage, or AI infrastructure, including product decomposition, supplier/customer/competitor mapping, bottleneck ranking, evidence cross-checking from filings/reports/news, and Markdown output designed for HTML consulting-report rendering.
---

# Industry Chain Atlas

Use this skill when the user wants to analyze an industry chain, product stack, or manufacturing ecosystem and turn it into a structured Markdown graph specification that another AI can render into a consulting-style HTML infographic.

The skill is designed for outputs such as:

- industry maps for HBM, EV batteries, optical modules, humanoid robots, cooling, power equipment, materials, or semiconductor equipment
- supplier, customer, competitor, and bottleneck analysis by product/component/process node
- graph-first Markdown reports that another AI or renderer can convert into styled HTML industry and commercial maps
- evidence-driven supply-chain work using filings, earnings calls, research reports, and industry news

## Core Promise

Do not flatten the chain into simple upstream/midstream/downstream buckets.

Instead, build a product-aware atlas:

1. define the final product or product generation
2. decompose the product into modules, materials, processes, equipment, testing, packaging, and integration steps
3. map how each node feeds the next node and how the pieces combine into the final product
4. label leading global companies, regional challengers, downstream customers, and competitors at every important node
5. rank bottlenecks by concentration, substitutability, qualification cycle, capacity ramp, technical difficulty, and evidence strength
6. produce a graph-first Markdown artifact that is easy to render into an HTML consulting report

## When To Read References

- For the full work sequence, read [references/workflow.md](references/workflow.md).
- For Mermaid diagrams, node fields, and table schemas, read [references/graph-schema.md](references/graph-schema.md).
- For long-form consulting infographic layouts that merge product structure and business relationships, read [references/visual-report-pattern.md](references/visual-report-pattern.md).
- For evidence grading, source hierarchy, and cross-check rules, read [references/evidence-standard.md](references/evidence-standard.md).
- For the final Markdown output scaffold, read [references/report-template.md](references/report-template.md).

## Required Workflow

Use this order unless the user explicitly requests a narrower task:

1. Scope gate: identify product, generation, geography, time horizon, and desired output depth.
2. Product decomposition: break the final product into modules, subcomponents, materials, equipment, processes, testing, and integration.
3. Main atlas design: for report-style outputs, merge the product structure tree and business relationship chain into one panoramic industry map; keep the process chain as a second-layer ribbon or drilldown.
4. Process-chain mapping: show how raw inputs become components, how components become subsystems, and how subsystems become the final product.
5. Company-role mapping: for each node, name global leaders, important regional players, downstream customers, competitors, and likely substitutes.
6. Bottleneck ranking: identify where demand growth would break the chain first.
7. Evidence cross-check: validate key claims with company evidence, research/report evidence, and industry-news evidence.
8. Markdown assembly: output a graph-first Markdown file whose primary artifact is the industry-plus-business flowchart; tables, cards, bottleneck notes, and evidence are supporting render data.

## Hard Rules

- Never output only a simple upstream/midstream/downstream table.
- For visual report requests, do not make company-only maps. Product/component/process nodes must be the primary structure; companies are labels, role cards, or relationship overlays.
- The Markdown artifact is an instruction/specification for the next renderer, not the visible report body.
- Clearly mark visible sections and non-render sections. The renderer must not place Evidence Ledger, Renderer Notes, source URLs, or long reasoning paragraphs into the final HTML.
- Node Render Data, Edge Render Data, and other production tables are inputs for image/HTML generation only. They must not appear as raw tables in the final rendered HTML unless explicitly transformed into visual nodes, arrows, cards, or hidden QA metadata.
- Use the user's target language for visible labels. For Chinese reports, all visible headings, card labels, node names, and legends should be Chinese.
- Avoid decorative explanatory prose in the visible hero. Use title, subtitle only if necessary, and compact metric chips.
- Bottleneck heatmaps should default to a top-to-bottom ranking layout: long, narrow horizontal rows or a slim table, not a wide grid of cards. Each row should show rank, node, bottleneck judgement, constraint type, and heat level.
- Commercial control points should be compact and easy to scan. Prefer two-column cards with only short fields such as `控制`, `龙头`, and `瓶颈`; avoid paragraph-style explanations inside these cards.
- Company annotations should use logo or wordmark plus ticker for listed companies whenever practical. For private companies, use a logo/wordmark or consistent text badge; do not invent tickers.
- Never claim supplier/customer relationships without labeling whether they are confirmed, inferred, or speculative.
- Never present a company as a bottleneck merely because it is a market leader; explain the actual constraint.
- Every major node must have an input, output, role in final-product formation, company leaders, and evidence status.
- Every major bottleneck call must include at least one falsification test.
- If live source access is unavailable, state that source verification is incomplete and mark claims as needing refresh.

## Default Output

For a full request, produce a graph-first Markdown artifact using the template in [references/report-template.md](references/report-template.md).

For a short answer, still include:

- one product/system definition
- one industry-plus-business flowchart
- compact node and edge render data
- top 3 bottlenecks
- strongest evidence and weakest assumption
- what to verify next

## Evidence Discipline

Always separate:

- confirmed disclosure
- management claim
- reputable third-party reporting
- analyst/research-report interpretation
- inference from adjacent-chain evidence
- speculation

Use current, source-backed information whenever possible. For public companies, prefer annual reports, quarterly reports, earnings-call transcripts, investor presentations, official announcements, and credible industry publications before market commentary.

## Final Artifact Bias

The final artifact should behave like a renderable graph specification, not a long memo or stock-picking note.

It may mention listed companies, but the primary object is the industry system:

- how the product is made
- who controls each node
- where bottlenecks sit
- how evidence supports or weakens the map
- what changes would force the map to be redrawn

Default final structure:

1. graph render brief
2. one panoramic industry-plus-business flowchart
3. compact process ribbon if useful
4. non-render node render table
5. non-render edge render table
6. compact commercial control-point cards
7. vertical bottleneck heat ranking
8. non-render evidence ledger
