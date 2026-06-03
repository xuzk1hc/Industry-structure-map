---
name: industry-map
description: Use when the user wants a structured industry-chain atlas for a product or sector such as HBM, EV batteries, semiconductors, robotics, energy storage, or AI infrastructure, including product decomposition, supplier/customer/competitor mapping, bottleneck ranking, evidence cross-checking from filings/reports/news, and Markdown output designed for HTML consulting-report rendering.
---

# Industry Map

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
- For portable input/output fields, examples, and agent-neutral contract details, read [references/io-contract.md](references/io-contract.md).
- For Claude Code-style confirmation behavior and portability notes, read [references/claude-code-adapter.md](references/claude-code-adapter.md).
- For a compact end-to-end example, read [references/hbm-mini-example.md](references/hbm-mini-example.md).

## Required Workflow

Use this order unless the user explicitly requests a narrower task:

1. Scope gate: identify product, generation, geography, time horizon, and desired output depth.
2. Product decomposition: break the final product into modules, subcomponents, materials, equipment, processes, testing, and integration.
2.5. Scope confirmation gate: show the product tree, proposed swimlanes, preliminary top-3 bottlenecks, and major route choices; ask the user to confirm or adjust before drawing the main atlas. If the user explicitly asks for one-pass output, proceed but state assumptions.
3. Technology-route divergence: when clear competing routes exist, identify them before graph design and preserve them as colored branches or route labels.
4. Main atlas design: for report-style outputs, merge the product structure tree and business relationship chain into one panoramic industry map; keep the process chain as a second-layer ribbon or drilldown.
5. Process-chain mapping: show how raw inputs become components, how components become subsystems, and how subsystems become the final product.
6. Company-role mapping: for each node, name global leaders, important regional players, downstream customers, competitors, and likely substitutes.
7. Bottleneck ranking: identify where demand growth would break the chain first; add optional quantitative signals only when data is available.
8. Evidence cross-check: validate key claims with company evidence, research/report evidence, and industry-news evidence using Evidence Tier 1-6.
9. Markdown assembly: output a graph-first Markdown file whose primary artifact is the industry-plus-business flowchart; tables, cards, bottleneck notes, and evidence are supporting render data.

## Hard Rules

- Never output only a simple upstream/midstream/downstream table.
- For visual report requests, do not make company-only maps. Product/component/process nodes must be the primary structure; companies are labels, role cards, or relationship overlays.
- The Markdown artifact is an instruction/specification for the next renderer, not the visible report body.
- Clearly mark visible sections and non-render sections. The renderer must not place Evidence Ledger, Renderer Notes, source URLs, or long reasoning paragraphs into the final HTML.
- Node Production Data, Edge Render Data, and other production tables are inputs for image/HTML generation only. They must not appear as raw tables in the final rendered HTML unless explicitly transformed into visual nodes, arrows, cards, or hidden QA metadata.
- Renderers must use a visible-section allowlist, not all Markdown headings. Do not create final HTML sections from Scope Confirmation Gate, Node Production Data, Edge Render Data, Evidence Ledger, Renderer Notes, JSON blocks, raw Markdown backups, source URL lists, observation tables, or other machine-readable sections.
- Layer or swimlane metadata must not become a standalone visible section such as `产业分层节点`. Use it only as background lanes, grouping labels, or layout metadata inside the main graph unless the user explicitly asks for a technical appendix.
- Use the user's target language for visible labels. For Chinese reports, all visible headings, card labels, node names, and legends should be Chinese.
- Avoid decorative explanatory prose in the visible hero. The first screen should usually contain only the main title, optional evidence-cutoff text, and compact chips/tags. Do not place a long thesis sentence, route explanation, or time-window paragraph under the title unless the user explicitly asks for it.
- In the panoramic graph, arrows and connector lines must never cover node titles, company names, badges, tickers, key metrics, or bottleneck labels. Use routed edges, lane gutters, anchor points on node borders, and enough spacing; if overlap remains, split the graph or move detail into a drilldown.
- Place the compact product-formation/process flow directly below the panoramic industry-plus-business flowchart when included. Do not bury it after all business cards and bottleneck tables unless the user requests that order.
- Bottleneck heatmaps should default to a top-to-bottom ranking layout: long, narrow horizontal rows or a slim table, not a wide grid of cards. Each row should show rank, node, bottleneck judgement, constraint type, and heat level.
- Commercial control points should be compact and easy to scan. Prefer two-column cards with only short fields such as `控制`, `龙头`, and `瓶颈`; avoid paragraph-style explanations inside these cards.
- Company annotations in visible HTML should use logo or wordmark plus ticker badges for listed companies whenever practical. For private companies, use a logo/wordmark or consistent text badge; do not invent tickers. Avoid plain comma-separated company lists in visible graph nodes or cards when badge data is available.
- Use Evidence Tier 1-6 for source quality. Do not use legacy letter source labels.
- Keep evidence quality separate from bottleneck heat. Evidence Tier 1-6 grades sources; bottleneck heat grades system constraint severity.
- Every output must include an evidence cutoff. If current source access is unavailable, set it to `not refreshed` and apply the degradation rules in [references/evidence-standard.md](references/evidence-standard.md).
- Use the exact claim-state and bottleneck-heat vocabularies from [references/evidence-standard.md](references/evidence-standard.md).
- Quantitative bottleneck signals are optional and evidence-bound. Use supplier concentration, HHI, capacity utilization, ASP trend, qualification cycle, lead time, or capex/ramp signals only when data is available; otherwise mark `unknown` and do not guess. Numeric metrics require method plus evidence ID.
- When competing technical routes matter, show route branches in the main graph and add `替代路线影响` to control-point cards.
- Never claim supplier/customer relationships without labeling whether they are confirmed, inferred, or speculative.
- Never present a company as a bottleneck merely because it is a market leader; explain the actual constraint.
- Every major node must have an input, output, role in final-product formation, company leaders, claim state, and source freshness.
- Every major bottleneck call must include at least one falsification test.
- If live source access is unavailable, state that source verification is incomplete and mark claims as needing refresh.

## Default Output

For a full request, produce a graph-first Markdown artifact using the template in [references/report-template.md](references/report-template.md).

For a short answer, still include:

- one product/system definition
- one industry-plus-business flowchart
- compact node and edge render data
- company badge data when companies are shown visibly
- top 3 bottlenecks
- strongest evidence and weakest assumption
- what to verify next

## Source Category Discipline

Always separate:

- confirmed disclosure
- management claim
- reputable third-party reporting
- analyst/research-report interpretation
- inference from adjacent-chain evidence
- speculation

These are source or reasoning categories, not claim-state labels.

Use Evidence Tier 1-6 to grade the source behind each claim. Use the claim-state labels defined in [references/evidence-standard.md](references/evidence-standard.md).

Use current, source-backed information whenever possible. For public companies, prefer annual reports, quarterly reports, earnings-call transcripts, investor presentations, official announcements, and credible industry publications before market commentary.

## Final Artifact Bias

The final artifact should behave like a renderable graph specification, not a long memo or stock-picking note.

It may mention listed companies, but the primary object is the industry system:

- how the product is made
- who controls each node
- where bottlenecks sit
- how evidence supports or weakens the map
- what changes would force the map to be redrawn

Default Markdown production structure. This is not the final HTML render order:

1. graph render brief
2. one panoramic industry-plus-business flowchart
3. compact process ribbon if useful
4. compact commercial control-point cards
5. vertical bottleneck heat ranking
6. non-render node production table
7. non-render edge render table
8. non-render evidence ledger
