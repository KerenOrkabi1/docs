# PM Landing — Masterplan PRD

## Vision
I want to build PM Landing Page for the Project Manager (PM) role in Altus PPM.

## Product context / shell definition
This screen sits inside the existing Altus product shell and is the standalone home page a PM sees when entering the product. It is not part of Project Overview and not inside an individual project record.

Use the Altus shell definition explicitly:
- Preserve the top banner/header
- Preserve the left side navigation
- Do not include a project header on this page
- Design only the landing page content area inside that shell
- Follow Fluent UI 9 patterns and styling consistent with Altus
- Ensure the outcome feels like one branded product, not a separate AI tool or disconnected concept
- Apply the global files under `/docs/global` and persona files under `/docs/personas` as the source of truth for reusable behavior
- Use the Operational Overview family as the canvas family for this page

## Shell layout constraints
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
- Main canvas / landing page background
  - Background color: #f9f9f9
- Treat the top banner and side navigation as fixed product chrome
- Use the remaining workspace efficiently and avoid unnecessary whitespace
- Keep the layout dense enough to feel useful and operational, not sparse

## The Problem
Project Managers need a single operational landing page that helps them quickly understand what needs attention today across all projects they own. Today, attention is often fragmented across tasks, risks, issues, approvals, dependencies, changes, and meeting actions. PMs waste time navigating across modules, scanning multiple records, and figuring out what is truly urgent versus what can wait. This creates delayed follow-up, missed interventions, and slower decision-making.

This page should solve that by acting as a PM operational intervention surface. It is not an executive dashboard, not BI reporting, and not a simple personal to-do list. It should help PMs identify where they need to intervene, who they need to follow up with, and what lightweight actions they can take immediately to protect delivery.

## Who will use it
Primary persona:
- Project Manager (daily, multiple times per day) — quickly identify what requires attention today across all owned projects, triage the most important items, and take lightweight follow-up actions
- Project Manager / PM acting in planning and control mode (daily and weekly) — scan upcoming risk, monitor blocked items, and use AI guidance to prioritize interventions across multiple projects

Persona source of truth:
- `/docs/personas/pm.md`

## Core workflows
1. PM lands on home page → system shows welcome header, selected default bucket, and multi-project action items → PM immediately sees what needs intervention today
2. PM switches between card view and list view → same underlying data remains intact → PM chooses the presentation that best supports scanning and action
3. PM clicks a bucket such as “At Risk Soon” → system filters the page to show only items in that bucket → PM focuses on one urgency category at a time
4. PM filters or searches by project name, item name, item type, owner, priority, due timeframe, or state → system narrows visible items → PM identifies the right work faster
5. PM takes lightweight action on an item such as send nudge, mark reviewed, update status, resolve, or open full record → system updates item state and feedback on screen
6. PM reviews the always-visible AI panel → system provides contextual insight across all visible items, with AI maturity options for descriptive, diagnostic, predictive, and agentic guidance
7. PM uses “Ask Altus” for broader prompts beyond the landing page context → system opens a new UI state/screen for generated output when appropriate → PM can close it and return to the landing page

## Success criteria
- In under 30 seconds, a PM can identify the top priorities requiring intervention today across all owned projects
- The page supports multi-project operational triage, not just per-project review
- Card view and list view use the same logic and same data, only changing presentation
- Buckets are interactive and help PM focus by urgency category
- Needs Action Now is selected by default on first load
- PM can take lightweight actions directly from the landing page
- The AI panel adds value without changing the core page structure
- The screen uses available space well, avoids awkward empty whitespace, and feels efficient and intentional on desktop
- The experience is consistent with the Altus shell, the Operational Overview family, and Fluent UI 9 patterns
- Ask Altus can generate broader outputs in a separate screen/state without disrupting the landing page itself

## Information model / page purpose
This page captures any type of work a PM needs to focus on today across multiple owned projects. The PM should only see items from projects they own.

Relevant item types can include:
- Tasks
- Risks
- Issues
- Decisions
- Change requests
- Deliverables
- Dependencies
- Approvals / sign-offs
- Meeting actions
- Other relevant PM intervention items as needed

Each item must appear under the correct intervention bucket.

## Primary page structure
Design the landing page as a desktop-first experience inside the Altus shell using the Operational Overview family with three main regions:

1. Welcome and orientation area
Include:
- Welcome message with user name, for example: Welcome, John
- Today’s date
- Optional short supporting sentence such as: Here’s what needs your attention today
- Top statement / summary always visible on landing placement

2. Main operational work area
This is the core landing-page content and should support two switchable views of the same data:

### A. Card / board view
- Default presentation option
- Items appear under interactive intervention buckets
- Buckets are clickable and filter the visible items
- Cards should feel actionable, compact, and scannable
- Cards appear under the currently selected bucket
- On first load, Needs Action Now is selected by default

### B. List view
- Same underlying items and logic
- Denser presentation for faster scanning
- Better suited for users wanting a more operational/tabular review mode
- Must respect the currently selected bucket the same way as card view

3. Always-visible right AI panel
- Persistent on desktop
- Dedicated to interpreting the current landing-page content
- Includes Ask Altus
- Not the place for general-purpose chat unrelated to the page unless the user explicitly moves into broader Ask Altus work
- Includes AI maturity switching and contextual insights across visible items

## Intervention buckets
Use fixed buckets for version one:
1. Needs Action Now
2. At Risk Soon
3. Monitor
4. Waiting / Blocked

These buckets should represent PM intervention urgency, not generic status.

Interpretation:
- Needs Action Now can include overdue items, items due today, urgent blockers, stalled approvals, or anything needing action now to avoid trouble
- At Risk Soon includes items likely to become problematic soon if not addressed
- Monitor includes items worth watching but not yet requiring active intervention
- Waiting / Blocked includes items dependent on external input, decisions, or approvals

## Default page behavior
- On first load, Needs Action Now is selected by default
- The main content initially shows the items under Needs Action Now
- The other buckets remain visible and interactive
- Clicking another bucket updates the visible content to that bucket
- Card view and list view must both respect the currently selected bucket

## Item content requirements
Whether shown in card or list format, items should present a consistent minimum set of useful information. Show:
- Item type icon + label
- Item title
- Project name
- Owner
- Due date or review date
- Priority
- Urgency/state tag
- One-line impact statement
- Optional secondary signal such as blocker, stale update, dependency impact, missing actuals, or no recent progress

Examples of impact hints:
- Blocks milestone approval
- May slip finish date
- Waiting on sponsor decision
- Risk review overdue
- No progress logged for 7 days

## Actions from landing page
Prioritize lightweight actions first, with full record access as secondary.

Support actions such as:
- Send nudge / reminder
- Mark reviewed
- Update status
- Mark complete
- Resolve / close
- Reassign owner
- Add note / comment
- Escalate
- Open full record

These actions should feel fast and operational, helping the PM stay in flow without unnecessary navigation.

## Filters, search, and control
Include strong filtering and scanning support across both card and list views:
- Search by item name / keyword
- Filter by project name
- Filter by item type
- Filter by owner
- Filter by priority
- Filter by urgency / state
- Filter by due timeframe

Sorting:
- Baseline logic: urgency first, then due date, then stale age / operational priority
- AI-enhanced logic: predicted impact + urgency + recommended next action priority

## AI panel behavior
The right AI panel is always visible on desktop and is dedicated to helping the PM interpret what is already on screen.

It should:
- Be aware of the current visible items across all buckets
- Already hold the data and insight of the current items on screen
- Provide page-level summary and guidance
- React to selected items when relevant, but still remain useful when nothing is selected
- Support AI maturity switching inside the panel
- Suggest actions and highlight what matters most across current items
- Never silently change data

## AI maturity options inside the panel
1. Descriptive — what changed / what is happening
2. Diagnostic — why it is happening
3. Predictive — what is likely to happen next
4. Agentic — proposed actions and suggested next steps, always requiring user confirmation

The panel should help the PM across the whole landing page, not only for one selected item.

## Ask Altus
In addition to the contextual AI panel, include a separate Ask Altus entry point on the landing page.

This is for broader prompts, not just action-list interpretation. Examples:
- What are my top risks across all my projects due next week?
- Generate a report for Project X
- Summarize blocked approvals across my projects
- Show me likely schedule risks this month

Behavior:
- Ask Altus should not overwrite or mutate the landing page
- If the request is simple and related to the current screen, it may return a plain-language response
- If the request deserves a richer output, open a new UI state/screen/workspace on top of or beside the landing page
- Examples of richer outputs: generated report UI, summary workspace, draft artifact, structured result page
- The user must be able to save, close, or return back to the landing page

## UI style
- Use Fluent UI 9 explicitly
- Enterprise, calm, clean, and highly usable
- Clear typography hierarchy
- Subtle semantic color
- Accessible contrast
- Space-efficient layout with minimal dead space
- Smart use of density so the screen feels useful, not sparse
- Modern but restrained
- Strong consistency across baseline and AI-enhanced experiences
- Avoid decorative analytics; any visual cue should be functional

## Responsiveness
- Desktop-first
- Tablet supported
- On desktop, keep the right AI panel always visible
- On narrower widths or tablet-sized screens, the AI panel can collapse into a drawer or secondary panel
- Filters, bucket controls, summary elements, and card/list controls should adapt without becoming cluttered
- The layout should continue to feel efficient and usable, not sparse or broken
- List view may become the denser preferred mode on smaller widths
- Mobile remains part of the same family purpose but may use a different family layout variant

## Demo data expectations
Use realistic PPM multi-project demo data across several projects owned by the PM. Include believable examples spanning:
- overdue tasks
- risks due for review
- stalled approvals
- blocked dependencies
- pending decisions
- meeting follow-ups
- deliverables at risk
- change requests with delivery impact
- items that belong in each of the four buckets

## Final intent
Generate a PM Landing Page that feels like the operational home screen for delivery control in Altus. It should help a Project Manager understand what needs attention today across all owned projects, take quick action, switch between card and list views, use contextual AI guidance through the right panel, and access broader product AI through Ask Altus without losing the landing-page context.
