# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: C2
- Evidence Pack path: `docs/prework-intelligence/cases/xnet-fftxnet-pde-ilw/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`先补证据`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `N001`, `N002`.

## Conclusion Rationale

- Primary conclusion: `先补证据`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `N001`, `N002`
- Why these evidence records support the conclusion: There is borrowable XNet/PDE evidence, but FFT-XNet naming and XNet+ILW direct evidence are not established.
- Important evidence gaps: exact method name, ILW meaning, direct code search, and benchmark fit.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | XNet has PDE/function approximation evidence. | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E001; E002 | Borrowable method neighborhood. | Needs benchmark review. |
| C002 | FFT-XNet is established as named PDE method. | cross_surface | not_applicable | unknown_date | `先补证据` | N001 | No strong named evidence in scope. | Confirm naming. |
| C003 | XNet + ILW direct combination exists. | cross_surface | not_applicable | unknown_date | `先补证据` | E001; E002; N002 | Direct combination missing. | Targeted search needed. |
| C004 | XNet may be borrowable for prototype. | cross_surface | not_applicable | recent_but_unverified | `自研小样` | E001; E002 | Small prototype could test fit after evidence gap is closed. | Not enough for full method claim. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | XNet / Cauchy activation for PDE solving | 8 | 6 | A | confirmed | Borrowable method evidence. |
| E002 | XNet outperforming KAN preprint | 7 | 5 | B | single-source | Additional method-transfer evidence. |

## What To Reuse

- Use XNet/Cauchy activation evidence as a candidate neural approximation baseline.

## What Not To Do

- Do not claim FFT-XNet is established without resolving `N001`.
- Do not claim XNet+ILW prior work without resolving `N002`.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | FFT-XNet named method | Academic web/arXiv | Supports supplement request. | Could be naming issue. |
| N002 | XNet + ILW direct work | Academic web/arXiv | Supports supplement request. | Does not prove absence. |

## Next Action

Clarify whether `FFT-XNet` is a real target method name, then search code and benchmarks before designing a prototype.
