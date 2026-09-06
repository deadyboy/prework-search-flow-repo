# GitHub Implementation Search

## Purpose

This strategy card serves only the Search Module.

Its purpose is to discover whether an idea, tool need, or feature has an existing open-source implementation or reusable code base.

It searches for repositories, libraries, plugins, scripts, CLIs, extensions, issues, and discussions that implement or approximate the target capability.

It does not produce Judgment conclusions.

## When To Use

Use this card when the idea is primarily about:

- software/tooling;
- developer workflow;
- automation script;
- plugin/extension;
- library/package;
- internal tool replacement.

## Inputs

Use available inputs from:

- Idea Card;
- Search Plan;
- query matrix;
- known names;
- known technologies;
- known programming languages;
- constraints such as local-only operation, license, maintenance, platform, runtime, deployment target, or integration environment.

## Source Classes

Use the relevant source classes below:

- GitHub repository search;
- GitHub code search;
- GitHub issues/discussions;
- package registries when relevant;
- official docs when a project is found.

## Query Templates

Use templates and fill them from the Idea Card and query matrix. Do not hard-code a case-specific query.

### GitHub Native Search Templates

Exact name search:

```text
"<exact name>"
"<exact name>" github
"<exact name>" tool
```

Function description search:

```text
"<function description>" github
"<function description>" tool
"<function description>" open source
```

Synonym / alternative naming search:

```text
"<synonym term>" "<object term>"
"<alternative name>" github
"<problem term>" "<solution term>"
```

Code symbol / config / CLI search:

```text
"<symbol_or_function_name>" language:<language>
"<config_key>" "<tool category>"
"<cli_command_or_flag>" github
```

### Web Search Constrained To GitHub Templates

README search:

```text
site:github.com "<function description>" "README"
site:github.com "<object term>" "<method term>"
site:github.com "<tool category>" "<expected output>"
```

Issue / pain-point search:

```text
site:github.com "<problem term>" "issue"
site:github.com "<pain point>" "feature request"
site:github.com "<tool category>" "discussion"
```

Abandoned / limitation search:

```text
"<project or function term>" "not maintained"
"<project or function term>" "deprecated"
"<project or function term>" "does not support"
"<project or function term>" "limitation"
"<project or function term>" "alternative"
```

## Execution Steps

1. Start with exact-name queries from known project, feature, package, plugin, or CLI names.
2. Search function terms from the goal, input, output, and object fields.
3. Search synonym and alternative naming terms from the query matrix.
4. Search code-level terms, including symbols, config keys, CLI flags, package names, and language-specific terms when available.
5. Search issue and pain terms to find feature requests, limitations, workarounds, and failed implementations.
6. Record every executed query in the Evidence Pack query log.
7. Screen candidate results for fit, maintenance, license, usability, and implementation depth.
8. Aggregate the same project's repository, docs, issues, discussions, and packages into one entity.

## Evidence To Record

For every retained entity, record at least:

- entity_name;
- repo or primary source;
- core_function;
- supported features;
- missing features;
- license or terms if available;
- maintenance signal;
- integration signal;
- relevant issues or discussions;
- relevance_score;
- reuse_score;
- method_similarity;
- method_note;
- source_grade;
- evidence_status.

## Entity Aggregation Rules

Aggregate by project entity, not URL.

For the same project, combine:

- GitHub repository;
- official docs;
- package registry page;
- release notes;
- issues;
- discussions.

Distinguish:

- original project from forks;
- mirror from upstream;
- template from working implementation;
- demo from maintained project.

If a wrapper project depends on an upstream project, record both the wrapper and upstream relationship in the entity notes.

## Negative / Failure Searches

Run negative and failure-oriented queries when a candidate looks relevant or when no strong candidate appears.

Include terms such as:

- `not maintained`;
- `deprecated`;
- `does not support`;
- `alternative`;
- `issue`;
- `limitation`;
- `abandoned`;
- `feature request`.

Record these as information gaps or Negative Evidence Records. Negative evidence means no strong evidence was found within the covered scope; it does not prove non-existence.

## Stopping Rules

L1 can stop when exact-name, function-description, and basic GitHub repository searches either find a clear candidate or produce a recorded negative scope.

L2 can stop when repository search, code search, issues/discussions, and relevant package registry checks have been performed for the main query families.

L3 can stop when close candidates have also been checked for license, maintenance, docs, issues, releases, forks/mirrors, and upstream dependencies.

If a high-relevance and high-reuse project is found, still check license, maintenance, docs, and issues before handoff.

If no result is found, record the negative evidence scope. Do not say the implementation does not exist.

## Common False Positives

Common false positives include:

- same name but different function;
- toy demo;
- abandoned repository;
- README overstates capability;
- fork or mirror duplicate;
- research code that is not reusable engineering;
- license blocks reuse;
- project solves only a subproblem, not the full need.

## Handoff To Evidence Pack

All retained results must be written into the Evidence Pack.

This strategy card must not output Judgment conclusions such as `放弃不做`, `直接采用`, `接入改造`, `场景定制`, `补齐缺口`, `自研小样`, or `先补证据`.

If evidence is insufficient, record information gaps and Negative Evidence Records only.
