# Evidence Pack

This is the Search Module handoff artifact for Case C3. It records evidence, not final decisions.

## Case Metadata

- Case ID: C3
- Idea title: Medical Transformer risk prediction reuse
- Search level: L3 deep review
- Search date: 2026-07-09
- Searcher: Codex with independent research subagent brief

## Coverage Summary

- Searched source classes: peer-reviewed papers; official code; ECMO ML literature.
- Unsearched source classes: full clinical guideline review; local ECMO dataset; ethics/IRB review; external validation details beyond recorded sources.
- Languages searched: English.
- Coverage note: Sufficient for research-method reuse framing, not for clinical deployment.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | academic | Nature / Scientific Reports | BEHRT Med-BERT EHR Transformer risk prediction | several | E001; E002 | Medical Transformer evidence. |
| Q002 | academic/code | GitHub / NPJ | Med-BERT official code | 1 | E001 | Reuse candidate. |
| Q003 | academic | ECMO ML papers | ECMO mortality machine learning risk prediction | several | E003 | Target-domain evidence. |
| Q004 | negative search | academic | ECMO Transformer Med-BERT risk prediction | 0 strong | N001 | Direct ECMO Transformer gap. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Medical/EHR Transformers are established for risk prediction. | cross_surface | not_applicable | recent_but_unverified | E001; E002 | none | confirmed | Dataset structure may differ. |
| C002 | Med-BERT has official code and possible small-data transfer value. | cross_surface | not_applicable | recent_but_unverified | E001 | none | confirmed | Variable mapping and pretraining fit unknown. |
| C003 | ECMO risk prediction has prior ML work. | cross_surface | not_applicable | recent_but_unverified | E003 | none | confirmed | Many models are structured-variable, not Transformer notes. |
| C004 | Direct ECMO Transformer risk-prediction prior work is established. | cross_surface | not_applicable | unknown_date | E001; E002; E003 | N001 | unverified | No strong direct source found in brief. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: Med-BERT
- entity_type: medical Transformer method with official code
- core_function: Pretrained structured EHR Transformer for disease/risk prediction tasks.
- relevance_score: 9
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 2
- method_note: Strong reusable medical Transformer method, but input structure may not match ECMO free-text and small dataset.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Med-BERT
- url_or_local_reference: https://doi.org/10.1038/s41746-021-00455-y
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Peer-reviewed Med-BERT paper supports EHR Transformer pretraining and transfer for prediction tasks.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| ZhiGroup/Med-BERT | https://github.com/ZhiGroup/Med-BERT | 2026-07-09 | S | C002 |

#### Gaps

- Not ECMO-specific.
- Structured EHR setup may not match unstructured local data.

#### Risks

- Small local sample and clinical leakage risk.

### Entity E002

- entity_id: E002
- entity_name: BEHRT
- entity_type: medical Transformer method
- core_function: Uses Transformer architecture for longitudinal electronic health records.
- relevance_score: 8
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 2
- method_note: Strong architecture precedent but task/data scale may differ substantially.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: BEHRT
- url_or_local_reference: https://doi.org/10.1038/s41598-020-62922-y
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Paper supports Transformer use for EHR disease prediction.

#### Gaps

- Not ECMO-specific and not necessarily small-sample.

#### Risks

- Architecture similarity can be overread as clinical fit.

### Entity E003

- entity_id: E003
- entity_name: ECMO machine-learning mortality prediction prior work
- entity_type: target-domain prior work
- core_function: Uses ML models for ECMO mortality/risk prediction.
- relevance_score: 9
- reuse_score: 5
- score_scope: whole_entity
- method_similarity: 1
- method_note: Strong target-domain evidence, but often structured-variable and not Transformer.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: AI-powered model for predicting mortality risk in VA-ECMO patients
- url_or_local_reference: https://www.nature.com/articles/s41598-025-94734-3
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: ECMO mortality prediction paper supports target-domain ML prior work.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| ECMO prediction review | https://doi.org/10.1186/s13643-023-02211-7 | 2026-07-09 | A | C003 |

#### Gaps

- Direct Transformer-based ECMO evidence not established.

#### Risks

- ECMO mode, endpoint, and sample-selection differences matter.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: Direct ECMO risk prediction using Medical Transformer / Med-BERT is established in strong sources.
- searched_source_classes: academic papers; code source search in subagent brief.
- searched_queries: `ECMO Transformer risk prediction`; `Medical Transformer ECMO`; `Med-BERT ECMO mortality`.
- result: No strong direct source found in searched scope; ECMO ML evidence is mostly non-Transformer in the recorded pack.
- interpretation_limit: Does not prove no such paper exists.

## Information Gaps

- Local dataset schema, sample size, missingness, time windows, and label definitions.
- Clinical reporting requirements and IRB/ethics constraints.
- External validation and calibration requirements.

## Search Module Notes

- This pack is for research planning only and does not provide clinical advice.
