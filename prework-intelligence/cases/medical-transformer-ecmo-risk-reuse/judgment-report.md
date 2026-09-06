# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: C3
- Evidence Pack path: `docs/prework-intelligence/cases/medical-transformer-ecmo-risk-reuse/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`场景定制`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `N001`.

## Conclusion Rationale

- Primary conclusion: `场景定制`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `N001`
- Why these evidence records support the conclusion: Medical Transformer methods and ECMO ML prior work are both relevant, but the direct ECMO Transformer fit is not established and local data constraints matter.
- Important evidence gaps: local data structure, time windows, label definitions, external validation, calibration, and ethics constraints.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Medical/EHR Transformers are established for risk prediction. | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E001; E002 | Useful method and writing reference. | Data fit uncertain. |
| C002 | Med-BERT has official code and transfer value. | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E001 | Reusable method/code candidate. | Variable mapping unknown. |
| C003 | ECMO risk prediction has prior ML work. | cross_surface | not_applicable | recent_but_unverified | `场景定制` | E003 | Target-domain baseline evidence. | Often non-Transformer. |
| C004 | Direct ECMO Transformer prior work is established. | cross_surface | not_applicable | unknown_date | `先补证据` | E001; E002; E003; N001 | Direct evidence gap remains. | Deeper academic search needed. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | Med-BERT | 9 | 8 | S | confirmed | Method/code reference. |
| E002 | BEHRT | 8 | 6 | A | confirmed | Architecture precedent. |
| E003 | ECMO ML mortality prediction prior work | 9 | 5 | A | confirmed | Target-domain baseline. |

## Why Existing Work Does Or Does Not Substitute

Existing work can guide a research method and paper structure, but it does not directly substitute for a locally validated ECMO Transformer study.

## What To Reuse

- Med-BERT/BEHRT framing and reporting from `E001` and `E002`.
- ECMO baseline and endpoint cautions from `E003`.

## What Not To Do

- Do not directly transfer large EHR Transformer results to a small ECMO dataset. Cite `E001` and `E002`.
- Do not claim direct ECMO Transformer prior work from non-Transformer ECMO ML. Cite `E003` and `N001`.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Direct ECMO Transformer prior work | Academic/code search | Preserves direct-evidence gap. | Does not prove absence. |

## Next Action

Use Transformer papers as method references and ECMO ML papers as domain baselines, then design a small-data validation plan before modeling.
