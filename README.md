# Altus Docs Source of Truth

This `/docs` structure is the reusable source of truth for Altus product design and initiative delivery.

## Core idea
- `global/` holds reusable product rules and patterns.
- `personas/` holds role-specific source-of-truth persona files.
- `families/` holds reusable canvas families and their variants.
- `views/` holds reusable view-pattern definitions.
- `components/` holds reusable component-pattern definitions.
- `shells/` holds reusable shell variants and host-specific shell rules.
- `initiatives/` holds initiative-specific files that inherit from the global source of truth.

## Reuse model
1. Start with `global/00_design-system.md`.
2. Apply shell rules from `global/01_shell-rules.md` and `global/02_product-shell-extension.md`.
3. Choose the correct family category such as `global/03_operational-overview-family.md`.
4. Use `global/04_persona-models.md` plus the relevant persona file under `/personas`.
5. Reference global AI, visualization, and view rules.
6. Create or update the initiative files under `/initiatives`.

## Glossary
- **Page** = screen.
- **Shell** = the global layout frame of the screen.
- **Canvas** = the main purposeful area of the page.
- **Family category** = a reusable canvas pattern with shared layout and behavior.
- **Persona alignment** = the way the same family changes emphasis, KPIs, AI insight, and action access by role and level.
