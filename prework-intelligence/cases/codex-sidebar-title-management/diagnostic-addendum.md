# Case 1 Diagnostic Addendum

## Purpose

This addendum records why Case 1 exposed a V1.1 framework gap. It does not replace the original Case 1 Evidence Pack or Judgment Report.

## Diagnosis

Case 1 found useful evidence, but the framework compressed several different claims into one broad title-management question.

The original case mixed at least these subproblems:

- manual thread renaming;
- app-server thread-name API support;
- auto title generation;
- fork or branch title lifecycle;
- legacy or abnormal title cleanup;
- batch review-based title governance;
- direct local state or database edits.

Those subproblems do not have the same answer. Some are already supported by official capability evidence, while others remain workflow gaps or evidence gaps.

## Root Causes

- Claim granularity was too coarse. Entity records grouped evidence by object, but not by capability claim.
- `surface_scope` was missing. Desktop app, VS Code extension, CLI, app-server, remote thread, and local state are different surfaces.
- `lifecycle_scope` was missing. Thread start, manual rename, fork, resume, read, legacy cleanup, and batch review are different lifecycle stages.
- Freshness was not a hard gate. Older issues were useful for historical pain, but they could be overread as current missing-feature evidence.
- Entity-level `reuse_score` was too broad. A high reuse score for app-server rename does not mean the same entity solves desktop batch governance.
- Current UI or user-observed evidence was not recorded. The original retrospective already noted that current client behavior was not verified hands-on.

## V1.1 Fix

V1.1 adds a lightweight claim layer:

- `Claim Decomposition` before search;
- `Capability Claim Matrix` inside Evidence Pack;
- `surface_scope`, `lifecycle_scope`, and `freshness_status` for each claim;
- `score_scope` when an entity score only applies to a claim or surface;
- claim-level local conclusions in Judgment Report.

This keeps Search and Judgment separated while letting Judgment say: one part is `直接采用`, another is `接入改造`, and another is `补齐缺口` or `先补证据`.

## Case 1 Regression Target

The regression should not rerun all searches. It should only add current official capability and lifecycle evidence, then rejudge the case at claim level.

The minimum claim set is:

- manual rename in the Codex app thread list;
- app-server `thread/name/set`;
- fork and thread-name lifecycle;
- legacy or abnormal title handling;
- batch review-based title governance;
- direct local state or database edit path.
