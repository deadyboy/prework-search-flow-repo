# Source Selection

This document defines minimum source coverage for Prework Intelligence searches by problem type and search level.

## Purpose

Source selection prevents a search from looking complete just because one convenient source returned plausible results.

The Search Module uses this document to decide which source classes are required, which are optional, and when an Evidence Pack can mark source coverage as sufficient.

## Search Levels

- `L1 quick scan`: fast check for obvious prior work or substitutes.
- `L2 standard scan`: normal prework review across the most relevant source classes.
- `L3 deep review`: higher-stakes review with cross-source validation and stronger negative evidence.

## Source Status

- `required`: must be searched or explicitly listed as an information gap.
- `optional`: useful when relevant, but not required for sufficiency unless the case depends on it.

If a required source cannot be searched, source coverage is not sufficient. The Evidence Pack must record why it was not searched and what decision risk remains.

## Software Or Tooling

| Level | Required sources | Optional sources |
| --- | --- | --- |
| L1 | General web; GitHub or primary open-source host | Package registries; official docs |
| L2 | General web; GitHub or primary open-source host; package registries; official docs; GitHub Issues or relevant developer community | Product directories; app stores; papers |
| L3 | L2 required sources; alternative code hosts; changelogs or releases; issue trackers; security or license sources | Patents; benchmark reports; maintainer discussions |

Coverage is sufficient when the required source classes were searched and the Evidence Pack either records the most relevant entities or explains why no strong entities were found.

Must supplement evidence when GitHub or the primary open-source host is unsearched, when license or maintenance status is needed for reuse, or when only blog posts support an implementation claim.

For current product capability questions at L2 or higher, official changelog, release notes, or current docs must be checked before older issues are used as current gap evidence. The Evidence Pack must record whether current UI or user-observed evidence was available and safe to use. If not, record it as an information gap rather than inferring current behavior from stale issue records.

## Product Or Competitor

| Level | Required sources | Optional sources |
| --- | --- | --- |
| L1 | General web; product homepage or product directory | AlternativeTo; Product Hunt; app stores |
| L2 | General web; product homepage; product directories; review or comparison sites; user communities | Pricing pages; changelogs; help docs |
| L3 | L2 required sources; official docs; reviews from multiple communities; comparison pages; market or procurement sources | Analyst reports; customer case studies; app-store reviews |

Coverage is sufficient when direct competitors, indirect substitutes, and at least one user-facing evidence source were checked.

Must supplement evidence when only vendor pages were searched, when no indirect substitutes were considered, or when reuse depends on pricing, terms, or integration that was not checked.

## Research Or Method

| Level | Required sources | Optional sources |
| --- | --- | --- |
| L1 | General web; Google Scholar, Semantic Scholar, OpenAlex, arXiv, or another relevant academic index | Review papers; library guides |
| L2 | Academic index; review or survey papers; highly cited or recent papers; reference chasing from one close paper | GitHub implementations; datasets; benchmark pages |
| L3 | L2 required sources; systematic or scoping reviews when available; citation chasing forward and backward; implementation or dataset sources | Standards; patents; expert commentary |

Coverage is sufficient when the Evidence Pack identifies close methods, their maturity, and whether they are operational, experimental, or only conceptual.

Must supplement evidence when no academic index was searched, when only abstracts were used for technical claims, or when a method's practical reuse depends on code or data that was not checked.

## Patent Or Invention

| Level | Required sources | Optional sources |
| --- | --- | --- |
| L1 | General web; Google Patents, USPTO, WIPO, Espacenet, or another patent database | Non-patent literature |
| L2 | Patent database; keyword variants; assignee or inventor search; classification search when obvious | Foreign patent databases; technical papers |
| L3 | L2 required sources; multiple patent databases; classification expansion; cited and citing patents; non-patent literature | Legal review; freedom-to-operate analysis |

Coverage is sufficient only as a prework signal, not as legal advice. The Evidence Pack must describe searched patent databases and whether non-patent literature was checked.

Must supplement evidence when no patent database was searched, when only exact-name terms were used, or when the case needs patentability, infringement, or freedom-to-operate conclusions.

## Vertical Business Process

| Level | Required sources | Optional sources |
| --- | --- | --- |
| L1 | General web; industry-specific web search; official or regulatory source if applicable | Vendor pages; practitioner forums |
| L2 | General web; industry-specific sources; official guidance or regulation; vendor or workflow products; practitioner communities | Academic papers; patents; internal examples provided by the user |
| L3 | L2 required sources; standards; regulations; mature vendor docs; workflow case studies; failure or complaint sources | Expert interviews; procurement documents; local operational manuals |

Coverage is sufficient when the Evidence Pack checks the domain's official constraints, existing workflow products or methods, and user pain or failure evidence.

Must supplement evidence when official or regulatory constraints are relevant but unsearched, when only generic tools were checked, or when the workflow depends on local practice not represented in the Evidence Pack.

## General Sufficiency Rules

Source coverage can be marked sufficient when:

- every required source class for the selected problem type and level is searched or explicitly justified as not applicable;
- query logs record source class, source name, query, result count, and kept entities;
- current product capability claims record a release or changelog check when relevant;
- key facts are linked to recorded sources in the Evidence Pack;
- negative evidence records describe where strong evidence was not found;
- remaining gaps are unlikely to change the primary judgment.

The Search Module must request or perform supplement search when:

- a required source class is unsearched;
- an entity has high relevance but weak `evidence_status`;
- a judgment-critical fact lacks a recorded supporting source or clear evidence status;
- negative evidence is based on too narrow a source set;
- source coverage does not match the declared search level;
- the Judgment Module returns `先补证据`.

## Negative Evidence Limit

Negative evidence never proves non-existence. It only means strong evidence was not found within the recorded source coverage.

Evidence Packs must state the covered source classes beside negative evidence so Judgment can avoid overreading it.
