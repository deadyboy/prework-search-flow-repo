# Prework Intelligence V1 Method

This document defines the Phase 1 workflow and module boundary for Prework Intelligence V1.

## Purpose

Prework Intelligence helps decide whether a rough idea, work problem, or tool need should be pursued from scratch, adapted from existing work, or paused for more evidence.

V1 is a semi-structured documentation workflow. It is not an autonomous research agent. The first phase establishes method documents and templates only.

## Core Flow

The workflow has one strict handoff:

```text
Idea Card
  -> Search Module
  -> Evidence Pack
  -> Judgment Module
  -> Judgment Report
```

The Evidence Pack is the only interface between Search and Judgment. Search gathers and normalizes evidence. Judgment reads that evidence and makes, withholds, or requests support for a conclusion.

An Evidence Pack can be a single file or a declared Evidence Pack bundle. A bundle may include a base Evidence Pack plus dated addenda when a case is updated without rewriting the original pack. The bundle is still one logical handoff input, and every cited entity or negative evidence record must appear in one of the declared bundle files.

V1.1 adds a lightweight claim layer above entity records:

```text
Idea Card
  -> Claim Decomposition
  -> Search Module
  -> Entity Records + Capability Claim Matrix
  -> Judgment Module
  -> Primary Conclusion + Claim Matrix
```

Entity records still group evidence by object. Capability claims describe what is true for a specific subproblem, surface, lifecycle stage, and freshness state.

## Relation To Existing Work Search Design

`docs/superpowers/specs/2026-06-10-existing-work-search-design.md` is the Phase 0 search-only design.

It answers only how to search for whether comparable work already exists.

Prework Intelligence V1 is a search + judgment workflow. It uses the Phase 0 file as a foundation for Search Module principles, but not as the final Judgment specification.

Do not delete or overwrite the Phase 0 file. Prework Intelligence V1 extends it by adding the Evidence Pack handoff and Judgment Module boundary.

## Module Boundary

Search Module responsibilities:

- rewrite a rough idea into searchable dimensions;
- decompose broad ideas into stable `claim_id` records before search;
- produce a search plan;
- collect and normalize evidence in an Evidence Pack;
- assign entity-level `entity_id`, `relevance_score`, `reuse_score`, `method_similarity`, `method_note`, `source_grade`, and `evidence_status`;
- record claim-level `surface_scope`, `lifecycle_scope`, `freshness_status`, supporting records, `claim_evidence_status`, and gaps in the Capability Claim Matrix;
- record information gaps and negative search scope.

Search Module must not:

- recommend `放弃不做`, `直接采用`, `接入改造`, `场景定制`, `补齐缺口`, `自研小样`, or `先补证据`;
- produce the final Judgment Report;
- hide missing evidence behind confident language.

Judgment Module responsibilities:

- read one Evidence Pack;
- cite Evidence Pack `entity_id` or `negative_evidence_id` values for every conclusion;
- use the Capability Claim Matrix to separate local claim judgments from the single primary conclusion;
- choose one allowed conclusion when the evidence supports it;
- output `先补证据` when evidence is insufficient.

Judgment Module must not:

- call search tools;
- browse the web;
- inspect external sources;
- add new evidence;
- cite URLs that are not already present in the Evidence Pack.

## Phase Boundaries

Phase 1 creates method documents and templates under `docs/prework-intelligence`.

Phase 1 does not create:

- example cases;
- strategy-card files;
- crawlers;
- agents;
- rerankers;
- RAG stores;
- platform adapters;
- automation scripts.

Later phases may add cases and strategy cards only after the Phase 1 templates are reviewed.

## V1 Operating Rules

- Use a file-based workflow first. Do not automate until repeated cases show stable fields.
- Keep search and judgment separate even when the same person performs both roles.
- Decompose broad cases into claim-level records before judging product capability, surface support, or lifecycle behavior.
- Treat scores as structured initial judgments, not mathematical truth.
- Prefer source-specific evidence over generic summaries.
- Record what was not searched so the report cannot imply false completeness.
- Stop judgment when required evidence is missing; issue a supplement-evidence request instead.

## Conclusion Glossary

- `放弃不做`: Existing evidence shows the work is not worth pursuing now.
- `直接采用`: A sufficiently fitting existing solution can be used as-is.
- `接入改造`: Existing work can cover the base need if integrated, wrapped, or lightly adapted.
- `场景定制`: A general solution exists, but the user's domain needs a focused variant.
- `补齐缺口`: Prior work covers the foundation, and the main value is finishing missing workflow, UX, or operational pieces.
- `自研小样`: No suitable reusable base is evident, so a small in-house prototype is justified.
- `先补证据`: The Evidence Pack is not sufficient for a responsible judgment.

## Valid Work Product

Phase 1 is complete when the method files and templates exist, encode the strict module boundary, and can be used later to run a case without adding new design decisions.
