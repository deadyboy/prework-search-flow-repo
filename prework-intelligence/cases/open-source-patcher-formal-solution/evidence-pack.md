# Evidence Pack

This is the only Search Module handoff artifact for Case A2. It records evidence, not final decisions.

## Case Metadata

- Case ID: A2
- Idea title: Open-source patcher as formal solution
- Original idea: 评估公开 Codex title patcher 是否可以作为正式方案基础。
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent calibration subagent brief

## Coverage Summary

- Searched source classes: GitHub/open source; official Codex docs; targeted negative search.
- Unsearched source classes: hands-on patch execution; private local extension files; full code audit; legal review.
- Languages searched: English.
- Timebox: targeted calibration scan.
- Coverage note: This pack is sufficient to distinguish reference implementation from safe default path, but not sufficient for security approval.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | GitHub/open source | GitHub | `Just-Boring-Cat codex-thread-renamer` | 1 | E001 | Main patcher repo found. |
| Q002 | GitHub/open source | GitHub repo docs | `codex-thread-renamer how it works patch extension files` | 1 | E001 | Patching behavior and backup/restore notes found. |
| Q003 | official docs | OpenAI Codex docs | `Codex open source IDE extension not open source app-server` | 1 | E002 | Official support/source boundary found. |
| Q004 | web/package | targeted package search | `codex-thread-renamer npm package` | 0 strong | N002 | No strong public package-registry evidence found in this scan. |
| Q005 | official docs | OpenAI Codex docs | `codex-thread-renamer official OpenAI supported` | 0 strong | N001 | No official endorsement found in searched official docs. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | 有公开 patcher 能改 Codex / VS Code thread title 相关 UI。 | vscode_extension | manual_rename | recent_but_unverified | E001 | none | single-source | 未执行 patcher，也未验证当前扩展版本兼容性。 |
| C002 | patcher 有 license、维护和发布信号。 | vscode_extension | not_applicable | recent_but_unverified | E001 | N002 | single-source | 未做长期维护趋势或供应链审计。 |
| C003 | patcher 修改 installed extension files，存在兼容和安全风险。 | local_state | not_applicable | recent_but_unverified | E001 | none | single-source | 未做本地实测；风险来自项目文档。 |
| C004 | 官方支持边界与 patcher 目标 surface 不完全一致。 | cross_surface | not_applicable | current_official | E002 | N001 | confirmed | 未找到 patcher 官方认可证据。 |
| C005 | patcher 是否可作为正式默认方案。 | cross_surface | not_applicable | recent_but_unverified | E001; E002 | N001; N002 | unverified | 需要代码审计、terms 检查和当前版本兼容验证。 |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: Just-Boring-Cat/codex-thread-renamer
- entity_type: open-source patcher / workaround
- core_function: Patches an installed Codex-related VS Code extension to add thread renaming affordances.
- relevance_score: 8
- reuse_score: 4
- score_scope: claim:C001
- method_similarity: 2
- method_note: The method is close to the desired rename workflow, but it relies on patching installed extension files rather than an official integration surface.
- source_grade: A
- evidence_status: single-source

#### Main Source

- title: Just-Boring-Cat/codex-thread-renamer
- url_or_local_reference: https://github.com/Just-Boring-Cat/codex-thread-renamer
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Repository evidence records a Codex thread renamer patcher, MIT license, release/commit activity, and VS Code extension patching workflow.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| docs/how-it-works.md | https://github.com/Just-Boring-Cat/codex-thread-renamer/blob/main/docs/how-it-works.md | 2026-07-09 | A | C003 |

#### Key Facts

- The repo is relevant because it targets Codex thread renaming.
- The documented mechanism modifies installed extension files such as package metadata or bundled code.
- The project documents verify/apply/backup/restore style operations.
- MIT license and maintenance signals are visible, but maturity appears limited.

#### Similarity Notes

- Problem similarity: high.
- User similarity: medium.
- Input similarity: medium.
- Output similarity: high for manual rename affordance.
- Workflow similarity: medium; patch-based workflow differs from safe official integration.
- Constraint similarity: low for formal default deployment.

#### Reuse Notes

- Reusable parts: UI affordance, patch safety checklist, backup/restore concept.
- Integration cost: high if used as formal path because it depends on extension internals.
- License or terms: MIT license visible for the repo; official extension terms not evaluated.
- Maintenance signal: some release/commit signal, but not enough for default adoption.

#### Gaps

- No code audit.
- No current installed-extension compatibility test.
- No legal/terms review.
- No user-environment execution.

#### Risks

- Breakage after upstream extension updates.
- Unsupported modification of installed extension files.
- Supply-chain and rollback risk.

### Entity E002

- entity_id: E002
- entity_name: Official Codex open-source/support boundary
- entity_type: official documentation
- core_function: Clarifies which Codex components are open source and which are not.
- relevance_score: 7
- reuse_score: 7
- score_scope: claim:C004
- method_similarity: 1
- method_note: This does not provide the patcher method, but it defines the official boundary needed to judge whether patching is a supported path.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Codex open source
- url_or_local_reference: https://developers.openai.com/codex/open-source
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official Codex docs list app-server as open source and identify the IDE extension as not open source.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Codex app-server | https://developers.openai.com/codex/app-server | 2026-07-09 | S | C004 |

#### Key Facts

- Official app-server surfaces are different from patching a local IDE extension.
- Not-open-source IDE extension status limits confidence in patch-based reuse.

#### Similarity Notes

- Problem similarity: medium.
- User similarity: high.
- Input similarity: low.
- Output similarity: low.
- Workflow similarity: low.
- Constraint similarity: high for official support boundary.

#### Reuse Notes

- Reusable parts: official support boundary and possible official app-server direction.
- Integration cost: medium.
- License or terms: official docs, not a reusable code artifact.
- Maintenance signal: official source.

#### Gaps

- Does not evaluate the patcher's legality or extension-specific terms.

#### Risks

- Official support boundary may change; current docs should be rechecked before implementation.

## Information Gaps

- No patcher execution.
- No current extension compatibility test.
- No code audit or security review.
- No official endorsement found.
- No terms/legal review.

## Negative Evidence Records

Negative Evidence can only mean strong evidence was not found within the covered source classes, queries, and limits. It must not be used to claim absolute non-existence.

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: Just-Boring-Cat/codex-thread-renamer is officially endorsed or listed by OpenAI as a supported Codex path.
- searched_source_classes: official Codex docs; targeted web search.
- searched_queries: `codex-thread-renamer official OpenAI supported`; `Codex open source IDE extension not open source`.
- result: No strong official endorsement found in the searched scope.
- interpretation_limit: This does not prove no private or future endorsement exists.

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: The patcher is distributed as a stable public package-registry artifact.
- searched_source_classes: package/web search; GitHub repo metadata.
- searched_queries: `codex-thread-renamer npm package`; repo package metadata.
- result: No strong public package-registry evidence found in this scan; repo evidence suggests project-local distribution.
- interpretation_limit: This does not prove no package exists under another name.

## Negative Search Scope

- Official endorsement.
- Public package distribution.
- Deprecated / unsupported signals were not exhaustively searched.

## Search Module Notes

- This Evidence Pack does not recommend adoption.
- The key distinction is functional similarity versus supportable formal reuse.
