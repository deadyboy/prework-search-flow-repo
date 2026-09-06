# Evidence Pack

This is the only handoff artifact from Search Module to Judgment Module. It records evidence, not final decisions.

## Case Metadata

- Case ID:
- Idea title:
- Original idea:
- Search level:
- Search date:
- Searcher:

## Coverage Summary

- Searched source classes:
- Unsearched source classes:
- Languages searched:
- Timebox:
- Coverage note:

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 |  |  |  |  |  |  |

## Capability Claim Matrix

Use this matrix to separate broad cases into claim-level evidence records. It does not contain final Judgment conclusions.

Allowed `surface_scope` values: `desktop_app`, `vscode_extension`, `cli`, `app_server`, `web_product`, `remote_thread`, `local_state`, `cross_surface`, `unknown`.

Allowed `lifecycle_scope` values: `thread_start`, `manual_rename`, `auto_title_generation`, `thread_list`, `thread_read`, `thread_resume`, `thread_fork`, `legacy_thread`, `batch_review`, `archive_unarchive`, `not_applicable`, `unknown`.

Allowed `freshness_status` values: `current_official`, `current_observed`, `recent_but_unverified`, `stale_issue`, `conflicting`, `unknown_date`.

Use the same values for `claim_evidence_status` as `evidence_status`: `confirmed`, `single-source`, `conflicting`, or `unverified`.

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 |  |  |  |  |  |  |  |  |

## Entity Records

Create one record per entity, not one record per URL.

### Entity E001

- entity_id: E001
- entity_name:
- entity_type:
- core_function:
- relevance_score:
- reuse_score:
- score_scope:
- method_similarity:
- method_note:
- source_grade:
- evidence_status:

#### Main Source

- title:
- url_or_local_reference:
- accessed_at:
- source_grade:
- source_excerpt_or_summary:

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

#### Key Facts

Record facts that are directly supported by the listed sources.

#### Similarity Notes

- Problem similarity:
- User similarity:
- Input similarity:
- Output similarity:
- Workflow similarity:
- Constraint similarity:

#### Reuse Notes

- Reusable parts:
- Integration cost:
- License or terms:
- Maintenance signal:

#### Gaps

- Record missing facts needed for judgment.

#### Risks

- Record reliability, fit, compliance, maintenance, or implementation risks.

## Information Gaps

List missing evidence that may affect judgment.

## Negative Evidence Records

Record negative evidence as searched absence within a defined scope.

Negative Evidence can only mean strong evidence was not found within the covered source classes, queries, and limits. It must not be used to claim absolute non-existence.

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim:
- searched_source_classes:
- searched_queries:
- result:
- interpretation_limit:

## Negative Search Scope

Record searched failure cases, complaints, limitations, abandoned projects, and alternative approaches. If not searched, say which source classes remain unsearched.

## Search Module Notes

Write search limitations and uncertainty. Do not include final recommendations.
