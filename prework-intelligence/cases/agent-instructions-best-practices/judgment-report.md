# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: B2
- Evidence Pack path: `docs/prework-intelligence/cases/agent-instructions-best-practices/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`接入改造`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `E004`, `N001`.

## Conclusion Rationale

- Primary conclusion: `接入改造`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `E004`, `N001`
- Why these evidence records support the conclusion: Existing official and high-signal guidance provides reusable patterns, but tool-specific behavior means the project should adapt rather than copy a single template.
- Important evidence gaps: no broad repo mining or cross-tool conflict tests.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | AGENTS.md is reusable. | cross_surface | not_applicable | current_official | `直接采用` | E001 | Strong fit for Codex project instructions. | Loading varies by tool. |
| C002 | Best practices emphasize short concrete rules. | cross_surface | not_applicable | current_official | `接入改造` | E001; E002; E004 | Reuse categories, adapt locally. | No repo mining. |
| C003 | CLAUDE.md is Claude-specific. | cross_surface | not_applicable | current_official | `场景定制` | E003 | Useful reference, not Codex standard. | Migration needs adaptation. |
| C004 | Instruction files are not hard safety enforcement. | cross_surface | not_applicable | current_official | `补齐缺口` | E003; E004; N001 | Need hooks/policies for hard boundaries. | Enforcement not covered. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | AGENTS.md open format | 11 | 9 | S | confirmed | Main reusable base. |
| E002 | GitHub lessons from AGENTS.md usage | 9 | 8 | A | single-source | Best-practice patterns. |
| E003 | Claude Code CLAUDE.md memory | 9 | 7 | S | confirmed | Tool-specific comparison. |
| E004 | GitHub Copilot and VS Code custom instructions | 8 | 7 | S | confirmed | Cross-tool boundary evidence. |

## What To Reuse

- AGENTS.md structure from `E001`.
- Concise, local, testable rule categories from `E002`.
- Tool-specific layering caution from `E003` and `E004`.

## What Not To Do

- Do not treat CLAUDE.md rules as directly portable to Codex. Cite `E003`.
- Do not treat instruction files as safety enforcement. Cite `N001`.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Unified hard semantics | Official docs | Supports tool-specific adaptation. | Future standards may change. |

## Next Action

Adopt AGENTS.md-style concise project rules, but keep tool-specific sections and do not use instruction files as the only safety boundary.
