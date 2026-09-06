# Scoring Rules

This document defines the separate scores and labels used by Evidence Packs and Judgment Reports.

## Purpose

Scores and labels make Evidence Packs comparable across cases. They are structured estimates, not precise measurements.

Do not use a single `confidence` number. Keep similarity, reusability, source authority, and evidence confirmation separate.

## relevance_score

`relevance_score` is entity-level. It measures how similar an entity is to the original idea.

Use a 0-12 integer score across six dimensions:

| Dimension | 0 | 1 | 2 |
| --- | --- | --- | --- |
| Problem | Different problem | Related problem | Same core problem |
| User | Different user | Overlapping user | Same target user |
| Input | Different input | Partly similar input | Same or equivalent input |
| Output | Different output | Partly similar output | Same or equivalent output |
| Workflow | Different workflow | Borrowable workflow | Closely matching workflow |
| Constraint | Different constraints | Some shared constraints | Same key constraints |

Interpretation:

- `0-4`: generally related;
- `5-7`: weakly similar;
- `8-10`: strongly similar;
- `11-12`: near-equivalent.

## method_similarity

`method_similarity` is entity-level. It records whether the technical route, implementation style, or core method is similar to the user's idea.

Workflow is not the same as method. Workflow describes how a user moves through the work; method describes the underlying approach used to solve it.

Use:

- `0`: different method;
- `1`: partly similar or borrowable method;
- `2`: closely similar method.

Use `method_note` to explain the score in one or two sentences.

Record both of these cases when they appear:

- same goal, different method;
- same method, different goal.

Do not add `method_similarity` into `relevance_score`. Keep `relevance_score` on its existing 0-12 scale.

## method_note

`method_note` is entity-level. It briefly states what method is used and how it compares with the user's intended method.

## reuse_score

`reuse_score` is entity-level. It measures how practically reusable the entity is for the user's work.

Use a 0-10 integer score across five dimensions:

| Dimension | 0 | 1 | 2 |
| --- | --- | --- | --- |
| Availability | Not accessible | Partly accessible | Directly accessible |
| Documentation | Unclear | Partial | Clear enough to use |
| Integration | Hard to connect | Moderate effort | Easy to integrate |
| License or terms | Blocks reuse | Needs review | Reuse appears allowed |
| Maintenance | Abandoned or unknown | Some activity | Active or stable |

Interpretation:

- `0-3`: not worth reusing;
- `4-6`: reusable as reference only;
- `7-8`: reusable with adaptation;
- `9-10`: likely directly reusable.

## score_scope

`score_scope` is an optional lightweight qualifier for `reuse_score`.

Use it only when the entity-level reuse score would be misleading across claims or surfaces. If no `score_scope` is recorded, treat `reuse_score` as a whole-entity summary.

Allowed forms:

- `whole_entity`
- `claim:C001`
- `surface:desktop_app`
- `surface:vscode_extension`
- `surface:cli`
- `surface:app_server`
- `surface:web_product`
- `surface:remote_thread`
- `surface:local_state`
- `surface:cross_surface`

Example: an official API may have `reuse_score: 8` with `score_scope: claim:C002` for app-server rename, while the same entity does not solve a batch governance claim.

## source_grade

`source_grade` measures source authority for the specific claim being used.

Use:

- `S`: official source, official repository, authoritative standard, peer-reviewed paper for a research claim, or primary documentation;
- `A`: reputable expert source, active high-signal community record, well-maintained project metadata, or recognized institutional guidance;
- `B`: ordinary blog, forum discussion, product listing, tutorial, or secondary summary;
- `C`: marketing-only page, anonymous claim, SEO article, unverified aggregator, or weak indirect mention.

Grades are claim-specific. A GitHub issue can be high value for user pain but weaker for feature support. A product homepage can confirm positioning but not independent effectiveness.

Evidence Packs may keep an entity-level `source_grade` as a summary of the entity's strongest or most representative support.

When a Key Fact explicitly records a supporting source and evidence status, Judgment should use that specific record. Otherwise, use entity-level `source_grade`.

`source_grade` may therefore appear at source level and entity level. It may also appear in a lightweight Key Facts note when the Evidence Pack records one, but the Evidence Pack template does not require a structured facts table.

## evidence_status

`evidence_status` records whether the key claims about an entity are confirmed.

Use:

- `confirmed`: supported by at least two independent relevant sources, or by one authoritative primary source for a narrow factual claim;
- `single-source`: supported by one relevant source;
- `conflicting`: sources disagree on an important fact;
- `unverified`: mentioned but not supported enough to rely on.

Do not upgrade `evidence_status` because a claim sounds plausible. Use only recorded Evidence Pack sources.

Evidence Packs may keep an entity-level `evidence_status` as a summary of the entity's overall support.

When a Key Fact explicitly records a supporting source and evidence status, Judgment should use that specific record. Otherwise, use entity-level `evidence_status`.

Judgment should not treat an entity-level `confirmed` label as confirmation of every fact about that entity.

## Level Summary

- `relevance_score`: entity-level only.
- `method_similarity`: entity-level only.
- `method_note`: entity-level only.
- `reuse_score`: entity-level by default, optionally qualified by `score_scope`.
- `score_scope`: optional qualifier for claim-specific or surface-specific reuse.
- `source_grade`: source-level and entity-level, with optional Key Facts notes when recorded.
- `evidence_status`: entity-level, with optional Key Facts notes when recorded.
- `claim_evidence_status`: claim-level, using the same values as `evidence_status`.

## Score Use In Judgment

Judgment can use scores to compare entities, but it must cite `entity_id` or `negative_evidence_id` values and explain the reasoning.

High `relevance_score` without high `reuse_score` may support `补齐缺口`, `场景定制`, or `自研小样`.

High `reuse_score` with strong relevance may support `直接采用` or `接入改造`.

Low scores or weak `evidence_status` should usually trigger `先补证据` unless the decision is explicitly low stakes.

## Conclusion Glossary

- `放弃不做`: Existing evidence shows the work is not worth pursuing now.
- `直接采用`: A sufficiently fitting existing solution can be used as-is.
- `接入改造`: Existing work can cover the base need if integrated, wrapped, or lightly adapted.
- `场景定制`: A general solution exists, but the user's domain needs a focused variant.
- `补齐缺口`: Prior work covers the foundation, and the main value is finishing missing workflow, UX, or operational pieces.
- `自研小样`: No suitable reusable base is evident, so a small in-house prototype is justified.
- `先补证据`: The Evidence Pack is not sufficient for a responsible judgment.
