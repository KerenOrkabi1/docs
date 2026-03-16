# 07 View Patterns

## Purpose
This file defines reusable global view patterns and how pages/families should reference them.

## Why this is separate
The same family category may support multiple views. Those views should be reusable, versionable, and centrally improved.

## Core view patterns
### Board / bucket view
Use when the user benefits from grouped operational scanning by category or urgency.

Best for:
- action grouping
- intervention buckets
- decision categories
- operational overview pages

### List view
Use when the user benefits from denser scanning while keeping row-level narrative clarity.

Best for:
- operational scanning
- moderate-density review
- users who prefer structured reading over cards

### Table view
Use when the user needs high-density review, more fields, or deeper comparison.

Best for:
- power-user analysis
- detailed operational review
- follow-up work after overview-level triage

## View-switching rules
- switching view should not change underlying meaning
- switching view should preserve the same item set and filters
- changing view changes presentation, not logic
- default view may vary by persona and initiative

## Pattern versioning
Each reusable view should point to a current approved global pattern.

If a view is redesigned and accepted:
- the global pattern reference updates
- screens using that view inherit the latest approved pattern

## Relationship to families
Families such as Operational Overview should link to these patterns rather than redefining them.

## Theme reference rule
Reusable views must not define local theme values.

Board, list, and table patterns should reference:
- global semantic tokens
- approved global alias tokens
- theme-governed reusable pattern tokens

Examples:
- table header should use a global table/header token
- selected row should use a global selected-state token
- focus should use a global focus token
- board/list emphasis should use globally governed accent tokens

## Suggested companion files
- `/docs/views/board.md`
- `/docs/views/list.md`
- `/docs/views/table.md`
