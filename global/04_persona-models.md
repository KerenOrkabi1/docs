# 04 Persona Models

## Purpose
This file defines the global persona framework for Altus and references the source-of-truth persona files stored under `/docs/personas`.

The goal is to keep persona logic reusable and role-driven without duplicating persona content inside initiative files.

## Source-of-truth model
Persona detail files live separately and are the editable source of truth.

Current persona files:
- `/docs/personas/pm.md`
- `/docs/personas/program-manager.md`
- `/docs/personas/portfolio-manager.md`

If a persona changes, update the persona file. This framework file continues to reference the latest version.

## Why persona models are global
Persona definitions should influence:
- default emphasis on overview pages
- bucket meaning
- KPI priority
- AI insight style
- drill-down depth
- action permissions
- detail tolerance
- success language

The shell and family can stay stable while persona behavior changes.

## Persona template
Every persona file should use the same structure:
1. role summary
2. responsibilities
3. objectives
4. pain points
5. emotional context
6. decisions they make
7. data they need to see
8. default action focus
9. KPI emphasis
10. AI support needs
11. permissions and action scope
12. impact on Operational Overview family behavior

## Persona-driven behavior rules
When persona changes, the following may change:
- which summary is most visible
- which buckets are shown first
- what the user can do directly from overview
- how much detail appears before drill-down
- how AI explains state and priority
- which KPIs are promoted to primary

The following should not change only because persona changes:
- base shell behavior
- theme
- core family structure
- product-wide AI maturity definitions

## Initial personas in scope
Version 1 global personas:
- Project Manager
- Program Manager
- Portfolio Manager

## Initiative usage
Every initiative using the Operational Overview family should:
1. reference the relevant persona file(s)
2. derive initiative-specific buckets from persona needs and domain purpose
3. derive KPIs from persona goals and decision responsibilities
4. derive AI support style from persona context

## Future extension
If new personas are added, they should be added as separate persona files rather than expanding this file into a narrative repository.
