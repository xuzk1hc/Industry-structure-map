# Visual Report Pattern

Use this file when the user wants the final Markdown to be rendered as a long-form HTML consulting infographic.

## Design Goal

The output should feel like a structured industry research poster and a render-ready graph specification:

- immediately readable from top to bottom
- richer than a simple upstream/midstream/downstream chart
- precise enough for serious industry analysis
- compatible with a renderer that can consume Markdown graph specs and production data
- easy for another AI to transform into a styled visual report

## Core Layout

Use one primary visual block plus supporting render data:

1. **Panoramic industry-plus-business flowchart**
   - Merge product structure and business relationships.
   - Use product/component/process nodes as the backbone.
   - Attach company leaders, customer groups, competitors, and bottlenecks to those nodes.

2. **Supporting render data**
   - Node table.
   - Edge table.
   - Commercial control-point cards.
   - Bottleneck heat table.

3. **Optional compact product-formation/process ribbon**
   - Only include enough process flow for the renderer to understand the sequence.
   - Do not let process detail dominate the main graph.
   - When included, place it directly below the panoramic industry-plus-business flowchart.

## Preferred HTML Rendering Method

When the final artifact is an HTML long infographic, prefer a hand-laid SVG main graph over generic HTML card grids.

Use SVG for the primary map when:

- arrow direction matters
- several nodes feed into one bottleneck
- physical paths and business-validation paths must coexist
- the output should resemble a polished consulting long image

Use HTML/CSS cards for supporting blocks:

- commercial control-point cards
- bottleneck heat table
- compact process ribbon
- small legend or metric chips

Do not build the primary map as stacked rows of cards unless arrows and merge/split relations remain visually clear.

Recommended canvas:

- max width around 900-1000 px for long-form social/report rendering
- dark blue background
- compact centered title
- small chips under title
- one large SVG flow map as the first major content block
- compact product-formation/process ribbon directly under the main map when useful
- two-column commercial-control cards
- dense bottleneck heat table

Avoid hero paragraphs. The top title area should not include a long thesis sentence, route explanation, or time-window paragraph unless the user explicitly requests it.

## Primary Output Rule

The main deliverable is the graph, not the prose.

For each output, make sure another AI can render the graph without guessing:

- node labels are short and stable
- every node has a type, layer, leader companies, bottleneck status, and evidence hooks
- every edge has a relationship type such as `physical input`, `integration`, `supplier`, `qualification`, `customer`, `substitute`, or `competition`
- commercial control points are separated from evidence notes
- competing technology routes use stable route labels and branch colors when they materially change the chain

## Visible Versus Non-Render Content

The Markdown file is a production brief for the next AI.

Visible in final HTML:

- title
- compact chips under title
- panoramic industry-plus-business flowchart
- compact product-formation/process ribbon when useful
- commercial control-point cards
- bottleneck heat table
- small legend for arrow styles and bottleneck colors

Do not render directly:

- Render Brief instructions
- Scope Confirmation Gate
- Node Production Data and Edge Render Data tables unless converting them into visual nodes, arrows, cards, or hidden QA metadata
- Company Badge Data table
- Evidence Ledger
- Renderer Notes
- raw JSON or machine-readable blocks
- raw Markdown backup
- source URLs
- source list or bibliography
- investment/research observation tables
- standalone layer inventory such as `产业分层节点`
- long reasoning paragraphs

The final HTML should never look like it rendered the production Markdown line by line. Treat production tables as data behind the graphic.

Do not build the report navigation from all Markdown headings. Build navigation only from visible blocks.

For Chinese outputs, visible text should be Chinese. Keep English only for unavoidable company names, product names, and standards such as HBM4, CoWoS, TSV, GPU, ASIC.

Avoid visible hero paragraphs. The top area should usually contain only:

- title
- optional evidence-cutoff text if the user wants it visible
- 3-6 compact chips or tags

Do not render a paragraph under the title that explains every route, time window, or constraint thesis. Put route details in chips, legends, graph labels, or control cards instead.

## Graph Legibility And Edge Routing

Treat line overlap as a rendering error, not a minor style issue.

Rules for the panoramic graph:

- arrows and connector lines must not pass through node titles, company names, company badges, tickers, metric chips, or bottleneck labels
- connect arrows to node borders or explicit anchor points, not through the center of text blocks
- reserve horizontal and vertical gutters between lanes for edges
- route edges behind nodes only when they remain visually separated from text; otherwise route around nodes
- keep edge labels outside node bodies and away from company badges
- use orthogonal, elbow, curved, or bundled edges when straight lines would cross text
- use z-index/layering so node panels, text, and badges sit above decorative lines, but do not rely on layering to hide bad routing
- when the graph becomes too dense, split into a main overview plus a focused drilldown instead of allowing unreadable crossings

## Graph-First Markdown Production Order

Use this order in the Markdown production brief when the user mainly wants a chart. This is not the final HTML section order; final HTML must follow the visible-section allowlist.

1. title
2. render brief
3. panoramic industry-plus-business flowchart
4. compact product-formation/process ribbon if useful
5. node production data
6. edge render data
7. commercial control-point cards
8. bottleneck heat table
9. non-render evidence ledger

## Commercial Control-Point Map

Use 4-8 cards when the business logic matters. Keep them compact.

Default layout:

- two-column card grid on desktop, single column on narrow screens
- each card has a short title and severity dot
- each card uses only concise rows: `控制`, `龙头`, `瓶颈`
- optional fourth row: `客户` or `验证`, only when needed
- no paragraph body inside cards
- no source URLs inside cards

The card should read like a control-point label, not a mini essay.

## Bottleneck Heat Map Layout

Use a vertical ranking by default.

Preferred structure:

- one top-to-bottom list or slim table
- long horizontal rows with compact height
- columns: `排名`, `节点`, `瓶颈判断`, `约束类型`, `热力`
- heat chips at the right edge
- row backgrounds can alternate subtly, but avoid wide card grids

This block should resemble an investment-research bottleneck ranking: dense, directional, and easy to scan from rank 1 downward.

## Company Logo And Ticker Rule

For visible company labels:

- listed companies: show logo or wordmark plus ticker whenever practical, such as `NVIDIA (NVDA)`, `TSMC (TSM)`, `Samsung Electronics (005930.KS)`, `SK hynix (000660.KS)`, `Micron (MU)`, `AMD (AMD)`, `Broadcom (AVGO)`, `ASML (ASML)`
- private or unlisted companies: show logo/wordmark or a consistent text badge
- if the renderer cannot fetch a logo, use a styled fallback badge with the company name and ticker if available
- do not invent logos, listing status, or tickers
- keep company badges smaller than product/process node labels so the graph remains product-led
- avoid plain comma-separated company lists in visible graph nodes or cards when company badge data exists

## Panoramic Atlas Layout

Default swimlanes:

1. Key input layer: materials, equipment, wafers, tools, IP, data, energy, or other enabling resources.
2. Product structure layer: subcomponents, modules, bottleneck processes, tests, and finished product.
3. Finished supplier layer: companies that actually ship the finished product or critical subsystem.
4. Integration/platform layer: packaging, foundry, system integration, marketplace, or platform controller.
5. Downstream customer layer: immediate customers and terminal demand.
6. Bottom data strip: market size, share, lead time, capacity, growth, adoption, or bottleneck metrics.

Swimlanes are layout metadata. Render them as graph backgrounds, group labels, or lane headers inside the main atlas. Do not render a separate layer-card grid or standalone `产业分层节点` section unless the user explicitly asks for a technical appendix.

Company labels inside nodes should use compact logo/wordmark plus ticker badges for listed companies whenever badge data is available. Keep badges below or beside the node label, never as loose comma-separated text that forces long line wrapping.

## What To Merge

Merge:

- product structure tree
- supplier/customer/competitor relationships
- bottleneck markers
- global leader labels

Keep separate or secondary:

- detailed manufacturing process
- full evidence notes
- long company descriptions
- numerical model assumptions

## Visual Encoding

- Solid arrow: physical composition, required input, or product formation.
- Dashed arrow: customer qualification, reported supply, alternative route, substitute, or competitive relation.
- Red marker: bottleneck.
- Yellow marker: watchlist bottleneck.
- Grey marker: weakly inferred, speculative, stale, or otherwise low-confidence relationship.
- Blue/green/purple route lines: competing technical routes or design variants. Use only when route divergence matters.

## Commercial Control-Point Cards

Each card should include:

- control point name
- `控制`: the thing being controlled in one short phrase
- `龙头`: 1-4 leader badges, ideally logo plus ticker for listed companies
- `瓶颈`: the constraint mechanism in one short phrase
- `替代路线影响`: optional one short phrase when a competing route can bypass, weaken, or reinforce the control point

Recommended card types:

- finished-product supplier
- core component or module
- equipment/tooling gate
- material or substrate gate
- integration/platform gate
- downstream platform customer
- terminal demand pool
- emerging substitute or challenger

## Quantitative Bottleneck Signals

Use quantitative signals only when sourced data exists.

Good visible formats:

- small metric chips inside bottleneck rows
- concise tokens such as `concentration: high`, `HHI proxy: top-3`, `utilization: >90%`, `qualification: 12-18 months`
- `unknown` when the metric is material but unavailable

Do not fabricate exact figures for visual polish. Numeric metrics require method plus evidence ID in non-render data.

## Full Markdown Production Order

Use this order for full Markdown production briefs. This is not permission to render every section into final HTML.

1. title and render brief
2. panoramic industry-plus-business flowchart
3. compact product-formation/process ribbon if useful
4. node production data
5. edge render data
6. commercial control-point cards
7. bottleneck ranking and heatmap
8. evidence ledger
9. thesis breakers and update triggers

## Writing Rules

- Keep diagram labels short.
- Put company names in node subtitles or cards, not in every edge.
- Put evidence IDs in tables, not the diagram.
- Keep raw node/edge tables out of the rendered HTML. The renderer should consume them as data, not display them.
- Keep company badge, evidence, JSON, source, and renderer-note tables out of the rendered HTML.
- Do not claim direct supply unless confirmed or clearly labeled as reported/inferred.
- If the main chart becomes too dense, split by system: product formation, commercial control points, and end demand.
- Do not render the Evidence Ledger in final HTML unless the user explicitly asks for visible citations.
- For complex maps, show merge/split relationships explicitly. Do not imply that peer companies are sequential steps.
- Use Evidence Tier 1-6 in source ledgers; do not use legacy letter source labels.
- Treat visible-section denylist violations as render failures, not style preferences.
