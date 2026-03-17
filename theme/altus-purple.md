# Theme — Altus Purple

## Purpose
Named brand theme for Altus.

This file owns theme values only.
Other files should consume semantic or alias tokens and should not hard-code raw theme values.

## Theme identity
- Theme display name: `Altus Purple`
- Theme key: `altus-purple`

## Core semantic tokens
### Brand and interaction
- color-primary: `#8b5cf6`
- color-primary-hover: `#7c3aed`
- color-primary-subtle: `#f5f3ff`
- color-focus: `#8b5cf6`
- color-info: `#8b5cf6`

### Neutral surfaces
- background-app: `#f9f9f9`
- background-surface-1: `#ffffff`
- background-surface-2: `#f5f7fa`
- background-nav: `#f0f0f0`
- background-shell-top: `#616161`

### Text
- text-primary: `#1a1a1a`
- text-secondary: `#5f6b7a`
- text-on-primary: `#ffffff`

### Borders and dividers
- border-subtle: `#d8dde6`
- border-strong: `#b8c2cf`

### State and semantic colors
- color-success: `#2e7d32`
- color-warning: `#b26a00`
- color-danger: `#c62828`
- color-selected: `#ede9fe`
- color-disabled: `#a0a0a0`

## Alias tokens
### Shell
- shell-top-banner-bg: `background-shell-top`
- shell-top-banner-text: `text-on-primary`
- shell-nav-bg: `background-nav`
- shell-nav-text: `text-primary`
- page-canvas-bg: `background-app`

### Product-header accent usage
- product-header-accent: `color-primary`
- product-tab-selected-indicator: `color-primary`
- product-stage-current-accent: `color-primary`
- product-stage-icon-accent: `color-primary`

### Interaction
- interactive-focus-ring: `color-focus`
- interactive-selected-bg: `color-selected`
- primary-action-bg: `color-primary`
- primary-action-text: `text-on-primary`

## Theme behavior rules
- Side navigation remains neutral by default.
- Canvas background remains neutral by default.
- Product header uses brand as accent, not as a full-surface background.
- Top banner may stay independent from primary brand color.
