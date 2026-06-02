# Industry Structure Map

A reusable skill package for building graph-first industry-chain and business-control maps.

The skill turns a product or sector such as HBM, EV batteries, optical modules, rockets, robotics, semiconductor equipment, energy storage, or AI infrastructure into a Markdown rendering brief that another AI or renderer can convert into a consulting-style HTML infographic.

It is designed for users who need a detailed industry plus commercial graph, not a generic upstream/midstream/downstream summary.

## What This Skill Does

- Decomposes a final product into modules, subcomponents, materials, processes, equipment, integration, testing, and downstream demand.
- Maps suppliers, customers, competitors, substitutes, route alternatives, commercial control points, and bottlenecks.
- Produces a graph-first Markdown brief for HTML rendering, not a prose-first research memo.
- Separates visible report blocks from non-render production data.
- Enforces evidence tiers, claim-state labels, bottleneck heat labels, renderer allowlists, and company logo/ticker badge data.

## When To Use It

Use this skill when you want:

- a panoramic industry plus business flowchart
- product structure and commercial relationships in one map
- process-chain context without burying the report in process detail
- commercial control-point cards
- bottleneck ranking and heat levels
- source-backed claims with evidence quality labels
- a Markdown instruction file that can guide another AI to render a long-form HTML consulting infographic

Typical targets include:

- HBM / advanced memory / advanced packaging
- EV batteries / energy storage / battery materials
- optical modules / silicon photonics / AI networking
- rockets / launch services / satellite infrastructure
- humanoid robots / industrial robots
- semiconductor equipment / materials / fabs
- AI data centers / cooling / power infrastructure

## What It Produces

The expected output is a Markdown rendering brief. The final rendered HTML should look like a long-form consulting infographic or industry atlas.

Visible report blocks normally include:

- title area with compact metric chips
- one panoramic industry plus business graph
- compact commercial control-point cards
- top-to-bottom bottleneck heat ranking
- optional process-flow ribbon or drilldown
- legend for route colors, claim states, and bottleneck heat

Non-render production data may also be included in the Markdown brief, but it must not be shown directly in the final HTML:

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
10. Assemble a Markdown brief that tells the next AI or renderer exactly what to show and what not to show.

## Output Safeguards

- Do not output only a simple upstream/midstream/downstream table.
- Do not make a company-only map. Product, component, process, and integration nodes must drive the graph.
- Do not render evidence ledgers, source URLs, raw JSON, renderer notes, or node/edge production tables as visible report sections.
- Do not create standalone inventory sections such as `产业分层节点` unless the user explicitly asks for a technical appendix.
- Use the user's target language for visible headings, nodes, cards, legends, and labels.
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
| `skills/industry-chain-atlas/SKILL.md` | Skill entrypoint, trigger description, workflow, and hard rules |
| `skills/industry-chain-atlas/agents/openai.yaml` | OpenAI/Codex metadata, input schema, output schema, and examples |
| `skills/industry-chain-atlas/references/workflow.md` | Detailed step-by-step workflow |
| `skills/industry-chain-atlas/references/report-template.md` | Markdown scaffold and HTML rendering contract |
| `skills/industry-chain-atlas/references/visual-report-pattern.md` | Long infographic layout rules |
| `skills/industry-chain-atlas/references/graph-schema.md` | Node, edge, route, and company badge schemas |
| `skills/industry-chain-atlas/references/evidence-standard.md` | Evidence Tier 1-6, claim states, and bottleneck heat vocabulary |
| `skills/industry-chain-atlas/references/io-contract.md` | Portable input and output contract |
| `skills/industry-chain-atlas/references/claude-code-adapter.md` | Claude Code confirmation behavior and portability notes |
| `skills/industry-chain-atlas/references/hbm-mini-example.md` | Compact example using HBM |

## Quick Start Prompts

Use the skill for HBM:

```text
Use $industry-chain-atlas to build a graph-first Markdown atlas for HBM3E/HBM4.
Use global scope, a 12-24 month bottleneck outlook, Chinese visible labels, and interactive scope confirmation.
The final Markdown should guide another AI to render a blue chip-tech style HTML long infographic.
```

Use the skill for rockets:

```text
Use $industry-chain-atlas to map the launch vehicle industry.
Focus on reusable rockets, propulsion, avionics/GNC, structures, ground test, launch sites, launch services, satellite-constellation demand, commercial control points, and bottlenecks.
Use Chinese visible labels and include company logo/ticker badge data where possible.
```

## Installation

Install or copy the skill folder into your skill runtime:

```text
skills/industry-chain-atlas/
```

Then invoke the skill by name:

```text
$industry-chain-atlas
```

## Current Status

This repository currently contains one skill: `industry-chain-atlas`.

The package is meant to be portable across AI agents. Runtime-specific metadata is kept in `agents/`, while the main workflow and rendering contract live in `references/`.
