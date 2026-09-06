# Evidence Pack

This is the Search Module handoff artifact for Case B1. It records evidence, not final decisions.

## Case Metadata

- Case ID: B1
- Idea title: Desktop always-available AI floating assistant
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent product/tooling subagent brief

## Coverage Summary

- Searched source classes: official product docs/pages; third-party tool docs; targeted negative evidence.
- Unsearched source classes: hands-on latency/permission tests; enterprise policy review; full Windows Store/App Store search.
- Languages searched: English.
- Coverage note: Coverage is sufficient to separate product categories, but not to select a final purchased tool.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official product | OpenAI / Google | desktop AI app chat bar companion context | several | E001; E002 | First-party desktop assistants. |
| Q002 | product docs | BoltAI / Elephas / Raycast | AI command selected text floating assistant | several | E003; E004 | Third-party desktop workflows. |
| Q003 | negative search | mixed product docs | free cross-platform global floating AI screen context | 0 strong | N001 | No single complete free cross-platform solution found. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Major first-party AI products provide desktop entry points such as app, chat bar, or companion windows. | desktop_app | not_applicable | current_official | E001; E002 | none | confirmed | Exact feature parity varies by platform. |
| C002 | Third-party Mac tools cover selected-text and shortcut-based AI commands. | desktop_app | not_applicable | current_official | E003; E004 | none | confirmed | Windows/Linux evidence weaker. |
| C003 | Full value depends on context capture, permissions, privacy, model choice, and automation. | cross_surface | not_applicable | recent_but_unverified | E001; E002; E003; E004 | N001 | confirmed | Requires hands-on testing. |
| C004 | A single free, cross-platform, low-permission, context-aware floating assistant is already mature. | cross_surface | not_applicable | recent_but_unverified | none | N001 | unverified | Negative evidence limited to searched product docs. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: ChatGPT Desktop / Chat Bar
- entity_type: first-party desktop AI product
- core_function: Provides desktop ChatGPT access through desktop app and quick-launch chat bar.
- relevance_score: 8
- reuse_score: 7
- score_scope: surface:desktop_app
- method_similarity: 1
- method_note: Same broad goal of always-available AI, but not necessarily full custom floating assistant with arbitrary page/context capture.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: ChatGPT desktop
- url_or_local_reference: https://chatgpt.com/features/desktop/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official product page documents ChatGPT desktop availability and desktop access.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| How to launch the Chat Bar | https://help.openai.com/en/articles/9295241-how-to-launch-the-chat-bar | 2026-07-09 | S | C001 |

#### Key Facts

- First-party desktop access exists.
- It does not by itself prove custom cross-app context capture or local API-key workflow.

#### Gaps

- No hands-on Windows permission or context test.

#### Risks

- Feature availability may vary by platform, account, and release.

### Entity E002

- entity_id: E002
- entity_name: Gemini desktop / Google desktop app
- entity_type: first-party desktop AI product
- core_function: Provides desktop AI access and some window or local context features.
- relevance_score: 8
- reuse_score: 7
- score_scope: surface:desktop_app
- method_similarity: 1
- method_note: Similar product category, but not necessarily a reusable custom assistant foundation.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Gemini macOS
- url_or_local_reference: https://gemini.google/mac/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official page describes Gemini desktop access on macOS.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Google app for desktop | https://search.google/google-app/desktop/ | 2026-07-09 | S | C001 |

#### Gaps

- No Windows feature parity test.

#### Risks

- Ecosystem-specific and not necessarily OpenAI-compatible.

### Entity E003

- entity_id: E003
- entity_name: BoltAI
- entity_type: third-party desktop AI tool
- core_function: Provides AI commands, shortcut workflows, and model integration on desktop.
- relevance_score: 9
- reuse_score: 6
- score_scope: surface:desktop_app
- method_similarity: 2
- method_note: Closely matches selected-text and desktop command workflow, but platform and product fit need verification.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: BoltAI
- url_or_local_reference: https://boltai.com/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Product documentation describes desktop AI workflows and AI Command.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| BoltAI AI Command | https://docs.boltai.com/docs/ai-command/overview | 2026-07-09 | S | C002 |

#### Gaps

- Windows support and enterprise controls not established in this pack.

#### Risks

- Pricing and product limits may change.

### Entity E004

- entity_id: E004
- entity_name: Elephas / Raycast AI
- entity_type: third-party desktop AI tools
- core_function: Provides selected-text, command, and productivity AI workflows.
- relevance_score: 8
- reuse_score: 6
- score_scope: surface:desktop_app
- method_similarity: 1
- method_note: Useful comparable workflows, but not direct substitutes for a Windows global assistant.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Elephas
- url_or_local_reference: https://elephas.app/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Product page describes desktop AI productivity workflows.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Raycast AI Chat | https://manual.raycast.com/ai/chat | 2026-07-09 | S | C002 |

#### Gaps

- Tools grouped as comparable patterns; not one unified entity for procurement.

#### Risks

- Platform lock-in and pricing.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: A single free, mature, cross-platform, low-permission desktop AI floating assistant already covers global invocation, screen/file context, API-key flexibility, and Windows support.
- searched_source_classes: official product pages; third-party product docs.
- searched_queries: `free cross platform AI floating assistant screen context`; `desktop AI assistant selected text Windows API key`.
- result: No strong single-solution evidence found in the searched scope; evidence points to partial product categories.
- interpretation_limit: This does not prove such a tool does not exist.

## Information Gaps

- Hands-on permission, latency, stability, and pricing verification.
- Windows-specific context-reading test.
- Enterprise/security policy review.

## Search Module Notes

- This pack records product categories and gaps only.
