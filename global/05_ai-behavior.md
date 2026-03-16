# 05 AI Behavior

## Purpose
This file defines global AI behavior for Altus across shells, families, and initiatives.

It governs consistency of AI maturity, human control, Ask Altus behavior, and AI placement patterns.

## AI principles
1. AI should feel integrated, not bolted on.
2. AI should help interpretation, prioritization, and guidance.
3. AI must preserve user control.
4. AI should never silently change underlying data.
5. AI capability is global even when placement changes by family or host.

## Maturity model
Use the same maturity model across the product.

### 1. Descriptive
What is happening or what changed.

### 2. Diagnostic
Why it is happening.

### 3. Predictive
What is likely to happen next.

### 4. Agentic
What the system recommends doing next, always with user confirmation and visible control.

## Ask Altus
Ask Altus is the broader conversational AI capability for the product.

Rules:
- Ask Altus should be available wherever the chosen family/host supports visible AI access
- Ask Altus should not silently mutate the current page
- richer outputs may open new workspaces, overlays, or generated states
- the user must be able to return to the original page context

## AI placement patterns
### Pattern A: visible AI panel
Used by overview-family screens on supported desktop/tablet layouts.

### Pattern B: AI cue
Used where AI is not persistently visible. Cue placement may be top-right, bottom-right, or another approved shell location.

AI placement is governed by family and host rules.

## Context behavior
AI should understand:
- current page context
- current visible items
- active filters/views when appropriate
- selected item when relevant
- persona expectations where configured

## Human-in-control rules
- AI recommends; user decides.
- AI may draft or prepare actions, but user confirms.
- AI must make reasoning legible enough for trust.
- AI outputs should be contextual and safe.

## Persona alignment
AI should adapt tone and emphasis by persona.

Examples:
- PM: delivery control, variance, follow-up, request status
- Program Manager: dependencies, approvals, trade-offs, forecast risk
- Portfolio Manager: funding, investment value, balance, aggregate risk

## Relationship to other files
- Family-level AI usage is referenced in `03_operational-overview-family.md`
- Host-specific placement is referenced in `08_host-shell-variants.md`
- Persona influence is referenced in `04_persona-models.md`
