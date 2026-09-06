# Evidence Pack

This is the Search Module handoff artifact for Case D1. It records evidence, not final decisions.

## Case Metadata

- Case ID: D1
- Idea title: PDF-VLLM ICU nursing-record extraction improvement
- Search level: L3 deep review
- Search date: 2026-07-09
- Searcher: Codex with independent vertical-workflow subagent brief

## Coverage Summary

- Searched source classes: public clinical datasets; nursing-note NLP review; LLM clinical extraction papers; vLLM docs; PDF/OCR/layout tool docs.
- Unsearched source classes: private patient records; local hospital templates; hands-on extraction benchmark.
- Languages searched: English.
- Coverage note: Sufficient to map components and gaps, not to validate clinical extraction performance.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | dataset | PhysioNet | MIMIC ICU notes nursing notes | several | E001 | Clinical note evidence. |
| Q002 | academic | nursing note NLP review | nursing notes NLP integrative review | 1 | E002 | Nursing note NLP evidence. |
| Q003 | academic | JMIR / BMC | LLM clinical entity extraction EHR free text | several | E003 | Clinical extraction method evidence. |
| Q004 | official docs | vLLM | vLLM offline inference OpenAI server | several | E004 | Inference infrastructure evidence. |
| Q005 | official/tool docs | PyMuPDF / LlamaParse / Textract | PDF OCR layout table parsing | several | E005 | PDF/OCR parsing evidence. |
| Q006 | negative search | mixed sources | PDF vLLM ICU nursing record extraction workflow | 0 strong | N001 | No complete same-topic workflow found. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Public ICU/clinical notes can support method analogies. | cross_surface | not_applicable | recent_but_unverified | E001 | none | confirmed | Public note form may not match PDF nursing records. |
| C002 | Nursing-note NLP is an existing but specialized research area. | cross_surface | not_applicable | recent_but_unverified | E002 | none | confirmed | Task labels and evaluations vary. |
| C003 | LLMs can support clinical text extraction pipelines with review. | cross_surface | not_applicable | recent_but_unverified | E003 | none | confirmed | Needs gold labels and error review. |
| C004 | vLLM is reusable inference infrastructure. | local_state | not_applicable | current_official | E004 | none | confirmed | It does not prove extraction quality. |
| C005 | PDF/OCR/layout parsing must be verified separately. | local_state | not_applicable | current_official | E005 | none | confirmed | Scans, tables, handwriting, and layout untested. |
| C006 | A mature full PDF -> vLLM -> ICU nursing extraction workflow exists publicly. | cross_surface | not_applicable | recent_but_unverified | E001; E002; E003; E004; E005 | N001 | unverified | No complete same-topic workflow found. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: MIMIC clinical note datasets
- entity_type: public clinical data source
- core_function: Provides de-identified ICU/clinical note data for research.
- relevance_score: 8
- reuse_score: 7
- score_scope: whole_entity
- method_similarity: 1
- method_note: Useful public clinical note evidence, but not equivalent to private ICU nursing PDFs.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: MIMIC-III Clinical Database
- url_or_local_reference: https://physionet.org/content/mimiciii/1.4/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: PhysioNet dataset includes ICU patient data and clinical notes.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| MIMIC-IV-Note | https://physionet.org/content/mimic-iv-note/2.2/ | 2026-07-09 | S | C001 |

#### Gaps

- MIMIC-IV-Note public table focus may not match nursing-record PDFs.

#### Risks

- Public data shape may mislead local workflow design.

### Entity E002

- entity_id: E002
- entity_name: Nursing notes NLP literature review
- entity_type: academic review
- core_function: Reviews NLP work on nursing notes.
- relevance_score: 9
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 2
- method_note: Directly relevant to nursing-note extraction, but not necessarily PDF/VLM.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Natural Language Processing of Nursing Notes: An Integrative Review
- url_or_local_reference: https://doi.org/10.1097/CIN.0000000000000967
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Review evidence supports nursing-note NLP as an existing specialized research area.

#### Gaps

- Does not solve PDF layout or local deployment.

#### Risks

- Evaluation metrics and task definitions vary.

### Entity E003

- entity_id: E003
- entity_name: LLM clinical text extraction pipelines
- entity_type: academic method evidence
- core_function: Uses LLMs for entity extraction and structured clinical text extraction workflows.
- relevance_score: 8
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 1
- method_note: Similar extraction method, but not nursing-PDF-specific.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: JMIR 2024 LLM entity extraction pipeline
- url_or_local_reference: https://www.jmir.org/2024/1/e54580/
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Paper evidence supports LLM-based clinical entity extraction pipelines with evaluation needs.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| BMC 2025 free-text EHR LLM extraction | https://link.springer.com/article/10.1186/s12874-025-02470-z | 2026-07-09 | A | C003 |

#### Gaps

- Gold-label schema and review workflow needed.

#### Risks

- Hallucination, missed negation, time ambiguity.

### Entity E004

- entity_id: E004
- entity_name: vLLM offline/server inference
- entity_type: local inference infrastructure
- core_function: Provides high-throughput local/offline and OpenAI-compatible inference.
- relevance_score: 7
- reuse_score: 8
- score_scope: surface:local_state
- method_similarity: 1
- method_note: Infrastructure is reusable, but extraction quality comes from model/prompt/data.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: vLLM Offline Inference
- url_or_local_reference: https://docs.vllm.ai/en/latest/examples/basic/offline_inference/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official docs show offline inference usage.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| vLLM Quickstart | https://docs.vllm.ai/en/stable/getting_started/quickstart/ | 2026-07-09 | S | C004 |

#### Gaps

- No extraction benchmark.

#### Risks

- Deployment success can be mistaken for task accuracy.

### Entity E005

- entity_id: E005
- entity_name: PDF/OCR/layout parsing stack
- entity_type: document processing tools
- core_function: Extracts text/layout/tables from PDFs or scans.
- relevance_score: 8
- reuse_score: 7
- score_scope: whole_entity
- method_similarity: 1
- method_note: Necessary preprocessing layer, not clinical extraction logic.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: PyMuPDF text recipes
- url_or_local_reference: https://pymupdf.readthedocs.io/en/latest/recipes-text.html
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Documentation supports PDF text extraction operations.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| LlamaParse docs | https://developers.llamaindex.ai/llamaparse/parse/ | 2026-07-09 | B | C005 |
| AWS Textract | https://aws.amazon.com/textract/ | 2026-07-09 | S | C005 |

#### Gaps

- Layout quality not tested on ICU nursing records.

#### Risks

- OCR/layout errors propagate to extraction.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: A mature public workflow already exists for PDF -> vLLM -> ICU nursing-record extraction improvement.
- searched_source_classes: public datasets; academic clinical NLP; vLLM docs; PDF/OCR tools.
- searched_queries: `PDF vLLM ICU nursing record extraction`; `clinical nursing notes PDF LLM extraction`.
- result: No strong complete same-topic workflow found in searched scope; evidence is component-level.
- interpretation_limit: Does not prove no workflow exists in private or niche settings.

## Information Gaps

- No private record access.
- No local template, gold label, or extraction benchmark.
- No privacy/IRB review.

## Search Module Notes

- This pack intentionally separates data, parsing, inference, extraction, and review.
