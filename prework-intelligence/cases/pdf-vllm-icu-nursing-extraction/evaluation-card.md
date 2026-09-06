# Case Evaluation Card

## Case ID

D1

## Case Type

Stress Test

## Why This Case Exists

This case tests privacy-sensitive vertical workflow search: OCR/PDF parsing, VLM/LLM extraction, clinical note NLP, local inference, and human review must be separated.

## Must Discover

- Public clinical note/NLP evidence.
- Nursing-note NLP evidence.
- PDF/OCR/layout parsing tools.
- vLLM as inference infrastructure, not extraction quality proof.
- Privacy and local deployment constraints.

## Must Not Misjudge

- Do not treat generic OCR as ICU nursing-record extraction.
- Do not treat vLLM deployment as evidence of extraction accuracy.
- Do not use private patient data.

## Reviewer Verdict

Pending review
