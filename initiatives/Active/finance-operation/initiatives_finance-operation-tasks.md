# Finance Operation — Tasks & Implementation Source of Truth

> This file is the single source of truth for planning, sequencing, and tracking the Finance Operation initiative.
> It records selected global building blocks, gap analysis, new reusable elements to be created, and the full task sequence.
> Update status fields as work progresses.

---

## A. Initiative Summary

| Field | Value |
|---|---|
| Initiative | Finance Operation |
| Product area | Finance — product-level page under Altus PPM |
| Page purpose | Financial operations center for monitoring portfolio/program financial health, controlling approvals and funding actions, and acting on finance signals across the full lifecycle |
| Primary personas | Portfolio Manager, Program Manager |
| Secondary persona | Project Manager (view + request only; no approval authority on this page) |
| Persona scope model | Role-determined: Portfolio Manager sees portfolio-level scope; Program Manager sees program-level scope. Scope is set automatically by role, not by manual filter selection |
| Shell type | Base shell + product shell (Power Apps OOB product header included) |
| Canvas family | Operational Overview — product/sub-level placement |
| Default bucket | Needs Financial Decision |
| Summary default state | Collapsed on load (product-level placement rule) |
| View default | Bucket / board view |
| Host | Standard app / web |
| Design system | Fluent UI 9 |

### What this page is
A finance operations center. Not a passive budget report. Not a request inbox only.
It helps Portfolio Managers and Program Managers understand where money is now, where it is heading, what decisions are pending, and what actions to take — all in one operational surface with AI guidance alongside.

### How it differs from PM Landing
| Dimension | PM Landing | Finance Operation |
|---|---|---|
| Shell | Base shell only (no product header) | Base shell + product header (239px) |
| Summary default | Always visible | Collapsed by default |
| Views | Board + List | Board + List + Table |
| Buckets | 4 (PM delivery-domain) | 5 (finance-domain) |
| Personas | Project Manager (1) | Portfolio Manager + Program Manager (2, role-scoped) |
| Item domain | Delivery work items | Finance objects and funding actions |
| Actions | Lightweight delivery actions | Financial decisions: approve, partially approve, reject, release, escalate |

---

## B. Selected Global Building Blocks

These are the reusable system elements selected for this initiative. All are locked to their source files. If a source file changes, this initiative inherits the update.

### Shell
| Element | Source file | Usage in this initiative |
|---|---|---|
| Base shell | `/docs/global/01_shell-rules.md` | Top banner 48px #616161, left nav 199px/43px #f0f0f0, canvas #f9f9f9 |
| Product shell extension | `/docs/global/02_product-shell-extension.md` | Product header 239px, Power Apps OOB, includes context header, metadata strip, lifecycle strip, tab list, utility actions |

### Canvas family
| Element | Source file | Usage in this initiative |
|---|---|---|
| Operational Overview family | `/docs/global/03_operational-overview-family.md` | Product/sub-level placement: summary collapsed, buckets visible, AI panel persistent |
| Operational Overview desktop variant | `/docs/families/operational-overview/desktop.md` | Desktop-first layout; AI panel always visible on desktop |

### Persona source files
| Element | Source file | Usage in this initiative |
|---|---|---|
| Portfolio Manager | `/docs/personas/portfolio-manager.md` | Portfolio-level scope, strategic finance signals, escalation and governance decisions |
| Program Manager | `/docs/personas/program-manager.md` | Program-level scope, budget drift, funding request and approval decisions |

### AI behavior
| Element | Source file | Usage in this initiative |
|---|---|---|
| Global AI behavior | `/docs/global/05_ai-behavior.md` | AI panel persistent, Ask Altus inside panel, maturity levels: Descriptive → Diagnostic → Predictive → Agentic, human confirmation required for all proposed actions |

### View patterns
| Element | Source file | Usage in this initiative |
|---|---|---|
| Board / bucket view | `/docs/views/board.md` → defined in Task 3.1 | Default view. Finance buckets as interactive columns |
| List view | `/docs/views/list.md` → defined in Task 3.2 | Compact row presentation of same finance items |
| Table view | `/docs/views/table.md` → defined in Task 3.3 | Detail-dense tabular view, net-new for this initiative |

### Reusable components
| Element | Source file | Usage in this initiative |
|---|---|---|
| Executive summary state | `/docs/components/executive-summary-state.md` → defined in Task 2.1 | Finance health summary block — collapsed by default, expandable |
| Bucket pattern | `/docs/components/bucket-pattern.md` → defined in Task 2.2 | 5-bucket finance layout: Needs Financial Decision, Overspend Risk, Ready to Release, Monitor, Waiting / Blocked |
| Card pattern | `/docs/components/card-pattern.md` → defined in Task 2.3 | Finance item card with finance-domain field set (budget, actuals, forecast, variance, fiscal timing, impact hint) |
| AI panel | `/docs/components/ai-panel.md` → defined in Task 2.4 | Right panel, always visible desktop, finance-context aware, maturity switcher, Ask Altus inside |
| Ask Altus | `/docs/components/ask-altus.md` → defined in Task 2.5 | Conversational AI entry point inside the AI panel |
| Table pattern | `/docs/components/table-pattern.md` → defined in Task 3.3 | Reusable table pattern used by table view; net-new |

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

Both persona files are structurally complete and usable as source of truth. Wording is marked placeholder but the structure, responsibilities, decisions, and overview-family behavior sections are sufficient to build against.

The Operational Overview family definition in `global/03` is fully specified and covers the product-level placement rules this initiative needs (collapsed summary, bucket focus, persistent AI panel).

### What exists as stubs and must be specified before build

Every component and view file in `/docs/components/` and `/docs/views/` is currently a one-line placeholder. These must be specified as part of this initiative before any build work begins. Specification is written back into the reusable location — not into the initiative folder — so PM Landing and future initiatives inherit the same patterns.

| File | Current state | Action required |
|---|---|---|
| `/docs/components/executive-summary-state.md` | Stub | Specify: collapsed state, expanded state, finance KPI slots, trigger behaviour — Task 2.1 |
| `/docs/components/bucket-pattern.md` | Stub | Specify: variable bucket count (4 or 5), bucket header, item count badge, selected state, empty state — Task 2.2 |
| `/docs/components/card-pattern.md` | Stub | Specify: base card structure + finance-domain field set tailoring — Task 2.3 |
| `/docs/components/ai-panel.md` | Stub | Specify: panel layout, maturity switcher, insight region, Ask Altus zone, loading/error states — Task 2.4 |
| `/docs/components/ask-altus.md` | Stub | Specify: input entry, response modes (inline vs generated output), return-to-page behaviour — Task 2.5 |
| `/docs/components/table-pattern.md` | Stub | Specify: column structure, sort, density, action column — Task 3.3 |
| `/docs/views/board.md` | Stub | Specify: bucket column layout, card rendering, bucket interaction, empty/loading states — Task 3.1 |
| `/docs/views/list.md` | Stub | Specify: row layout, field set, inline actions, sort, density — Task 3.2 |
| `/docs/views/table.md` | Stub | Specify: full column model, finance field columns, sort, filter integration — Task 3.3 |
| `/docs/families/operational-overview/desktop.md` | Stub | Specify: desktop layout regions, column proportions, AI panel width, canvas split — Task 1.3 |

### What does not exist yet and must be created new

| Element | Type | Location | Notes |
|---|---|---|---|
| Finance item data model | New | `/docs/initiatives/finance-operation/data-model.md` | Defines finance objects: budget, actuals, forecast/EAC, variance, remaining funds, reserve, requests, approvals, fiscal timing, level (portfolio/program), action state |
| Finance card field spec | New (tailoring of card-pattern) | Recorded in `/docs/components/card-pattern.md` as a domain variant | Finance-domain field set differs from PM Landing delivery-domain field set |
| Finance bucket definitions | New (tailoring of bucket-pattern) | Recorded in `/docs/components/bucket-pattern.md` as a named variant | 5 finance buckets with specific membership logic |
| Role-scope model | New | `/docs/initiatives/finance-operation/tasks.md` (this file, Section E) + initiative app-flow | Portfolio Manager → portfolio scope auto-set; Program Manager → program scope auto-set |
| Finance AI panel prompts / context spec | New | `/docs/initiatives/finance-operation/tasks.md` notes | Finance-specific AI context: budget vs actuals, drift signals, pending approvals, forecast risk |
| Filter model for Finance Operation | New | Initiative-specific, recorded in implementation file | Finance-specific filters: level, status, risk, fiscal period, funding state, owner, category |

---

## D. New Reusable Elements

The following elements do not currently exist in a specified form. They will be created during this initiative and written into the correct reusable global location. Future initiatives inherit them from those locations.

### D1 — Executive Summary State component
**Location:** `/docs/components/executive-summary-state.md`
**Created in:** Task 2.1
**What it defines:**
- Collapsed state: single-row summary bar showing top 3–4 finance KPI signals (e.g. total approved budget, actuals to date, forecast variance %, pending decisions count)
- Expanded state: full summary block with additional breakdown, trend indicators, and health signals
- Expand / collapse trigger: user-controlled, chevron or label, persists within session
- Placement rule: collapsed by default at product-level; always visible at landing-level
- Finance KPI slots are an initiative-specific configuration of this component; the component itself is domain-agnostic

**Reuse note:** PM Landing will use this component in always-expanded mode. Finance Operation uses it in collapsed-by-default mode. Both inherit the same component; placement context controls default state.

### D2 — Bucket Pattern component
**Location:** `/docs/components/bucket-pattern.md`
**Created in:** Task 2.2
**What it defines:**
- Variable bucket count: supports 4 (PM Landing) or 5 (Finance Operation) or more
- Bucket header: label + item count badge
- Selected / unselected state: one bucket active at a time, highlighted
- Empty bucket state: message, no broken layout
- Bucket click: updates visible item area to show only that bucket's items
- Named variant: `finance-buckets` — 5 buckets: Needs Financial Decision, Overspend Risk, Ready to Release, Monitor, Waiting / Blocked; default selected: Needs Financial Decision

**Reuse note:** PM Landing uses the same bucket-pattern component with a different named variant (`pm-buckets`, 4 buckets). Both inherit the same base pattern.

### D3 — Card Pattern component (base + finance domain variant)
**Location:** `/docs/components/card-pattern.md`
**Created in:** Task 2.3
**What it defines:**
- Base card structure: type icon + label, title, parent context, primary signals (up to 4), impact hint, action menu trigger
- PM Landing domain variant fields: item type, project name, owner, due date, priority, urgency tag, impact hint, optional secondary signal
- Finance domain variant fields: level/object type, title/identifier, parent portfolio or program, approved budget, actuals, forecast/EAC, variance or drift signal, remaining funds/reserve, fiscal timing or review date, impact hint, optional secondary signal (stale forecast, blocked approval, cross-level impact)
- Card action menu: context-sensitive by role and domain
- States: default, hover, selected, loading, success feedback, error feedback

**Reuse note:** Both initiatives use the card-pattern base. Domain variant is selected per initiative. Field sets are initiative-specific configurations, not separate components.

### D4 — AI Panel component
**Location:** `/docs/components/ai-panel.md`
**Created in:** Task 2.4
**What it defines:**
- Panel position: right side of canvas, fixed width on desktop (approx 320px, exact token TBD in build)
- Always visible on desktop; collapses to drawer on tablet/narrow widths
- Regions: page context summary (top), insight body (scrollable), maturity switcher (inline toggle), Ask Altus zone (bottom, persistent)
- Maturity switcher: Descriptive / Diagnostic / Predictive / Agentic — changes the tone and depth of AI insight shown
- Insight body: aware of currently visible items and selected bucket; updates when bucket or view changes
- Proposed actions: shown as chips or buttons; require user confirmation before execution
- Loading state, error state, empty state (no items visible)
- Ask Altus zone: see D5

**Reuse note:** Same component used in PM Landing and Finance Operation. Context feed is initiative-specific (delivery items vs finance items) but panel structure, maturity switcher, and Ask Altus zone are identical.

### D5 — Ask Altus component
**Location:** `/docs/components/ask-altus.md`
**Created in:** Task 2.5
**What it defines:**
- Entry point: text input at the bottom of the AI panel, always accessible
- Inline response mode: short answers rendered inside the AI panel without leaving the page
- Generated output mode: richer responses (reports, summaries, simulations) open in a temporary workspace overlaid or adjacent to the current page
- Generated output workspace: has save, close, and return-to-page controls; does not replace the underlying page
- Ask Altus does not mutate page data or records
- Finance-specific prompt examples (recorded in initiative): "What finance areas need my decision today?", "Show likely overspend hotspots this quarter", "Summarize pending funding requests across my program", "Simulate what happens if we defer release to next month"

**Reuse note:** Same component structure used across both initiatives and any future overview-family page. Prompt examples and context feed are initiative-specific; the component itself is reusable.

### D6 — Table Pattern component + Table View
**Location:** `/docs/components/table-pattern.md` and `/docs/views/table.md`
**Created in:** Task 3.3
**What it defines:**
- Column structure: configurable per initiative
- Finance column set: level, title, parent, approved budget, actuals, forecast/EAC, variance, remaining, fiscal period, status/action state, last updated
- Sort: any column, ascending/descending, one active sort at a time
- Density: compact enterprise row height
- Action column: rightmost, context menu trigger
- Inline edit: not in v1; read + action menu only
- Empty state, loading state
- Pagination or virtual scroll: TBD in build

**Reuse note:** Table pattern is net-new for this initiative. PM Landing does not use table view. Finance Operation introduces it. Future initiatives inherit this pattern from `/docs/components/table-pattern.md` and `/docs/views/table.md`.

### D7 — Operational Overview Desktop variant specification
**Location:** `/docs/families/operational-overview/desktop.md`
**Created in:** Task 1.3
**What it defines:**
- Layout regions and proportions for desktop
- Left-to-right: shell left nav | main canvas area | AI panel
- Canvas area: summary region (top, collapsible) + bucket/view controls + item area
- AI panel: fixed right, always visible, does not collapse on desktop
- Approximate column split: main canvas ~75%, AI panel ~25% (exact px TBD in build)
- Product header sits above the canvas area when product shell is active
- Responsive breakpoint: AI panel collapses to drawer below tablet width

**Reuse note:** This desktop variant is referenced by all initiatives that use the Operational Overview family on desktop. Both PM Landing and Finance Operation use it.

---

## E. Implementation Order

The sequence below must be followed. Later tasks depend on earlier ones. Do not begin build tasks until specification tasks for that area are complete.

### Phase 1 — Foundation (shell, family, layout)

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 1.1 | Confirm base shell tokens | Reuse | — | `/docs/global/01_shell-rules.md` (read-only reference) | ✅ Ready |
| 1.2 | Confirm product shell extension | Reuse | 1.1 | `/docs/global/02_product-shell-extension.md` (read-only reference) | ✅ Ready |
| 1.3 | Specify Operational Overview desktop variant | Tailor | 1.1, 1.2 | `/docs/families/operational-overview/desktop.md` | ⬜ Not started |
| 1.4 | Scaffold page layout in code | New | 1.1, 1.2, 1.3 | Initiative build | ⬜ Not started |

### Phase 2 — Reusable component specification

These tasks write the reusable pattern into the correct global location. They must be completed before any build work on those components.

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 2.1 | Specify executive-summary-state component | New | 1.3 | `/docs/components/executive-summary-state.md` | ⬜ Not started |
| 2.2 | Specify bucket-pattern component (base + finance variant) | New | 1.3 | `/docs/components/bucket-pattern.md` | ⬜ Not started |
| 2.3 | Specify card-pattern component (base + finance domain variant) | New | 2.2 | `/docs/components/card-pattern.md` | ⬜ Not started |
| 2.4 | Specify AI panel component | New | 1.3 | `/docs/components/ai-panel.md` | ⬜ Not started |
| 2.5 | Specify Ask Altus component | New | 2.4 | `/docs/components/ask-altus.md` | ⬜ Not started |

### Phase 3 — View pattern specification

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 3.1 | Specify board / bucket view pattern | New | 2.2, 2.3 | `/docs/views/board.md` | ⬜ Not started |
| 3.2 | Specify list view pattern | New | 2.3 | `/docs/views/list.md` | ⬜ Not started |
| 3.3 | Specify table view pattern + table component (net-new) | New | 2.3 | `/docs/views/table.md` + `/docs/components/table-pattern.md` | ⬜ Not started |

### Phase 4 — Initiative-specific definition

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 4.1 | Define finance item data model | New | — | `/docs/initiatives/finance-operation/data-model.md` | ⬜ Not started |
| 4.2 | Define role-scope model (Portfolio Manager = portfolio, Program Manager = program) | New | 4.1 | `/docs/initiatives/finance-operation/data-model.md` | ⬜ Not started |
| 4.3 | Define finance bucket membership logic (which items go in which bucket and why) | New | 4.1, 2.2 | `/docs/initiatives/finance-operation/data-model.md` | ⬜ Not started |
| 4.4 | Define finance filter model (level, status, risk, fiscal period, funding state, owner, category) | New | 4.1 | `/docs/initiatives/finance-operation/data-model.md` | ⬜ Not started |
| 4.5 | Define finance AI panel context spec (what signals feed the panel, finance-specific prompt examples) | New | 2.4, 2.5, 4.1 | `/docs/initiatives/finance-operation/data-model.md` | ⬜ Not started |
| 4.6 | Define demo data set (portfolio + program levels, all 5 buckets populated, realistic signals) | New | 4.1, 4.3 | `/docs/initiatives/finance-operation/data-model.md` | ⬜ Not started |

### Phase 5 — Build

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 5.1 | Build shell scaffold (base shell + product header) | Build | 1.4 | Initiative build | ⬜ Not started |
| 5.2 | Build executive summary state component (collapsed default, expandable) | Build | 2.1, 5.1 | Initiative build | ⬜ Not started |
| 5.3 | Build bucket bar and bucket-pattern (5 finance buckets, Needs Financial Decision default) | Build | 2.2, 4.3, 5.1 | Initiative build | ⬜ Not started |
| 5.4 | Build finance data model and demo data | Build | 4.1–4.6 | Initiative build | ⬜ Not started |
| 5.5 | Build board view with finance item cards | Build | 2.3, 3.1, 5.3, 5.4 | Initiative build | ⬜ Not started |
| 5.6 | Build list view | Build | 3.2, 5.4 | Initiative build | ⬜ Not started |
| 5.7 | Build table view (net-new) | Build | 3.3, 5.4 | Initiative build | ⬜ Not started |
| 5.8 | Build view toggle control (board / list / table) | Build | 5.5, 5.6, 5.7 | Initiative build | ⬜ Not started |
| 5.9 | Build filter and search controls | Build | 4.4, 5.5 | Initiative build | ⬜ Not started |
| 5.10 | Build role-scope model (auto-scope by role on load) | Build | 4.2, 5.4 | Initiative build | ⬜ Not started |
| 5.11 | Build item action model (approve, partially approve, reject, release, escalate, mark reviewed, add note, open record) | Build | 4.1, 5.5 | Initiative build | ⬜ Not started |
| 5.12 | Build AI panel (persistent right, maturity switcher, finance context feed) | Build | 2.4, 4.5, 5.1 | Initiative build | ⬜ Not started |
| 5.13 | Build Ask Altus (inline + generated output workspace) | Build | 2.5, 5.12 | Initiative build | ⬜ Not started |

### Phase 6 — States, responsiveness, and consistency review

| Task | Description | Type | Depends on | Output location | Status |
|---|---|---|---|---|---|
| 6.1 | Implement all page states (loading, empty bucket, empty filter, error, success feedback) | Build | 5.1–5.13 | Initiative build | ⬜ Not started |
| 6.2 | Implement responsive behaviour (tablet: AI panel to drawer, layout adapt) | Build | 5.1–5.13 | Initiative build | ⬜ Not started |
| 6.3 | Consistency review against global rules (design system, shell rules, AI behavior, visualization rules) | Review | 6.1, 6.2 | — | ⬜ Not started |
| 6.4 | Cross-initiative consistency check against PM Landing patterns | Review | 6.3 | — | ⬜ Not started |
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

This register tracks which elements created or specified for this initiative are also available to PM Landing and any future initiative.

| Element | Location | Available to |
|---|---|---|
| Executive summary state | `/docs/components/executive-summary-state.md` | PM Landing, Finance Operation, all future overview-family pages |
| Bucket pattern (base) | `/docs/components/bucket-pattern.md` | PM Landing (pm-buckets variant), Finance Operation (finance-buckets variant), future |
| Card pattern (base) | `/docs/components/card-pattern.md` | PM Landing (delivery variant), Finance Operation (finance variant), future |
| AI panel | `/docs/components/ai-panel.md` | PM Landing, Finance Operation, all future overview-family pages |
| Ask Altus | `/docs/components/ask-altus.md` | PM Landing, Finance Operation, all future overview-family pages |
| Table pattern | `/docs/components/table-pattern.md` | Finance Operation (first use), all future pages needing table view |
| Board view pattern | `/docs/views/board.md` | PM Landing, Finance Operation, future |
| List view pattern | `/docs/views/list.md` | PM Landing, Finance Operation, future |
| Table view pattern | `/docs/views/table.md` | Finance Operation (first use), future |
| Operational Overview desktop variant | `/docs/families/operational-overview/desktop.md` | PM Landing, Finance Operation, all future overview-family desktop pages |

---

## H. Decisions Recorded

| Decision | Value | Rationale |
|---|---|---|
| Persona scope model | Role-determined (Portfolio Manager = portfolio, Program Manager = program) | Confirmed by product owner |
| Default selected bucket | Needs Financial Decision | Confirmed by product owner — matches most urgent action intent |
| Summary default state | Collapsed | Inherits product-level placement rule from global/03 |
| Table view | Included in v1 | Specified in masterplan; Finance Operation is the first initiative to introduce table view |
| AI panel placement | Right side, always visible on desktop | Inherits Operational Overview family rule |
| Role-scope switching | No manual scope toggle in v1; scope is set by role on load | Confirmed by product owner; simplest correct model for v1 |
| Demo data | Must cover all 5 buckets at both portfolio and program level with realistic finance signals | Masterplan requirement |
