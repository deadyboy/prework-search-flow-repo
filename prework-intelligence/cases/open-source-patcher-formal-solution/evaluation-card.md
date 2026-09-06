# Case Evaluation Card

## Case ID

A2

## Case Type

Calibration

## Why This Case Exists

This case tests whether the workflow can distinguish "there is an open-source implementation" from "it is safe and appropriate to reuse as a formal solution."

## Must Discover

- Whether the patcher modifies installed extension files.
- Whether license and maintenance signals are visible.
- Whether the target surface matches the user's desired Codex title-governance surface.
- Whether backup, verification, rollback, and reapply behavior exist.
- Whether the patcher is official, supported, or only a workaround/reference implementation.

## Must Not Misjudge

- Do not recommend `直接采用` only because the repo is functionally similar.
- Do not treat local patching as a safe default path.
- Do not ignore license, maintenance, compatibility, and official-support boundaries.

## Critical Distinctions

- claim_scope: patcher capability; official support boundary; maintenance and license; patching risk; formal default path.
- surface_scope: vscode_extension; app_server; local_state; cross_surface.
- lifecycle_scope: manual_rename; not_applicable.
- freshness_scope: recent_but_unverified; current_official.
- privacy_scope: no local extension or account files inspected.

## Required Source Classes

- official docs: Codex open-source boundary and official capability docs.
- GitHub/open-source: patcher repo, docs, license, releases, commit activity.
- product/community: optional; not required for this calibration case.
- papers: not applicable.
- local/user-provided: not searched.
- negative/failure search: official endorsement and package distribution search.

## Minimum Acceptable Evidence Pack

- Contains an entity for the patcher and an entity for official support boundary.
- Records license, maintenance, patch points, backup/rollback behavior, and risks.
- Records negative evidence for official endorsement or formal package distribution.
- Does not output Judgment conclusions.

## Minimum Acceptable Judgment Report

- Does not say the patcher can be directly adopted as formal default.
- Separates reusable implementation ideas from unsafe default deployment.
- Cites only Evidence Pack `entity_id` or `negative_evidence_id` records.

## Reviewer Verdict

Pending review

## Failure Type

Not yet assigned
