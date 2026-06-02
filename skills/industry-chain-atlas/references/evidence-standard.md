# Evidence Standard

Use this file to grade source quality and prevent unsupported supply-chain claims.

## Source Hierarchy

Grade evidence by source type:

| Grade | Source type | Examples | Use |
|---|---|---|---|
| A | Direct official evidence | Annual reports, 10-K/20-F, quarterly reports, earnings-call transcripts, investor presentations, official capacity announcements, customer/supplier disclosures | Best for confirmed relationships, capacity, capex, strategy, risk factors |
| B | Official adjacent-chain evidence | Supplier announcement, customer qualification comment, equipment order, regulatory filing, industry association data | Strong when it confirms the same node from another side |
| C | Credible industry reporting | Reputable trade press, technical publications, market research summaries, supply-chain news | Useful for timing, pricing, lead time, and industry context |
| D | Analyst or broker interpretation | Sell-side reports, industry notes, expert-call summaries when accessible | Useful but must be labeled as interpretation unless backed by direct evidence |
| E | Weak signal | Social media, forums, unattributed channel checks, unsourced screenshots | Never use alone for a major claim |

## Evidence Buckets

Every important bottleneck should be tested with three buckets:

1. Company evidence: what the companies themselves disclose.
2. Industry evidence: what neutral or trade sources report.
3. Cross-chain evidence: whether upstream and downstream companies describe the same stress point.

If one bucket is missing, say so.

## Claim Labels

Label major claims:

- Confirmed: direct evidence supports the claim.
- Strongly inferred: several high-quality sources point to it, but no direct disclosure exists.
- Weakly inferred: plausible, but depends on one indirect source or old evidence.
- Speculative: useful hypothesis, not yet evidence-backed.
- Disputed: sources conflict.
- Stale: evidence is older than the current cycle and needs refresh.

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

| ID | Source | Date | Evidence grade | Claim supported | Notes |
|---|---|---|---|---|---|
| E01 | Company annual report / earnings call / report title | YYYY-MM-DD | A/B/C/D/E |  |  |

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
