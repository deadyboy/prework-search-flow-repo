# Judgment Module

This document defines how the Judgment Module reads Evidence Packs and when it must request more evidence.

## Role

The Judgment Module reads an Evidence Pack and produces a Judgment Report. It decides only from evidence already present in the pack.

The module must not search, browse, inspect external sources, call APIs, read new URLs, or add evidence. If the Evidence Pack is insufficient, the only valid output is `先补证据`.

## Input Contract

The only input is one Evidence Pack or one declared Evidence Pack bundle.

An Evidence Pack bundle may contain a base `evidence-pack.md` plus dated addenda for the same case. The Judgment Report must list every file in the bundle under `Evidence Pack Used`. The Judgment Module must treat the bundle as one logical input and must not read sources outside that declared bundle.

The Judgment Module may use:

- entity records and their `entity_id` values;
- capability claim matrix records and their `claim_id` values;
- negative evidence records and their `negative_evidence_id` values;
- source notes already captured in the Evidence Pack;
- query logs already captured in the Evidence Pack;
- gaps and negative search scope already captured in the Evidence Pack.

When a bundle is used, cited `entity_id` and `negative_evidence_id` values may come from any declared bundle file, but the report must not cite records that are outside the bundle.

The Judgment Module must ignore:

- external URLs not recorded in the Evidence Pack;
- the judge's private knowledge;
- search plans that are not reflected in the Evidence Pack;
- claims that lack an entity record or negative evidence record.

## Allowed Conclusions

Each Judgment Report must choose exactly one primary conclusion:

- `放弃不做`
- `直接采用`
- `接入改造`
- `场景定制`
- `补齐缺口`
- `自研小样`
- `先补证据`

Secondary notes may explain tradeoffs, but they must not introduce a second primary conclusion.

For V1.1 Evidence Packs, the report should also include claim-level local conclusions. These local conclusions do not replace the single primary conclusion. They explain how different subproblems, surfaces, or lifecycle stages should be handled.

## Conclusion Glossary

- `放弃不做`: Existing evidence shows the work is not worth pursuing now.
- `直接采用`: A sufficiently fitting existing solution can be used as-is.
- `接入改造`: Existing work can cover the base need if integrated, wrapped, or lightly adapted.
- `场景定制`: A general solution exists, but the user's domain needs a focused variant.
- `补齐缺口`: Prior work covers the foundation, and the main value is finishing missing workflow, UX, or operational pieces.
- `自研小样`: No suitable reusable base is evident, so a small in-house prototype is justified.
- `先补证据`: The Evidence Pack is not sufficient for a responsible judgment.

## Evidence Citation Rule

Every conclusion must cite one or more Evidence Pack `entity_id` or `negative_evidence_id` values.

Valid conclusion statements must include:

- primary conclusion;
- claim-level conclusion when using a Capability Claim Matrix;
- cited `entity_id` or `negative_evidence_id` values;
- why those evidence records support the conclusion;
- what evidence gaps remain.

The report is invalid if a conclusion does not cite an `entity_id` or `negative_evidence_id`.

For `先补证据`, cite the `entity_id` or `negative_evidence_id` values that are too weak, conflicting, or incomplete. If no relevant evidence record exists, cite `none` and explain which missing evidence record type would be needed, such as entity record, source record, negative evidence record, or method comparison note.

Claim-level `先补证据` may cite `none` only when the Evidence Pack has no relevant entity or negative evidence record for that claim. The report must then name the missing claim, surface, lifecycle stage, and evidence record type.

## Negative Evidence Interpretation

Negative evidence must not be interpreted as absolute non-existence.

The Judgment Module may only state that strong evidence was not found within the source classes, queries, and limits recorded by the Evidence Pack.

Negative evidence cannot support claims like "no one has done this" or "this does not exist." It can only support claims like "no strong evidence was found within the covered search scope."

If negative evidence comes from narrow coverage, the Judgment Module should prefer `先补证据` over a confident conclusion.

## Evidence Sufficiency

Use `先补证据` when:

- the strongest entity has low relevance and low reuse;
- source coverage is too narrow for the decision;
- key entities have `evidence_status: conflicting`;
- a required source class is unsearched;
- the Evidence Pack lacks `entity_id` or `negative_evidence_id` citations for the claims being considered;
- a capability claim lacks `surface_scope`, `lifecycle_scope`, `freshness_status`, or supporting records needed for the local conclusion;
- a needed key fact lacks a recorded supporting source or clear evidence status.

The request must specify:

- missing source type or source class;
- missing claim or comparison;
- missing surface, lifecycle, or freshness record when relevant;
- affected `entity_id` or `negative_evidence_id` values, or `none`;
- missing evidence record type;
- the decision that cannot be made until evidence is added.

## Prohibited Behavior

The Judgment Module must not:

- perform new search;
- browse cited URLs;
- inspect local files beyond the declared Evidence Pack or Evidence Pack bundle;
- change scores in the Evidence Pack;
- infer current product capability from stale issue records without a recorded freshness check;
- add new entities;
- add new negative evidence records;
- cite evidence that is not in the Evidence Pack;
- treat negative evidence as proof that no solution exists;
- convert missing evidence into a confident conclusion.

## Completion Criteria

A Judgment Report is complete when:

- it selects one allowed primary conclusion;
- every conclusion cites `entity_id` or `negative_evidence_id` values, or a justified `none` for supplement requests;
- claim-level local conclusions cite supporting records and do not replace the primary conclusion;
- it distinguishes evidence-backed claims from gaps;
- it recommends a next action that follows from the cited evidence records;
- it does not contain new evidence.
