# Evidence Pack

This is the Search Module handoff artifact for Case C2. It records evidence, not final decisions.

## Case Metadata

- Case ID: C2
- Idea title: X-Net / FFT-XNet for PDE solving with ILW
- Search level: L2/L3 targeted research scan
- Search date: 2026-07-09
- Searcher: Codex with independent research subagent brief

## Coverage Summary

- Searched source classes: academic papers; arXiv; DOI pages.
- Unsearched source classes: full citation graph; implementation repos; benchmark replication.
- Languages searched: English.
- Coverage note: Sufficient to separate XNet PDE evidence from missing FFT-XNet/ILW evidence.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | academic | Neural Networks / arXiv | `XNet Cauchy activation PDE solving` | several | E001 | XNet PDE evidence. |
| Q002 | academic | arXiv | `XNet outperforming KAN PDE` | 1 | E002 | Preprint evidence. |
| Q003 | academic | mixed | `FFT-XNet FFTXNet XNet FFT PDE` | 0 strong | N001 | No strong named FFT-XNet evidence. |
| Q004 | academic | mixed | `XNet ILW intermediate long wave inverse Lax Wendroff` | 0 strong | N002 | No direct XNet+ILW evidence. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | XNet has evidence for PDE/function approximation contexts. | cross_surface | not_applicable | recent_but_unverified | E001; E002 | none | confirmed | Benchmark quality not independently verified. |
| C002 | FFT-XNet is established as a named PDE method. | cross_surface | not_applicable | unknown_date | none | N001 | unverified | Could be internal name or confused with Fourier/FNO methods. |
| C003 | XNet + ILW direct combination has prior work. | cross_surface | not_applicable | unknown_date | E001; E002 | N002 | unverified | No direct combination evidence found. |
| C004 | XNet structure may be borrowable for a PDE prototype. | cross_surface | not_applicable | recent_but_unverified | E001; E002 | none | single-source | Needs implementation feasibility check. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: XNet / Cauchy activation for PDE solving
- entity_type: academic method
- core_function: Uses Cauchy activation / XNet-like function approximation for PDE-related neural approximation.
- relevance_score: 8
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 1
- method_note: Similar neural PDE approximation direction, but not direct ILW or FFT-XNet evidence.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Cauchy activation function and XNet
- url_or_local_reference: https://doi.org/10.1016/j.neunet.2025.107375
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Paper evidence supports XNet/Cauchy activation in neural function approximation and PDE contexts.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| arXiv:2409.19221 | https://arxiv.org/abs/2409.19221 | 2026-07-09 | B | C001 |

#### Gaps

- Direct ILW and FFT naming not established.

#### Risks

- Method transfer may fail due to input/output and boundary-condition mismatch.

### Entity E002

- entity_id: E002
- entity_name: XNet outperforming KAN preprint
- entity_type: academic preprint
- core_function: Compares XNet-like method against KAN/function approximation baselines.
- relevance_score: 7
- reuse_score: 5
- score_scope: whole_entity
- method_similarity: 1
- method_note: Useful method-transfer evidence, but still not direct target evidence.
- source_grade: B
- evidence_status: single-source

#### Main Source

- title: Enhancing Neural Function Approximation: The XNet Outperforming KAN
- url_or_local_reference: https://arxiv.org/abs/2501.18959
- accessed_at: 2026-07-09
- source_grade: B
- source_excerpt_or_summary: Preprint evidence suggests XNet can be a competitive neural approximation method.

#### Gaps

- Preprint status and benchmark scope need review.

#### Risks

- Preprint claims may not generalize to ILW/PDE boundary constraints.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: FFT-XNet is established as a named PDE-solving method.
- searched_source_classes: academic web/arXiv search.
- searched_queries: `FFT-XNet`; `FFTXNet`; `FFT XNet PDE`; `XNet FFT PDE`.
- result: No strong named FFT-XNet source found in the searched scope.
- interpretation_limit: Could be an internal name, typo, or confused with Fourier-feature/FNO methods.

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: XNet has direct published integration with ILW.
- searched_source_classes: academic web/arXiv search.
- searched_queries: `XNet ILW`; `XNet intermediate long wave`; `XNet inverse Lax Wendroff`.
- result: No strong direct XNet+ILW evidence found in the searched scope.
- interpretation_limit: Does not prove no such work exists.

## Information Gaps

- `FFT-XNet` naming needs confirmation.
- Direct code and benchmark search not performed.
- ILW meaning may need disambiguation as in C1.

## Search Module Notes

- This pack distinguishes borrowable method evidence from direct combination evidence.
