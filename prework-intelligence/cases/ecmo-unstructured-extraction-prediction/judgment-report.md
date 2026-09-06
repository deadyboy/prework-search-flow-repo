# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: D2
- Evidence Pack path: `docs/prework-intelligence/cases/ecmo-unstructured-extraction-prediction/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`场景定制`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `E004`, `N001`.

## Conclusion Rationale

- Primary conclusion: `场景定制`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `E004`, `N001`
- Why these evidence records support the conclusion: Structured ECMO resources, ECMO ML prediction, and ICU free-text methods exist, but a complete ECMO unstructured extraction-prediction loop is not established in the searched public evidence.
- Important evidence gaps: local schema, temporal labels, endpoint definitions, privacy/ethics, and external validation.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | ECMO registry foundations exist. | cross_surface | not_applicable | current_official | `接入改造` | E001 | Use for field schema. | Local notes may differ. |
| C002 | ECMO prediction prior work exists. | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E002; E003 | Use as baseline/reference. | Mostly structured variables. |
| C003 | ICU free-text prediction methods exist. | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E004 | Reusable method analogy. | Not ECMO-specific. |
| C004 | Complete ECMO unstructured loop exists. | cross_surface | not_applicable | recent_but_unverified | `补齐缺口` | E001; E002; E003; E004; N001 | Components exist, complete workflow must be tailored. | No complete public loop found. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | ELSO Registry and data definitions | 11 | 8 | S | confirmed | Schema foundation. |
| E002 | ELSO outcome prediction scores | 9 | 5 | S | confirmed | Baseline/constraints. |
| E003 | ECMO ML mortality prediction papers | 9 | 6 | A | confirmed | Target-domain prediction evidence. |
| E004 | ICU free-text mortality prediction methods | 8 | 7 | A | confirmed | Unstructured-method analogy. |

## Why Existing Work Does Or Does Not Substitute

Existing work supports an extraction-then-modeling architecture, but not a complete off-the-shelf ECMO unstructured extraction and prediction workflow.

## What To Reuse

- ELSO fields from `E001`.
- Score/baseline framing from `E002`.
- ECMO ML modeling cautions from `E003`.
- ICU note NLP pattern from `E004`.

## What Not To Do

- Do not use one LLM classifier for extraction and prediction without schema and time windows.
- Do not treat ELSO scores as automated clinical decision systems. Cite `E002`.
- Do not use private notes as search evidence.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Complete ECMO unstructured extraction-prediction workflow | Registry, papers, ICU NLP | Supports scenario customization. | Does not prove absence. |

## Next Action

Create a non-private extraction schema and temporal-label plan before modeling; keep prediction separate from extraction validation.
