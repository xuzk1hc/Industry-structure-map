# Input And Output Contract

Use this file when adapting the skill to another agent, a form UI, or a batch workflow.

## Input Schema

Required:

| Field | Type | Meaning |
|---|---|---|
| product | string | Product, product generation, or sector to map |

Optional:

| Field | Type | Default | Meaning |
|---|---|---|---|
| generation | string | current generation | Product generation, chemistry, architecture, or standard |
| geography | string | global | Global, China, US, Japan, Korea, Europe, Taiwan, or another relevant scope |
| time_horizon | string | sector-appropriate outlook | Bottleneck outlook horizon; start from 12-24 months only when the sector cycle does not imply a better window |
| depth | enum | full | `short`, `full`, or `deep_dive` |
| target_language | string | user language | Visible report language |
| output_mode | enum | interactive | `interactive` pauses at the scope confirmation gate; `one_pass` states assumptions and continues |
| deliverables | enum | markdown_and_html | `markdown_and_html`, `markdown_only`, or `html_only` |
| render_style | string | consulting long infographic | Visual style instruction for final HTML rendering |
| style_profile | string | domain-appropriate profile | Named profile from `style-profiles.md` or a custom natural-language profile |
| reference_assets | list | none | Attached screenshots, HTML reports, logos, icons, or other visual references |
| compare_routes | enum | auto | `true`, `false`, or `auto`; whether to identify competing technical routes when material |
| include_quant_signals | boolean | true | Include supplier concentration, HHI only when share data supports it, utilization, ASP trend, qualification cycle, or lead-time signals when sourced data exists |
| evidence_refresh | string | latest practical source refresh | Source recency requirement |

## Output Schema

Interactive mode first output:

| Section | Purpose |
|---|---|
| Product tree | 3-5 level product decomposition |
| Proposed swimlanes | Draft main-atlas lanes |
| Preliminary bottlenecks | Top-3 suspected constraints, not final |
| Technology routes | Route IDs and branch assumptions if routes matter |
| Confirmation request | Ask user to confirm or adjust before final atlas |

Default final delivery:

| Artifact | Purpose |
|---|---|
| `[topic]_industry-map.md` | Editable research source, graph specification, style brief, evidence record, and re-creation instructions |
| `[topic]_industry-map.html` | Directly usable rendered consulting-report infographic based on the Markdown source |

Final Markdown source sections:

| Section | Render status |
|---|---|
| Render Brief | Non-render instruction |
| Render Style Brief | Non-render natural-language visual direction and creative-freedom boundary |
| Visible HTML Requirements | Non-render instruction |
| Panoramic Industry + Business Flowchart | Visible, transformed into SVG/HTML graph |
| Compact Process-Flow Ribbon | Visible if useful; place directly below the panoramic graph |
| Node Production Data | Non-render production data |
| Edge Render Data | Non-render production data |
| Commercial Control-Point Cards | Visible, transformed into compact cards |
| Bottleneck Heat Table | Visible, transformed into vertical ranking |
| Company Badge Data | Non-render production data for logo/ticker badges |
| Evidence Ledger | Non-render source QA |
| Renderer Notes | Non-render instruction |

Final HTML requirements:

- render only the visible allowlist
- follow the Render Style Brief without using it as visible copy
- preserve relationship direction and evidence-bound meaning
- use creative rendering rather than mechanically converting all Markdown headings
- pass the automatic failure checks in `render-quality-rubric.md`

Final HTML allowlist:

- Main Title
- Panoramic Industry + Business Flowchart
- Compact Process-Flow Ribbon
- Commercial Control-Point Cards
- Bottleneck Heat Table
- Small Legend

Final HTML denylist:

- Scope Confirmation Gate
- Node Production Data
- Edge Render Data
- Company Badge Data
- Evidence Ledger
- Renderer Notes
- Render Style Brief
- raw JSON or machine-readable blocks
- raw Markdown backup
- source URL lists
- standalone layer inventory

## Evidence Fields

Use `Evidence Tier 1-6` for source quality:

- Tier 1: confirmed official disclosure
- Tier 2: management statement or official company commentary
- Tier 3: official adjacent-chain evidence
- Tier 4: credible industry reporting or technical publication
- Tier 5: analyst or broker interpretation
- Tier 6: weak signal

Use this exact claim-state set:

- confirmed
- strongly inferred
- weakly inferred
- speculative
- disputed
- stale

Use this exact bottleneck-heat set:

- Critical
- High
- Watchlist
- Not bottleneck

Every final output must include evidence cutoff and source freshness status.

## Capability Summary

This skill can:

- decompose product systems into product, component, process, equipment, material, and integration nodes
- build a graph-first industry-plus-business map
- separate visible HTML blocks from non-render production data
- prevent downstream renderers from turning non-render Markdown headings into visible report sections
- rank bottlenecks with evidence-bound qualitative and optional quantitative signals
- compare competing technology routes when they materially affect the chain
- degrade gracefully when live source access is unavailable
- deliver both a reusable Markdown source and a directly usable HTML consulting infographic
- stabilize creative HTML rendering through natural-language style profiles, visual references, hard restrictions, and a quality rubric without forcing a fixed template

## Examples

HBM:

```yaml
product: HBM
generation: HBM3E/HBM4
geography: global
time_horizon: sector-appropriate outlook, starting from 12-24 months
depth: full
output_mode: interactive
compare_routes: true
include_quant_signals: true
deliverables: markdown_and_html
style_profile: Chip-Tech Blue
```

EV battery:

```yaml
product: automotive lithium-ion battery cell and pack
generation: LFP versus NMC, graphite versus silicon-rich anode
geography: China and global
depth: full
output_mode: interactive
compare_routes: true
deliverables: markdown_and_html
style_profile: Industrial Engineering
```

Optical modules:

```yaml
product: 1.6T optical modules
generation: EML versus silicon photonics, LPO versus DSP
geography: global
depth: deep_dive
output_mode: interactive
compare_routes: true
deliverables: markdown_and_html
style_profile: Chip-Tech Blue
```
