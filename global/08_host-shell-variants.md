# 08 Host Shell Variants

## Purpose
This file defines how the same product experience may adapt across different host environments without forcing unnecessary redesign of the canvas family.

## Host model
A host is the environment where Altus is experienced.

Examples:
- standard web/app shell
- Teams
- future embedded/partner hosts

## Rule
Host changes should not force a new family category unless the page purpose fundamentally changes.

In many cases:
- family purpose stays the same
- persona logic stays the same
- shell placement and AI docking change

## Standard app/web host
Typical behavior:
- base shell and product shell as defined in shell files
- overview family may use visible right AI panel
- Ask Altus appears inside that panel when visible

## Teams host variant
Teams may change:
- shell constraints
- available width
- docking of Ask Altus
- persistence of AI placement
- top-level frame behavior

In Teams, Ask Altus may become part of the shell while the overview-family canvas remains the same conceptual family.

## Mobile host/device note
Mobile may use a different layout variant of the same family.

That should be treated as:
- same family purpose
- different responsive/family variant pattern

## What belongs here
- host-specific shell adjustments
- AI placement by host
- persistent vs cue-based AI by host
- host-level layout constraints

## What does not belong here
- initiative-specific domain content
- persona detail
- reusable view definitions
