# Paper Prior Work Search

## Purpose

This strategy card serves only the Search Module.

Its purpose is to find academic prior work, research methods, surveys, benchmarks, datasets, research prototypes, and paper-with-code style implementations that may already cover the idea or a core method.

It does not produce Judgment conclusions or a full literature review.

All retained results must be recorded in the Evidence Pack.

## When To Use

Use this card when the idea depends on:

- a research method;
- a model, algorithm, or technical approach;
- benchmark or dataset precedent;
- paper claims about feasibility or performance;
- academic prototypes;
- comparison against published prior work;
- same method with a different goal;
- same goal with a different method.

## Inputs

Use available inputs from:

- Idea Card;
- Search Plan;
- query matrix;
- method terms;
- task, input, output, and domain terms;
- known papers, authors, labs, datasets, or benchmarks;
- constraints such as reproducibility, code availability, data access, license, compute, and deployment fit.

## Source Classes

Use relevant source classes below:

- academic search indexes;
- preprint servers;
- publisher pages;
- survey and review papers;
- benchmark and dataset pages;
- paper-with-code or implementation listings;
- official project pages;
- associated GitHub repositories when relevant;
- citation trails from close papers.

Do not turn this source list into an API adapter, crawler, or automated review pipeline.

## Query Templates

Use templates and fill them from the Idea Card and query matrix. Do not hard-code a case-specific query.

Task and method search:

```text
"<task term>" "<method term>"
"<input object>" "<output object>" "<method term>"
"<domain term>" "<technical approach>"
```

Survey and review search:

```text
"<task term>" survey
"<method family>" review
"<domain term>" systematic review
```

Benchmark and dataset search:

```text
"<task term>" benchmark
"<task term>" dataset
"<method term>" leaderboard
```

Paper-with-code and implementation search:

```text
"<paper or method term>" code
"<task term>" "paper with code"
"<method term>" github
```

Synonym and alternate framing search:

```text
"<synonym task term>" "<method term>"
"<alternate method name>" "<domain term>"
"<problem framing>" "<research term>"
```

Limitation and failure search:

```text
"<method term>" limitation
"<method term>" failure
"<task term>" challenge
"<dataset or benchmark>" bias
```

## Execution Steps

1. Start with task and method terms from the Idea Card.
2. Search survey or review terms to identify established terminology and major branches.
3. Search recent, highly cited, and closely matching papers.
4. Search benchmark, dataset, and leaderboard terms when the idea depends on measurable performance.
5. Search for associated code, project pages, reproducibility notes, and implementation listings.
6. Follow citations backward and forward for close papers when the search level requires it.
7. Record every executed query in the Evidence Pack query log.
8. Screen candidates for task fit, method similarity, evidence strength, reproducibility, code or data availability, and operational relevance.
9. Aggregate one paper, its project page, code, dataset links, and benchmark entries into one entity when they describe the same research work.

## Evidence To Record

For every retained entity, record at least:

- entity_name;
- paper title or primary source;
- authors or organization when relevant;
- publication venue or source class;
- year or version;
- core_method;
- task and domain;
- input and output;
- supported claims;
- benchmark or dataset evidence when available;
- code, data, or project availability when available;
- reproducibility signal;
- practical reuse constraints;
- relevance_score;
- reuse_score;
- method_similarity;
- method_note;
- source_grade;
- evidence_status.

## Entity Aggregation Rules

Aggregate by research work or method entity, not URL.

For the same research work, combine:

- paper page;
- preprint page;
- publisher page;
- official project page;
- code repository;
- dataset or benchmark page;
- errata, follow-up note, or reproducibility report.

Distinguish:

- survey paper from original method paper;
- benchmark from method;
- dataset from model or algorithm;
- paper claim from working implementation;
- research prototype from production-ready tool;
- follow-up paper from the original work.

If a paper builds on a prior method or dataset, record that relationship in entity notes.

## Negative / Failure Searches

Run negative and failure-oriented queries when no close prior work appears or when a candidate appears close.

Include terms such as:

- `survey`;
- `review`;
- `benchmark`;
- `dataset`;
- `limitation`;
- `failure`;
- `challenge`;
- `reproducibility`;
- `no code`;
- `ablation`;
- `baseline`;
- `comparison`.

Record these as information gaps or Negative Evidence Records. Negative evidence means no strong evidence was found within the covered scope; it does not prove non-existence.

## Stopping Rules

L1 can stop when an academic index or preprint source and general web search either find obvious close papers or produce a recorded negative scope.

L2 can stop when academic indexes, surveys or reviews, recent or highly cited papers, and implementation or dataset sources have been searched for the main query families.

L3 can stop when close papers have also been checked through backward citations, forward citations, benchmark or dataset evidence, code availability, and limitation or reproducibility searches.

If no academic index was searched, source coverage is not sufficient for prior-work claims.

If no result is found, record the negative evidence scope. Do not say the prior work does not exist.

## Common False Positives

Common false positives include:

- similar title but different task;
- same task but different method;
- same method but different goal;
- paper only proposes a concept without implementation;
- benchmark result does not match the user's constraints;
- dataset is not available or not reusable;
- code exists but is incomplete, stale, or non-reproducible;
- survey mentions an area but not the specific workflow;
- abstract claims are stronger than the method or experiments support.

## Handoff To Evidence Pack

All retained results must be written into the Evidence Pack.

This strategy card must not output Judgment conclusions such as `放弃不做`, `直接采用`, `接入改造`, `场景定制`, `补齐缺口`, `自研小样`, or `先补证据`.

If evidence is insufficient, record information gaps and Negative Evidence Records only.
