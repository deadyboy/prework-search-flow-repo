# Search Plan

Use this template inside the Search Module. This is not evidence and must not be used by the Judgment Module unless the executed results appear in the Evidence Pack.

## Case Metadata

- Case ID:
- Idea title:
- Search level:
- Search date:
- Searcher:

## Search Objective

State what the search must discover before judgment can happen.

## Claim Decomposition

Search each claim separately enough that Judgment can make claim-level local conclusions.

| claim_id | claim | surface_scope | lifecycle_scope | planned evidence needed |
| --- | --- | --- | --- | --- |
| C001 |  |  |  |  |

## Domain Routes

Mark applicable routes:

- Software or tooling:
- Academic or research:
- Product or startup:
- Patent or invention:
- R&D or technology scouting:
- Policy or process:
- Internal workflow:

## Query Matrix

| Dimension | Chinese terms | English terms | Formal terms | Product terms | User-language terms |
| --- | --- | --- | --- | --- | --- |
| Goal |  |  |  |  |  |
| Problem |  |  |  |  |  |
| Object |  |  |  |  |  |
| Method |  |  |  |  |  |
| Substitute |  |  |  |  |  |

## Planned Sources

| Source class | Planned source | Query families | Why this source matters |
| --- | --- | --- | --- |
| Web |  |  |  |
| GitHub or open source |  |  |  |
| Papers |  |  |  |
| Product directories |  |  |  |
| Communities |  |  |  |
| Patents or standards |  |  |  |
| Local or user-provided sources |  |  |  |

## Current Product Capability Gate

Use this section when the case depends on whether a current product capability exists.

- Official changelog / release notes checked:
- Current docs checked:
- Current UI or user-observed evidence available:
- Older issues or community posts used only as historical evidence:
- Freshness gaps:

## Exclusion Rules

List result types that should be ignored because they do not answer the case.

## Stopping Rules

State what makes the Search Module stop, such as source coverage, timebox, entity count, or discovery of a strong substitute.

## Negative Search Scope

State which failure cases, complaints, limitations, abandoned projects, or alternatives should be searched.

## Evidence Pack Handoff Checklist

- Query log records what was searched.
- Results are grouped by entity.
- Every entity has `entity_id`.
- Every entity has `relevance_score`, `reuse_score`, `method_similarity`, `method_note`, `source_grade`, and `evidence_status`.
- Capability Claim Matrix records `claim_id`, `surface_scope`, `lifecycle_scope`, `freshness_status`, supporting records, and gaps.
- Information gaps are explicit.
- No final judgment is included.
