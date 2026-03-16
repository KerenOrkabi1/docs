# 06 Visualization Rules

## Purpose
This file defines the reusable visual logic for how information is presented across Altus.

It covers visual presentation principles and reusable state/summary patterns, not the full design system.

## Visualization principles
1. Show what helps action.
2. Use summary first, detail on demand.
3. Avoid decorative charts without operational value.
4. Keep visual meaning consistent across domains.
5. Reuse global visual components wherever possible.

## Core visual patterns
### State / executive summary components
Reusable components that communicate the current state of a domain or scope.

They may show:
- current health
- trend
- risk signal
- envelope or capacity state
- summary KPIs

Examples:
- delivery state
- financial state
- strategy/value state

### Risk and urgency cues
Use restrained but clear semantic cues for:
- risk
- urgency
- blocked state
- drift
- trend direction

### Summary-to-detail logic
The visual hierarchy should usually move from:
1. state summary
2. action grouping or item list
3. detail/drill-down

## Component consistency
Reusable visual components such as summary blocks, tables, and boards should have a global reference and visual version.

If a global component changes and is accepted, downstream pages should inherit the approved update.

## What belongs here
- visual hierarchy rules
- semantic state treatment
- card/list/table visual conventions
- chart usage principles
- summary-state component expectations
- density rules for visual components

## What does not belong here
- exact shell dimensions
- persona definitions
- initiative-specific KPI sets
- family-specific workflow logic

## Finance-friendly note
This file should also support domains such as Finance Operation, where visuals may need to represent:
- budget vs actual vs forecast
- remaining envelope
- disbursement state
- approvals needing attention

The exact domain content lives in initiative files, but the visual rules remain reusable.
