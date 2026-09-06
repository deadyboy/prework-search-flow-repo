# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: E2
- Evidence Pack path: `docs/prework-intelligence/cases/existing-work-search-method-prior-work/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`场景定制`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `E004`, `E005`, `N001`, `N002`.

## Conclusion Rationale

- Primary conclusion: `场景定制`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `E004`, `E005`, `N001`, `N002`
- Why these evidence records support the conclusion: Mature methods cover important parts of Prework, but no single searched framework covers the whole cross-source existing-work and action-judgment problem with strict Search/Judgment separation.
- Important evidence gaps: paywalled analyst detail, non-English methods, and expert interviews remain unsearched.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Prior-art search 可增强 Search Module。 | cross_surface | not_applicable | current_official | `接入改造` | E001 | Strong source-coverage and query-expansion methods. | Patent methods are narrow. |
| C002 | Systematic/scoping review 可增强检索可审计性。 | cross_surface | not_applicable | current_official | `接入改造` | E002 | Strong protocol and reporting value. | May be heavy for L1/L2. |
| C003 | Snowballing / grey literature 可覆盖软件和实践来源。 | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E003 | Useful for software and open-source cases. | Source quality varies. |
| C004 | Technology scouting / CI / build-vs-buy 可作为 Judgment 输入。 | cross_surface | not_applicable | current_official | `场景定制` | E004; E005; N002 | Useful judgment inputs, but must stay out of Search output. | Need future lightweight judgment criteria. |
| C005 | 未发现统一跨源公共标准。 | cross_surface | not_applicable | recent_but_unverified | `自研小样` | E001; E002; E003; E004; E005; N001 | Prework needs a tailored synthesis. | Negative evidence is scoped. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | USPTO / WIPO / EPO prior-art and patent landscape methods | 9 | 7 | S | confirmed | Search coverage method. |
| E002 | PRISMA / Cochrane / JBI systematic and scoping review methods | 10 | 8 | S | confirmed | Search audit method. |
| E003 | Snowballing and multivocal literature review | 9 | 8 | S | confirmed | Software and grey-literature method. |
| E004 | Technology scouting and strategic intelligence | 8 | 6 | S | confirmed | Discovery/judgment-adjacent method. |
| E005 | Build-vs-buy, intelligence cycle, and competitive analysis | 7 | 6 | A | confirmed | Judgment input method. |

## Why Existing Work Does Or Does Not Substitute

Existing methods strongly inform Prework but do not fully substitute for it. Prework needs a tailored workflow that spans patents, papers, products, code, communities, and vertical workflows while keeping evidence search separate from action judgment.

## What To Reuse

- Prior-art query expansion and non-patent literature discipline from `E001`.
- Protocol, eligibility, and audit-trail concepts from `E002`.
- Snowballing and grey-literature quality checks from `E003`.
- Strategic and build-vs-buy inputs from `E004` and `E005`, only inside Judgment.

## What Not To Do

- Do not replace Prework with a patent-only prior-art method. Cite `E001`.
- Do not force every case into full systematic-review overhead. Cite `E002`.
- Do not let build-vs-buy frameworks produce Search Module conclusions. Cite `E005` and `N002`.
- Do not claim a unified standard does not exist absolutely. Cite `N001`.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Unified cross-source standard | Patent, review, software, scouting, decision frameworks | Supports tailored method. | Does not prove no standard exists. |
| N002 | Search/Judgment separation in established frameworks | Scouting and judgment references | Supports keeping Prework separation explicit. | Adapted frameworks could separate them. |

## Next Action

Absorb lightweight search-audit and source-quality practices into future V1.x revisions only when cases show they reduce errors.

## Supplement-Evidence Request

Not used for the primary conclusion.

## Validity Checklist

- The report reads only the Evidence Pack.
- The primary conclusion is one of the allowed values.
- The primary conclusion cites `entity_id` or `negative_evidence_id` values.
- Every claim-level local conclusion cites `entity_id` or `negative_evidence_id` values.
- No new sources, URLs, or entities are introduced.
- Negative evidence is interpreted only as no strong evidence found within covered sources.
- Evidence gaps are not converted into confident claims.
