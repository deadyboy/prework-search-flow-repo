# Case Calibration Catalog

This catalog lists candidate cases for calibrating Prework Intelligence. It is a backlog, not authorization to run all cases.

## Purpose

The case set is designed to expose workflow defects, calibrate fields, and test whether Search and Judgment stay separated.

Cases should cover different source-selection routes: software/tooling, product/competitor, research/method, vertical business process, and meta-framework comparison.

Do not create a case directory until that case is selected for execution.

## Recommended Execution Order

| order | case_id | case | why first |
| ---: | --- | --- | --- |
| 1 | A1 | Codex sidebar title management regression | Existing failure sample; best test for V1.1 claim matrix, surface scope, and freshness. |
| 2 | E1 | Existing skill / agent workflow framework comparison | Tests whether the framework should learn from mature skill systems without copying their complexity. |
| 3 | B1 | Desktop always-available AI floating assistant | Roadmap Case 2; tests product substitution and current user-facing utility. |
| 4 | D1 | PDF-VLLM ICU nursing-record extraction improvement | Tests privacy-sensitive vertical workflow and internal-project constraints. |
| 5 | C1 | PINN + ILW prior work | Tests academic prior work, method similarity, and baseline separation. |

Run only one case at a time. After each case, update the retrospective before selecting the next case.

## Calibration Backlog

### A1 - Codex sidebar title management regression

- case_type: Calibration
- search_level: L2 standard scan
- tests: Claim Matrix; `surface_scope`; `freshness_status`; Current Product Capability Gate
- must_discover: manual rename, app-server rename API, fork or branch title lifecycle, legacy title handling, batch governance are separate claims.
- must_not_misjudge: do not describe Codex title management as wholly missing; do not treat old issues as current product gaps.
- pass_signal: Judgment expresses manual rename as existing capability while batch, fork, and legacy governance remain gaps or supplement-evidence requests.

### A2 - Open-source patcher as formal solution

- case_type: Calibration
- search_level: L2, L3 if license and compatibility are decision-critical
- tests: GitHub Implementation Search; `reuse_score`; risks; What Not To Do
- must_discover: file patching behavior, license, maintenance signal, target surface, backup, verification, rollback, official support status.
- must_not_misjudge: do not recommend `直接采用` only because a repo is functionally similar.
- pass_signal: Judgment distinguishes workaround, reference implementation, and safe default path.

### A3 - Fast-changing current product capability

- case_type: Calibration
- search_level: L2 standard scan
- tests: `freshness_status`; release timeline; issue staleness detection
- must_discover: official changelog, current docs, issue date versus release date, and current UI or user-observed evidence when allowed.
- must_not_misjudge: do not let stale issues override newer official release evidence.
- pass_signal: Evidence Pack has a clear timeline and Judgment treats old issues as historical unless freshness is confirmed.

### B1 - Desktop always-available AI floating assistant

- case_type: Real Exploration
- search_level: L2 standard scan
- tests: Product Competitor Search; GitHub Implementation Search; `surface_scope`; privacy constraints; product substitution
- must_discover: browser sidebars, desktop floating windows, local LLM tools, OpenAI-compatible API support, page or active-window context capture, Windows support, permissions.
- must_not_misjudge: do not treat browser sidebar or ordinary chat overlay as a global desktop assistant with page-context access.
- pass_signal: Judgment separates direct-use tools, configurable API-key tools, UI-pattern references, and tools that fail context-reading requirements.

### B2 - AGENTS.md / CLAUDE.md best practices

- case_type: Real Exploration
- search_level: L2 standard scan
- tests: source authority grading; pattern aggregation; cross-tool comparison; `method_similarity`
- must_discover: official docs, real repo examples, community experience, risk of overconstraint, file-name and loading-rule differences.
- must_not_misjudge: do not treat one user's template as a general standard or copy Claude Code rules directly into Codex.
- pass_signal: Report produces reusable rule categories and fit limits, not only links.

### B3 - Obsidian plus coding-agent knowledge workflow

- case_type: Real Exploration
- search_level: L2 standard scan
- tests: product versus workflow substitute; private-source policy; Unacceptable Substitutes; workflow-pattern gap
- must_discover: Obsidian plugins, Git-based docs workflows, AI agent memory systems, Markdown-first context, bidirectional sync, RAG or embeddings dependence, privacy risk.
- must_not_misjudge: do not treat ordinary Obsidian AI plugins as stable coding-agent project context.
- pass_signal: Claim Matrix separates note management, agent context injection, long-term memory, and task sync.

### B4 - Free large-file translation tool combination

- case_type: Real Exploration
- search_level: L2 standard scan
- tests: Product Competitor Search; pricing and access model; privacy risk; terms coverage
- must_discover: file size limits, supported formats, real free limits, batching, upload privacy, local translation alternatives, API or desktop substitutes.
- must_not_misjudge: do not treat short-text translation pages as large-file translation tools.
- pass_signal: Report groups online free, freemium, local open-source, and paid reliable options with limits.

### C1 - PINN + ILW prior work

- case_type: Stress Test
- search_level: L3 deep review
- tests: Paper Prior Work Search; `method_similarity`; same method different goal; baseline identification
- must_discover: PINN hard constraints, weak or soft boundary constraints, inverse Lax-Wendroff boundary handling, related PDE domains, code, benchmark, baseline.
- must_not_misjudge: do not treat generic PINN boundary constraints or numerical ILW alone as direct ILW-PINN prior work.
- pass_signal: Prior work map separates direct, adjacent, baseline, and unrelated work.

### C2 - X-Net / FFT-XNet for PDE solving with ILW

- case_type: Stress Test
- search_level: L2 or L3
- tests: method transfer; research source coverage; negative evidence interpretation; `先补证据`
- must_discover: original task domain, PDE solver evidence, architecture-to-physics interface, spectral or high-frequency signal support, code, benchmark, relation to PINN, DeepONet, FNO, Fourier PINN.
- must_not_misjudge: do not treat name similarity or image-network structure as evidence of PDE suitability.
- pass_signal: Judgment separates direct evidence, borrowable structure, and unsupported combination claims.

### C3 - Medical Transformer risk prediction reuse

- case_type: Stress Test
- search_level: L3 deep review
- tests: Research/Method Search; Vertical Business Process; data-fit judgment; evidence sufficiency
- must_discover: task, data structure, time window, label definition, irregular time-series handling, structured and unstructured inputs, code, metrics, sample-size fit, reporting expectations.
- must_not_misjudge: do not transfer large EHR Transformer papers directly to a 160-case ECMO task.
- pass_signal: Judgment separates writing-structure reuse, model-module reuse, and non-reusable parts.

### D1 - PDF-VLLM ICU nursing-record extraction improvement

- case_type: Stress Test
- search_level: L3 deep review
- tests: Vertical Business Process; local/private evidence handling; source selection completeness; field-level claim decomposition
- must_discover: medical table OCR, VLM table extraction, layout-aware OCR, human review, rule-based QC, privacy limits, local deployment needs, gap from existing PDF-VLLM workflow.
- must_not_misjudge: do not treat generic OCR as a complete ICU nursing-record semantic extraction solution.
- pass_signal: Evidence Pack separates layout extraction, semantic grouping, field validation, review workflow, and privacy deployment.

### D2 - ECMO unstructured extraction and prediction

- case_type: Stress Test
- search_level: L3 deep review
- tests: claim decomposition; research plus vertical source selection; privacy constraints; Judgment actionability
- must_discover: clinical information extraction, temporal event extraction, medication dosage extraction, ICU/EHR risk prediction, medical LLM/SFT, small-sample modeling, annotation schema, privacy and ethics.
- must_not_misjudge: do not collapse extraction and prediction into one LLM classification task.
- pass_signal: Report builds an evidence chain from extraction to modeling instead of directly recommending LLM prediction.

### D3 - Fluent blood-flow simulation automation

- case_type: Real Exploration
- search_level: L2 or L3
- tests: vertical technical workflow; official docs plus scripts; implementation feasibility; operational risk recording
- must_discover: Fluent journal, TUI, Python automation, boundary-condition import, mesh checks, batch solving, residual monitoring, parameter sweeps, adjacent medical-flow simulation examples.
- must_not_misjudge: do not treat GUI tutorials as automation workflows.
- pass_signal: Report separates scriptable steps, human-confirmation steps, and high-risk failure points.

### E1 - Existing skill / agent workflow framework comparison

- case_type: Meta-framework
- search_level: L3 deep review
- tests: framework prior-work search; method comparison; gap analysis; future roadmap design
- must_discover: skill file structure, triggers, input and output contracts, allowed and prohibited behavior, verification checklist, examples, tests, routing, failure handling, safety boundary, maintenance model.
- must_not_misjudge: do not copy execution-skill complexity into Prework Intelligence without a proven need.
- pass_signal: Report compares others have, we have, we lack, worth adding, and timing.

### E2 - Existing-work-search method prior work

- case_type: Meta-framework
- search_level: L3 deep review
- tests: meta-method search; source-class expansion; scoring-rule revision; Judgment glossary revision
- must_discover: prior art search, systematic or scoping review, technology scouting, build-vs-buy frameworks, evidence grading, competitive intelligence, absence-of-evidence handling, decision matrix methods.
- must_not_misjudge: do not treat one source-class method as a full replacement for Prework Intelligence.
- pass_signal: Judgment identifies which mature frameworks should influence V1.1 or V2 and which should remain out of scope.

## Current Next Step

Use A1 as the first calibration review. Do not start E1 or B1 until A1 evaluation and V1.1 regression are reviewed.
