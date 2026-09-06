# 15-Case Run Summary

## Purpose

This summary records the overnight 15-case calibration run. It is a review index, not a replacement for the Evidence Packs or Judgment Reports.

## Run Scope

- Branch: `codex/prework-15-case-iteration`
- Run date: 2026-07-09
- Case count: 15
- Review mode: independent research subagent briefs plus per-case independent review files
- Boundary: no crawler, RAG, reranker, platform adapter, or automation implementation was added

## Case Coverage

| case_id | case directory | primary conclusion | review status | key lesson |
| --- | --- | --- | --- | --- |
| A1 / PI-C001 | `codex-sidebar-title-management` | `补齐缺口` | Pass | Claim matrix fixed the broad-title-management misread. |
| A2 | `open-source-patcher-formal-solution` | `接入改造` | Pass | Open-source workaround is not automatically a safe default path. |
| A3 | `fast-changing-product-capability` | `直接采用` | Pass | Fresh official release evidence can supersede old issues. |
| B1 | `desktop-ai-floating-assistant` | `场景定制` | Pass | Product category exists, but full context-aware workflow needs tailoring. |
| B2 | `agent-instructions-best-practices` | `接入改造` | Pass | AGENTS.md patterns are reusable, but instruction files are not hard policy. |
| B3 | `obsidian-agent-knowledge-workflow` | `场景定制` | Pass | Obsidian is a good substrate, not a complete agent workflow by itself. |
| B4 | `free-large-file-translation-tools` | `接入改造` | Pass | Large-file translation is a pipeline, not one free unlimited tool. |
| C1 | `pinn-ilw-prior-work` | `先补证据` | Pass | The workflow correctly stopped on `ILW` ambiguity. |
| C2 | `xnet-fftxnet-pde-ilw` | `先补证据` | Pass | XNet evidence is borrowable, but FFT-XNet and XNet+ILW remain unverified. |
| C3 | `medical-transformer-ecmo-risk-reuse` | `场景定制` | Pass | Medical Transformer work is a method reference, not direct ECMO proof. |
| D1 | `pdf-vllm-icu-nursing-extraction` | `场景定制` | Pass | Clinical extraction requires separate PDF, NLP, inference, and review layers. |
| D2 | `ecmo-unstructured-extraction-prediction` | `场景定制` | Pass | Extraction and prediction must remain separate workflow stages. |
| D3 | `fluent-blood-flow-automation` | `接入改造` | Pass | Fluent automation is feasible, but physical validation remains separate. |
| E1 | `existing-skill-agent-framework-comparison` | `接入改造` | Pass | Skills and agent frameworks provide packaging/execution primitives, not the method itself. |
| E2 | `existing-work-search-method-prior-work` | `场景定制` | Pass | Mature methods should be absorbed selectively while preserving Search/Judgment separation. |

## Cross-Case Findings

- `先补证据` is working as a real stop condition, especially in C1 and C2.
- `freshness_status` matters most for fast-changing product cases such as A1 and A3.
- `surface_scope` matters most for Codex, desktop assistant, Obsidian, and local workflow cases.
- Medical and clinical cases need explicit non-clinical boundaries and privacy gaps.
- Engineering workflow cases need a separate validation layer; tool/API existence is not enough.
- Existing frameworks and methodologies support Prework, but no searched source replaces the whole workflow.

## Tomorrow Review Priority

Review these first:

1. C1, because the `ILW` ambiguity may require rerunning that case with the intended meaning.
2. A3, because it validates whether the freshness gate behaves as intended.
3. D1 and D2, because they are privacy-sensitive and clinically adjacent.
4. B1, because it is likely the next practical product/tooling exploration case.

## Final Independent Review Notes

- Final reviewer verdict: Pass with concerns.
- Critical issues: none.
- Important issue fixed: A3 C004 now records `claim_evidence_status: unverified` for background same-desktop Windows Computer Use.
- Minor issue fixed: D1 `What Not To Do` now cites Evidence Pack records instead of a generic privacy gap.
- Minor issue accepted: A1 is displayed as `A1 / PI-C001` to preserve legacy case identity.

## Suggested Next Decision

Decide whether to revise V1.1 into V1.2 based on the recurring lessons from these cases, especially:

- a formal ambiguity gate for overloaded terms;
- a stronger local/private data boundary;
- a validation-layer field for clinical and simulation workflows;
- a compact case package standard for high-volume calibration runs.
