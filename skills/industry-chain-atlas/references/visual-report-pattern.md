# Visual Report Pattern

Use this file when the user wants the final Markdown to be rendered as a long-form HTML consulting infographic.

## Design Goal

The output should feel like a structured industry research poster and a render-ready graph specification:

- immediately readable from top to bottom
- richer than a simple upstream/midstream/downstream chart
- precise enough for serious industry analysis
- compatible with Markdown-to-HTML rendering
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

3. **Optional compact process ribbon**
   - Only include enough process flow for the renderer to understand the sequence.
   - Do not let process detail dominate the main graph.

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
- two-column commercial-control cards
- dense bottleneck heat table
- compact process ribbon at the end

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
- commercial control-point cards
- bottleneck heat table
- compact process-flow ribbon
- small legend for arrow styles and bottleneck colors

Do not render directly:

- Render Brief instructions
- Node Render Data and Edge Render Data tables unless converting them into visual nodes, arrows, cards, or hidden QA metadata
- Evidence Ledger
- Renderer Notes
- source URLs
- long reasoning paragraphs

The final HTML should never look like it rendered the production Markdown line by line. Treat production tables as data behind the graphic.

For Chinese outputs, visible text should be Chinese. Keep English only for unavoidable company names, product names, and standards such as HBM4, CoWoS, TSV, GPU, ASIC.

Avoid visible hero paragraphs. The top area should usually contain only:

- title
- 4-6 chips
- optional legend

## Graph-First Markdown Order

Use this order when the user mainly wants a chart:

1. title
2. render brief
3. panoramic industry-plus-business flowchart
4. node render data
5. edge render data
6. commercial control-point cards
7. bottleneck heat table
8. compact process ribbon if useful
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

## Panoramic Atlas Layout

Default swimlanes:

1. Key input layer: materials, equipment, wafers, tools, IP, data, energy, or other enabling resources.
2. Product structure layer: subcomponents, modules, bottleneck processes, tests, and finished product.
3. Finished supplier layer: companies that actually ship the finished product or critical subsystem.
4. Integration/platform layer: packaging, foundry, system integration, marketplace, or platform controller.
5. Downstream customer layer: immediate customers and terminal demand.
6. Bottom data strip: market size, share, lead time, capacity, growth, adoption, or bottleneck metrics.

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
- Grey marker: weak or unverified relationship.
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
- concise tokens such as `HHI: high`, `utilization: >90%`, `qualification: 12-18 months`
- `unknown` when the metric is material but unavailable

Do not fabricate exact figures for visual polish.

## Full Report Order

Use this order for full reports:

1. title and render brief
2. panoramic industry-plus-business flowchart
3. node render data
4. edge render data
5. commercial control-point cards
6. bottleneck ranking and heatmap
7. compact process-flow ribbon if useful
8. evidence ledger
9. thesis breakers and update triggers

## Writing Rules

- Keep diagram labels short.
- Put company names in node subtitles or cards, not in every edge.
- Put evidence IDs in tables, not the diagram.
- Keep raw node/edge tables out of the rendered HTML. The renderer should consume them as data, not display them.
- Do not claim direct supply unless confirmed or clearly labeled as reported/inferred.
- If the main chart becomes too dense, split by system: product formation, commercial control points, and end demand.
- Do not render the Evidence Ledger in final HTML unless the user explicitly asks for visible citations.
- For complex maps, show merge/split relationships explicitly. Do not imply that peer companies are sequential steps.
- Use Evidence Tier 1-6 in source ledgers; do not use legacy letter source labels.
