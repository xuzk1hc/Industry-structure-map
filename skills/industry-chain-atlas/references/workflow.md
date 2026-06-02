# Workflow

Use this file for a full industry-chain atlas, especially when the user asks for a Markdown report or a consulting-style industry map.

## 1. Scope Gate

Clarify only what is needed, then proceed with reasonable defaults.

Minimum scope fields:

- product or sector: the actual object being mapped, such as HBM3E, HBM4, LFP battery cells, NMC battery cells, SiC MOSFETs, 1.6T optical modules
- product boundary: final product, component family, manufacturing process, or full ecosystem
- geography: global by default; add China, US, Japan, Korea, Europe, or Taiwan if relevant
- horizon: current state plus 12-24 month bottleneck outlook by default
- output depth: short map, full Markdown report, or company drilldown

If the user gives only a sector name, use:

- geography: global
- horizon: current state plus 12-24 months
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

## 4. Process-Chain Mapping

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

## 5. Visual Atlas Design

For consulting-style Markdown or HTML reports, build the visual hierarchy before writing all text.

Default visual system:

1. Panoramic industry-chain atlas: one main diagram that merges product structure and business relationships.
2. Process-flow ribbon: a compact manufacturing sequence below or after the main diagram.
3. Commercial control-point cards: 6-8 cards explaining where power, margin, qualification, and bottlenecks sit.
4. Node atlas table: dense facts that do not fit inside the diagram.
5. Bottleneck heatmap: rank constraints and falsification tests.

Main diagram rule:

- The main diagram should use product/component/process nodes as the skeleton.
- Companies should appear as node labels, leader lists, side cards, or dashed relationship overlays.
- Process details should appear only as a compact centerline unless the user asks for a process deep dive.

When the report needs to resemble a long-form infographic, read [visual-report-pattern.md](visual-report-pattern.md).

## 6. Company-Role Mapping

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

## 7. Bottleneck Ranking

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

Use the following labels:

- Tier 1 bottleneck: likely to constrain system ramp now or within 12-24 months, with strong evidence.
- Tier 2 bottleneck: plausible constraint, but timing or evidence is less certain.
- Watchlist bottleneck: structurally important, but not yet proven as the binding constraint.
- False bottleneck: important node, but ample capacity, easy substitution, or weak demand proof.

## 8. Evidence Cross-Check

Do not let one source drive the map.

For each major bottleneck, seek at least three angles:

- company evidence: filings, earnings calls, investor decks, official announcements
- industry evidence: trade press, industry association data, credible market research, capacity news
- cross-chain evidence: upstream supplier and downstream customer describe the same constraint

Output the evidence state clearly:

- confirmed
- likely inferred
- unverified
- disputed
- stale and needs refresh

## 9. Report Assembly

The final Markdown should include:

- executive summary
- scope and assumptions
- final-product definition
- panoramic industry-chain atlas that merges product structure and business relationships
- process-flow ribbon or focused process-chain map
- commercial control-point map
- node-by-node atlas table
- bottleneck ranking
- supplier/customer/competitor matrix
- evidence ledger
- thesis breakers and update triggers
- appendix for unresolved questions

Use [report-template.md](report-template.md) for the exact scaffold.
