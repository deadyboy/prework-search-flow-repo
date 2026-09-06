# Evidence Pack

This is the Search Module handoff artifact for Case D3. It records evidence, not final decisions.

## Case Metadata

- Case ID: D3
- Idea title: Fluent blood-flow simulation automation
- Search level: L2/L3 standard engineering workflow scan
- Search date: 2026-07-09
- Searcher: Codex with independent vertical-workflow subagent brief

## Coverage Summary

- Searched source classes: official PyFluent docs; Fluent journal/TUI docs; Ansys blood-flow tutorials; blood-flow simulation papers.
- Unsearched source classes: local Fluent installation; version-specific API test; patient geometry pipeline; validation benchmark.
- Languages searched: English.
- Coverage note: Sufficient to establish automation feasibility, not physical/clinical validation.

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official docs | PyFluent | PyFluent automation parametric study Fluent | several | E001 | Automation API evidence. |
| Q002 | official/tutorial | Ansys | Fluent journal TUI batch automation | several | E002 | Journal/TUI evidence. |
| Q003 | official/tutorial | Ansys education | artery blood flow Fluent Carreau WSS UDF | several | E003 | Blood-flow workflow evidence. |
| Q004 | academic | blood-flow Fluent papers | Carreau blood flow artery Fluent WSS | several | E004 | Modeling evidence. |
| Q005 | negative search | mixed | one-click patient-specific Fluent blood flow automation pipeline | 0 strong | N001 | No production workflow found in searched scope. |

## Capability Claim Matrix

| claim_id | claim | surface_scope | lifecycle_scope | freshness_status | supporting_entities | supporting_negative_evidence | claim_evidence_status | gaps |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C001 | Fluent automation APIs and components exist. | local_state | not_applicable | current_official | E001; E002 | none | confirmed | Local version not tested. |
| C002 | Blood-flow Fluent tutorials and workflows exist. | cross_surface | not_applicable | current_official | E003 | none | confirmed | Tutorial robustness not proven. |
| C003 | Blood-flow modeling choices such as Carreau/WSS/UDF are documented in papers/tutorials. | cross_surface | not_applicable | recent_but_unverified | E003; E004 | none | confirmed | Patient-specific validation missing. |
| C004 | A production-ready one-click patient-specific workflow exists publicly. | cross_surface | not_applicable | recent_but_unverified | E001; E002; E003; E004 | N001 | unverified | No strong public production pipeline found. |

## Entity Records

### Entity E001

- entity_id: E001
- entity_name: PyFluent automation API
- entity_type: official automation API
- core_function: Automates Fluent setup, solving, monitoring, postprocessing, and parametric workflows through Python.
- relevance_score: 11
- reuse_score: 9
- score_scope: whole_entity
- method_similarity: 2
- method_note: Directly matches automation route for Fluent workflows.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: PyFluent documentation
- url_or_local_reference: https://fluent.docs.pyansys.com/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Official PyFluent docs provide Python automation API for Fluent.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| PyFluent user guide | https://fluent.docs.pyansys.com/version/stable/user_guide/user_guide_contents.html | 2026-07-09 | S | C001 |
| Parametric API | https://fluent.docs.pyansys.com/version/stable/api/parametric.html | 2026-07-09 | S | C001 |

#### Gaps

- Local license/version/API behavior not tested.

#### Risks

- Version differences and solver failures.

### Entity E002

- entity_id: E002
- entity_name: Fluent journal and TUI automation
- entity_type: official/tutorial automation route
- core_function: Uses Fluent journals and text user interface commands for repeatable batch operations.
- relevance_score: 10
- reuse_score: 8
- score_scope: whole_entity
- method_similarity: 2
- method_note: Direct automation route, lower-level than PyFluent.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Create and execute a Fluent journal file
- url_or_local_reference: https://innovationspace.ansys.com/knowledge/forums/topic/how-to-create-and-execute-a-fluent-journal-file/
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Ansys knowledge source describes Fluent journal creation and execution.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| PyFluent TUI commands | https://fluent.docs.pyansys.com/version/stable/user_guide/legacy/tui.html | 2026-07-09 | S | C001 |

#### Gaps

- Journal files can be brittle across versions.

#### Risks

- GUI-recorded journals can fail when geometry/mesh changes.

### Entity E003

- entity_id: E003
- entity_name: Ansys artery blood-flow Fluent tutorials
- entity_type: official/tutorial workflow evidence
- core_function: Shows blood-flow simulation setup with geometry, mesh, boundary conditions, blood model, and outputs.
- relevance_score: 10
- reuse_score: 7
- score_scope: whole_entity
- method_similarity: 2
- method_note: Direct workflow reference, but tutorial-level not production automation.
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: Realistic Coronary Artery Flow
- url_or_local_reference: https://www.ansys.com/academic/educators/education-resources/coronary-artery-flow-ansys-fluent
- accessed_at: 2026-07-09
- source_grade: S
- source_excerpt_or_summary: Ansys educational workflow for coronary artery flow in Fluent.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| 3D Bifurcating Artery | https://innovationspace.ansys.com/product/3d-bifurcating-artery/ | 2026-07-09 | S | C002 |

#### Gaps

- Does not prove robust automation over patient-specific batches.

#### Risks

- Tutorial assumptions may not hold for clinical geometries.

### Entity E004

- entity_id: E004
- entity_name: Blood-flow Fluent modeling papers
- entity_type: academic modeling evidence
- core_function: Documents blood-flow modeling choices such as Carreau/Carreau-Yasuda, WSS, velocity/pressure outputs.
- relevance_score: 8
- reuse_score: 6
- score_scope: whole_entity
- method_similarity: 1
- method_note: Provides modeling precedent, not automation implementation.
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Simulation analysis of blood flow in arteries of the human arm
- url_or_local_reference: https://doi.org/10.4015/S1016237217500314
- accessed_at: 2026-07-09
- source_grade: A
- source_excerpt_or_summary: Academic paper supports Fluent-style blood-flow modeling outputs and assumptions.

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Stenosed artery Fluent study | https://doi.org/10.34218/IJMET_16_05_001 | 2026-07-09 | B | C003 |

#### Gaps

- Validation and patient-specific boundary conditions not resolved.

#### Risks

- Physical credibility depends on mesh, boundary, solver, and validation.

## Negative Evidence Records

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: A reusable production-grade one-click patient-specific Fluent blood-flow automation pipeline exists publicly.
- searched_source_classes: official PyFluent docs; Ansys tutorials; academic blood-flow papers.
- searched_queries: `patient-specific Fluent blood flow automation pipeline`; `PyFluent blood flow batch simulation`.
- result: No strong public production pipeline found in searched scope; evidence is components and tutorial/paper workflows.
- interpretation_limit: Does not prove no private or commercial pipeline exists.

## Information Gaps

- Local Fluent version/license/API availability.
- Geometry import and mesh quality pipeline.
- Boundary condition source and validation baseline.

## Search Module Notes

- This pack supports automation feasibility, not physical validity.
