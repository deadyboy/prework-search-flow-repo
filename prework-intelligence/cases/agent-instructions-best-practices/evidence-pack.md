# Evidence Pack

This is the Search Module handoff artifact for Case B2. It records evidence, not final decisions.

## Case Metadata

- Case ID: B2
- Idea title: AGENTS.md / CLAUDE.md best practices
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent product/tooling subagent brief

## Coverage Summary

- Searched source classes: official docs; open format docs; GitHub/VS Code docs; official community analysis.
- Unsearched source classes: full repository mining; hands-on multi-tool conflict tests.
- Languages searched: English.
- Coverage note: Sufficient to identify reusable categories and tool differences.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official/open format | agents.md / OpenAI Codex | AGENTS.md Codex guide | several | E001; E002 | AGENTS.md evidence. |
| Q002 | official docs | Anthropic Claude Code | CLAUDE.md memory docs | 1 | E003 | Claude memory behavior. |
| Q003 | official docs | GitHub / VS Code | Copilot custom instructions VS Code | several | E004 | Tool differences. |
| Q004 | negative search | official docs | unified hard execution semantics AGENTS CLAUDE | 0 strong | N001 | No unified enforcement semantics. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | AGENTS.md is a reusable project-instruction format candidate. | cross_surface | not_applicable | current_official | E001; E002 | none | confirmed | Exact loading varies by tool. |
| C002 | Best practices emphasize short, concrete, executable, local-scope rules with tests and boundaries. | cross_surface | not_applicable | current_official | E001; E002; E004 | none | confirmed | Full repo-mining not done. |
| C003 | CLAUDE.md is Claude Code memory/context, not a universal Codex standard. | cross_surface | not_applicable | current_official | E003 | none | confirmed | Cross-tool migration needs adaptation. |
| C004 | Instruction files are not hard safety or policy boundaries. | cross_surface | not_applicable | current_official | E003; E004 | N001 | confirmed | Enforcement requires hooks/policy outside this case. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: AGENTS.md open format
- entity_type: instruction-file convention
- core_function: Provides a shared project instruction file convention for coding agents.
- relevance_score: 11
- reuse_score: 9
- score_scope: whole_entity
- method_similarity: 2
- method_note: Closely matches project-level agent instruction needs.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: AGENTS.md
- url_or_local_reference: https://agents.md/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Open format page describes AGENTS.md as a shared instruction convention.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| OpenAI Codex AGENTS.md | https://developers.openai.com/codex/guides/agents-md | 2026-07-09 | S | C001 |

#### Key Facts

- AGENTS.md is highly relevant to Codex-style project rules.
- It should be adapted to local project needs.

#### Gaps

- No broad repository mining in this case.

#### Risks

- Adoption signal does not prove effectiveness.

### Entity E002

- entity_id: E002
- entity_name: GitHub lessons from AGENTS.md usage
- entity_type: official community analysis
- core_function: Summarizes observed best-practice patterns from many repositories.
- relevance_score: 9
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 2
- method_note: Directly supports reusable rule categories, but is not a formal standard.
- source_grade: A
- evidence_status: single-source

#### Main Source

- title: How to write a great AGENTS.md
- url_or_local_reference: https://github.blog/ai-and-ml/github-copilot/how-to-write-a-great-agents-md-lessons-from-over-2500-repositories/
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: GitHub analysis discusses lessons from observed AGENTS.md usage.

#### Gaps

- Analysis is guidance, not a binding spec.

#### Risks

- Popular patterns may not fit every tool.

### Entity E003

- entity_id: E003
- entity_name: Claude Code CLAUDE.md memory
- entity_type: official tool memory/instruction docs
- core_function: Defines Claude Code's persistent memory and project instruction behavior.
- relevance_score: 9
- reuse_score: 7
- score_scope: whole_entity
- method_similarity: 1
- method_note: Similar purpose but tool-specific loading and memory behavior.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Claude Code memory
- url_or_local_reference: https://code.claude.com/docs/en/memory
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Claude Code docs describe CLAUDE.md project/user/local memory behavior and imports.

#### Gaps

- Does not define Codex behavior.

#### Risks

- Tool-specific rules can be misapplied.

### Entity E004

- entity_id: E004
- entity_name: GitHub Copilot and VS Code custom instructions
- entity_type: official tool instruction docs
- core_function: Defines custom instruction behavior in Copilot and VS Code.
- relevance_score: 8
- reuse_score: 7
- score_scope: whole_entity
- method_similarity: 1
- method_note: Similar instruction concept, but different loading rules and execution semantics.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: GitHub Copilot custom instructions
- url_or_local_reference: https://docs.github.com/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official docs describe Copilot custom instructions.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| VS Code custom instructions | https://code.visualstudio.com/docs/agent-customization/custom-instructions | 2026-07-09 | S | C002; C004 |

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: AGENTS.md, CLAUDE.md, and GitHub/VS Code instruction files share one unified cross-tool priority model and hard execution semantics.
- searched_source_classes: official docs and open format docs.
- searched_queries: `AGENTS.md CLAUDE.md unified priority hard enforcement`.
- result: No strong evidence found for one unified hard execution model; evidence indicates tool-specific behavior.
- interpretation_limit: This does not prove no adapter or future standard exists.

## Information Gaps

- No full repo mining.
- No hands-on conflict behavior tests across tools.

## Search Module Notes

- This pack records reusable patterns and tool boundaries only.
