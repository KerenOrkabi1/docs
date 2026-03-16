# PM Landing — App Flow PRD

## Flow relationship to the global system
This initiative inherits from:
- `/docs/global/01_shell-rules.md`
- `/docs/global/03_operational-overview-family.md`
- `/docs/global/05_ai-behavior.md`
- `/docs/global/07_view-patterns.md`
- `/docs/personas/pm.md`

This file only describes PM Landing-specific workflow and state details.

## Primary user journey
1. PM opens Altus and lands on the PM Landing page inside the Altus shell.
2. The page shows the welcome statement, top summary, selected default bucket, and visible AI panel.
3. Needs Action Now is selected by default.
4. PM scans the bucket content in board/card view or switches to list view.
5. PM filters or searches to narrow work.
6. PM reviews AI insight and prioritization in the right panel.
7. PM takes a lightweight action directly from the page or drills into the full record.
8. PM optionally uses Ask Altus for broader output, then returns to the landing page.

## Page structure
### Page required
- PM Landing page inside the base Altus shell
- No product header on this page
- Overview-family canvas
- Always-visible AI panel on desktop

### Navigation
- PM reaches this page as the landing/home destination
- Current page is always clear in the shell
- Ask Altus may open a temporary adjacent or overlaid workspace without replacing the landing page permanently

## View modes
### Default view
- Board/card view
- Needs Action Now selected by default

### Alternate view
- List view using the same data and same bucket logic

## States to handle
- Loading state for page, filters, and AI insight
- Empty state when no items exist in the selected bucket
- Empty state when filters return no results
- Error state for item actions or AI insight retrieval
- Success state for lightweight actions such as mark reviewed or send nudge
- Ask Altus generated output state

## PM-specific bucket behavior
### Needs Action Now
Overdue, urgent, blocking, or immediate follow-up items.

### At Risk Soon
Items likely to become urgent soon if not addressed.

### Monitor
Items worth watching but not requiring direct action yet.

### Waiting / Blocked
Items dependent on others, approvals, or external input.

## PM-specific drill-down logic
- If enough detail is visible, the PM acts directly from the landing page.
- If more detail is needed, the PM opens the full record.
- Returning from the full record should preserve the landing-page context where possible.

## AI-specific flow
- AI panel interprets current visible landing-page items.
- Ask Altus supports broader PM questions and richer generated outputs.
- AI never silently changes records.
- Agentic suggestions always require user confirmation.
