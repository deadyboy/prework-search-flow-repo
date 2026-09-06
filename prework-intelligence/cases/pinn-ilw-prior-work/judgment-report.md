# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: C1
- Evidence Pack path: `docs/prework-intelligence/cases/pinn-ilw-prior-work/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`先补证据`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `N001`, `N002`.

## Conclusion Rationale

- Primary conclusion: `先补证据`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `N001`, `N002`
- Why these evidence records support the conclusion: The pack contains adjacent PINN and ILW-domain evidence, but it also records unresolved ambiguity about whether `ILW` means inverse Lax-Wendroff or intermediate long wave.
- Important evidence gaps: explicit term disambiguation, targeted inverse-Lax-Wendroff search, code/baseline search, and citation chasing.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | PINN has adjacent evidence on nonlinear dispersive PDEs. | cross_surface | not_applicable | recent_but_unverified | `接入改造` | E001 | Useful baseline neighborhood. | Not direct ILW boundary evidence. |
| C002 | Intermediate-long-wave is an active PDE/domain. | cross_surface | not_applicable | recent_but_unverified | `先补证据` | E002 | Relevant only if this is the intended ILW. | User intent ambiguous. |
| C003 | Direct PINN + inverse Lax-Wendroff boundary prior work is established. | cross_surface | not_applicable | unknown_date | `先补证据` | N001 | No strong evidence in brief; search insufficient. | Needs targeted rerun. |
| C004 | Direct PINN + intermediate long wave prior work is established. | cross_surface | not_applicable | unknown_date | `先补证据` | E001; E002; N002 | Adjacent only. | Needs deeper academic search. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | PINN for nonlinear dispersive PDEs | 7 | 5 | A | confirmed | Adjacent method evidence. |
| E002 | Modified intermediate long wave equation | 6 | 3 | A | confirmed | Possible domain evidence. |

## Why Existing Work Does Or Does Not Substitute

The existing evidence does not responsibly substitute for a direct prior-work conclusion because the key term is ambiguous and direct evidence is not established.

## What To Reuse

- Use `E001` as adjacent PINN baseline evidence.
- Use `E002` only if the intended `ILW` is intermediate long wave.

## What Not To Do

- Do not claim direct novelty from `N001` or `N002`.
- Do not mix inverse Lax-Wendroff with intermediate long wave evidence.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | PINN + inverse Lax-Wendroff | Academic brief search | Supports supplement request. | Search should be rerun. |
| N002 | PINN + intermediate long wave | Academic brief search | Supports supplement request. | Does not prove absence. |

## Next Action

Clarify `ILW` meaning, then rerun targeted academic and code search before judging novelty or reuse.

## Supplement-Evidence Request

- Affected entity_id values or `none`: `E001`, `E002`
- Affected negative_evidence_id values or `none`: `N001`, `N002`
- Missing source class: targeted academic index and code repository search
- Missing claim or comparison: inverse Lax-Wendroff boundary treatment versus intermediate long wave equation
- Missing evidence record type: direct method entity record and baseline/code record
- Why judgment cannot proceed: the Evidence Pack does not resolve the central term ambiguity.
- What the Search Module should add to a revised Evidence Pack: disambiguated query families, direct prior-work map, and baseline/code entities.
