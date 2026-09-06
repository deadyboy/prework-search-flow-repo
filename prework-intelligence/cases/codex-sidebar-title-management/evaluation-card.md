# Case Evaluation Card

## Case ID

A1 / PI-C001

## Case Type

Calibration

## Why This Case Exists

This case checks whether V1.1 fixes the original Case 1 failure mode: broad title-management evidence was found, but current product capability, surface, lifecycle, and governance claims were not separated clearly enough.

## Must Discover

- Official manual rename capability is separate from batch governance.
- App-server `thread/name/set` is separate from desktop UI behavior.
- `thread/start` and `thread/fork` lifecycle behavior need separate claims.
- Legacy or abnormal title handling remains distinct from manual rename.
- Old issues are historical pain unless current freshness is established.
- Current UI or user-observed evidence should be recorded when safe.

## Must Not Misjudge

- Do not describe Codex title management as wholly missing.
- Do not treat old issues as current missing-feature evidence.
- Do not treat API-level capability as a complete user-facing workflow.
- Do not treat local state or installed-extension patching as the default path.

## Critical Distinctions

- claim_scope: manual rename; app-server rename; fork/start lifecycle; legacy title handling; batch governance; local-state workaround.
- surface_scope: desktop_app; app_server; local_state; cross_surface.
- lifecycle_scope: manual_rename; thread_fork; legacy_thread; batch_review; not_applicable.
- freshness_scope: current_official; recent_but_unverified; unknown_date.
- privacy_scope: no private `.codex` state, account settings, or private thread content unless explicitly authorized.

## Required Source Classes

- official docs: Codex changelog; Codex app-server docs.
- GitHub/open-source: original Case 1 entities for issue cluster and patcher evidence.
- product/community: original Case 1 community evidence only; no full refresh for this calibration pass.
- papers: not applicable.
- local/user-provided: current UI observation only if safe and user-provided.
- negative/failure search: official-source negative evidence for complete batch governance and legacy cleanup.

## Minimum Acceptable Evidence Pack

- Contains a Capability Claim Matrix.
- Separates manual rename, app-server rename, fork/start lifecycle, legacy title handling, batch governance, and local-state workaround.
- Records `surface_scope`, `lifecycle_scope`, `freshness_status`, and `claim_evidence_status`.
- Treats old issue evidence as historical unless freshness is established.
- Does not output Judgment conclusions.

## Minimum Acceptable Judgment Report

- Keeps one Primary Conclusion.
- Includes claim-level local conclusions.
- Expresses manual rename as `直接采用`.
- Expresses app-server rename as `接入改造`.
- Expresses fork/start lifecycle and legacy handling as `先补证据` when current UI or official workflow evidence is missing.
- Expresses batch governance as `补齐缺口`.
- Expresses local-state or installed-extension patching as not a default path, through a cited local conclusion.
- Cites only records from the declared Evidence Pack bundle.

## Reviewer Verdict

Pending review

## Failure Type

Not yet assigned
