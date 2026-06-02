# Industry Structure Map

Reusable skill package for creating graph-first industry and commercial structure maps.

## Included Skill

- `skills/industry-chain-atlas/` - builds product-aware industry chain maps, commercial control-point maps, bottleneck rankings, and non-render evidence ledgers for downstream AI rendering.

## Output Philosophy

The skill produces Markdown rendering briefs, not final visible report text. It separates visible infographic blocks from non-render data such as evidence ledgers, edge tables, and renderer notes.

## Current Defaults

- Interactive scope confirmation after product decomposition for full visual reports.
- Evidence quality uses `Evidence Tier 1-6`; bottleneck heat is tracked separately.
- Competing technology routes are shown as route branches when they materially change the chain.
- Bottleneck rankings can include sourced quantitative signals such as HHI, utilization, ASP trend, qualification cycle, lead time, and capex/ramp triggers.
- Portable input/output fields live in `references/io-contract.md`; Claude Code confirmation behavior lives in `references/claude-code-adapter.md`.
