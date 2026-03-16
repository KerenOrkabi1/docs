# 03 Operational Overview Family

## Purpose
This file defines the reusable Operational Overview family category.

This family is used for persona-led operational home/overview screens that help users understand the current state, identify what needs attention, and act or drill down with AI assistance.

Examples of this family include:
- PM landing page
- Finance Operation overview for portfolio/program roles
- future overview-style operational pages

## Family definition
Operational Overview is a reusable canvas family with shared:
- layout logic
- behaviour
- view-switching support
- AI-panel behaviour
- Ask Altus presence when AI is visible
- action-first scanning model

The family purpose stays consistent even when:
- the persona changes
- the domain changes
- the placement changes
- the host changes
- the responsive layout changes

## Core family promise
The user should be able to quickly answer:
- what is the current state?
- what needs attention now?
- what is changing?
- what can I act on immediately?
- where do I need to drill deeper before acting?

## Family anatomy
### 1. Overview state region
A high-level summary area that helps the user understand current state at the relevant level.

Examples:
- PM landing page: intervention summary across owned projects
- Finance Operation: portfolio/program financial health, available funds, forecast risk

This region may be:
- visible by default on landing-level pages
- collapsible
- collapsed by default on narrower product/sub-level pages

### 2. Main operational work area
This is the primary work area of the family.

It should support:
- bucket/board style action grouping
- alternate list and/or table view when appropriate
- same underlying logic across views
- actionability when enough detail is visible
- drill-down when more context is required

### 3. Visible AI panel
When this family uses the visible AI layout pattern, the right AI panel should:
- stay persistently visible on supported screen sizes
- interpret the current page/canvas data
- support maturity switching
- include Ask Altus
- never silently change data

If another family or host does not use a visible AI panel, AI may appear through cue behaviour defined elsewhere.

## Family flow
The shared family flow is:
1. user lands on the page
2. user scans current state
3. user reviews buckets/items needing attention
4. user uses AI panel for interpretation, prioritisation, or recommendation
5. user changes view if needed
6. user drills into an item if more context is required
7. user takes action if enough detail is visible
8. user returns to the overview with updated state

Domain-specific workflow steps belong in initiative app-flow files.

## View support
This family is designed to support multiple reusable views.

Typical views:
- bucket/board view
- list view
- table view when appropriate

Rules:
- all views should reflect the same underlying data model
- changing view should change presentation, not meaning
- default view may vary by initiative and persona
- view definitions point to global reusable patterns in `07_view-patterns.md`

## Persona alignment
The same family should remain structurally stable while persona changes:
- emphasis
- KPI priority
- bucket meaning
- action permissions
- AI tone and recommendations
- drill-down depth

Persona logic is governed by:
- `04_persona-models.md`
- persona source files under `/docs/personas`

## Landing vs product-level defaults
### Landing-level overview
Typical defaults:
- top statement/summary always visible
- broader responsibility-level summary
- high-level state region visible by default
- broader cross-domain or cross-scope awareness
- visible AI panel with Ask Altus
- welcome/orientation allowed as part of the shell

### Product/sub-level overview
Typical defaults:
- same family structure and behaviour
- narrower scope
- top statement/summary collapsed by default to keep focus
- more specific domain summary
- more focus on immediate local decisions
- same visible AI panel with Ask Altus when this family uses the visible AI layout pattern

## Example family use
### PM landing page
- domain: operational intervention across owned projects
- state region: project/intervention summary
- buckets: action urgency
- AI: multi-project delivery interpretation

### Finance Operation overview
- domain: financial control and visibility
- state region: executive/financial summary
- buckets: financial action categories
- AI: financial insight and recommendation

## Responsive variants
The family purpose remains the same across devices, but layout may change.

### Desktop/tablet
Can use:
- visible right AI panel
- wider bucket or list/table layout
- larger summary region

### Mobile
May use a different family layout pattern while preserving the same family purpose.

Mobile may:
- collapse or reposition AI
- change component stacking
- use a different interaction pattern for summary and action buckets

A mobile-specific family variant may be documented under `/docs/families/operational-overview/mobile.md`.

## Ask Altus
When the visible AI pattern is present, Ask Altus is part of the AI panel.

Ask Altus is for broader prompts and should not overwrite the overview canvas.

## Relationship to reusable files
This family references:
- `05_ai-behavior.md`
- `06_visualization-rules.md`
- `07_view-patterns.md`
- persona files under `/docs/personas`

## Not in scope for this file
Do not place initiative-specific buckets, KPIs, or data fields here unless they are examples.
