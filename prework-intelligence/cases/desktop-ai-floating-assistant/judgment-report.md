# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: B1
- Evidence Pack path: `docs/prework-intelligence/cases/desktop-ai-floating-assistant/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`场景定制`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `E004`, `N001`.

## Conclusion Rationale

- Primary conclusion: `场景定制`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `E004`, `N001`
- Why these evidence records support the conclusion: Existing products show the category is real, but the complete desired combination of desktop availability, context access, privacy, API-key flexibility, and Windows support is not established as one mature direct substitute.
- Important evidence gaps: hands-on Windows tests, privacy/security review, pricing, and context capture behavior.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | First-party AI products provide desktop entry points. | desktop_app | not_applicable | current_official | `直接采用` | E001; E002 | Use where built-in capability is enough. | Feature parity varies. |
| C002 | Third-party Mac tools cover shortcut/selected-text workflows. | desktop_app | not_applicable | current_official | `接入改造` | E003; E004 | Strong workflow references. | Windows fit uncertain. |
| C003 | Full value depends on context, privacy, model choice, and automation. | cross_surface | not_applicable | recent_but_unverified | `场景定制` | E001; E002; E003; E004; N001 | Existing tools cover parts, not the full target. | Needs hands-on constraints. |
| C004 | One mature free cross-platform complete solution exists. | cross_surface | not_applicable | recent_but_unverified | `先补证据` | N001 | No strong evidence in searched scope. | Broader product search could refine. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | ChatGPT Desktop / Chat Bar | 8 | 7 | S | confirmed | Direct first-party baseline. |
| E002 | Gemini desktop / Google desktop app | 8 | 7 | S | confirmed | Comparable first-party baseline. |
| E003 | BoltAI | 9 | 6 | S | confirmed | Strong workflow reference. |
| E004 | Elephas / Raycast AI | 8 | 6 | S | confirmed | Comparable workflow reference. |

## Why Existing Work Does Or Does Not Substitute

Existing products substitute for parts of the idea, but not clearly for the full Windows-oriented, context-aware, privacy-controlled, API-flexible assistant.

## What To Reuse

- First-party desktop app expectations from `E001` and `E002`.
- Shortcut and selected-text command patterns from `E003` and `E004`.
- Permission and privacy questions implied by `N001`.

## What Not To Do

- Do not call a browser sidebar a global desktop assistant. Cite `N001`.
- Do not assume overlay chat means context capture. Cite `E001`, `E003`, and `N001`.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Complete single free cross-platform solution | Product pages and docs | Supports `场景定制`. | Does not prove none exists. |

## Next Action

Define the minimum target surface and run a narrower hands-on comparison of Windows-capable candidates before building anything.
