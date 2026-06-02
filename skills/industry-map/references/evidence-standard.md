# Evidence Standard

Use this file to grade source quality and prevent unsupported supply-chain claims.

## Source Hierarchy

Use Evidence Tier 1-6. Do not use legacy letter source labels.

| Evidence tier | Source type | Examples | Use |
|---|---|---|---|
| Tier 1 | Confirmed official disclosure | Annual reports, 10-K/20-F, quarterly reports, official capacity announcements, named customer/supplier disclosures, regulatory filings with direct claim support | Best for confirmed relationships, capacity, capex, strategy, risk factors, named customer/supplier links |
| Tier 2 | Management statement or official company commentary | Earnings-call transcripts, investor presentations, IR Q&A, official guidance, executive interviews on company channels | Strong but label as management claim unless backed by Tier 1 disclosure |
| Tier 3 | Official adjacent-chain evidence | Supplier announcements, customer qualification comments, equipment orders, industry association data, government or standards-body data | Strong when it confirms the same node from another side |
| Tier 4 | Credible industry reporting or technical publication | Reputable trade press, technical publications, market research summaries, supply-chain news from named outlets | Useful for timing, pricing, lead time, and industry context |
| Tier 5 | Analyst or broker interpretation | Sell-side reports, industry notes, expert-call summaries when accessible | Useful but must be labeled as interpretation unless backed by Tier 1-4 evidence |
| Tier 6 | Weak signal | Social media, forums, unattributed channel checks, unsourced screenshots, anonymous rumors | Never use alone for a major claim |

## Evidence Buckets

Every important bottleneck should be tested with three buckets:

1. Company evidence: what the companies themselves disclose.
2. Industry evidence: what neutral or trade sources report.
3. Cross-chain evidence: whether upstream and downstream companies describe the same stress point.

If one bucket is missing, say so.

## Claim State Labels

Use this exact claim-state set for major claims:

| Claim state | Meaning |
|---|---|
| confirmed | Direct evidence supports the claim |
| strongly inferred | Several high-quality sources point to it, but no direct disclosure exists |
| weakly inferred | Plausible, but depends on one indirect source, old evidence, or adjacent-chain inference |
| speculative | Useful hypothesis, not yet evidence-backed |
| disputed | Sources conflict |
| stale | Evidence is older than the relevant industry cycle or has not been refreshed |

Evidence tier grades the source. Claim state grades what can be asserted from that source. Keep them separate.

## Bottleneck Heat Labels

Use this exact bottleneck-heat set:

| Bottleneck heat | Meaning |
|---|---|
| Critical | Likely to constrain system ramp now or within the stated outlook window |
| High | Plausible constraint, but timing, severity, or evidence is less certain |
| Watchlist | Structurally important, but not yet proven as a binding constraint |
| Not bottleneck | Important node, but evidence points to ample capacity, easy substitution, or weak demand proof |

Do not use `None` for a reviewed bottleneck. Use `Not bottleneck` when a candidate node was examined and rejected as a bottleneck.

## Supplier/Customer Relationship Rules

Do not write "Company A supplies Company B" unless one of the following is true:

- Company A or B publicly disclosed it.
- A reliable filing, official supplier list, or named customer announcement confirms it.
- Multiple credible industry sources report the relationship.

If not directly confirmed, write:

- "reported supplier"
- "likely supplier based on industry reporting"
- "possible supplier; public confirmation not found"
- "ecosystem exposure, not confirmed direct supply"

## Bottleneck Evidence Test

A bottleneck thesis is stronger when:

- multiple companies mention the same constraint
- customers discuss shortage, qualification, or ramp limits
- suppliers discuss booked capacity, capex, yield, lead times, or allocation
- competitors cannot quickly substitute
- the node is technically hard, regulated, or customer-qualified
- pricing power or margins reflect scarcity

A bottleneck thesis is weaker when:

- capacity expansions are already online
- customer dual-sourcing is easy
- the component is commoditized
- evidence depends on a single market rumor
- the demand driver is unproven
- the node is important but not binding

## Evidence Ledger Format

Use short source IDs in the report body and full details in the ledger.

| ID | Source | Date | Evidence tier | Claim state | Claim supported | Method / metric note | Notes |
|---|---|---|---|---|---|---|---|
| E01 | Company annual report / earnings call / report title | YYYY-MM-DD | Tier 1-6 | confirmed / strongly inferred / weakly inferred / speculative / disputed / stale |  | Calculation method if a metric is used |  |

## Optional Quantitative Bottleneck Signals

Use quantitative support when available:

| Signal | Use | Rule |
|---|---|---|
| Supplier concentration | Measures supply concentration | Prefer qualitative `high / medium / low / unknown` unless share data supports a calculation |
| HHI | Measures market concentration using share squared sum | Use only with sourced share data and show method plus evidence ID. If only top-N shares are known, label it `top-N concentration proxy` or `HHI lower-bound estimate`; never present it as full-market HHI |
| Capacity utilization | Shows whether capacity is likely binding | Use disclosed utilization, shipment/capacity data, or credible estimates only; include method and evidence ID when numeric |
| ASP trend, latest four quarters | Shows scarcity or commoditization pressure | Use company disclosure or reputable market data; include source and period |
| Qualification cycle, months | Shows customer lock-in and ramp friction | Use disclosed qualification timelines or credible industry reporting |
| Lead time / allocation signal | Shows near-term shortage or easing | Use official comments, credible channel checks, or trade reporting |
| Capex / ramp trigger | Shows when bottleneck could break | Use disclosed capex, tool delivery, or capacity-ramp announcements |

If a metric is unavailable, write `unknown`. Do not invent precision. Every numeric metric must include `method + evidence ID`.

## Source Freshness And Degradation

Every report must state an evidence cutoff.

If live or current source access is unavailable:

- still map the product structure if the structure is stable enough
- set evidence cutoff to `not refreshed`
- add source freshness status `stale` or `needs refresh`
- downgrade supplier and customer relationships to `weakly inferred` or `speculative` unless direct evidence is already available in context
- do not label any new commercial relationship as `confirmed`
- keep the Evidence Ledger non-render unless the user explicitly asks for visible citations

## Cross-Verification Matrix

For each top bottleneck:

| Bottleneck | Company evidence | Industry evidence | Cross-chain evidence | Evidence gap | Confidence |
|---|---|---|---|---|---|
|  |  |  |  |  | High/Medium/Low |

## Update Discipline

Supply-chain maps become stale quickly.

Call out when the answer depends on:

- capacity ramp dates
- customer qualification status
- product generation transitions
- export controls or sanctions
- pricing cycles
- major supplier capex
- announced but not yet delivered technology

For these cases, include an "update trigger" in the report.
