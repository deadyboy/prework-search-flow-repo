# Evidence Pack

This is the Search Module handoff artifact for Case E2. It records evidence, not final decisions.

## Case Metadata

- Case ID: E2
- Idea title: Existing-work-search method prior work
- Original idea: Search for prior methods behind Prework Intelligence.
- Search level: L3 deep review
- Search date: 2026-07-09
- Searcher: Codex with independent meta-framework subagent brief

## Coverage Summary

- Searched source classes: patent/prior-art methods; systematic/scoping review methods; software grey-literature methods; technology scouting; build-vs-buy and competitive intelligence references.
- Unsearched source classes: paywalled full analyst reports; non-English methodology sources; expert interviews.
- Languages searched: English.
- Timebox: targeted method-prior-work scan.
- Coverage note: Sufficient to identify reusable method families, not sufficient to claim no unified standard exists globally.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | patent/prior art | USPTO/WIPO/EPO | `prior art search strategy patent landscape` | several | E001 | Prior-art search methods. |
| Q002 | academic method | PRISMA/Cochrane/JBI | `systematic review scoping review search protocol PRISMA` | several | E002 | Review protocol methods. |
| Q003 | software engineering method | Wohlin/Garousi | `snowballing grey literature multivocal literature review software engineering` | several | E003 | Software/practice sources. |
| Q004 | institutional method | ISO/DHS/WIPO | `technology scouting strategic intelligence framework` | several | E004 | Scouting/intelligence methods. |
| Q005 | decision framework | AWS/Intelligence/HBS | `build vs buy competitive intelligence decision framework` | several | E005 | Judgment inputs. |
| Q006 | negative search | mixed sources | `unified existing work search standard patent paper product code community` | 0 strong | N001 | No unified public standard found in searched scope. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Prior-art search 可增强 Search Module。 | cross_surface | not_applicable | current_official | E001 | none | confirmed | Patent methods do not cover all source classes. |
| C002 | Systematic/scoping review 可增强检索可审计性。 | cross_surface | not_applicable | current_official | E002 | none | confirmed | May be too heavy for quick product/tool searches. |
| C003 | Snowballing / grey literature 可覆盖软件和实践来源。 | cross_surface | not_applicable | recent_but_unverified | E003 | none | confirmed | Grey literature quality varies. |
| C004 | Technology scouting / CI / build-vs-buy 可作为 Judgment 输入。 | cross_surface | not_applicable | current_official | E004; E005 | N002 | confirmed | Must not move into Search Module output. |
| C005 | 未发现统一跨源公共标准。 | cross_surface | not_applicable | recent_but_unverified | E001; E002; E003; E004; E005 | N001 | unverified | Negative evidence limited to searched scope. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: USPTO / WIPO / EPO prior-art and patent landscape methods
- entity_type: prior-art search methodology
- core_function: Provides structured ways to search patents and technical prior art.
- relevance_score: 9
- reuse_score: 7
- score_scope: claim:C001
- method_similarity: 2
- method_note: Strong fit for prior-art source coverage, but narrower than Prework's code/product/workflow scope.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: USPTO patent search strategy
- url_or_local_reference: https://www.uspto.gov/patents/search/patent-search-strategy
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official guidance on patent search strategy and prior-art search.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| USPTO MPEP 904 | https://www.uspto.gov/web/offices/pac/mpep/s904.html | 2026-07-09 | S | C001 |
| WIPO Patent Landscape Reports | https://www.wipo.int/publications/en/details.jsp?id=3938 | 2026-07-09 | S | C001 |
| Espacenet | https://www.epo.org/en/searching-for-patents/technical/espacenet | 2026-07-09 | S | C001 |

#### Key Facts

- Prior-art methods offer query expansion, classification, patent/non-patent literature, and landscape reporting concepts.
- They are not complete replacements for product, code, and community search.

#### Similarity Notes

- Problem similarity: high.
- User similarity: medium.
- Input similarity: medium.
- Output similarity: high.
- Workflow similarity: high.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: classification search, non-patent literature search, search-scope documentation.
- Integration cost: medium.
- License or terms: public institutional guidance.
- Maintenance signal: official sources.

#### Gaps

- Patentability and legal conclusions remain out of scope.

#### Risks

- Could overemphasize patents for software/product cases.

### Entity E002

- entity_id: E002
- entity_name: PRISMA / Cochrane / JBI systematic and scoping review methods
- entity_type: evidence review methodology
- core_function: Defines protocol, eligibility, search, screening, exclusion, and reporting practices.
- relevance_score: 10
- reuse_score: 8
- score_scope: claim:C002
- method_similarity: 2
- method_note: Strong fit for auditable search protocol and evidence reporting, but may be too heavy for quick scans.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: PRISMA 2020
- url_or_local_reference: https://www.prisma-statement.org/prisma-2020
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: PRISMA provides reporting standards for systematic reviews.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Cochrane Handbook Chapter 4 | https://www.cochrane.org/authors/handbooks-and-manuals/handbook/current/chapter-04 | 2026-07-09 | S | C002 |
| JBI scoping review resources | https://jbi.global/scoping-review-network/resources | 2026-07-09 | S | C002 |
| Arksey and O'Malley scoping studies | https://www.tandfonline.com/doi/full/10.1080/1364557032000119616 | 2026-07-09 | S | C002 |

#### Key Facts

- Systematic/scoping review methods support repeatable and auditable search.
- They should inform Search Module structure, not dictate every lightweight case.

#### Similarity Notes

- Problem similarity: high.
- User similarity: medium.
- Input similarity: high.
- Output similarity: high.
- Workflow similarity: high.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: protocol, eligibility, screening log, exclusion reasons, PRISMA-like flow concepts.
- Integration cost: medium.
- License or terms: public method references.
- Maintenance signal: mature guidance.

#### Gaps

- Does not cover build-vs-buy action judgment directly.

#### Risks

- May slow down low-stakes quick scans if applied wholesale.

### Entity E003

- entity_id: E003
- entity_name: Snowballing and multivocal literature review in software engineering
- entity_type: software evidence methodology
- core_function: Covers backward/forward snowballing and grey-literature quality handling.
- relevance_score: 9
- reuse_score: 8
- score_scope: claim:C003
- method_similarity: 2
- method_note: Strong fit for software/tooling cases where blogs, repos, and docs matter.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Wohlin 2014 snowballing
- url_or_local_reference: https://dl.acm.org/doi/10.1145/2601248.2601268
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Software engineering paper proposes snowballing as a systematic literature search approach.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Garousi et al. Multivocal Literature Review | https://arxiv.org/abs/1707.02553 | 2026-07-09 | A | C003 |

#### Key Facts

- Software evidence often includes grey literature, not only academic papers.
- Grey literature needs quality checks and source risk labeling.

#### Similarity Notes

- Problem similarity: high.
- User similarity: high.
- Input similarity: high.
- Output similarity: high.
- Workflow similarity: high.
- Constraint similarity: high.

#### Reuse Notes

- Reusable parts: backward/forward snowballing, grey literature source grading.
- Integration cost: low to medium.
- License or terms: public paper references.
- Maintenance signal: established method literature.

#### Gaps

- Grey literature remains unstable and may disappear.

#### Risks

- Overweighting blogs or vendor material without source grading.

### Entity E004

- entity_id: E004
- entity_name: ISO 56006 / DHS / WIPO technology scouting and strategic intelligence
- entity_type: technology scouting methodology
- core_function: Provides discovery and monitoring concepts for external technology opportunities.
- relevance_score: 8
- reuse_score: 6
- score_scope: claim:C004
- method_similarity: 1
- method_note: Adjacent to Prework's external opportunity search, but often blends discovery and strategy.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: ISO 56006 strategic intelligence
- url_or_local_reference: https://www.iso.org/standard/72621.html
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: ISO strategic intelligence standard provides a framework for strategic intelligence management.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| DHS Technology Scouting | https://www.dhs.gov/science-and-technology/technology-scouting | 2026-07-09 | A | C004 |
| WIPO Patent Analytics | https://www.wipo.int/en/web/patent-analytics | 2026-07-09 | S | C004 |

#### Key Facts

- Technology scouting supports external discovery and monitoring.
- It does not guarantee Search/Judgment module separation.

#### Similarity Notes

- Problem similarity: medium.
- User similarity: medium.
- Input similarity: medium.
- Output similarity: high.
- Workflow similarity: medium.
- Constraint similarity: medium.

#### Reuse Notes

- Reusable parts: opportunity scouting framing and monitoring.
- Integration cost: medium.
- License or terms: source-specific.
- Maintenance signal: institutional sources.

#### Gaps

- Search/Judgment split not explicit.

#### Risks

- May pull Prework toward strategic planning beyond intended scope.

### Entity E005

- entity_id: E005
- entity_name: Build-vs-buy, intelligence cycle, and competitive analysis frameworks
- entity_type: judgment input frameworks
- core_function: Offers decision criteria after evidence has been collected.
- relevance_score: 7
- reuse_score: 6
- score_scope: claim:C004
- method_similarity: 1
- method_note: Useful for Judgment Module inputs, but not Search Module evidence generation.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: AWS revisiting buy vs build
- url_or_local_reference: https://aws.amazon.com/blogs/enterprise-strategy/revisiting-buy-vs-build-3-traps-to-avoid/
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: AWS guidance discusses build-vs-buy traps and decision considerations.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Intelligence.gov cycle | https://www.intelligence.gov/how-the-ic-works | 2026-07-09 | S | C004 |
| HBS Five Forces | https://www.isc.hbs.edu/strategy/business-strategy/Pages/the-five-forces.aspx | 2026-07-09 | S | C004 |

#### Key Facts

- These frameworks help action judgment and strategic framing.
- They should not be used by Search Module to output final recommendations.

#### Similarity Notes

- Problem similarity: medium.
- User similarity: medium.
- Input similarity: low.
- Output similarity: high.
- Workflow similarity: low.
- Constraint similarity: high.

#### Reuse Notes

- Reusable parts: decision criteria and risk framing.
- Integration cost: medium.
- License or terms: public guidance.
- Maintenance signal: institutional sources.

#### Gaps

- Some commercial framework details are paywalled.

#### Risks

- May induce premature judgment if mixed into Search Module.

## Information Gaps

- Paywalled analyst detail not reviewed.
- Non-English methodology not covered.
- No expert interviews.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: There is a single public standard that unifies patent, paper, code, product, community, and business-process existing-work search.
- searched_source_classes: patent methods; review methods; software grey literature; technology scouting; build-vs-buy; CI references.
- searched_queries: `unified existing work search standard patent paper product code community`; `existing work search build vs buy systematic review prior art`.
- result: No strong unified standard found in searched scope.
- interpretation_limit: This does not prove no unified standard exists; it only limits the current searched scope.

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: Technology scouting and build-vs-buy frameworks explicitly enforce Search Module and Judgment Module separation.
- searched_source_classes: ISO/DHS/AWS/Intelligence/Five Forces references.
- searched_queries: `technology scouting search judgment separation`; `build vs buy evidence module judgment module`.
- result: No strong evidence found that these frameworks enforce the same module separation; many combine collection, analysis, and action advice.
- interpretation_limit: This does not prove no adapted implementation could separate them.

## Negative Search Scope

- Unified cross-source standard.
- Search/Judgment separation in established frameworks.
- Paywalled detail gaps.

## Search Module Notes

- Mature methods exist, but each covers part of Prework's source and decision space.
- This pack contains no final Judgment conclusion.
