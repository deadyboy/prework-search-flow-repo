# Evidence Pack

This is the only Search Module handoff artifact for Case A3. It records evidence, not final decisions.

## Case Metadata

- Case ID: A3
- Idea title: Fast-changing current product capability
- Original idea: 用 Codex Windows Computer Use 测试 current product capability freshness gate。
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent calibration subagent brief

## Coverage Summary

- Searched source classes: official Codex changelog; official Codex Computer Use docs; GitHub issue.
- Unsearched source classes: hands-on UI/account verification; full issue refresh; regional eligibility test.
- Languages searched: English.
- Timebox: targeted calibration scan.
- Coverage note: Official current sources are sufficient for product-level capability existence, but not for the user's account-specific availability.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official changelog | OpenAI Codex changelog | `Codex Windows Computer Use 2026 changelog` | 1 | E001 | Official release timeline found. |
| Q002 | official docs | Codex Computer Use docs | `Codex Computer Use Windows foreground` | 1 | E002 | Current support and limits found. |
| Q003 | GitHub/open source | openai/codex issue | `Windows Codex Computer Use issue 19305` | 1 | E003 | Historical issue found. |
| Q004 | official docs | Computer Use / remote behavior | `Windows active desktop foreground Computer Use` | 1 | E002; N001 | Foreground limitation found. |
| Q005 | official docs | Account availability | `Codex Computer Use plan region availability` | partial | E002; N002 | Official docs do not prove this user's account availability. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | 旧 issue 记录 Windows Computer Use 曾经缺失或不足。 | desktop_app | not_applicable | stale_issue | E003 | none | confirmed | Only historical pain, not current status. |
| C002 | 官方 changelog 记录 Windows Computer Use 发布或扩展。 | desktop_app | not_applicable | current_official | E001 | none | confirmed | No hands-on user account test. |
| C003 | 当前 docs 记录 Windows Computer Use 支持和限制。 | desktop_app | not_applicable | current_official | E002 | none | confirmed | Region/plan details may still vary. |
| C004 | Windows Computer Use 可后台运行且不占用当前桌面。 | desktop_app | not_applicable | current_official | E002 | N001 | unverified | Official docs record foreground or active-desktop constraints; no strong background same-desktop evidence is recorded. |
| C005 | 当前用户账号、地区、plan 一定可用。 | cross_surface | not_applicable | recent_but_unverified | E002 | N002 | unverified | No user-observed or account-level evidence. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: Codex changelog Windows Computer Use timeline
- entity_type: official changelog
- core_function: Official Codex release timeline records Windows Computer Use support and expansion.
- relevance_score: 10
- reuse_score: 9
- score_scope: claim:C002
- method_similarity: 2
- method_note: Direct current official capability evidence for the selected feature.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Codex changelog
- url_or_local_reference: https://developers.openai.com/codex/changelog
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official changelog entries record Windows Computer Use support/expansion after the older issue date.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Codex Computer Use docs | https://developers.openai.com/codex/app/computer-use | 2026-07-09 | S | C002; C003 |

#### Key Facts

- Official release evidence post-dates the older issue.
- Changelog evidence is stronger than stale issue evidence for current capability existence.

#### Similarity Notes

- Problem similarity: high.
- User similarity: high.
- Input similarity: high.
- Output similarity: high.
- Workflow similarity: high.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: official product capability.
- Integration cost: low if account/region supports it.
- License or terms: official product docs.
- Maintenance signal: official changelog.

#### Gaps

- No user-specific hands-on verification.

#### Risks

- Feature availability may depend on plan, region, app version, or feature flag.

### Entity E002

- entity_id: E002
- entity_name: Codex Computer Use current docs
- entity_type: official documentation
- core_function: Describes current Computer Use support and limits, including Windows behavior.
- relevance_score: 10
- reuse_score: 8
- score_scope: claim:C003
- method_similarity: 2
- method_note: Direct documentation for capability boundaries.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Codex Computer Use
- url_or_local_reference: https://developers.openai.com/codex/app/computer-use
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Current docs describe supported platforms and Windows foreground/active desktop behavior.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Codex changelog | https://developers.openai.com/codex/changelog | 2026-07-09 | S | C003 |

#### Key Facts

- Current docs support Windows Computer Use as an official feature.
- The docs record important operating constraints rather than unlimited background control.

#### Similarity Notes

- Problem similarity: high.
- User similarity: high.
- Input similarity: high.
- Output similarity: high.
- Workflow similarity: high.
- Constraint similarity: high for documented limits.

#### Reuse Notes

- Reusable parts: current official capability and limit language.
- Integration cost: low for use, medium if workflow needs non-foreground operation.
- License or terms: official product docs.
- Maintenance signal: official docs.

#### Gaps

- No account-specific evidence.

#### Risks

- Foreground behavior may conflict with workflows requiring simultaneous user desktop control.

### Entity E003

- entity_id: E003
- entity_name: openai/codex issue #19305 Windows Computer Use request
- entity_type: GitHub issue / historical pain record
- core_function: Records a pre-release or older state where Windows Computer Use was requested or missing.
- relevance_score: 8
- reuse_score: 2
- score_scope: claim:C001
- method_similarity: 1
- method_note: The issue is relevant as historical pain, not current official capability evidence.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: openai/codex issue #19305
- url_or_local_reference: https://github.com/openai/codex/issues/19305
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Issue evidence records Windows Computer Use pain before later official release evidence.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Codex changelog | https://developers.openai.com/codex/changelog | 2026-07-09 | S | C001 freshness comparison |

#### Key Facts

- The issue date predates later official release evidence.
- It should be interpreted as historical pain unless refreshed by current evidence.

#### Similarity Notes

- Problem similarity: high.
- User similarity: high.
- Input similarity: medium.
- Output similarity: low for current solution.
- Workflow similarity: low.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: pain framing and requirement signal.
- Integration cost: not a reusable implementation.
- License or terms: GitHub issue.
- Maintenance signal: issue state not sufficient for current product status.

#### Gaps

- Issue does not determine current behavior after releases.

#### Risks

- Overreading stale issues can cause false missing-feature judgments.

## Information Gaps

- No current user account/plan/region verification.
- No hands-on UI observation.
- No full community refresh.

## Negative Evidence Records

Negative Evidence can only mean strong evidence was not found within the covered source classes, queries, and limits. It must not be used to claim absolute non-existence.

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: Windows Computer Use can run in the background while the user continues controlling the same Windows desktop.
- searched_source_classes: official Codex Computer Use docs.
- searched_queries: `Windows active desktop foreground Computer Use`.
- result: No strong evidence found for non-foreground same-desktop operation; current docs record foreground/active desktop constraints.
- interpretation_limit: This only covers the searched official docs and does not prove no other mode exists.

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: The current user's account, region, plan, and installed app version definitely support Windows Computer Use.
- searched_source_classes: official docs only.
- searched_queries: `Codex Computer Use plan region availability`.
- result: No user-specific evidence exists in this pack.
- interpretation_limit: This is an evidence gap, not proof of unavailability.

## Negative Search Scope

- Background operation.
- Account-specific availability.
- Product-wide absence after official release evidence.

## Search Module Notes

- The central evidence pattern is timeline correction: old issue first, official release later.
- This pack contains no final Judgment conclusion.
