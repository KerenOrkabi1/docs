# Finance Operation — Masterplan PRD

## Vision
I want to build Finance Operation for the Portfolio Manager and Program Manager roles in Altus PPM.

## Product context / shell definition
This screen sits inside the existing Altus product shell and uses the Microsoft Power Apps OOB product header.

Use the Altus shell definition explicitly:
- Preserve the top banner/header
- Preserve the left side navigation
- Include the product header on this page
- Treat the page as a product-level Finance area under a menu/tab structure
- Design the Finance Operation canvas inside that shell and product header
- Follow Fluent UI 9 patterns and styling consistent with Altus
- Ensure the outcome feels like one branded product, not a separate AI tool or disconnected concept
- Apply the global files under `/docs/global` and persona files under `/docs/personas` as the source of truth for reusable behavior
- Use the Operational Overview family as the canvas family for this page

## Shell layout constraints
### Base shell
- Top banner/header
  - Height: 48px
  - Width: full screen
  - Background color: #616161
- Left side navigation
  - Sits below the top banner
  - Expanded width: 199px
  - Collapsed width: 43px
  - Height: full remaining screen below the top banner
  - Background color: #f0f0f0
- Main canvas background
  - Background color: #f9f9f9

### Product header
- Based on Microsoft Power Apps OOB product header
- Total height: 239px
- Includes product-level title/context, metadata summary, lifecycle/state strip where relevant, tab list, and contextual utility actions
- Product shell details can be refined later without changing the Overview family itself

## The Problem
Portfolio Managers and Program Managers need a single operational place to understand, control, and act on portfolio and program financial health across the full lifecycle of work. In practice, they need to manage both top-down allocation of approved funds and in-flight funding control when forecasts shift, change requests arise, or additional money is needed. Today, the meaning of budget is inconsistent, visibility is fragmented, approvals are hard to assess quickly, and real-world funding paths vary across organizations. As a result, decision-making is slower, transparency is weaker, manual admin increases, and teams struggle to know where the money is now, where it is heading, and what action should happen next.

This page should solve that by acting as a finance operations center. It is not only a static budget report and not only a request inbox. It should help Portfolio Managers and Program Managers monitor financial health, understand available and committed funds, assess forecast risk, and confidently control approvals and funding actions across different organizational maturity levels.

## Who will use it
Primary personas:
- Portfolio Manager — monitor portfolio-level finance status, remaining envelope, allocation balance, strategic funding confidence, and escalation needs
- Program Manager — monitor program-level budget health, project drift, funding requests, approvals, and intervention priorities

Secondary behavior note:
- Project Manager may view finance at project level and request funding, but does not approve portfolio/program finance decisions here

Persona source of truth:
- `/docs/personas/portfolio-manager.md`
- `/docs/personas/program-manager.md`

## Core workflows
1. User lands on Finance Operation under the Finance product area → system shows finance summary, selected action bucket or view, and visible AI panel
2. User scans portfolio/program financial health, available funds, budget vs actual vs forecast, and overspend signals
3. User reviews items needing attention now such as pending approvals, forecast drift, low contingency, or funding requests
4. User switches between bucket/board view, list view, and table view using the same underlying data
5. User drills into a specific financial area or request when more detail is required before taking action
6. User reviews AI insight in the right panel for prioritization, anomaly detection, explanation, and next-step guidance
7. User uses Ask Altus for broader finance prompts, scenario questions, and generated outputs
8. User approves, partially approves, rejects, escalates, or defers action when enough information is available and the role allows it

## Success criteria
- In under 30 seconds, a Portfolio Manager or Program Manager can understand current financial health and what needs attention
- The page clearly separates approved budget, actuals, forecast, remaining envelope, and pending requests
- Reusable Overview-family structure stays consistent with PM Landing while finance content changes appropriately
- Users can move from summary to decision with enough supporting context
- The AI panel adds prioritization and explanation value without changing the page structure
- Landing-level placement supports broader summary by default; product/sub-level placement collapses summary by default for focus
- The screen feels operational, not like a passive finance report
- The experience is consistent with the Altus shell, Power Apps OOB product header, Operational Overview family, and Fluent UI 9 patterns

## Information model / page purpose
This page captures financial operation across portfolio and program levels and supports monitoring, control, and action.

Relevant finance objects and signals can include:
- Portfolio budget / envelope
- Program budget / envelope
- Disbursement / released funds
- Remaining available funds
- Approved budget
- Actuals
- Forecast / EAC
- Variance / drift
- Contingency / reserve
- Pending funding requests
- Pending approvals
- Partial approvals
- Rejected or revised requests
- Fiscal timing
- Cost categories where relevant
- Exceptions and escalations

## Primary page structure
Design the Finance Operation page as a desktop-first experience inside the Altus shell and product shell using the Operational Overview family with three main regions:

1. Context and summary area
Include:
- Finance page context inside the product header
- Top statement / summary collapsed by default at product-level placement
- High-level finance summary visualisation state component for the current level
- Optional visible summary expansion when needed

2. Main finance operational work area
This is the core canvas and should support multiple views of the same data:

### A. Bucket / board view
- Operational finance buckets grouped by what needs attention
- Visual first, scannable, decision-oriented
- Good for role-based intervention focus

### B. List view
- Same underlying data and same logic
- Useful for compact scanning and operational review

### C. Table view
- Same underlying data and same logic
- Best when the user needs more detail before acting
- Can be reused in deeper sub-areas or future families as needed

3. Always-visible right AI panel
- Persistent on desktop
- Dedicated to interpreting the current Finance Operation page content
- Includes Ask Altus
- Provides finance-specific AI maturity support from descriptive to agentic, always human-controlled

## Finance operation buckets
Use finance-centered action buckets for version one:
1. Needs Financial Decision
2. Overspend Risk
3. Ready to Release
4. Monitor
5. Waiting / Blocked

Interpretation:
- Needs Financial Decision includes pending approvals, partial approvals, and requests requiring decision
- Overspend Risk includes forecast drift, low contingency, variance pressure, or high-risk spend patterns
- Ready to Release includes approved next-step funding or disbursement actions ready for controlled release
- Monitor includes areas worth watching but not yet requiring intervention
- Waiting / Blocked includes items dependent on external decision, supporting evidence, or another governance step

## Default page behavior
- Landing-level overview can show broader summary by default when used as a role landing page
- Product-level finance placement collapses the top statement / summary by default so the user can focus on buckets and action
- The selected bucket or default view should be clear on first load
- Multiple views must respect the same underlying logic and same data

## Item content requirements
Whether shown in board, list, or table format, finance items should present a consistent minimum set of useful information. Show:
- Level / object type (portfolio, program, request, project finance item)
- Title or identifier
- Parent portfolio/program where relevant
- Budget / approved amount
- Actuals
- Forecast / EAC
- Variance or drift signal
- Remaining funds / contingency where relevant
- Fiscal timing or due/review date
- One-line impact statement
- Optional secondary signal such as stale forecast, missing actuals, cross-level impact, or blocked approval

Examples of impact hints:
- Forecast exceeds approved budget by 8%
- Remaining reserve below threshold
- Pending approval blocks next release
- No updated forecast this period
- Delay may shift spend into next fiscal quarter

## Actions from Finance Operation
Actions depend on role and detail visibility.

Support actions such as:
- Approve
- Partially approve
- Reject
- Request more information
- Escalate
- Reallocate recommendation
- Release next amount
- Mark reviewed
- Add note / comment
- Open detailed finance area or full record

These actions should feel controlled and transparent. When visible information is insufficient, the user should drill down before acting.

## Filters, search, and control
Include strong filtering and scanning support across views:
- Search by portfolio, program, project, or request name
- Filter by level
- Filter by status / action state
- Filter by risk / urgency
- Filter by fiscal period
- Filter by funding state
- Filter by owner / approver
- Filter by category where relevant

Sorting:
- Baseline logic: urgency + financial impact + due/review timing
- AI-enhanced logic: predicted impact + urgency + recommended next action priority

## AI panel behavior
The right AI panel is always visible on desktop and is dedicated to helping the user interpret what is already on screen.

It should:
- Be aware of current visible finance items and summaries
- Explain what changed and why it matters
- Highlight what needs decision first
- Support maturity switching
- Suggest next best actions and plan-B options
- Never silently change financial data
- Keep human control for any proposed action

## AI maturity options inside the panel
1. Descriptive — what changed / what is happening
2. Diagnostic — why it is happening
3. Predictive — what is likely to happen next
4. Agentic — proposed actions and suggested next steps, always requiring user confirmation

## Ask Altus
In addition to the contextual AI panel, include a separate Ask Altus capability inside the visible AI panel.

Examples:
- What finance areas need my decision today?
- Show likely overspend hotspots this quarter
- Summarize pending funding requests across my program
- Simulate what happens if we defer release to next month
- Compare current forecast against available envelope

Behavior:
- Ask Altus should not overwrite or mutate the page
- If the request is simple and related to the current screen, it may return a plain-language response
- If the request deserves a richer output, open a new UI state/screen/workspace on top of or beside the page
- The user must be able to save, close, or return back to the Finance Operation page

## UI style
- Use Fluent UI 9 explicitly
- Enterprise, calm, clean, and highly usable
- Strong visual hierarchy for summary vs action
- Subtle semantic color
- Accessible contrast
- Space-efficient layout with minimal dead space
- Smart use of density so the screen feels useful, not sparse
- Avoid decorative charts; visualisation should support decisions and status understanding
- Keep reusable visual and view patterns aligned with global rules

## Responsiveness
- Desktop-first
- Tablet supported
- On desktop, keep the right AI panel always visible
- On narrower widths or tablet-sized screens, the AI panel can collapse into a drawer or secondary panel
- Mobile remains part of the same family purpose but may use a different family layout variant
- Product shell and overview family should adapt without losing clarity of finance status and actions

## Demo data expectations
Use realistic finance demo data across portfolio and program levels. Include believable examples spanning:
- over-budget forecasts
- pending funding requests
- partially approved requests
- low contingency items
- blocked releases
- fiscal timing shifts
- stale forecasts
- items that belong in each finance bucket

## Final intent
Generate a Finance Operation page that feels like the financial operations center for Portfolio Managers and Program Managers in Altus. It should help users understand current financial health, see where money is now and where it is heading, focus on the right decisions, use contextual AI guidance through the right panel, and access broader product AI through Ask Altus without losing the page context.
