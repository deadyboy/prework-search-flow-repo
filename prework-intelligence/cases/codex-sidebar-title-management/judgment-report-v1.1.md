# Judgment Report V1.1

This report is written by the Judgment Module after reading the original Case 1 Evidence Pack and the V1.1 Evidence Pack addendum. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: PI-C001
- Evidence Pack path: `docs/prework-intelligence/cases/codex-sidebar-title-management/evidence-pack.md`
- V1.1 addendum path: `docs/prework-intelligence/cases/codex-sidebar-title-management/evidence-pack-v1.1-addendum.md`
- Evidence date: original 2026-07-04; addendum 2026-07-08

## Primary Conclusion

`补齐缺口`

## Conclusion Glossary

- `放弃不做`: 现有证据表明现在不值得继续。
- `直接采用`: 已有方案足够贴合，可以直接使用。
- `接入改造`: 已有方案能覆盖基础需求，但需要集成、包装或轻改。
- `场景定制`: 通用方案存在，但用户场景需要垂直定制。
- `补齐缺口`: 已有工作覆盖了基础，主要价值在于补 workflow、UX 或 operational pieces。
- `自研小样`: 没看到合适可复用基础，可以先做小型内部 prototype。
- `先补证据`: Evidence Pack 不足以支撑负责任的判断。

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `E005`, `E006`, `N003`.

This report treats negative evidence only as no strong evidence found within the recorded scope.

## Conclusion Rationale

- Primary conclusion: `补齐缺口`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `E005`, `E006`, `N003`
- Why these evidence records support the conclusion: `E005` shows manual desktop thread-list rename exists. `E001` and `E006` show app-server thread-name capability exists. `E006` also shows lifecycle nuance around `thread/start` and `thread/fork`. `E002` preserves historical pain and surface-specific requests. `E003` shows a risky local or extension patching implementation pattern. `N003` shows this targeted official-source addendum did not find a complete batch review-based governance workflow.
- Important evidence gaps: current hands-on UI behavior, forked thread UI behavior, legacy-title cleanup, and account-specific availability remain unverified.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Codex app supports manual thread renaming in the thread list. | desktop_app | manual_rename | current_official | `直接采用` | E005 | Official changelog evidence says desktop thread-list double-click rename exists. | Need user-environment hands-on confirmation if execution depends on the installed client. |
| C002 | App-server exposes a reusable thread-name setting path. | app_server | manual_rename | current_official | `接入改造` | E001; E006 | Official app-server evidence supports `thread/name/set`, but integration and permissions still need implementation-specific handling. | Need client integration check before building on it. |
| C003 | Fork and start lifecycle title behavior is not the same as an already-set title. | app_server | thread_fork | current_official | `先补证据` | E006 | Official docs say `thread/start` and `thread/fork` may omit or return null `name` until set later. | Need current desktop fork UI observation and desired policy. |
| C004 | Legacy or abnormal title cleanup has a documented official governance workflow. | cross_surface | legacy_thread | unknown_date | `先补证据` | N003 | Targeted official-source addendum did not find strong evidence for this workflow. | Need either official docs, current UI observation, or user-provided local examples. |
| C005 | Official base title capabilities exist, but a complete batch review-based governance workflow is not established. | cross_surface | batch_review | recent_but_unverified | `补齐缺口` | E001; E002; E005; E006; N003 | Base rename capabilities and pain evidence exist, but the complete reviewed batch workflow is not established. | Need workflow design and current UI constraints before implementation. |
| C006 | Public evidence records local state or installed-extension editing as workaround or patching patterns. | local_state | not_applicable | recent_but_unverified | `放弃不做` | E002; E003 | Original evidence records local workaround and patching patterns, but they carry safety and compatibility risk. | Local state may still be inspected only under explicit safe conditions, not as the default path. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E005 | Codex app 26.203 thread-list double-click rename | 10 | 9 | S | confirmed | Supports local `直接采用` for manual desktop rename. |
| E006 | Codex app-server thread-name API and lifecycle behavior | 10 | 8 | S | confirmed | Supports `接入改造` and lifecycle evidence gaps. |
| E001 | Codex app-server thread naming API | 10 | 7 | S | confirmed | Original official API capability evidence. |
| E002 | Public Codex rename feature-request cluster | 9 | 3 | A | confirmed | Historical pain and surface-specific demand evidence. |
| E003 | Just-Boring-Cat/codex-thread-renamer | 8 | 5 | A | single-source | Shows close but risky patching pattern. |

## Why Existing Work Does Or Does Not Substitute

Manual rename is no longer a missing capability at the broad desktop-app level because `E005` confirms official support.

App-server rename is also not missing because `E001` and `E006` support an official API path.

Those facts do not solve batch review governance, legacy title cleanup, fork lifecycle policy, or safety rules for avoiding direct local state edits. Those remain separate claims, not evidence that the whole idea should be discarded.

## What To Reuse

- Use `E005` as the first path for manual desktop renaming.
- Use `E001` and `E006` as the integration basis for app-server naming flows.
- Use `E002` as pain and workflow requirement evidence.
- Use `E003` only as a cautionary reference for UI affordances and safety concerns, not as a default implementation path.

## What Not To Do

- Do not describe Codex title management as wholly missing. `E005` and `E006` contradict that.
- Do not treat old issues as current missing-feature evidence without freshness checks. `E005` updates the manual rename claim.
- Do not make direct local state or database editing the default path. `E002` and `E003` show why that path is risky.
- Do not infer a complete batch governance workflow from API-level rename support. `E001`, `E006`, and `N003` separate those claims.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N003 | Complete official batch review-based title governance workflow | Official Codex changelog; official app-server docs; original Case 1 Evidence Pack | Supports the remaining `补齐缺口` conclusion for batch governance and legacy cleanup. | Does not prove no workflow exists outside the targeted addendum scope. |

## Next Action

Review V1.1 framework changes and this Case 1 regression before running Case 2.

## Supplement-Evidence Request

Used only for claim-level local conclusions `C003` and `C004`, not for the primary conclusion.

- Affected entity_id values or `none`: `E006` for C003; `none` for C004
- Affected negative_evidence_id values or `none`: `N003`
- Missing source class: current hands-on UI observation; official docs or user-provided examples for legacy-title cleanup
- Missing claim or comparison: fork title behavior and legacy abnormal title governance
- Missing evidence record type: current observed source record or entity record
- Why judgment cannot proceed for those local claims: the addendum separates official API lifecycle evidence from current desktop behavior and legacy cleanup behavior.
- What the Search Module should add to a revised Evidence Pack: current UI observation on a non-private test thread, plus any official or user-provided evidence about forked thread title inheritance and legacy title cleanup.

## Validity Checklist

- The report reads only the original Evidence Pack and V1.1 addendum.
- The primary conclusion is one of the allowed values.
- The primary conclusion cites `entity_id` or `negative_evidence_id` values.
- Every claim-level local conclusion cites `entity_id` or `negative_evidence_id` values, or justified `none` for `先补证据`.
- No new sources, URLs, or entities are introduced.
- Negative evidence is interpreted only as no strong evidence found within covered sources.
- Evidence gaps are not converted into confident claims.
