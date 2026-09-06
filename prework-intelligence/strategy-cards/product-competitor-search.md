# Product Competitor Search

## Purpose

This strategy card serves only the Search Module.

Its purpose is to find existing products, commercial tools, hosted services, apps, plugins, and workflow substitutes that may solve the same user problem as the idea.

It does not produce Judgment conclusions, market reports, business plans, or product strategy.

All retained results must be recorded in the Evidence Pack.

## When To Use

Use this card when the idea may already be covered by:

- a commercial product;
- a SaaS workflow;
- a desktop or mobile app;
- a browser extension or marketplace app;
- a vertical industry tool;
- a no-code or low-code service;
- an internal-tool replacement with available public substitutes.

## Inputs

Use available inputs from:

- Idea Card;
- Search Plan;
- query matrix;
- target user or buyer;
- workflow steps;
- known product names;
- platform constraints;
- pricing, deployment, privacy, integration, or compliance constraints.

## Source Classes

Use relevant source classes below:

- general web search;
- product homepages;
- product directories;
- app stores or extension marketplaces;
- review and comparison pages;
- pricing pages and terms pages;
- help docs, changelogs, and integration docs;
- user communities, forums, and issue-like complaint sources.

Do not turn this source list into a crawler, platform adapter, or market database plan.

## Query Templates

Use templates and fill them from the Idea Card and query matrix. Do not hard-code a case-specific query.

Exact product or category search:

```text
"<exact product name>"
"<tool category>" "<target user>"
"<workflow name>" software
```

Function and outcome search:

```text
"<function description>" tool
"<desired output>" software
"<input object>" "<desired action>" app
```

Competitor and alternative search:

```text
"<known product>" alternative
"<known product>" competitor
"<tool category>" comparison
```

Directory and marketplace search:

```text
"<tool category>" product directory
"<tool category>" marketplace
"<platform>" "<extension or app category>"
```

Pricing, terms, and integration search:

```text
"<product name>" pricing
"<product name>" API
"<product name>" integration
"<product name>" terms
```

User pain and limitation search:

```text
"<product name>" limitation
"<product name>" complaint
"<product name>" does not support
"<workflow problem>" workaround
```

## Execution Steps

1. Start with known product names and exact category terms.
2. Search function, outcome, input, and workflow terms.
3. Search competitor, alternative, comparison, and directory terms.
4. For close candidates, inspect product pages, docs, pricing or terms, integrations, and user-facing evidence.
5. Search limitation, complaint, and workaround terms for close candidates.
6. Record every executed query in the Evidence Pack query log.
7. Screen candidates for problem fit, target user fit, workflow coverage, integration, cost, terms, and operational limits.
8. Aggregate the same product's homepage, docs, pricing, reviews, marketplace listing, and community evidence into one entity.

## Evidence To Record

For every retained entity, record at least:

- entity_name;
- product or primary source;
- core_function;
- target user;
- supported workflow steps;
- missing workflow steps;
- pricing or access model when available;
- license, terms, privacy, or deployment constraints when available;
- integration signal;
- maintenance or product activity signal;
- relevant reviews, complaints, or comparisons;
- relevance_score;
- reuse_score;
- method_similarity;
- method_note;
- source_grade;
- evidence_status.

## Entity Aggregation Rules

Aggregate by product entity, not URL.

For the same product, combine:

- official homepage;
- official docs;
- pricing or terms pages;
- marketplace or app-store listing;
- changelog or release notes;
- review pages;
- user community or complaint sources.

Distinguish:

- direct competitor from indirect substitute;
- product from marketplace wrapper;
- product family from individual module;
- official page from reseller or affiliate listing;
- current product from discontinued product.

If one product depends on another platform or upstream service, record that relationship in entity notes.

## Negative / Failure Searches

Run negative and failure-oriented queries when no strong substitute appears or when a candidate appears close.

Include terms such as:

- `alternative`;
- `competitor`;
- `limitation`;
- `complaint`;
- `does not support`;
- `missing feature`;
- `deprecated`;
- `discontinued`;
- `pricing`;
- `terms`;
- `integration`.

Record these as information gaps or Negative Evidence Records. Negative evidence means no strong evidence was found within the covered scope; it does not prove non-existence.

## Stopping Rules

L1 can stop when general web, product homepage or directory, and obvious alternative queries either find clear candidates or produce a recorded negative scope.

L2 can stop when product homepages, product directories, review or comparison sources, and at least one user-facing source class have been searched for the main query families.

L3 can stop when close candidates have also been checked for docs, pricing or terms, integrations, changelogs, multiple user communities, and limitation or complaint evidence.

If only vendor pages were searched, source coverage is not sufficient for product substitute claims.

If no result is found, record the negative evidence scope. Do not say the product or competitor does not exist.

## Common False Positives

Common false positives include:

- same category name but different user problem;
- marketing page claims unsupported by docs or user evidence;
- generic platform that needs too much custom build;
- product covers only one workflow step;
- discontinued or renamed product;
- reseller, affiliate, or SEO listing mistaken for an official source;
- pricing or terms block reuse;
- product exists but lacks required integration or deployment mode.

## Handoff To Evidence Pack

All retained results must be written into the Evidence Pack.

This strategy card must not output Judgment conclusions such as `放弃不做`, `直接采用`, `接入改造`, `场景定制`, `补齐缺口`, `自研小样`, or `先补证据`.

If evidence is insufficient, record information gaps and Negative Evidence Records only.
