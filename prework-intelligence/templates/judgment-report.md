# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It must not introduce new evidence.

## Evidence Pack Used

- Case ID:
- Evidence Pack path:
- Evidence Pack addendum paths, or `none`:
- Evidence Pack date:

If addenda are listed, the base pack plus addenda form one Evidence Pack bundle for this Judgment Report. Do not cite records outside that declared bundle.

## Primary Conclusion

Choose exactly one:

- `放弃不做`
- `直接采用`
- `接入改造`
- `场景定制`
- `补齐缺口`
- `自研小样`
- `先补证据`

## Conclusion Glossary

- `放弃不做`: Existing evidence shows the work is not worth pursuing now.
- `直接采用`: A sufficiently fitting existing solution can be used as-is.
- `接入改造`: Existing work can cover the base need if integrated, wrapped, or lightly adapted.
- `场景定制`: A general solution exists, but the user's domain needs a focused variant.
- `补齐缺口`: Prior work covers the foundation, and the main value is finishing missing workflow, UX, or operational pieces.
- `自研小样`: No suitable reusable base is evident, so a small in-house prototype is justified.
- `先补证据`: The Evidence Pack is not sufficient for a responsible judgment.

## Required Evidence Citations

Every conclusion in this report must cite Evidence Pack `entity_id` values such as `E001` or `E002`, or `negative_evidence_id` values such as `N001`.

The report is invalid if the primary conclusion does not cite at least one `entity_id` or `negative_evidence_id`, except `先补证据` may cite `none` when the Evidence Pack contains no relevant evidence record.

When `先补证据` cites `none`, the report must explain which evidence record is missing: entity record, source record, negative evidence record, or method comparison note.

Claim-level local conclusions must also cite `entity_id` or `negative_evidence_id` values. A claim-level `先补证据` may cite `none` only when the missing claim has no relevant evidence record, and must name the missing surface, lifecycle, freshness, or source record.

Negative evidence means strong evidence was not found within the recorded source coverage. It must not be interpreted as proof that no solution, product, method, or prior work exists.

## Judgment Rule Table

These are rough judgment rules, not a full decision formula.

- Coverage is insufficient or a key source class is unsearched: `先补证据`
- High relevance and high reuse: `直接采用` / `接入改造`
- High relevance and low reuse: `补齐缺口` / `场景定制`
- One entity is insufficient, but multiple entities together cover the need: `接入改造` / `补齐缺口`
- No strong substitute and negative evidence coverage is sufficient: `自研小样`
- Strong substitute exists and the remaining difference is not important: `放弃不做`

## Conclusion Rationale

- Primary conclusion:
- Cited entity_id or negative_evidence_id values:
- Why these evidence records support the conclusion:
- Important evidence gaps:

## Claim Matrix

Use this table when the Evidence Pack contains a Capability Claim Matrix. Local conclusions do not replace the Primary Conclusion.

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 |  |  |  |  |  |  |  |  |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 |  |  |  |  |  |  |

## Why Existing Work Does Or Does Not Substitute

Explain the substitute strength of cited entities only. Do not reference uncited sources.

## What To Reuse

List reusable code, workflow, data model, interface, method, product pattern, or operational process from cited entities.

## What Not To Do

List work that the evidence suggests avoiding. Cite `entity_id` or `negative_evidence_id` values for each claim.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 |  |  |  |  |

## Next Action

State one next action that follows from the primary conclusion.

## Supplement-Evidence Request

Use this section only when the primary conclusion is `先补证据`.

- Affected entity_id values or `none`:
- Affected negative_evidence_id values or `none`:
- Missing source class:
- Missing claim or comparison:
- Missing evidence record type:
- Why judgment cannot proceed:
- What the Search Module should add to a revised Evidence Pack:

## Validity Checklist

- The report reads only the Evidence Pack.
- The primary conclusion is one of the allowed values.
- The primary conclusion cites `entity_id` or `negative_evidence_id` values, or `none` for a justified supplement-evidence request.
- Every claim-level local conclusion cites `entity_id` or `negative_evidence_id` values, or justified `none` for `先补证据`.
- No new sources, URLs, or entities are introduced.
- Negative evidence is interpreted only as no strong evidence found within covered sources.
- Evidence gaps are not converted into confident claims.
