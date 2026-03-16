# PM Landing — Tasks & Implementation Source of Truth

> This file is the single source of truth for planning, sequencing, and tracking the PM Landing initiative.
> It records selected global building blocks, gap analysis, new reusable elements to be created, and the full task sequence.
> Update status fields as work progresses.

---

## A. Initiative Summary

| Field | Value |
|---|---|
| Initiative | PM Landing |
| Product area | Landing page — the home screen a Project Manager sees on entering Altus PPM |
| Page purpose | Operational intervention surface for daily delivery triage across all PM-owned projects. Helps the PM see what needs attention now, take lightweight actions, and use AI guidance — without navigating across modules |
| Primary persona | Project Manager |
| Persona scope model | PM sees only items from projects they own. No scope toggle needed — ownership is implicit |
| Shell type | Base shell only — no product header |
| Canvas family | Operational Overview — landing placement |
| Default bucket | Needs Action Now |
| Summary default state | Always visible (landing placement rule) |
| View default | Board / card view |
| Host | Standard app / web |
| Design system | Fluent UI 9 |

### What this page is
A PM operational intervention surface. Not an executive dashboard. Not BI reporting. Not a simple to-do list.
It helps Project Managers identify where to intervene, who to follow up with, and what lightweight actions to take — all from a single landing screen, across all owned projects.

### How it differs from Finance Operation
| Dimension | PM Landing | Finance Operation |
|---|---|---|
| Shell | Base shell only (no product header) | Base shell + product header (239px) |
| Summary default | Always visible | Collapsed by default |
| Views | Board + List | Board + List + Table |
| Buckets | 4 (delivery-domain) | 5 (finance-domain) |
| Personas | Project Manager (1, ownership-scoped) | Portfolio Manager + Program Manager (2, role-scoped) |
| Item domain | Delivery work items (tasks, risks, issues, approvals, decisions, dependencies, etc.) | Finance objects and funding actions |
| Actions | Lightweight delivery actions (nudge, mark reviewed, update status, resolve, reassign) | Financial decisions (approve, partially approve, reject, release, escalate) |
| Welcome region | Yes — name, date, orientation statement | No |

---

## B. Selected Global Building Blocks

These are the reusable system elements selected for this initiative. All are locked to their source files. If a source file changes, this initiative inherits the update.

### Shell
| Element | Source file | Usage in this initiative |
|---|---|---|
| Base shell | `/docs/global/01_shell-rules.md` | Top banner 48px #616161, left nav 199px/43px #f0f0f0, canvas #f9f9f9. No product header on this page |

### Canvas family
| Element | Source file | Usage in this initiative |
|---|---|---|
| Operational Overview family | `/docs/global/03_operational-overview-family.md` | Landing placement: summary always visible, welcome/orientation allowed, AI panel persistent, broader summary visible by default |
| Operational Overview desktop variant | `/docs/families/operational-overview/desktop.md` | Desktop-first layout; AI panel always visible on desktop |

### Persona source files
| Element | Source file | Usage in this initiative |
|---|---|---|
| Project Manager | `/docs/personas/pm.md` | Delivery-domain items, project-level scope, action-now intervention focus, lightweight action permissions |

### AI behavior
| Element | Source file | Usage in this initiative |
|---|---|---|
| Global AI behavior | `/docs/global/05_ai-behavior.md` | AI panel persistent, Ask Altus inside panel, maturity levels: Descriptive → Diagnostic → Predictive → Agentic, human confirmation required for all proposed actions |

### View patterns
| Element | Source file | Usage in this initiative |
|---|---|---|
| Board / bucket view | `/docs/views/board.md` → specified in Task 3.1 | Default view. PM delivery buckets as interactive columns |
| List view | `/docs/views/list.md` → specified in Task 3.2 | Compact row presentation of same delivery items |

### Reusable components
| Element | Source file | Usage in this initiative |
|---|---|---|
| Executive summary state | `/docs/components/executive-summary-state.md` → specified in Task 2.1 | Delivery summary block — always visible at landing placement |
| Bucket pattern | `/docs/components/bucket-pattern.md` → specified in Task 2.2 | 4-bucket delivery layout: Needs Action Now, At Risk Soon, Monitor, Waiting / Blocked |
| Card pattern | `/docs/components/card-pattern.md` → specified in Task 2.3 | Delivery item card with PM-domain field set (item type, project, owner, due date, priority, urgency tag, impact hint) |
| AI panel | `/docs/components/ai-panel.md` → specified in Task 2.4 | Right panel, always visible on desktop, delivery-context aware, maturity switcher, Ask Altus inside |
| Ask Altus | `/docs/components/ask-altus.md` → specified in Task 2.5 | Conversational AI entry point inside the AI panel |

### Visualization rules
| Element | Source file |
|---|---|
| Visualization rules | `/docs/global/06_visualization-rules.md` |

### Design system
| Element | Source file |
|---|---|
| Design system | `/docs/global/00_design-system.md` |

---

## C. Gap Analysis

### What exists and can be reused (structure only — content is stubs)
All global rule files (00–08) are fully specified and can be inherited directly. No changes needed to any global file for this initiative.

The Project Manager persona file is structurally complete and usable as source of truth. Wording is marked placeholder but the structure, responsibilities, decisions, and overview-family behavior sections are sufficient to build against.

The Operational Overview family definition in `global/03` is fully specified and covers the landing placement rules this initiative needs (summary always visible, welcome/orientation allowed, persistent AI panel).

### What exists as stubs and must be specified before build

| File | Current state | Action required |
|---|---|---|
| `/docs/components/executive-summary-state.md` | Stub | Specify: always-visible state at landing placement, delivery KPI slots, expand/collapse optional — Task 2.1 |
| `/docs/components/bucket-pattern.md` | Stub | Specify: variable bucket count, bucket header, item count badge, selected state, empty state — Task 2.2 |
| `/docs/components/card-pattern.md` | Stub | Specify: base card structure + PM delivery-domain field set tailoring — Task 2.3 |
| `/docs/components/ai-panel.md` | Stub | Specify: panel layout, maturity switcher, insight region, Ask Altus zone, loading/error states — Task 2.4 |
| `/docs/components/ask-altus.md` | Stub | Specify: input entry, response modes (inline vs generated output), return-to-page behaviour — Task 2.5 |
| `/docs/views/board.md` | Stub | Specify: bucket column layout, card rendering, bucket interaction, empty/loading states — Task 3.1 |
| `/docs/views/list.md` | Stub | Specify: row layout, field set, inline actions, sort, density — Task 3.2 |
| `/docs/families/operational-overview/desktop.md` | Stub | Specify: desktop layout regions, column proportions, AI panel width, canvas split — Task 1.3 |

### What does not exist yet and must be created new

| Element | Type | Location | Notes |
|---|---|---|---|
| PM delivery item data model | New | `/docs/initiatives/pm-landing/data-model.md` | Defines delivery objects: tasks, risks, issues, decisions, change requests, deliverables, dependencies, approvals, meeting actions. Includes item type, project, owner, due date, priority, urgency, impact signal |
| PM bucket membership logic | New | `/docs/initiatives/pm-landing/data-model.md` | Which items go in which of the 4 buckets and why |
| PM delivery card field spec | New (tailoring of card-pattern) | Recorded in `/docs/components/card-pattern.md` as delivery domain variant | Delivery-domain field set differs from Finance Operation finance-domain field set |
| PM filter model | New | `/docs/initiatives/pm-landing/data-model.md` | Item name/keyword, project name, item type, owner, priority, urgency/state, due timeframe |
| PM AI panel context spec | New | `/docs/initiatives/pm-landing/data-model.md` | Delivery-specific AI context: overdue signals, risk triggers, stale items, blockers, PM-specific prompt examples |
| Demo data set | New | `/docs/initiatives/pm-landing/data-model.md` | Multi-project PM-owned items, all 4 buckets populated, realistic delivery signals |

---

## D. New Reusable Elements

The following elements do not currently exist in a specified form. They will be created during this initiative and written into the correct reusable global location. Future initiatives inherit them from those locations.

> Note: If Finance Operation tasks.md has already been worked through first, components D1–D5 and the desktop variant may already be specified. In that case, this initiative inherits those specifications and only needs to add its domain-specific tailoring (delivery bucket variant, delivery card field set, delivery AI context). Check each component file before re-specifying.

### D1 — Executive Summary State component
**Location:** `/docs/components/executive-summary-state.md`
**Created in:** Task 2.1
**What it defines:**
- Always-visible state at landing placement: full summary block visible on load
- Delivery KPI slots: items needing action today (count), at-risk items (count), blocked items (count), projects with overdue work (count)
- Optional expand for additional breakdown (not collapsed by default at landing)
- Placement rule: always visible at landing-level; collapsed by default at product-level (Finance Operation)
- Component is domain-agnostic; KPI slot content is initiative-specific configuration

**Reuse note:** Finance Operation uses this same component in collapsed-by-default mode. Both inherit the same component; placement context controls default state.

### D2 — Bucket Pattern component
**Location:** `/docs/components/bucket-pattern.md`
**Created in:** Task 2.2
**What it defines:**
- Variable bucket count: supports 4 (PM Landing) or 5 (Finance Operation) or more
- Bucket header: label + item count badge
- Selected / unselected state: one bucket active at a time, highlighted
- Empty bucket state: message, no broken layout
- Bucket click: updates visible item area to show only that bucket's items
- Named variant: `pm-buckets` — 4 buckets: Needs Action Now, At Risk Soon, Monitor, Waiting / Blocked; default selected: Needs Action Now

**Reuse note:** Finance Operation uses the same bucket-pattern base with a `finance-buckets` variant (5 buckets). Both inherit the same base pattern.

### D3 — Card Pattern component (base + PM delivery domain variant)
**Location:** `/docs/components/card-pattern.md`
**Created in:** Task 2.3
**What it defines:**
- Base card structure: type icon + label, title, parent context, primary signals (up to 4), impact hint, action menu trigger
- PM delivery domain variant fields: item type icon + label, item title, project name, owner, due date, priority, urgency/state tag, one-line impact hint, optional secondary signal (blocker, stale update, dependency impact, missing actuals, no recent progress)
- Card action menu for PM: send nudge, mark reviewed, update status, mark complete, resolve/close, reassign owner, add note/comment, escalate, open full record
- States: default, hover, selected, loading, success feedback, error feedback

**Reuse note:** Finance Operation uses the card-pattern base with a finance domain variant (different field set and action menu). Both inherit the same base structure.

### D4 — AI Panel component
**Location:** `/docs/components/ai-panel.md`
**Created in:** Task 2.4
**What it defines:**
- Panel position: right side of canvas, fixed width on desktop (approx 320px, exact token TBD in build)
- Always visible on desktop; collapses to drawer on tablet/narrow widths
- Regions: page context summary (top), insight body (scrollable), maturity switcher (inline toggle), Ask Altus zone (bottom, persistent)
- Maturity switcher: Descriptive / Diagnostic / Predictive / Agentic
- Insight body: aware of currently visible items and selected bucket; updates when bucket or view changes
- Proposed actions shown as chips or buttons; require user confirmation before execution
- Loading state, error state, empty state

**Reuse note:** Same component structure used in Finance Operation. Context feed is initiative-specific (delivery items vs finance items) but panel structure is identical.

### D5 — Ask Altus component
**Location:** `/docs/components/ask-altus.md`
**Created in:** Task 2.5
**What it defines:**
- Entry point: text input at the bottom of the AI panel, always accessible
- Inline response mode: short answers rendered inside the AI panel
- Generated output mode: richer responses open in a temporary workspace overlaid or adjacent to the page
- Generated output workspace: save, close, and return-to-page controls; does not replace the underlying page
- Ask Altus does not mutate page data or records
- PM-specific prompt examples: "What are my top risks across all my projects due next week?", "Generate a report for Project X", "Summarize blocked approvals across my projects", "Show me likely schedule risks this month"

**Reuse note:** Same component structure used in Finance Operation. Prompt examples and context feed are initiative-specific; the component is reusable.

### D6 — Operational Overview Desktop variant specification
**Location:** `/docs/families/operational-overview/desktop.md`
**Created in:** Task 1.3
**What it defines:**
- Layout regions and proportions for desktop
- Left-to-right: shell left nav | main canvas area | AI panel
- Canvas area at landing placement: welcome/orientation strip (top) + summary block (always visible) + bucket/view controls + item area
- AI panel: fixed right, always visible, does not collapse on desktop
- Approximate column split: main canvas ~75%, AI panel ~25% (exact px TBD in build)
- No product header on landing placement pages
- Responsive breakpoint: AI panel collapses to drawer below tablet width

**Reuse note:** Finance Operation uses this same desktop variant with the product header active above the canvas. Both inherit the same layout proportions below the header.

---

## E. Implementation Order

The sequence below must be followed. Later tasks depend on earlier ones. Do not begin build tasks until specification tasks for that area are complete.

> If Finance Operation has already been built and components in Phase 2 are already specified, skip directly to the domain tailoring steps noted in each task rather than re-specifying the full component.

### Phase 1 — Foundation (shell and family layout)

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 1.1 | Confirm base shell tokens | Reuse | — | `/docs/global/01_shell-rules.md` (read-only reference) | ✅ Ready |
| 1.2 | Confirm no product header on this page (landing placement) | Reuse | 1.1 | `/docs/global/02_product-shell-extension.md` (read-only reference — mode: base shell only) | ✅ Ready |
| 1.3 | Specify Operational Overview desktop variant | New/Tailor | 1.1, 1.2 | `/docs/families/operational-overview/desktop.md` | ⬜ Not started |
| 1.4 | Scaffold page layout in code (shell + welcome region + canvas + AI panel placeholder) | New | 1.1, 1.2, 1.3 | Initiative build | ⬜ Not started |

### Phase 2 — Reusable component specification

These tasks write the reusable pattern into the correct global location. Complete before build work on those components begins.

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 2.1 | Specify executive-summary-state component (always-visible landing mode + delivery KPI slots) | New | 1.3 | `/docs/components/executive-summary-state.md` | ⬜ Not started |
| 2.2 | Specify bucket-pattern component (base + pm-buckets variant, 4 buckets, Needs Action Now default) | New | 1.3 | `/docs/components/bucket-pattern.md` | ⬜ Not started |
| 2.3 | Specify card-pattern component (base + PM delivery domain variant field set and action menu) | New | 2.2 | `/docs/components/card-pattern.md` | ⬜ Not started |
| 2.4 | Specify AI panel component (layout, maturity switcher, insight body, Ask Altus zone) | New | 1.3 | `/docs/components/ai-panel.md` | ⬜ Not started |
| 2.5 | Specify Ask Altus component (inline + generated output modes, return-to-page behaviour) | New | 2.4 | `/docs/components/ask-altus.md` | ⬜ Not started |

### Phase 3 — View pattern specification

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 3.1 | Specify board / bucket view pattern (bucket columns, card rendering, interaction, states) | New | 2.2, 2.3 | `/docs/views/board.md` | ⬜ Not started |
| 3.2 | Specify list view pattern (row layout, delivery field set, inline actions, sort, density) | New | 2.3 | `/docs/views/list.md` | ⬜ Not started |

### Phase 4 — Initiative-specific definition

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 4.1 | Define PM delivery item data model (item types, fields, ownership logic) | New | — | `/docs/initiatives/pm-landing/data-model.md` | ⬜ Not started |
| 4.2 | Define PM bucket membership logic (which items go in which bucket and why) | New | 4.1, 2.2 | `/docs/initiatives/pm-landing/data-model.md` | ⬜ Not started |
| 4.3 | Define PM filter model (item name, project, item type, owner, priority, urgency, due timeframe) | New | 4.1 | `/docs/initiatives/pm-landing/data-model.md` | ⬜ Not started |
| 4.4 | Define PM AI panel context spec (delivery signals, overdue triggers, PM-specific prompt examples) | New | 2.4, 2.5, 4.1 | `/docs/initiatives/pm-landing/data-model.md` | ⬜ Not started |
| 4.5 | Define demo data set (multi-project PM-owned items, all 4 buckets populated, realistic delivery signals) | New | 4.1, 4.2 | `/docs/initiatives/pm-landing/data-model.md` | ⬜ Not started |

### Phase 5 — Build

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 5.1 | Build shell scaffold (base shell only, no product header, welcome region) | Build | 1.4 | Initiative build | ⬜ Not started |
| 5.2 | Build welcome and orientation region (name, date, supporting statement) | Build | 5.1 | Initiative build | ⬜ Not started |
| 5.3 | Build executive summary state component (always-visible, delivery KPIs) | Build | 2.1, 5.1 | Initiative build | ⬜ Not started |
| 5.4 | Build bucket bar and bucket-pattern (4 PM buckets, Needs Action Now default) | Build | 2.2, 4.2, 5.1 | Initiative build | ⬜ Not started |
| 5.5 | Build PM delivery data model and demo data | Build | 4.1–4.5 | Initiative build | ⬜ Not started |
| 5.6 | Build board view with PM delivery item cards | Build | 2.3, 3.1, 5.4, 5.5 | Initiative build | ⬜ Not started |
| 5.7 | Build list view | Build | 3.2, 5.5 | Initiative build | ⬜ Not started |
| 5.8 | Build view toggle control (board / list) | Build | 5.6, 5.7 | Initiative build | ⬜ Not started |
| 5.9 | Build filter and search controls | Build | 4.3, 5.6 | Initiative build | ⬜ Not started |
| 5.10 | Build item action model (nudge, mark reviewed, update status, resolve, reassign, add note, escalate, open record) | Build | 4.1, 5.6 | Initiative build | ⬜ Not started |
| 5.11 | Build AI panel (persistent right, maturity switcher, delivery context feed) | Build | 2.4, 4.4, 5.1 | Initiative build | ⬜ Not started |
| 5.12 | Build Ask Altus (inline + generated output workspace) | Build | 2.5, 5.11 | Initiative build | ⬜ Not started |

### Phase 6 — States, responsiveness, and consistency review

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 6.1 | Implement all page states (loading, empty bucket, empty filter, error, success feedback) | Build | 5.1–5.12 | Initiative build | ⬜ Not started |
| 6.2 | Implement responsive behaviour (tablet: AI panel to drawer, layout adapt) | Build | 5.1–5.12 | Initiative build | ⬜ Not started |
| 6.3 | Consistency review against global rules (design system, shell rules, AI behavior, visualization rules) | Review | 6.1, 6.2 | — | ⬜ Not started |
| 6.4 | Cross-initiative consistency check against Finance Operation patterns | Review | 6.3 | — | ⬜ Not started |
| 6.5 | Final sign-off and tasks.md status update | Review | 6.3, 6.4 | This file | ⬜ Not started |

---

## F. Task Status Key

| Symbol | Meaning |
|---|---|
| ✅ Ready | Source exists, no action needed — can be referenced directly |
| 🔲 Spec needed | File exists as stub — must be specified before build |
| ⬜ Not started | Task not yet begun |
| 🔄 In progress | Task actively being worked |
| ✅ Done | Task complete and output in place |
| ⚠️ Blocked | Task cannot proceed — dependency not met |

---

## G. Cross-Initiative Reuse Register

This register tracks which elements specified for this initiative are also available to Finance Operation and any future initiative.

| Element | Location | Available to |
|---|---|---|
| Executive summary state | `/docs/components/executive-summary-state.md` | PM Landing, Finance Operation, all future overview-family pages |
| Bucket pattern (base) | `/docs/components/bucket-pattern.md` | PM Landing (pm-buckets variant), Finance Operation (finance-buckets variant), future |
| Card pattern (base) | `/docs/components/card-pattern.md` | PM Landing (delivery variant), Finance Operation (finance variant), future |
| AI panel | `/docs/components/ai-panel.md` | PM Landing, Finance Operation, all future overview-family pages |
| Ask Altus | `/docs/components/ask-altus.md` | PM Landing, Finance Operation, all future overview-family pages |
| Board view pattern | `/docs/views/board.md` | PM Landing, Finance Operation, future |
| List view pattern | `/docs/views/list.md` | PM Landing, Finance Operation, future |
| Operational Overview desktop variant | `/docs/families/operational-overview/desktop.md` | PM Landing, Finance Operation, all future overview-family desktop pages |

---

## H. Decisions Recorded

| Decision | Value | Rationale |
|---|---|---|
| Shell type | Base shell only, no product header | PM Landing is a home/landing page, not a product-level page. Inherits from global/03 landing placement rules |
| Summary default state | Always visible | Inherits landing placement rule from global/03 |
| Default selected bucket | Needs Action Now | Specified in masterplan — matches most urgent daily intervention intent |
| Views | Board + List only (no table) | Table view is not needed for delivery triage at this granularity. Finance Operation introduces table as net-new |
| Scope model | PM sees only items from projects they own | Ownership-implicit scope; no manual toggle needed |
| Welcome region | Included | Landing placement allows welcome/orientation per global/03 and masterplan requirement |
| Demo data | Multi-project, all 4 buckets, realistic delivery signals | Masterplan requirement |
