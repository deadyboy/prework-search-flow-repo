# Prework Search Process

This repository contains a standalone documentation snapshot of our **prework intelligence / search-flow design** project.

## What this project is doing

This project is a pre-work quality gate for agent tasks, especially for Vibe Coding style work:

- Decide whether a new request is worth starting from scratch.
- Search whether similar work already exists (methods, tools, products, frameworks, cases).
- Estimate effort and reuseability before implementation.
- Track evidence, assumptions, and confidence in a structured way.

## Core idea

The project does **pre-start assessment first**:

1. Parse request intent and expected outcome.
2. Judge whether search/reuse is valuable.
3. Execute a scoped search process (search plans + source routing).
4. Generate evidence pack + judgment report.
5. Output a clear start recommendation (direct do / adopt existing / adapt / defer).

## What is included

- `docs/prework-intelligence/` : methods, rules, case templates, scoring rules, strategy cards, and worked retrospectives.
- Case folders under `docs/prework-intelligence/cases/` showing trial records and judgment outputs.
- Retrospective and evaluation materials from the 15-case loop.

## Scope and boundaries

This repo is intentionally documentation-first.

- No runtime platform implementation.
- No desktop/web UI product packaging.
- Focus on searchable decision framework and reusable process artifacts.

## Notes

- Language: Chinese-first docs.
- This snapshot was built from the local development workspace and shared for review/sync.
