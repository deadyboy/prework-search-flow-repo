# Evidence Pack

This is the Search Module handoff artifact for Case E1. It records evidence, not final decisions.

## Case Metadata

- Case ID: E1
- Idea title: Existing skill / agent workflow framework comparison
- Original idea: Compare mature skill and agent workflow frameworks against Prework Intelligence.
- Search level: L3 deep review
- Search date: 2026-07-09
- Searcher: Codex with independent meta-framework subagent brief

## Coverage Summary

- Searched source classes: official skill docs; official agent-framework docs; institutional framework comparison guidance.
- Unsearched source classes: hands-on framework implementation; private framework repos; paid analyst reports.
- Languages searched: English.
- Timebox: targeted meta-framework scan.
- Coverage note: Coverage is sufficient for method comparison, not for selecting an implementation runtime.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official docs | Agent Skills / Claude / Codex / GitHub | `agent skills SKILL.md Codex Claude GitHub` | many | E001 | Skill packaging evidence. |
| Q002 | official docs | LangGraph / OpenAI Agents SDK / CrewAI / Microsoft / Haystack / LlamaIndex | `agent workflow framework guardrails handoff tracing` | many | E002 | Execution framework evidence. |
| Q003 | official docs | OpenAI Agents SDK / LangGraph / Haystack | `guardrails workflow boundary handoff tracing pipeline tool` | several | E003 | Boundary-control evidence. |
| Q004 | web/institutional | AWS comparison | `comparing agentic AI frameworks` | 1 | E004 | Framework comparison criteria. |
| Q005 | negative search | major framework docs | `prior work search judgment evidence pack agent framework` | 0 strong | N001 | No ready-made Prework equivalent found in searched scope. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Skill 格式已形成可复用的工作流封装模式。 | cross_surface | not_applicable | current_official | E001 | none | confirmed | Need later decision on whether to package Prework as a skill. |
| C002 | Agent frameworks 提供可复用的执行原语。 | cross_surface | not_applicable | current_official | E002 | none | confirmed | No runtime selection or prototype done. |
| C003 | Guardrails / handoff / tracing 可帮助保持边界。 | cross_surface | not_applicable | current_official | E003 | none | confirmed | Needs future case proof before implementation. |
| C004 | 未发现现成 Prework Intelligence 等价框架。 | cross_surface | not_applicable | recent_but_unverified | E001; E002; E004 | N001 | unverified | Negative evidence limited to searched public docs. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: Agent Skills / Claude Skills / Codex Skills / GitHub Copilot agent skills
- entity_type: skill packaging format
- core_function: Encapsulates instructions, triggers, resources, scripts, and reusable workflow assets.
- relevance_score: 10
- reuse_score: 9
- score_scope: whole_entity
- method_similarity: 2
- method_note: The packaging method closely matches Prework's need for reusable methods, templates, and strategy cards.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Agent Skills
- url_or_local_reference: https://agentskills.io/home
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Public skill format documents a portable structure for instructions, metadata, scripts, and resources.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Claude Code Skills | https://docs.anthropic.com/en/docs/claude-code/skills | 2026-07-09 | S | C001 |
| Codex Agent Skills | https://developers.openai.com/codex/skills | 2026-07-09 | S | C001 |
| GitHub Copilot agent skills | https://docs.github.com/copilot/concepts/agents/about-agent-skills | 2026-07-09 | S | C001 |

#### Key Facts

- Skill formats are strong evidence for reusable workflow packaging.
- They do not by themselves define a prior-work search or worth-doing judgment method.

#### Similarity Notes

- Problem similarity: high.
- User similarity: high.
- Input similarity: high.
- Output similarity: high.
- Workflow similarity: high.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: file structure, triggers, inputs/outputs, resources, verification sections.
- Integration cost: low for documentation packaging; higher for runtime execution.
- License or terms: depends on source; docs are public references.
- Maintenance signal: current official docs.

#### Gaps

- No decision to package Prework as a deployable skill yet.

#### Risks

- Over-packaging could add ceremony before more cases prove stability.

### Entity E002

- entity_id: E002
- entity_name: LangGraph, OpenAI Agents SDK, CrewAI, Microsoft Agent Framework, LlamaIndex AgentWorkflow, Haystack Agents
- entity_type: agent workflow frameworks
- core_function: Provide graph/state, tools, handoff, memory, tracing, and multi-agent orchestration primitives.
- relevance_score: 8
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 1
- method_note: These frameworks are method-adjacent: useful for future execution, but not the same as Prework's evidence/judgment method.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: LangGraph overview
- url_or_local_reference: https://docs.langchain.com/oss/python/langgraph/overview
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: LangGraph documents graph/state-based agent workflows and durable execution concepts.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| OpenAI Agents SDK | https://openai.github.io/openai-agents-python/ | 2026-07-09 | S | C002 |
| CrewAI docs | https://docs.crewai.com/ | 2026-07-09 | S | C002 |
| Microsoft Agent Framework | https://learn.microsoft.com/en-us/agent-framework/overview/ | 2026-07-09 | S | C002 |
| LlamaIndex AgentWorkflow | https://developers.llamaindex.ai/python/examples/agent/agent_workflow_basic/ | 2026-07-09 | A | C002 |
| Haystack Agents | https://docs.haystack.deepset.ai/docs/agents | 2026-07-09 | S | C002 |

#### Key Facts

- Agent frameworks can implement workflows, but do not prove Prework should automate now.
- Execution primitives are relevant later, after the file-based method stabilizes.

#### Similarity Notes

- Problem similarity: medium.
- User similarity: medium.
- Input similarity: low.
- Output similarity: low.
- Workflow similarity: medium.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: orchestration, persistence, tools, handoff, tracing.
- Integration cost: medium to high.
- License or terms: framework-specific.
- Maintenance signal: active official docs.

#### Gaps

- No prototype or runtime comparison.

#### Risks

- Premature automation could blur Search/Judgment separation.

### Entity E003

- entity_id: E003
- entity_name: Guardrails, handoff, tracing, and workflow-boundary patterns
- entity_type: boundary-control pattern
- core_function: Provides concepts for enforcing or observing workflow boundaries.
- relevance_score: 8
- reuse_score: 7
- score_scope: claim:C003
- method_similarity: 1
- method_note: Boundary-control concepts are useful, but Prework currently enforces boundaries through documents rather than runtime.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: OpenAI Agents SDK guardrails
- url_or_local_reference: https://openai.github.io/openai-agents-python/guardrails/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Guardrails documentation describes boundary checks around agent workflows.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| LangGraph workflows and agents | https://docs.langchain.com/oss/python/langgraph/workflows-agents | 2026-07-09 | S | C003 |
| Haystack PipelineTool | https://docs.haystack.deepset.ai/docs/pipelinetool | 2026-07-09 | S | C003 |

#### Key Facts

- Runtime boundary tools exist.
- They are future candidates, not needed for current file-based cases.

#### Similarity Notes

- Problem similarity: medium.
- User similarity: medium.
- Input similarity: low.
- Output similarity: low.
- Workflow similarity: medium.
- Constraint similarity: high.

#### Reuse Notes

- Reusable parts: guardrail concept, traceability, handoff boundaries.
- Integration cost: medium.
- License or terms: framework-specific.
- Maintenance signal: current docs.

#### Gaps

- No case yet proves runtime guardrails are necessary.

#### Risks

- Could add complexity without improving current evidence quality.

### Entity E004

- entity_id: E004
- entity_name: AWS agentic AI framework comparison
- entity_type: framework selection guidance
- core_function: Offers comparison dimensions for agentic AI frameworks.
- relevance_score: 6
- reuse_score: 5
- score_scope: whole_entity
- method_similarity: 1
- method_note: Useful for future runtime selection, not for Prework's current evidence/judgment method.
- source_grade: A
- evidence_status: single-source

#### Main Source

- title: Comparing agentic AI frameworks
- url_or_local_reference: https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-frameworks/comparing-agentic-ai-frameworks.html
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Institutional guidance compares agentic frameworks by dimensions such as customization, maintainability, and organizational fit.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Agentic AI frameworks | https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-frameworks/frameworks.html | 2026-07-09 | A | C004 |

#### Key Facts

- Framework comparison dimensions exist.
- They do not replace Prework's case-based evidence method.

#### Similarity Notes

- Problem similarity: medium.
- User similarity: medium.
- Input similarity: low.
- Output similarity: medium.
- Workflow similarity: low.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: comparison dimensions for future runtime choice.
- Integration cost: low as reference.
- License or terms: public guidance.
- Maintenance signal: institutional docs.

#### Gaps

- Does not cover Search/Judgment split.

#### Risks

- May bias toward implementation frameworks before method maturity.

## Information Gaps

- No hands-on implementation comparison.
- No runtime benchmark.
- No full GitHub ecosystem scan.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: A ready-made public framework already implements Prework Intelligence's three-question method with strict Search Module -> Evidence Pack -> Judgment Module separation.
- searched_source_classes: official skill docs; agent framework docs; AWS framework comparison.
- searched_queries: `prior work search judgment evidence pack agent framework`; `Search Module Evidence Pack Judgment Module agent framework`; `skill prior work search decision framework`.
- result: No strong evidence found for a ready-made equivalent in the searched scope.
- interpretation_limit: This does not prove no such private or niche framework exists.

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: Skill standards themselves contain prior-work search and worth-doing judgment methodology.
- searched_source_classes: Agent Skills spec; Claude/Codex/GitHub skill docs.
- searched_queries: `agent skills prior work search`; `skills worth doing judgment`.
- result: Skill docs support packaging and invocation, not a complete Prework judgment method.
- interpretation_limit: This is scoped to public docs searched.

## Negative Search Scope

- Ready-made Prework equivalent.
- Skill standard as decision method.
- Runtime framework as direct replacement.

## Search Module Notes

- This pack does not recommend automation.
- It records reusable structures and boundaries for future method evolution.
