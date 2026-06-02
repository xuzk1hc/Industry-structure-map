# Workflow

Use this file for a full industry-chain atlas, especially when the user asks for a Markdown report or a consulting-style industry map.

## 1. Scope Gate

Clarify only what is needed, then proceed with reasonable defaults.

Minimum scope fields:

- product or sector: the actual object being mapped, such as HBM3E, HBM4, LFP battery cells, NMC battery cells, SiC MOSFETs, 1.6T optical modules
- product boundary: final product, component family, manufacturing process, or full ecosystem
- geography: global by default; add China, US, Japan, Korea, Europe, or Taiwan if relevant
- horizon: sector-appropriate bottleneck outlook; use 12-24 months as a starting point, then adjust for capacity cycle, qualification cycle, or product iteration speed
- output depth: short map, full Markdown report, deep dive, or company drilldown
- mode: interactive by default for full or deep-dive visual reports; one-pass only when the user asks to skip confirmation

If the user gives only a sector name, use:

- geography: global
- horizon: sector-appropriate outlook, usually starting from current state plus 12-24 months
- output: full Markdown atlas
- evidence: current public sources where available

## 2. Product Definition

Start with a precise product/system definition.

Bad:

- "HBM industry chain"
- "EV battery upstream and downstream"

Good:

- "HBM3E/HBM4 stack used with AI accelerators, including DRAM dies, TSV, microbump/hybrid bonding, base die logic, interposer/CoWoS integration, test, and AI accelerator customer qualification."
- "Automotive lithium-ion battery cell and pack system, split by cathode chemistry, anode material, separator, electrolyte, cell format, BMS, module/pack design, and OEM integration."

Required questions:

- What is the final product?
- What generation, chemistry, architecture, or standard matters?
- What performance constraint drives the chain?
- Which part of the chain gets paid now, and which part gets paid later?

## 3. Product Decomposition

Create a product structure tree before discussing companies.

Break the product into:

- final product
- systems or modules
- key subcomponents
- critical materials
- process steps
- manufacturing equipment
- packaging/assembly
- testing/qualification
- downstream integration

For each component or process node, capture:

- function in the final product
- required input
- output delivered to the next node
- relevant variants or design choices
- what can and cannot be substituted

Important: show composition and optionality. Many products are not one fixed chain.

Examples:

- EV batteries can combine LFP/NMC cathodes, graphite/silicon anodes, wet/dry separators, liquid/solid electrolytes, cylindrical/prismatic/pouch formats, and different pack structures.
- HBM combines DRAM die technology, TSV, bonding, base die or logic interface, advanced packaging, interposer/substrate, thermal handling, and GPU/accelerator qualification.

## 3.5 Scope Confirmation Gate

Pause after product decomposition for `full` or `deep_dive` visual-map tasks.

Show a brief structured summary:

- product tree, 3-5 levels
- proposed swimlanes for the main atlas
- top-3 suspected bottlenecks, clearly marked as preliminary
- major technology-route choices or design variants, if any
- assumptions that will affect the graph

Ask the user to confirm or adjust before proceeding to atlas design.

For `short` outputs, do not pause unless the user asks for confirmation.

If the user explicitly asks for a one-pass answer, skip the pause but state the product-tree assumptions before continuing.

## 4. Technology-Route Divergence

Before the main atlas, check whether the product has meaningful route competition.

Examples:

- optical modules: EML versus silicon photonics; LPO versus DSP-retimed architectures
- batteries: LFP versus NMC; graphite versus silicon-rich anode; liquid versus solid electrolyte
- AI memory: HBM versus GDDR, CXL memory pooling, on-package SRAM, or other memory hierarchy alternatives
- power semiconductors: SiC MOSFET versus IGBT or GaN in relevant voltage/power ranges

When routes matter:

- assign route IDs such as `R1`, `R2`, `R3`
- use route colors or branch labels in the main graph
- add `alternative route impact` or `替代路线影响` to commercial control-point cards
- include the route's impact on bottleneck strength, customer qualification, capex, and substitution risk

Skip this step when there is no material route split. Do not invent a route battle for visual symmetry.

## 5. Process-Chain Mapping

After decomposition, map how pieces become the final product.

Use at least three views:

- product structure: what the product is made of
- process flow: how inputs become outputs
- commercial chain: who sells to whom, who certifies whom, and who competes with whom

Avoid generic links such as "materials -> components -> final product" unless each link is expanded into real nodes.

For each link, ask:

- What physical, chemical, software, design, or qualification transformation occurs here?
- Which node controls yield, performance, cost, or delivery time?
- What must be true before the downstream node can ramp?
- Is the constraint capacity, yield, quality, certification, IP, tooling, materials, geopolitics, or customer concentration?

## 6. Visual Atlas Design

For consulting-style Markdown or HTML reports, build the visual hierarchy before writing all text.

Default visual system:

1. Panoramic industry-chain atlas: one main diagram that merges product structure and business relationships.
2. Process-flow ribbon: a compact manufacturing sequence below or after the main diagram.
3. Commercial control-point cards: 4-8 compact cards explaining where power, margin, qualification, and bottlenecks sit.
4. Node atlas table: dense facts that do not fit inside the diagram.
5. Bottleneck heatmap: rank constraints and falsification tests.

Main diagram rule:

- The main diagram should use product/component/process nodes as the skeleton.
- Companies should appear as node labels, leader lists, side cards, or dashed relationship overlays.
- Process details should appear only as a compact centerline unless the user asks for a process deep dive.

When the report needs to resemble a long-form infographic, read [visual-report-pattern.md](visual-report-pattern.md).

## 7. Company-Role Mapping

For each important node, identify:

- global leaders
- regional leaders or challengers
- downstream customers
- key competitors
- substitute technologies or alternate suppliers
- customer qualification status if public evidence exists

Use roles rather than generic labels:

- final-product integrator
- core component supplier
- bottleneck material supplier
- equipment/tooling gatekeeper
- yield/test enabler
- packaging/foundry partner
- downstream system customer
- design owner
- platform controller
- emerging substitute

For listed companies, capture logo/ticker hints where practical. For private companies, capture logo/wordmark or fallback badge text.

## 8. Bottleneck Ranking

A bottleneck is a node that can limit system ramp, not merely a famous company.

Rank candidate bottlenecks across:

- supply concentration
- substitutability
- capacity ramp time
- qualification/certification cycle
- yield or reliability difficulty
- material or equipment scarcity
- customer dependency
- geopolitical exposure
- pricing power
- evidence strength

Optional quantitative signals, only when data is available:

- supplier concentration, usually `high / medium / low / unknown`
- HHI only when share data supports the calculation
- capacity utilization estimate
- ASP trend over the latest four quarters
- qualification or certification cycle in months
- lead time, allocation, or booked-capacity signal
- capex, tool delivery, or capacity-ramp trigger

If data is unavailable, write `unknown` or omit the metric. Do not estimate precise figures without evidence. Numeric metrics require method plus evidence ID; top-N share math must be labeled as a proxy or lower-bound estimate, not full-market HHI.

Use the bottleneck-heat labels from [evidence-standard.md](evidence-standard.md):

- Critical: likely to constrain system ramp now or within the stated outlook window.
- High: plausible constraint, but timing or evidence is less certain.
- Watchlist: structurally important, but not yet proven as the binding constraint.
- Not bottleneck: important node, but ample capacity, easy substitution, or weak demand proof.

## 9. Evidence Cross-Check

Do not let one source drive the map.

For each major bottleneck, seek at least three angles:

- company evidence: filings, earnings calls, investor decks, official announcements
- industry evidence: trade press, industry association data, credible market research, capacity news
- cross-chain evidence: upstream supplier and downstream customer describe the same constraint

Output claim state using the exact labels from [evidence-standard.md](evidence-standard.md):

- confirmed
- strongly inferred
- weakly inferred
- speculative
- disputed
- stale

Grade source quality with Evidence Tier 1-6 from [evidence-standard.md](evidence-standard.md). Do not use legacy letter source labels.

If live source access is unavailable, follow the degradation rules in [evidence-standard.md](evidence-standard.md): set evidence cutoff to `not refreshed`, treat source freshness as stale, and do not introduce new confirmed supplier/customer claims.

## 10. Report Assembly

The final Markdown production brief should include:

- executive summary
- scope and assumptions
- final-product definition
- evidence cutoff and source freshness status
- panoramic industry-chain atlas that merges product structure and business relationships
- process-flow ribbon or focused process-chain map
- commercial control-point map
- node-by-node atlas table
- bottleneck ranking
- supplier/customer/competitor matrix
- evidence ledger
- thesis breakers and update triggers
- appendix for unresolved questions

The final HTML must not render every Markdown section. It must follow the visible-section allowlist in [report-template.md](report-template.md).

Use [report-template.md](report-template.md) for the exact scaffold.
