# Industry Structure Map

Reusable skill package for creating graph-first industry and commercial structure maps.

## Included Skill

- `skills/industry-chain-atlas/` - builds product-aware industry chain maps, commercial control-point maps, bottleneck rankings, and non-render evidence ledgers for downstream AI rendering.

## Output Philosophy

The skill produces Markdown rendering briefs, not final visible report text. It separates visible infographic blocks from non-render data such as evidence ledgers, edge tables, and renderer notes.

## Current Defaults

- Interactive scope confirmation after product decomposition for full or deep-dive visual reports; short outputs skip the pause unless requested.
- Evidence quality uses `Evidence Tier 1-6`; claim state and bottleneck heat use fixed vocabularies from `references/evidence-standard.md`.
- Competing technology routes are shown as route branches when they materially change the chain.
- Bottleneck rankings can include sourced quantitative signals such as supplier concentration, HHI proxy or lower-bound estimates, utilization, ASP trend, qualification cycle, lead time, and capex/ramp triggers.
- Portable input/output fields live in `references/io-contract.md`; Claude Code confirmation behavior lives in `references/claude-code-adapter.md`.
- A compact HBM example lives in `references/hbm-mini-example.md`.
