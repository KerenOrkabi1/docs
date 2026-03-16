# Finance Operation — App Flow PRD

## Flow relationship to the global system
This initiative inherits from:
- `/docs/global/01_shell-rules.md`
- `/docs/global/02_product-shell-extension.md`
- `/docs/global/03_operational-overview-family.md`
- `/docs/global/05_ai-behavior.md`
- `/docs/global/07_view-patterns.md`
- `/docs/personas/portfolio-manager.md`
- `/docs/personas/program-manager.md`

This file only describes Finance Operation-specific workflow and state details.

## Primary user journey
1. User opens the Finance area under the product shell.
2. Product header provides page context.
3. Summary is collapsed by default at product level.
4. User scans finance health, remaining funds, actuals, forecast, and action buckets.
5. User switches between bucket/board, list, and table views depending on the depth needed.
6. User reviews AI insight and prioritization in the right panel.
7. If enough detail is visible, the user takes an action directly.
8. If more detail is needed, the user drills into the relevant finance area or full record.
9. User optionally uses Ask Altus for broader finance questions or generated outputs.

## Page structure
### Page required
- Finance page inside the base Altus shell and product shell
- Overview-family canvas
- Always-visible AI panel on desktop

### Navigation
- User reaches this page through the Finance product area
- Product tab/header context remains clear
- Ask Altus may open a temporary adjacent or overlaid workspace without replacing the Finance Operation page permanently

## View modes
### Overview-family views
- Bucket / board view
- List view
- Table view

All views use the same underlying logic and data.

## States to handle
- Loading state for finance summary, views, and AI insight
- Empty state when no items exist in the selected bucket or current scope
- Empty state when filters return no results
- Error state for approval/release actions or AI insight retrieval
- Success state for direct actions such as approve, partially approve, mark reviewed, or request more information
- Ask Altus generated output state

## Finance-specific bucket behavior
### Needs Financial Decision
Pending approvals, requests, or review actions needing a decision.

### Overspend Risk
Forecast drift, low contingency, or variance pressure that may require intervention.

### Ready to Release
Controlled next-step funding or disbursement actions ready for release.

### Monitor
Items worth watching but not yet requiring action.

### Waiting / Blocked
Items dependent on another approval, evidence, or governance step.

## Finance-specific drill-down logic
- If enough detail is visible, the user can act directly from the page.
- If the risk or impact is too high, the user drills deeper first.
- Deeper finance areas may later use another family or more data-heavy pattern while remaining consistent with global shell and view rules.
- Returning from deeper areas should preserve the Finance Operation context where possible.

## AI-specific flow
- AI panel interprets current visible finance items and summaries.
- Ask Altus supports broader finance and scenario questions.
- Agentic suggestions always require human confirmation.
- AI never silently changes budget, forecast, or approvals.
