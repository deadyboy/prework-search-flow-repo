# Evidence Pack

This is the Search Module handoff artifact for Case B4. It records evidence, not final decisions.

## Case Metadata

- Case ID: B4
- Idea title: Free large-file translation tool combination
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent product/tooling subagent brief

## Coverage Summary

- Searched source classes: official product/help docs; open-source tool docs; OCR/PDF parsing docs.
- Unsearched source classes: hands-on file tests; privacy/legal review; paid enterprise procurement.
- Languages searched: English.
- Coverage note: Coverage is sufficient to separate online free, freemium, local open-source, and OCR/parsing components.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official docs | OmegaT / Argos / LibreTranslate | free local document translation CAT MT | several | E001; E002 | Local/free candidates. |
| Q002 | official docs | Google / DeepL | document translation file size character limits | several | E003 | Hosted limits. |
| Q003 | open-source docs | OCRmyPDF / Tesseract / Docling | OCR PDF parsing table extraction document translation | several | E004 | Preprocessing needs. |
| Q004 | negative search | mixed docs | free unlimited large file translation preserve layout | 0 strong | N001 | No complete free unlimited hosted solution found. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Local/free translation components exist. | local_state | not_applicable | current_official | E001; E002 | none | confirmed | Quality and language-pair fit need testing. |
| C002 | Hosted document translation usually has file/character/page limits. | web_product | not_applicable | current_official | E003 | none | confirmed | Exact free vs paid tiers may change. |
| C003 | Large PDF/scanned documents require OCR/parsing before translation. | local_state | not_applicable | current_official | E004 | none | confirmed | Layout/format preservation untested. |
| C004 | One free hosted tool covers unlimited large files with complex layout and no review. | web_product | not_applicable | recent_but_unverified | none | N001 | unverified | Negative evidence limited to searched sources. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: OmegaT CAT / translation memory workflow
- entity_type: open-source translation workflow tool
- core_function: Computer-assisted translation and translation memory, not automatic machine translation by itself.
- relevance_score: 8
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 1
- method_note: Useful workflow infrastructure, but not a one-click large-file MT solution.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: OmegaT
- url_or_local_reference: https://omegat.org/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official site describes OmegaT as a CAT / translation-memory tool.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| OmegaT resources / Okapi | https://omegat.org/resources | 2026-07-09 | S | C001 |

#### Gaps

- Machine translation engine quality not determined.

#### Risks

- User may expect automatic translation, but CAT workflow requires review.

### Entity E002

- entity_id: E002
- entity_name: Argos Translate / LibreTranslate
- entity_type: open-source/local or hosted machine translation tools
- core_function: Provides machine translation components that can be run locally or via service.
- relevance_score: 8
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 2
- method_note: Directly supports local/free MT component, but document workflow still needs parsing and QA.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Argos Translate documentation
- url_or_local_reference: https://argos-translate.readthedocs.io/
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Documentation describes open-source machine translation usage.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| LibreTranslate | https://libretranslate.com/ | 2026-07-09 | S | C001 |

#### Gaps

- Translation quality for English/Japanese and large documents not tested.

#### Risks

- Local compute and language-model quality vary.

### Entity E003

- entity_id: E003
- entity_name: Google Translate / DeepL hosted document limits
- entity_type: hosted translation limits evidence
- core_function: Documents file-size, page, and character limits for hosted translation.
- relevance_score: 10
- reuse_score: 6
- score_scope: surface:web_product
- method_similarity: 1
- method_note: Strong evidence for constraint boundaries, not a local workflow.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Google Translate documents
- url_or_local_reference: https://support.google.com/translate/answer/2534559?co=GENIE.Platform%3DDesktop&hl=en
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Google support page documents document translation limits such as file size and PDF page limits.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| DeepL usage limits | https://developers.deepl.com/docs/resources/usage-limits | 2026-07-09 | S | C002 |

#### Gaps

- Web UI and API free tiers differ.

#### Risks

- Limits and pricing can change.

### Entity E004

- entity_id: E004
- entity_name: OCRmyPDF / Tesseract / Docling
- entity_type: OCR and document parsing stack
- core_function: Converts scanned or complex documents into machine-readable text/structure before translation.
- relevance_score: 8
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 1
- method_note: Necessary preprocessing for scanned/structured large files, but not translation itself.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: OCRmyPDF documentation
- url_or_local_reference: https://ocrmypdf.readthedocs.io/
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: OCRmyPDF documentation describes adding OCR text layers to PDFs.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Tesseract documentation | https://tesseract-ocr.github.io/ | 2026-07-09 | A | C003 |
| Docling | https://docling-project.github.io/docling/ | 2026-07-09 | A | C003 |

#### Gaps

- OCR accuracy and layout preservation not tested.

#### Risks

- OCR errors propagate into translation.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: A free hosted solution supports unlimited large files, complex layout preservation, no OCR/preprocessing, and no manual review.
- searched_source_classes: Google/DeepL/Microsoft-style hosted docs; local open-source tools; OCR/parser docs.
- searched_queries: `free unlimited document translation large PDF preserve layout`; `free large file translation no limit OCR`.
- result: No strong evidence found for a complete free unlimited hosted solution in searched scope.
- interpretation_limit: This does not prove no such tool exists.

## Information Gaps

- User's exact file size, format, scanned status, and privacy constraints.
- Hands-on translation quality and layout test.

## Search Module Notes

- Treat large-file translation as a pipeline, not a single product name.
