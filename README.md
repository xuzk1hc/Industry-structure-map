# Industry Map

A reusable skill package for building graph-first industry-chain and business-control maps.

The skill turns a product or sector such as HBM, EV batteries, optical modules, rockets, robotics, semiconductor equipment, energy storage, or AI infrastructure into two coordinated outputs: a reusable Markdown research/rendering source and a directly usable HTML consulting infographic.

It is designed for users who need a detailed industry plus commercial graph, not a generic upstream/midstream/downstream summary.

## What This Skill Does

- Decomposes a final product into modules, subcomponents, materials, processes, equipment, integration, testing, and downstream demand.
- Maps suppliers, customers, competitors, substitutes, route alternatives, commercial control points, and bottlenecks.
- Produces a graph-first Markdown source plus a rendered HTML consulting report by default.
- Separates visible report blocks from non-render production data.
- Enforces evidence tiers, claim-state labels, bottleneck heat labels, renderer allowlists, and company logo/ticker badge data.
- Stabilizes creative rendering through natural-language style profiles, visual references, anti-patterns, and a quality rubric without forcing a fixed HTML template.

## When To Use It

Use this skill when you want:

- a panoramic industry plus business flowchart
- product structure and commercial relationships in one map
- process-chain context without burying the report in process detail
- commercial control-point cards
- bottleneck ranking and heat levels
- source-backed claims with evidence quality labels
- an immediately usable HTML consulting infographic plus a Markdown source that can be sent to another AI for re-rendering or further creation

Typical targets include:

- HBM / advanced memory / advanced packaging
- EV batteries / energy storage / battery materials
- optical modules / silicon photonics / AI networking
- rockets / launch services / satellite infrastructure
- humanoid robots / industrial robots
- semiconductor equipment / materials / fabs
- AI data centers / cooling / power infrastructure

## Default Deliverables

Every full run produces:

| Artifact | Purpose |
| --- | --- |
| `[topic]_industry-map.md` | Editable research source, graph specification, evidence record, style brief, and re-creation instructions |
| `[topic]_industry-map.html` | Directly usable rendered consulting-report infographic |

The HTML should look intentionally designed rather than mechanically converted from Markdown. The renderer retains freedom over SVG, Canvas, HTML/CSS, typography, layout geometry, and restrained motion.

Visible report blocks normally include:

- title area with compact metric chips
- one panoramic industry plus business graph
- compact product-formation/process ribbon directly below the main graph when useful
- compact commercial control-point cards
- top-to-bottom bottleneck heat ranking
- legend for route colors, claim states, and bottleneck heat

Non-render production data may also be included in the Markdown brief, but it must not be shown directly in the final HTML:

- Render Style Brief
- Scope Confirmation Gate
- Node Production Data
- Edge Render Data
- Company Badge Data
- Evidence Ledger
- Renderer Notes
- raw JSON or other machine-readable blocks
- source URL lists and raw Markdown backups

## Key Rendering Rule

The final HTML renderer must use a visible-section allowlist.

Do not render every Markdown heading into the report. In particular, do not create visible HTML sections for production-only blocks such as `Node Production Data`, `Edge Render Data`, `Evidence Ledger`, `Renderer Notes`, source lists, JSON blocks, or standalone layer inventories.

Layer or swimlane metadata is only layout metadata. It should become background lanes, grouping labels, or graph structure inside the main map. It should not appear as a standalone section such as `产业分层节点`.

## Controlled Creative Rendering

The skill does not require a fixed HTML template or mandatory JSON schema.

Instead, rendering quality is bounded by:

- a natural-language Render Style Brief
- reusable style profiles
- visual-reference and asset guidance
- optional external motion and interaction references such as React Bits
- explicit anti-patterns
- hard visible-section and legibility restrictions
- a scored render-quality rubric and automatic failure conditions

This preserves differences between AI renderers while establishing a consistent quality floor.

## Why It Is Different

- Product-first: it starts from how the final product is formed, not from a simple upstream/midstream/downstream table.
- Graph-first: the main artifact is an industry plus business flowchart, not a long article.
- Commercially useful: it highlights control points, route divergence, customer validation, capacity constraints, and substitution risk.
- Evidence-aware: it uses `Evidence Tier 1-6`, fixed claim-state labels, and source freshness rules.
- Renderer-safe: it explicitly separates visible infographic blocks from machine instructions and evidence ledgers.
- Visual-ready: company labels should use logo or wordmark plus ticker badges where practical; private companies use logo or text badges without invented tickers.

## Workflow

1. Define scope: product, generation, geography, time horizon, and output depth.
2. Decompose the product: modules, materials, processes, equipment, testing, and integration.
3. Confirm scope: show the product tree, proposed swimlanes, preliminary bottlenecks, and route choices before drawing the main atlas.
4. Identify technology-route divergence when competing routes materially change the chain.
5. Design the main atlas by merging product structure and commercial relationships.
6. Add process-chain context as a ribbon, branch, or drilldown instead of a standalone process memo.
7. Map company roles: leaders, challengers, customers, competitors, and substitutes.
8. Rank bottlenecks with evidence-bound quantitative signals when available.
9. Cross-check important claims with filings, reports, earnings materials, research, and industry news.
10. Assemble the reusable Markdown source, including the non-render Render Style Brief.
11. Render the Markdown source into an HTML consulting infographic with creative freedom inside the hard restrictions.
12. Inspect and revise the actual HTML using the render-quality rubric before delivering both files.

## Output Safeguards

- Do not output only a simple upstream/midstream/downstream table.
- Do not make a company-only map. Product, component, process, and integration nodes must drive the graph.
- Do not render evidence ledgers, source URLs, raw JSON, renderer notes, or node/edge production tables as visible report sections.
- Do not create standalone inventory sections such as `产业分层节点` unless the user explicitly asks for a technical appendix.
- Use the user's target language for visible headings, nodes, cards, legends, and labels.
- Keep the title area compact: main title, optional evidence-cutoff text, and chips/tags only by default. Do not place a long explanatory paragraph under the title.
- Route graph arrows around text and badges. Lines must not cover node labels, company logos, ticker badges, metric chips, or bottleneck tags.
- Place the product-formation/process flow directly below the panoramic graph when included.
- For listed companies, prefer logo or wordmark plus ticker badge. For private companies, use logo or consistent text badge without inventing stock codes.
- Keep commercial control-point cards compact: `控制`, `龙头`, `瓶颈`, and `替代路线影响` when relevant.
- Bottleneck heatmaps should default to a vertical top-to-bottom ranking with long, narrow rows.
- Use quantitative signals only when data is available. If unavailable, mark `unknown` and do not guess.

## Evidence Standard

The skill uses `Evidence Tier 1-6`.

- Tier 1: confirmed company disclosure or official filing
- Tier 2: management statement or investor communication
- Tier 3: reputable third-party reporting
- Tier 4: analyst or research-report interpretation
- Tier 5: inference from adjacent-chain evidence
- Tier 6: weak or speculative signal

Evidence quality is separate from bottleneck heat. A node can be hot but weakly evidenced, or well evidenced but not a bottleneck.

## Repository Layout

| Path | Purpose |
| --- | --- |
| `skills/industry-map/SKILL.md` | Skill entrypoint, trigger description, workflow, and hard rules |
| `skills/industry-map/agents/openai.yaml` | OpenAI/Codex metadata, input schema, output schema, and examples |
| `skills/industry-map/references/workflow.md` | Detailed step-by-step workflow |
| `skills/industry-map/references/report-template.md` | Markdown scaffold and HTML rendering contract |
| `skills/industry-map/references/visual-report-pattern.md` | Long infographic layout rules |
| `skills/industry-map/references/graph-schema.md` | Node, edge, route, and company badge schemas |
| `skills/industry-map/references/evidence-standard.md` | Evidence Tier 1-6, claim states, and bottleneck heat vocabulary |
| `skills/industry-map/references/io-contract.md` | Portable input and output contract |
| `skills/industry-map/references/claude-code-adapter.md` | Claude Code confirmation behavior and portability notes |
| `skills/industry-map/references/hbm-mini-example.md` | Compact example using HBM |
| `skills/industry-map/references/render-style-brief.md` | Natural-language visual direction and creative-freedom boundary |
| `skills/industry-map/references/style-profiles.md` | Reusable visual-style profiles |
| `skills/industry-map/references/visual-reference-library.md` | Reference-image, asset, and anti-pattern guidance |
| `skills/industry-map/references/external-design-libraries.md` | Optional motion and interaction libraries, including React Bits usage rules |
| `skills/industry-map/references/render-quality-rubric.md` | HTML scoring and automatic failure conditions |

## Quick Start Prompts

Use the skill for HBM:

```text
Use $industry-map to build an HBM3E/HBM4 industry map.
Use global scope, a 12-24 month bottleneck outlook, Chinese visible labels, and interactive scope confirmation.
Deliver both the reusable Markdown source and a rendered HTML consulting infographic.
Use the Chip-Tech Blue style profile, retain creative freedom, and inspect the rendered HTML before delivery.
```

Use the skill for rockets:

```text
Use $industry-map to map the launch vehicle industry.
Focus on reusable rockets, propulsion, avionics/GNC, structures, ground test, launch sites, launch services, satellite-constellation demand, commercial control points, and bottlenecks.
Use Chinese visible labels, the Industrial Engineering style profile, and company logo/ticker badge data where possible.
Deliver both the Markdown source and the rendered HTML report.
```

## Installation

Install or copy the skill folder into your skill runtime:

```text
skills/industry-map/
```

Then invoke the skill by name:

```text
$industry-map
```

## Current Status

This repository currently contains one skill: `industry-map`.

The package is meant to be portable across AI agents. Runtime-specific metadata is kept in `agents/`, while the main workflow and rendering contract live in `references/`.
