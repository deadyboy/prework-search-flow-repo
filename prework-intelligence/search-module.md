# Search Module

This document defines what the Search Module may produce and what it must leave to Judgment.

## Role

The Search Module turns a rough idea into a structured Evidence Pack. It is responsible for recall, normalization, source notes, and evidence gaps.

The handoff output to the Judgment Module is only `evidence-pack.md`.

## Inputs

The Search Module may use:

- an Idea Card;
- a Search Plan;
- user-provided constraints;
- source-selection rules from the method.

The Search Plan is a planning artifact for the search worker. It is not a judgment artifact and must not be used by the Judgment Module as evidence.

## Outputs

The Search Module must produce an Evidence Pack with:

- case metadata;
- coverage summary;
- query log;
- entity-level evidence records;
- capability claim matrix records;
- information gaps;
- negative search scope;
- searcher's notes about uncertainty.

Every entity record must include:

- `entity_id`, using stable local IDs such as `E001`, `E002`, `E003`;
- `entity_name`;
- `entity_type`;
- `core_function`;
- `relevance_score`;
- `reuse_score`;
- `method_similarity`;
- `method_note`;
- `source_grade`;
- `evidence_status`;
- `main_source`;
- `support_sources`;
- `key_facts`;
- `gaps`;
- `risks`.

Every capability claim record must include:

- `claim_id`, using stable local IDs such as `C001`, `C002`, `C003`;
- `claim`;
- `surface_scope`;
- `lifecycle_scope`;
- `freshness_status`;
- `supporting_entities`;
- `supporting_negative_evidence`;
- `claim_evidence_status`, using the same values as `evidence_status`;
- `gaps`.

## Prohibited Outputs

The Search Module must not output:

- final go/no-go recommendations;
- build-vs-buy conclusions;
- implementation plans;
- product strategy;
- untracked evidence outside the Evidence Pack.

If the searcher has an opinion about likely direction, it belongs outside the handoff artifact. The Evidence Pack should remain usable by a separate Judgment Module.

## Entity Aggregation

The Search Module groups results by entity, not by URL.

An entity may be:

- an open-source project;
- a commercial product;
- an academic method;
- a patent or standard;
- a forum-described workflow;
- an official feature;
- an internal or local tool if the user provides it as allowed evidence.

Multiple URLs about the same entity should become one entity record with a main source and support sources.

## Scoring Responsibilities

The Search Module assigns initial scores and labels:

- `relevance_score`: similarity to the original idea;
- `reuse_score`: practical reusability for the user's work;
- `method_similarity`: similarity of technical route, implementation style, or core method;
- `method_note`: short explanation of the method comparison;
- `source_grade`: source authority for the specific claim;
- `evidence_status`: confirmation state of the entity's key claims.

The module must not collapse these fields into a single confidence score.

When a `reuse_score` applies only to a specific claim or surface, record `score_scope` in the relevant entity notes, such as `claim:C001` or `surface:app_server`. If no scope is recorded, Judgment should treat the score as entity-level only.

## Current Product Capability Gate

When the case asks whether a current product capability exists, the Search Module must check current official sources before treating older issues or community posts as evidence of present gaps.

For fast-changing products, search in this order:

- official changelog, release notes, or current docs;
- current UI or user-observed evidence when allowed and safe;
- official issues, community posts, or older discussions;
- third-party summaries or adjacent products.

Older issues can record historical pain or missing features at the time they were filed. They must not be treated as current missing-feature evidence unless the Evidence Pack records a freshness check showing the gap still applies.

## Insufficient Evidence

If evidence is weak, the Search Module records:

- missing source types;
- query families not yet tried;
- claims with only single-source support;
- entities with conflicting evidence;
- likely places where missed evidence may exist.

The Search Module does not decide whether the idea should proceed. It only makes the Evidence Pack honest about its limits.

## Completion Criteria

A Search Module run is complete when:

- planned source types are marked searched or explicitly unsearched;
- query logs record what was searched and where;
- useful results are grouped into entities;
- each entity has required scoring fields, including `method_similarity` and `method_note`;
- capability claims have `claim_id`, `surface_scope`, `lifecycle_scope`, `freshness_status`, supporting records, and gaps;
- information gaps and negative search scope are explicit;
- no final judgment is included.
