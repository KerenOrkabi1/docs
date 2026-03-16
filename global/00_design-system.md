# 00 Design System

## Purpose
This file is the product-wide visual and interaction foundation for Altus. It defines the reusable theme, tokens, system principles, and component-alignment rules that should stay consistent across all initiatives, page families, shells, and hosts.

This is the single place to change the active theme and core visual language for the product.

## Scope
This file governs:
- theme and token foundations
- typography
- spacing
- color semantics
- Fluent UI 9 baseline usage
- Bryntum alignment rules
- reusable component styling principles
- enterprise interaction tone
- accessibility baselines

This file does not define:
- shell anatomy
- family-specific canvas layout
- persona-specific behavior
- initiative-specific workflows

## Product design intent
Altus should feel:
- professional
- operational
- calm under pressure
- enterprise-grade and trustworthy
- action-focused rather than report-focused
- dense enough to be useful, but not cluttered
- cohesive as one product, not a collection of disconnected tools

The product should avoid a decorative BI-dashboard feel. Visual emphasis should come from:
- strong structure
- clear hierarchy
- semantic state cues
- compact but readable components
- intentional whitespace
- meaningful icons and trend indicators

## Design principles
1. Clarity over decoration.
2. Consistency over one-off styling.
3. Operational usefulness over visual novelty.
4. Reusable patterns over bespoke screens.
5. Human control over opaque automation.
6. Responsive by design, not as an afterthought.
7. Accessibility is a baseline requirement.

## Theme model
The active product theme must be defined centrally and cascade everywhere.

Theme should include:
- background surfaces
- text colors
- semantic status colors
- focus and selection colors
- border and divider colors
- emphasis and accent colors
- chart and visualization palette rules
- density/tone options where needed

### Theme rule
Any future theme change should be made here first, then inherited across:
- shells
- canvas families
- views
- reusable components
- AI panel surfaces
- Bryntum-aligned components

## Theme architecture
All real theme values must be owned globally.

Theme values may live:
- directly in this file
- or in named theme files under `/docs/theme/`

Other files must not define raw theme values.
Other files may only reference:
- semantic tokens
- alias tokens

## Theme registry
Altus supports named brand themes.

Initial theme files:
- `/docs/theme/altus-blue.md`
- `/docs/theme/altus-emerald.md`

Each theme file should define:
- theme display name
- theme key
- core semantic token values
- alias token mappings where approved

## Active theme rule
One named theme should be treated as the active product theme at a time.

Changing the active theme should update:
- shell tokens
- product-header accent tokens
- reusable interaction tokens
- reusable view/pattern tokens
- AI surface tokens where relevant
- Bryntum-aligned theme references where relevant

## Alias token model
Semantic tokens define core color meaning.
Alias tokens define where those values are used.

Example semantic tokens:
- color-primary
- color-focus
- background-app
- background-nav
- background-shell-top
- text-primary
- text-on-primary
- border-subtle
- color-selected

Example alias tokens:
- shell-top-banner-bg
- shell-nav-bg
- page-canvas-bg
- product-header-accent
- product-tab-selected-indicator
- product-stage-current-accent
- product-stage-icon-accent
- interactive-focus-ring
- interactive-selected-bg
- table-header-bg
- table-row-hover-bg
- table-row-selected-bg
- table-focus-ring

## Brand-theme behavior rule
Altus uses brand themes rather than full surface-theme changes by default.

Default expectations:
- color-primary may change by theme
- color-focus may change by theme
- product-header accent usage may change by theme
- top banner may either inherit from the active brand theme or use its own theme-approved color
- side navigation should remain neutral by default
- canvas/page background should remain neutral by default

## Future view/component rule
If a new area is added later, such as a table, board, list, panel, or reusable component:
- it must reference global semantic or alias tokens
- it must not define its own raw theme values
- it may introduce a new alias token only if the alias remains globally governed

## Design system baseline
### Primary base system
Fluent UI 9 is the core design-system baseline for Altus.

Use Fluent UI 9 for:
- general component foundations
- tokens and spacing logic where suitable
- enterprise interaction consistency
- accessibility-aligned defaults
- Microsoft-aligned overall look and feel

### Extended capability layer
Bryntum v7 components may be used selectively for advanced operational patterns such as scheduling, planning, or richer data-heavy views.

Bryntum components must:
- align to the active Altus theme
- align to Altus typography
- align to Altus spacing and density rules
- align to Altus interaction tone
- feel like part of the same product

Bryntum adds capability, not a separate visual language.

## Typography
Use one primary product font family unless there is a strong system reason not to.

Typography should provide a clear hierarchy for:
- page titles
- section headings
- component headings
- body text
- metadata and helper text
- AI summaries and supporting notes

Typography rules:
- keep hierarchy obvious
- prioritize readability
- avoid oversized headline treatment
- maintain consistent line heights
- maintain consistent weight usage
- use emphasis sparingly and intentionally

## Spacing
Use a consistent spacing scale.

Recommended base scale:
- 4
- 8
- 12
- 16
- 24
- 32
- 48

Spacing should support:
- scanability
- grouping
- visual rhythm
- operational density without crowding

## Color semantics
Define semantic tokens rather than one-off colors.

Minimum semantic groups:
- background
- foreground
- primary
- secondary
- accent
- muted
- success
- warning
- danger
- info
- selected
- disabled
- focus

Status color should be meaningful but restrained.

## Component styling principles
Reusable components should feel:
- compact
- scannable
- dependable
- visually related to each other
- compatible with both overview and detailed work families

Component styling rules:
- use consistent corner radius decisions
- keep shadows subtle
- avoid decorative gradients unless part of the theme system
- favor semantic emphasis over heavy visual chrome
- maintain parity between equivalent list/card/table states

## Pattern versioning principle
Reusable patterns such as tables, lists, boards, and AI panels should reference a global pattern definition.

If a reusable pattern is improved and accepted:
- the global reference updates
- every screen pointing to that global pattern inherits the latest approved version

## Responsive principle
Desktop is the primary operational workspace, but responsive behavior must be designed intentionally.

The same family purpose may remain consistent across devices while layout patterns adapt by size and host.

## Accessibility baseline
Minimum expectations:
- keyboard access
- visible focus
- semantic headings
- readable contrast
- screen-reader-aware labeling
- no color-only meaning
- clear target sizes where interaction is required

## Governance
Change this file when updating:
- theme
- typography
- product-wide visual tone
- component styling baseline
- Fluent/Bryntum alignment rules

Do not place initiative-specific content here.
