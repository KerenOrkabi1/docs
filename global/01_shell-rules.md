# 01 Shell Rules

## Purpose
This file defines the base shell for Altus pages. The shell is the global layout frame of the screen.

## What the shell includes
The shell may include:
- top banner
- side navigation
- product header when enabled through product-shell extension rules
- persistent global framing behavior

The shell does not define the canvas family. The canvas family is defined separately.

## Base shell anatomy
### Top banner
- Height: 48px
- Width: full page width
- Default background: `shell-top-banner-bg`
- Default foreground/text: `shell-top-banner-text`
- Treated as fixed product chrome

### Left side navigation
- Located below the top banner
- Expanded width: 199px
- Collapsed width: 43px
- Height: full remaining height below the top banner
- Default background: `shell-nav-bg`
- Default foreground/text: `shell-nav-text`
- Treated as fixed product chrome

### Main page background
- Default canvas/page background: `page-canvas-bg`
  
## Shell token rule
Shell files must not define raw theme values.

Shell areas should reference global alias tokens defined by the active theme model.

Base shell token references:
- shell-top-banner-bg
- shell-top-banner-text
- shell-nav-bg
- shell-nav-text
- page-canvas-bg

## Shell behavior principles
- Preserve product chrome consistency.
- Keep navigation predictable.
- Use the remaining workspace efficiently.
- Avoid unnecessary empty space.
- Keep filters inside the page/canvas, not in the product header.
- Reuse the same shell behavior when the same shell elements are used.

## Shell modes
Base shell supports the following reusable modes:
1. Top banner + side navigation + canvas
2. Top banner + side navigation + product header + canvas
3. Landing-page variant using the same shell but different canvas defaults

## Scroll and stickiness
Default rules:
- top banner remains fixed
- side navigation remains fixed
- page-level filters stay in a predictable location inside the page
- AI docking and additional shell behavior may vary by family and host rules

## Responsive shell logic
The shell remains the same conceptual frame across breakpoints, but layout behavior may adapt.

Examples:
- side navigation may collapse
- product header may compress
- AI docking may change by host or family rules
- canvas family may use a different responsive layout pattern on mobile

## Filter placement rule
Filters belong inside the page/canvas area, not inside the product header.

This keeps:
- filtering behavior consistent across pages
- product header cleaner
- initiative logic inside the correct page context

## Relationship to other files
- Product-header variations are defined in `02_product-shell-extension.md`
- Host-specific changes are defined in `08_host-shell-variants.md`
- Canvas-family behavior is defined separately
