# 02 Product Shell Extension

## Purpose
This file defines how the base shell extends when a page also uses product-level framing such as a Microsoft Power Apps out-of-box product header, sub-area tab structure, or product navigation context.

## Why this exists
Some pages use only the base shell. Other pages sit inside a product area and need an additional product header layer while still reusing the same base shell and canvas-family logic.

## Extension model
The product shell sits between the global shell and the canvas.

Layer order:
1. Host context
2. Global shell
3. Product shell extension, when enabled
4. Canvas family
5. Initiative-specific content

## Product shell source
For the current Altus product pattern, the product header is based on Microsoft Power Apps out-of-box behaviour.

## Supported modes
### Mode A: Base shell only
Use for pages that do not need a product header.

Example:
- PM landing page home screen

### Mode B: Base shell + product header
Use for pages that sit inside a product area, record area, or sub-function tab.

Example:
- Finance tab inside a portfolio/program context
- Project overview tab inside a project context

### Mode C: Home page variant
Use for landing-style screens that may include welcome/orientation behaviour while still reusing the same family category inside the canvas.

## Product-header anatomy
When product shell is enabled, treat the product header as a reusable shell layer made of standard regions.

### A. Record/context header
Use for:
- record title
- save state
- entity context
- current sub-area context

Example pattern:
- record title + save status
- entity name + current area

### B. Metadata summary strip
Use for quick context items such as:
- role owner
- active status
- portfolio
- program
- overflow/dropdown

These should be treated as reusable product-shell metadata items, even when the exact fields vary by entity.

### C. Lifecycle/stage strip
Use for stage/progress navigation where the entity supports it.

The stage strip may include:
- left status/state block
- stage markers
- current stage emphasis
- next/previous affordance

This area is entity-specific and should only appear when relevant.

### D. Tab list row
Use for product-level navigation tabs.

This row is part of the product shell when product-header mode is enabled.

### E. Contextual utility action
Example:
- Form assist

This is part of the product shell pattern when present in the Power Apps out-of-box experience.

## Dimensions
### Product header height
- Total product header height: 239px

Use this as the current baseline for the Power Apps out-of-box product header pattern.

If more exact sub-row heights are later confirmed, add them here and treat them as the source of truth.

## Product-header rules
When product header is present:
- it should feel part of the same shell system
- it should preserve Microsoft Power Apps out-of-box behaviour where that is the source pattern
- it should not replace page-level filters
- filters should live inside the page/canvas, not inside the product header
- it should not break family consistency
- it should help orientation and context, not become the primary work area
  
## Product-header token and accent rule
The product header should remain structurally part of the shell system, but it should not become a full branded surface by default.

Default token behavior:
- product-header background should remain neutral by default
- product header may inherit theme through accent usage rather than full background fill

Approved accent usage:
- selected tab indicator uses `product-tab-selected-indicator`
- current stage emphasis uses `product-stage-current-accent`
- stage icon/emphasis uses `product-stage-icon-accent`
- general product-header accent uses `product-header-accent`

Product-header areas must not define raw theme values directly.

## Landing vs product-level defaults
The same family category can appear in different placements.

### Landing-level placement
Default behaviour may include:
- welcome/orientation statement visible
- broader responsibility-level summary
- larger domain/state visibility by default
- more cross-scope context

### Product/sub-level placement
Default behaviour may include:
- narrower domain focus
- top statement/summary collapsed by default to keep focus
- more immediate operational control
- less orientation chrome and more task-specific density

## Example: overview family reuse
The same Operational Overview family can appear:
- on a landing page
- on a project overview tab
- inside a finance area under a product section

The structure remains consistent, while the default emphasis changes by placement, persona, and domain.

## Relationship to host variants
If the host changes, such as Teams, this file works with `08_host-shell-variants.md`.

Placement of Ask Altus may change by host, while the underlying family purpose remains consistent.
