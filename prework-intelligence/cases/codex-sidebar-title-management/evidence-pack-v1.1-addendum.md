# Evidence Pack V1.1 Addendum

This addendum supplements the original Case 1 Evidence Pack. It records claim-level current product capability evidence and does not output final Judgment conclusions.

## Case Metadata

- Case ID: PI-C001
- Idea title: Codex sidebar title management
- Original Evidence Pack path: `docs/prework-intelligence/cases/codex-sidebar-title-management/evidence-pack.md`
- Addendum date: 2026-07-08
- Searcher: Codex
- Search level: L2 targeted regression addendum

## Coverage Summary

- Searched source classes: official Codex changelog; official Codex app-server docs; original Case 1 Evidence Pack.
- Unsearched source classes: current hands-on UI test; private local `.codex` state; private thread content; full GitHub issue refresh; product directory refresh.
- Languages searched: English official docs; original Case 1 mixed English and Chinese notes.
- Timebox: targeted V1.1 regression addendum only.
- Coverage note: This addendum checks current official capability and lifecycle evidence. It does not rerun the full Case 1 search.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q008 | official changelog | OpenAI Codex changelog | `Codex app 26.203 thread renaming double-click thread list` | 1 | E005 | Found official changelog evidence for thread-list double-click rename. |
| Q009 | official docs | OpenAI Codex app-server docs | `thread/name/set`; `thread.name`; `thread/fork`; `thread/start` | 1 | E006 | Found official API and lifecycle evidence for thread names. |

## Capability Claim Matrix

Allowed `surface_scope` values: `desktop_app`, `vscode_extension`, `cli`, `app_server`, `web_product`, `remote_thread`, `local_state`, `cross_surface`, `unknown`.

Allowed `lifecycle_scope` values: `thread_start`, `manual_rename`, `auto_title_generation`, `thread_list`, `thread_read`, `thread_resume`, `thread_fork`, `legacy_thread`, `batch_review`, `archive_unarchive`, `not_applicable`, `unknown`.

Allowed `freshness_status` values: `current_official`, `current_observed`, `recent_but_unverified`, `stale_issue`, `conflicting`, `unknown_date`.

Use the same values for `claim_evidence_status` as `evidence_status`: `confirmed`, `single-source`, `conflicting`, or `unverified`.

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Codex app supports manual thread renaming in the thread list. | desktop_app | manual_rename | current_official | E005 | none | confirmed | Current installed user environment was not hands-on verified in this addendum. |
| C002 | App-server exposes a reusable thread-name setting path. | app_server | manual_rename | current_official | E001; E006 | none | confirmed | Integration access and client permissions still need case-specific verification. |
| C003 | Thread-name lifecycle around `thread/start` and `thread/fork` is not equivalent to an already-set title. | app_server | thread_fork | current_official | E006 | none | confirmed | Current desktop fork UI behavior was not hands-on verified. |
| C004 | Legacy or abnormal title cleanup has a documented official governance workflow. | cross_surface | legacy_thread | unknown_date | none | N003 | unverified | No current official legacy-title cleanup workflow was found in this targeted addendum. |
| C005 | Official base title capabilities exist, but a complete batch review-based governance workflow is not established. | cross_surface | batch_review | recent_but_unverified | E001; E002; E005; E006 | N003 | unverified | Official base capabilities exist, but a complete batch review workflow was not found. |
| C006 | Public evidence records local state or installed-extension editing as workaround or patching patterns. | local_state | not_applicable | recent_but_unverified | E002; E003 | none | single-source | Local state details were intentionally not inspected for privacy and safety reasons. |

## Entity Records

This addendum keeps the original entity IDs from the original Evidence Pack and adds supplemental entities below. It still groups by entity, not by URL.

### Entity E005

- entity_id: E005
- entity_name: Codex app 26.203 thread-list double-click rename
- entity_type: official feature / changelog record
- core_function: Official Codex app changelog records manual thread renaming by double-click in the thread list.
- relevance_score: 10
- reuse_score: 9
- score_scope: claim:C001
- method_similarity: 2
- method_note: This directly matches manual title editing in the desktop thread-list surface, but it does not cover batch governance or lifecycle edge cases.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Codex changelog
- url_or_local_reference: https://developers.openai.com/codex/changelog
- accessed_at: 2026-07-08
- source_grade: S
- source_excerpt_or_summary: The official changelog entry for 2026-02-03, Codex app 26.203, records that thread renaming was added on double-click in the thread list.

#### Support Sources

No independent support source was needed for this narrow official product capability claim.

#### Key Facts

- Official changelog evidence supports current official manual thread-list rename capability.
- This evidence does not establish batch review, auto title governance, or fork-title behavior.

#### Gaps

- No hands-on UI observation was recorded in this addendum.
- The user's installed app version and account-specific availability were not checked.

#### Risks

- Changelog capability may not prove every deployed client surface behaves identically.

### Entity E006

- entity_id: E006
- entity_name: Codex app-server thread-name API and lifecycle behavior
- entity_type: official developer API
- core_function: Official app-server docs list `thread/name/set` and describe when `thread.name` is hydrated or omitted.
- relevance_score: 10
- reuse_score: 8
- score_scope: claim:C002
- method_similarity: 2
- method_note: This directly matches API-level thread-name setting and lifecycle observation, but it is not a user-facing batch governance workflow.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Codex App Server
- url_or_local_reference: https://developers.openai.com/codex/app-server
- accessed_at: 2026-07-08
- source_grade: S
- source_excerpt_or_summary: Official app-server docs list `thread/name/set` for setting or updating a thread user-facing name. The docs also say `thread.name` is hydrated on list/read/resume/unarchive/rollback responses after a title has been set, while `thread/start` and `thread/fork` may omit `name` or return `null` until a title is set later.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Original Case 1 Evidence Pack E001 | `docs/prework-intelligence/cases/codex-sidebar-title-management/evidence-pack.md#entity-e001` | 2026-07-08 | S | Prior Case 1 already recorded app-server thread naming API evidence. |

#### Key Facts

- `thread/name/set` is an official app-server method for user-facing thread names.
- `thread.name` is not guaranteed on every lifecycle response before a title has been set.
- `thread/start` and `thread/fork` lifecycle behavior needs separate judgment from manual rename support.

#### Gaps

- This addendum does not verify whether the user's current desktop UI exposes every app-server capability.
- Client authorization and integration behavior were not tested.

#### Risks

- API-level support does not automatically provide safe batch governance UX.

## Information Gaps

- No hands-on current UI test was run.
- No private local `.codex` files, SQLite state, account settings, or private thread content were inspected.
- Current behavior for desktop forked thread title inheritance was not observed directly.
- No full refresh of GitHub issues was performed after the original Case 1.

## Negative Evidence Records

Negative Evidence can only mean strong evidence was not found within the covered source classes, queries, and limits. It must not be used to claim absolute non-existence.

### Negative Evidence N003

- negative_evidence_id: N003
- searched_claim: Official current Codex docs provide a complete batch review-based title governance workflow, including legacy cleanup and fork lifecycle policy.
- searched_source_classes: Official Codex changelog; official Codex app-server docs; original Case 1 Evidence Pack.
- searched_queries: `Codex app 26.203 thread renaming double-click thread list`; `thread/name/set`; `thread.name`; `thread/fork`; `thread/start`.
- result: Official sources show manual rename and API-level thread-name support, but this targeted addendum did not find a complete batch review-based governance workflow or legacy cleanup policy.
- interpretation_limit: This does not prove no such workflow exists. It only records that the targeted official-source addendum did not find strong evidence for it.

## Negative Search Scope

- This addendum searched current official capability and lifecycle evidence only.
- It did not search private state, current UI directly, full GitHub issues, full product substitutes, or implementation repositories.

## Search Module Notes

- The main correction is claim separation, not broader search volume.
- Older issues from the original Case 1 remain useful for historical user pain, but should not be treated as current missing-feature evidence without a freshness check.
- This addendum contains no final Judgment conclusion.
