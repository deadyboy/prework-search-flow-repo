# Judgment Report

This report is written by the Judgment Module after reading one Evidence Pack. It does not introduce new evidence.

## Evidence Pack Used

- Case ID: B4
- Evidence Pack path: `docs/prework-intelligence/cases/free-large-file-translation-tools/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## Primary Conclusion

`接入改造`

## Required Evidence Citations

Primary cited records: `E001`, `E002`, `E003`, `E004`, `N001`.

## Conclusion Rationale

- Primary conclusion: `接入改造`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `E004`, `N001`
- Why these evidence records support the conclusion: Existing tools can be combined into a pipeline, but no single searched free hosted tool satisfies unlimited large-file translation with layout preservation and no review.
- Important evidence gaps: exact file constraints, privacy level, translation quality, and layout test.

## Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | local_conclusion | cited_records | rationale | remaining_gap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Local/free translation components exist. | local_state | not_applicable | current_official | `接入改造` | E001; E002 | Use CAT/MT components together. | Quality testing needed. |
| C002 | Hosted tools have limits. | web_product | not_applicable | current_official | `先补证据` | E003 | Limits must be checked against actual files. | Exact file size unknown. |
| C003 | OCR/parsing is needed for scanned/complex PDFs. | local_state | not_applicable | current_official | `接入改造` | E004 | Preprocess before translation. | Layout test needed. |
| C004 | One free hosted unlimited solution exists. | web_product | not_applicable | recent_but_unverified | `先补证据` | N001 | No strong evidence in searched scope. | Broader product scan possible. |

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | OmegaT CAT / translation memory workflow | 8 | 8 | S | confirmed | Workflow component. |
| E002 | Argos Translate / LibreTranslate | 8 | 8 | A | confirmed | Local/free MT component. |
| E003 | Google Translate / DeepL hosted document limits | 10 | 6 | S | confirmed | Limit evidence. |
| E004 | OCRmyPDF / Tesseract / Docling | 8 | 8 | A | confirmed | Preprocessing component. |

## Why Existing Work Does Or Does Not Substitute

Existing work substitutes for parts of the workflow. A practical answer is a pipeline, not a single free unlimited hosted tool.

## What To Reuse

- OmegaT-style CAT/TM workflow from `E001`.
- Local/free MT components from `E002`.
- Hosted-limit checks from `E003`.
- OCR/parsing stack from `E004`.

## What Not To Do

- Do not assume "free" means unlimited large-file translation. Cite `E003` and `N001`.
- Do not translate scanned PDFs before OCR. Cite `E004`.

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Complete free unlimited hosted solution | Hosted docs and open-source/local tools | Supports pipeline approach. | Does not prove none exists. |

## Next Action

Define file size, format, privacy, and language pair, then test a local pipeline on one representative non-sensitive file.
