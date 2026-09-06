# Evidence Pack

This is the Search Module handoff artifact for Case C1. It records evidence, not final decisions.

## Case Metadata

- Case ID: C1
- Idea title: PINN + ILW prior work
- Search level: L3 deep review
- Search date: 2026-07-09
- Searcher: Codex with independent research subagent brief

## Coverage Summary

- Searched source classes: academic papers; arXiv; DOI records; adjacent method papers.
- Unsearched source classes: complete inverse Lax-Wendroff boundary-method rerun; citation chasing; code repositories.
- Languages searched: English.
- Coverage note: Coverage is not sufficient for a final prior-work judgment because `ILW` ambiguity was discovered.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | academic | arXiv / journal DOI | `PINN nonlinear dispersive PDE KdV Benjamin Ono` | several | E001 | Adjacent PINN evidence. |
| Q002 | academic | JFM / DOI | `modified intermediate long wave internal solitary wave` | 1 | E002 | Intermediate-long-wave domain evidence. |
| Q003 | academic | mixed | `PINN ILW inverse Lax Wendroff boundary` | 0 strong in brief | N001; N002 | Needs rerun with disambiguation. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | PINN has adjacent evidence on nonlinear dispersive PDEs. | cross_surface | not_applicable | recent_but_unverified | E001 | none | confirmed | Not direct ILW boundary evidence. |
| C002 | Intermediate-long-wave / modified ILW is an active PDE/domain. | cross_surface | not_applicable | recent_but_unverified | E002 | none | confirmed | May be the wrong ILW sense for the user's idea. |
| C003 | Direct PINN + inverse Lax-Wendroff boundary prior work is established. | cross_surface | not_applicable | unknown_date | none | N001 | unverified | Needs targeted rerun. |
| C004 | Direct PINN + intermediate long wave equation prior work is established. | cross_surface | not_applicable | unknown_date | E001; E002 | N002 | unverified | Adjacent evidence only. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: PINN for nonlinear dispersive PDEs
- entity_type: academic method family
- core_function: Uses physics-informed neural networks for nonlinear dispersive equations such as KdV-family or Benjamin-Ono-like problems.
- relevance_score: 7
- reuse_score: 5
- score_scope: whole_entity
- method_similarity: 1
- method_note: Adjacent PINN method evidence, but not direct ILW boundary treatment.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Physics-informed neural networks for nonlinear dispersive PDEs
- url_or_local_reference: https://arxiv.org/abs/2104.05584
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Paper evidence supports PINN use on nonlinear dispersive PDEs adjacent to ILW-family problems.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Journal DOI | https://doi.org/10.4208/jcm.2101-m2020-0342 | 2026-07-09 | A | C001 |

#### Gaps

- Does not establish inverse Lax-Wendroff boundary use.

#### Risks

- Adjacent PDE family evidence can be overread as direct prior work.

### Entity E002

- entity_id: E002
- entity_name: Modified intermediate long wave equation for internal solitary waves
- entity_type: academic domain/model evidence
- core_function: Records modified intermediate long wave equation research for ocean internal solitary waves.
- relevance_score: 6
- reuse_score: 3
- score_scope: whole_entity
- method_similarity: 0
- method_note: Domain evidence for a possible ILW expansion, not the PINN method.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Dynamical properties of ocean internal solitary waves based on the modified intermediate long wave equation
- url_or_local_reference: https://doi.org/10.1017/jfm.2025.10719
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: JFM paper supports mILW as an active internal-wave model.

#### Gaps

- Does not mention PINN or inverse Lax-Wendroff boundary methods in the recorded evidence.

#### Risks

- The `ILW` expansion may not match the user's intent.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: Strong direct prior work exists for PINN plus inverse Lax-Wendroff boundary treatment.
- searched_source_classes: academic web/arXiv/DOI search in subagent brief.
- searched_queries: `PINN ILW inverse Lax Wendroff boundary`; `physics-informed neural inverse Lax-Wendroff`.
- result: No strong direct evidence found in the brief.
- interpretation_limit: This is not sufficient as final negative evidence because the search should be rerun with explicit inverse-Lax-Wendroff terms.

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: Strong direct prior work exists for PINN solving the intermediate long wave / modified ILW equation.
- searched_source_classes: academic web/arXiv/DOI search in subagent brief.
- searched_queries: `PINN intermediate long wave`; `physics-informed neural modified intermediate long wave`.
- result: No strong direct evidence found in the brief; only adjacent dispersive PDE and mILW domain evidence recorded.
- interpretation_limit: Does not prove no direct paper exists.

## Information Gaps

- The user's intended meaning of `ILW` must be confirmed.
- Need targeted citation search for inverse Lax-Wendroff + PINN if that is the intended method.
- Need code/baseline search after term disambiguation.

## Search Module Notes

- This Evidence Pack intentionally preserves ambiguity instead of forcing a novelty conclusion.
