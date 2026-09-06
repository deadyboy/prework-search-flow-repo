# Negative Evidence Search

## Purpose

This strategy card serves only the Search Module.

Its purpose is to record searched absence within a defined scope.

Negative evidence can only mean that strong evidence was not found within the covered sources, queries, timebox, and limits. It must not be used to claim absolute non-existence.

This card does not produce Judgment conclusions.

## When To Use

Use this card when:

- strong similar solutions are not found;
- the search needs to check whether there is no obvious open-source implementation, product, paper, or substitute;
- high-relevance entities have insufficient evidence;
- the search needs to check `abandoned`, `deprecated`, `limitation`, `does not support`, `alternative`, `complaint`, or failure-case signals;
- the Judgment Module may need to cite `negative_evidence_id`.

## Inputs

Use available inputs from:

- Idea Card;
- Search Plan;
- Query Matrix;
- Source Selection rules;
- executed query log;
- discovered entities;
- information gaps.

## Source Classes

Negative evidence can come from different source classes:

- general web;
- GitHub / open source;
- product directories;
- papers;
- communities / issues / forums;
- patents / standards;
- user-provided or local sources when allowed.

Do not turn this into a platform adapter plan or crawler plan.

## Query Templates

Use templates and fill them from the Idea Card, Search Plan, and query matrix. Do not hard-code a case-specific query.

Exact-name absence search:

```text
"<exact name>"
"<exact name>" "<source class term>"
"<exact name>" "<known platform or ecosystem>"
```

Function + alternative search:

```text
"<function description>" alternative
"<function description>" substitute
"<function description>" similar tool
```

Limitation search:

```text
"<entity or function term>" limitation
"<entity or function term>" limitations
"<entity or function term>" missing feature
```

Abandoned / deprecated search:

```text
"<entity or function term>" abandoned
"<entity or function term>" deprecated
"<entity or function term>" no longer maintained
```

Complaint / issue search:

```text
"<problem term>" complaint
"<problem term>" issue
"<problem term>" not working
```

Competitor / alternative search:

```text
"<tool or method term>" competitor
"<tool or method term>" alternative
"<tool or method term>" vs
```

Failure case search:

```text
"<method or tool term>" failure
"<method or tool term>" failed
"<method or tool term>" does not work
```

Does-not-support search:

```text
"<entity or function term>" "does not support"
"<entity or function term>" "not supported"
"<entity or function term>" "unsupported"
```

No open source / closed source only search:

```text
"<function description>" "no open source"
"<function description>" "closed source"
"<function description>" "proprietary"
```

Not maintained search:

```text
"<entity or function term>" "not maintained"
"<entity or function term>" "maintenance mode"
"<entity or function term>" "archived"
```

## Execution Steps

1. Confirm that positive search has already been executed for the relevant source classes.
2. Define the `searched_claim` being tested.
3. Run negative, limitation, failure, and alternative queries by source class.
4. Record every query in the Evidence Pack query log.
5. Distinguish `no result`, `weakly related results`, and `results exist but do not form a strong substitute`.
6. Write findings into Negative Evidence Records.
7. Do not write negative evidence as an absolute conclusion.

## Evidence To Record

Each Negative Evidence Record must record at least:

- negative_evidence_id;
- searched_claim;
- searched_source_classes;
- searched_queries;
- result;
- interpretation_limit.

The `result` should state one of these patterns when applicable:

- no strong result found;
- only weakly related results found;
- only stale / abandoned results found;
- only partial substitutes found;
- source class unsearched.

## Entity Aggregation Rules

Negative evidence is not aggregated as an entity.

If a weakly related object is found, create an entity record first and describe its weakness in gaps or risks.

If no entity can be formed from the covered search scope, record a Negative Evidence Record instead.

Do not reuse an `entity_id` as a `negative_evidence_id`.

## Interpretation Limits

Negative evidence never proves non-existence.

It only limits what was not found within recorded coverage.

Narrow coverage should create information gaps, not confident conclusions.

A negative record from one source class cannot stand for all source classes.

## Relationship To Entity Records

`negative_evidence_id` is not an `entity_id`.

If a weakly related object is found, create an entity record first and describe its weaknesses in gaps or risks.

If no entity can be formed, record negative evidence.

An Evidence Pack can contain both entity records and negative evidence records.

## Negative / Failure Searches

Use the query families above to search for absence, limitations, abandoned work, deprecated work, complaints, alternatives, and failure cases within recorded source classes.

Record the searched scope and result in Negative Evidence Records.

Do not convert a negative or failure search into a claim that no solution exists.

## Stopping Rules

L1 can stop when the main source classes have been searched and no obvious strong substitute appears; record preliminary negative evidence.

L2 can stop when required source classes have been searched and the main query families are covered; record standard negative evidence.

L3 can stop when multiple source classes have been checked, including failure, alternative, limitation, and stale-project searches; record stronger negative evidence.

If a required source class is unsearched, coverage cannot be marked sufficient.

## Common False Positives

Common false positives include:

- query terms are too narrow;
- only Chinese or only English was searched;
- only exact names were searched;
- platform content is not indexed by general search engines;
- private, closed-source, or internal tools are not visible;
- similar solutions use completely different names;
- only homepage snippets were read;
- no open source is misread as no one has done it.

## Handoff To Evidence Pack

All outputs from this card must be written into the Evidence Pack's Negative Evidence Records.

This strategy card must not output Judgment conclusions such as `放弃不做`, `直接采用`, `接入改造`, `场景定制`, `补齐缺口`, `自研小样`, or `先补证据`.

If negative evidence scope is too narrow, record information gaps only.
