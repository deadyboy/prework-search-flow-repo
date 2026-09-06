# Evidence Pack

This is the Search Module handoff artifact for Case D2. It records evidence, not final decisions.

## Case Metadata

- Case ID: D2
- Idea title: ECMO unstructured extraction and prediction
- Search level: L3 deep review
- Search date: 2026-07-09
- Searcher: Codex with independent vertical-workflow subagent brief

## Coverage Summary

- Searched source classes: official ECMO registry resources; ECMO prediction score resources; ECMO ML papers; ICU notes prediction papers; ECMO EMR workflow paper.
- Unsearched source classes: private ECMO notes; local data dictionary; ethics/IRB; full model validation review.
- Languages searched: English.
- Coverage note: Sufficient to map an extraction-then-prediction architecture, not to build a clinical model.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official registry | ELSO | ELSO registry data definitions forms | several | E001 | Field dictionary evidence. |
| Q002 | official/clinical | ELSO scores | ECMO outcome prediction scores | several | E002 | Structured risk evidence. |
| Q003 | academic | Scientific Reports / Sage | VA ECMO mortality ML MIMIC ECMO prediction | several | E003 | ECMO ML evidence. |
| Q004 | academic | PLOS / Crit Care Med | ICU notes mortality NLP unstructured text prediction | several | E004 | Unstructured method analogy. |
| Q005 | negative search | mixed | ECMO unstructured notes extraction prediction workflow | 0 strong | N001 | No complete public loop found. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | ECMO has structured registry/data dictionary foundations. | cross_surface | not_applicable | current_official | E001 | none | confirmed | Local notes may not follow ELSO fields. |
| C002 | ECMO outcome prediction scores and ML prior work exist. | cross_surface | not_applicable | recent_but_unverified | E002; E003 | none | confirmed | Mostly structured variables. |
| C003 | ICU unstructured notes can improve prediction in adjacent work. | cross_surface | not_applicable | recent_but_unverified | E004 | none | confirmed | Not ECMO-specific. |
| C004 | A mature ECMO unstructured extraction + prediction loop exists publicly. | cross_surface | not_applicable | recent_but_unverified | E001; E002; E003; E004 | N001 | unverified | No complete same-topic workflow found. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: ELSO Registry and data definitions
- entity_type: official registry / data dictionary
- core_function: Provides ECMO registry fields, forms, and data definitions.
- relevance_score: 11
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 1
- method_note: Strong field/schema source, not an unstructured extraction method.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: ELSO Registry
- url_or_local_reference: https://www.elso.org/registry.aspx
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official registry source for ECMO data and reporting.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| ECLS Registry Forms/Data Definitions | https://www.elso.org/registry/datadefinitions%2Cforms%2Cinstructions.aspx | 2026-07-09 | S | C001 |

#### Gaps

- Does not parse local free text.

#### Risks

- Registry fields may not cover local narrative details.

### Entity E002

- entity_id: E002
- entity_name: ELSO outcome prediction scores
- entity_type: official clinical research resource
- core_function: Provides ECMO outcome score references.
- relevance_score: 9
- reuse_score: 5
- score_scope: whole_entity
- method_similarity: 1
- method_note: Useful baseline/benchmark source, not an automated prediction pipeline.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: ELSO Outcome Prediction Scores
- url_or_local_reference: https://www.elso.org/ecmo-resources/ecmo-outcome-prediction-scores.aspx
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official ELSO page lists outcome prediction score resources and cautions.

#### Gaps

- Not a free-text extraction workflow.

#### Risks

- Scores should not be treated as automated patient-selection decisions.

### Entity E003

- entity_id: E003
- entity_name: ECMO machine-learning mortality prediction papers
- entity_type: academic target-domain prior work
- core_function: Uses ML for ECMO mortality or outcome prediction.
- relevance_score: 9
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 1
- method_note: Strong target-domain prediction evidence, mostly structured-variable.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: AI-powered model for predicting mortality risk in VA-ECMO patients
- url_or_local_reference: https://www.nature.com/articles/s41598-025-25423-4
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Academic evidence for ECMO mortality prediction with ML.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| MIMIC-IV ECMO 28-day mortality | https://journals.sagepub.com/doi/abs/10.1177/00031348251394273 | 2026-07-09 | A | C002 |

#### Gaps

- Direct unstructured extraction link not established.

#### Risks

- Sample, center, ECMO mode, endpoint, and leakage issues.

### Entity E004

- entity_id: E004
- entity_name: ICU free-text mortality prediction methods
- entity_type: adjacent academic method
- core_function: Uses unstructured ICU notes/NLP to improve mortality or outcome prediction.
- relevance_score: 8
- reuse_score: 7
- score_scope: whole_entity
- method_similarity: 2
- method_note: Strong method analogy for extracting and using notes, but not ECMO-specific.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: ICU notes mortality prediction
- url_or_local_reference: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0262182
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Paper evidence supports using ICU notes for mortality prediction.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Inclusion of Unstructured Clinical Text | https://doi.org/10.1097/CCM.0000000000003148 | 2026-07-09 | A | C003 |

#### Gaps

- ECMO-specific entity schema and temporal extraction not covered.

#### Risks

- Notes can contain leakage after prediction time.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: A mature public ECMO workflow exists for unstructured note extraction plus mortality/decannulation prediction.
- searched_source_classes: ELSO resources; ECMO ML papers; ICU notes NLP papers.
- searched_queries: `ECMO unstructured notes extraction prediction`; `ECMO clinical text mortality prediction NLP`.
- result: No strong complete same-topic workflow found in searched scope.
- interpretation_limit: Does not prove no such workflow exists in private clinical systems.

## Information Gaps

- No local note schema.
- No temporal event extraction schema.
- No ethics/IRB or deployment review.

## Search Module Notes

- This pack supports an extraction-first evidence chain, not direct LLM prediction.
