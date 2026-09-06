# Evidence Pack

This is the Search Module handoff artifact for Case B3. It records evidence, not final decisions.

## Case Metadata

- Case ID: B3
- Idea title: Obsidian plus coding-agent knowledge workflow
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent product/tooling subagent brief

## Coverage Summary

- Searched source classes: Obsidian official docs; community plugin directory; maintainer repos; security analysis.
- Unsearched source classes: hands-on plugin install; private vault inspection; plugin code audit.
- Languages searched: English.
- Coverage note: Sufficient to identify workflow components and risks, not to approve a production setup.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official docs | Obsidian | Obsidian local Markdown vault data storage | 2 | E001 | Vault data model. |
| Q002 | plugin directory | Obsidian community plugins | agent client vault MCP local REST API | several | E002; E003 | Agent/MCP access routes. |
| Q003 | security analysis | 0DIN | coding agent prompt injection repository markdown | 1 | E004 | Safety boundary. |
| Q004 | negative search | official Obsidian docs | official coding agent knowledge workflow best practice | 0 strong | N001 | No official complete workflow found. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Obsidian local Markdown vault is a compatible knowledge substrate. | local_state | not_applicable | current_official | E001 | none | confirmed | Compatibility does not prove workflow. |
| C002 | Plugins expose agent/CLI/MCP or API access to vault content. | cross_surface | not_applicable | recent_but_unverified | E002; E003 | none | single-source | Plugin quality and permissions need review. |
| C003 | A complete official coding-agent knowledge workflow is established. | cross_surface | not_applicable | recent_but_unverified | E001; E002; E003 | N001 | unverified | Evidence mainly plugin ecosystem. |
| C004 | Vault content can create prompt-injection or command-risk surfaces for coding agents. | local_state | not_applicable | recent_but_unverified | E004 | none | single-source | Evidence is adjacent, not Obsidian-specific. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: Obsidian local Markdown vault
- entity_type: local knowledge store
- core_function: Stores notes as local Markdown files.
- relevance_score: 10
- reuse_score: 9
- score_scope: surface:local_state
- method_similarity: 2
- method_note: Directly matches Markdown-first project context storage.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Obsidian data storage
- url_or_local_reference: https://obsidian.md/help/data-storage
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official docs describe Obsidian's local file storage model.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Import Markdown | https://obsidian.md/help/import/markdown | 2026-07-09 | S | C001 |

#### Gaps

- No agent workflow proof.

#### Risks

- Local files may contain sensitive project notes.

### Entity E002

- entity_id: E002
- entity_name: Obsidian Agent Client
- entity_type: community plugin
- core_function: Connects Obsidian to agent clients such as Claude Code, Codex, or Gemini CLI.
- relevance_score: 10
- reuse_score: 7
- score_scope: surface:cross_surface
- method_similarity: 2
- method_note: Closely matches agent-vault integration, but is community-maintained and needs audit.
- source_grade: A
- evidence_status: single-source

#### Main Source

- title: Agent Client plugin
- url_or_local_reference: https://community.obsidian.md/plugins/agent-client
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Plugin directory evidence indicates agent-client integration for Obsidian.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| obsidian-agent-client | https://github.com/rait-09/obsidian-agent-client | 2026-07-09 | A | C002 |

#### Gaps

- No plugin security audit.
- No hands-on workflow test.

#### Risks

- Permissions, token storage, and command execution need review.

### Entity E003

- entity_id: E003
- entity_name: Vault as MCP / Local REST API / mcp-obsidian
- entity_type: plugin/API access route
- core_function: Exposes vault content through MCP or local REST interfaces.
- relevance_score: 9
- reuse_score: 7
- score_scope: surface:cross_surface
- method_similarity: 2
- method_note: Provides plausible agent-access infrastructure, but not a full workflow design.
- source_grade: A
- evidence_status: single-source

#### Main Source

- title: Vault as MCP
- url_or_local_reference: https://community.obsidian.md/plugins/vault-as-mcp
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Community plugin evidence for exposing Obsidian vault through MCP.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Obsidian Local REST API | https://github.com/coddingtonbear/obsidian-local-rest-api | 2026-07-09 | A | C002 |

#### Gaps

- No end-to-end coding-agent workflow validation.

#### Risks

- Exposing vault APIs increases access-control risk.

### Entity E004

- entity_id: E004
- entity_name: Coding-agent prompt injection risk in repository content
- entity_type: security analysis
- core_function: Demonstrates that local text content can influence coding agents in unsafe ways.
- relevance_score: 7
- reuse_score: 5
- score_scope: claim:C004
- method_similarity: 1
- method_note: Adjacent risk evidence; not Obsidian-specific but relevant to vault-as-context workflows.
- source_grade: S
- evidence_status: single-source

#### Main Source

- title: Clone This Repo and I Own Your Machine
- url_or_local_reference: https://0din.ai/blog/clone-this-repo-and-i-own-your-machine
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Security analysis shows how repository content can become an agent prompt-injection vector.

#### Gaps

- Not specific to Obsidian plugins.

#### Risks

- Vault content can become untrusted agent context.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: Obsidian official documentation provides a mature coding-agent knowledge workflow best practice.
- searched_source_classes: Obsidian official docs; community plugin directory; plugin repos.
- searched_queries: `Obsidian coding agent workflow official`; `Obsidian Codex Claude Code workflow`.
- result: No strong official workflow found in searched scope; evidence mainly comes from plugin ecosystem.
- interpretation_limit: This does not prove no workflow exists in private/community practice.

## Information Gaps

- No plugin audit.
- No private vault inspection.
- No hands-on bidirectional sync test.

## Search Module Notes

- This pack distinguishes Markdown substrate, plugin access, workflow maturity, and safety risk.
