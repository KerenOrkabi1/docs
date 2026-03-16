# Finance Operation — Implementation PRD

## Implementation relationship to the global system
Build this initiative using:
- `/docs/global/00_design-system.md`
- `/docs/global/01_shell-rules.md`
- `/docs/global/02_product-shell-extension.md`
- `/docs/global/03_operational-overview-family.md`
- `/docs/global/05_ai-behavior.md`
- `/docs/global/06_visualization-rules.md`
- `/docs/global/07_view-patterns.md`
- `/docs/personas/portfolio-manager.md`
- `/docs/personas/program-manager.md`

## Technical stack
- Frontend: React + TypeScript + Tailwind CSS
- Backend: Lovable Cloud (Supabase)
- Auth: Managed authentication

## Core features (priority order)
### Feature 1
Finance Operation canvas inside the Altus shell and product shell
- [ ] Shell integration
- [ ] Product header integration
- [ ] Summary region
- [ ] Responsive behavior
- [ ] Testing

### Feature 2
Portfolio/program finance health summary
- [ ] Summary data model
- [ ] State visualisation component
- [ ] Expand/collapse behavior
- [ ] Testing

### Feature 3
Operational finance buckets and reusable views
- [ ] Bucket logic
- [ ] Board/list/table parity
- [ ] Default state handling
- [ ] Testing

### Feature 4
Budget, actuals, forecast, and variance item model
- [ ] Data schema
- [ ] Level hierarchy support
- [ ] Derived signals
- [ ] Testing

### Feature 5
Available funds, reserve, and release-state visibility
- [ ] Finance state logic
- [ ] Visual cues
- [ ] Filters and summaries
- [ ] Testing

### Feature 6
Pending approvals, requests, and direct actions
- [ ] Action model
- [ ] Permission checks by role
- [ ] Feedback states
- [ ] Testing

### Feature 7
Always-visible AI insight panel with maturity switching
- [ ] Panel integration
- [ ] Maturity switch behavior
- [ ] Finance-context data feed
- [ ] Testing

### Feature 8
Ask Altus entry point for broader finance tasks and generated outputs
- [ ] Trigger / entry point
- [ ] Generated output state
- [ ] Return-to-page behavior
- [ ] Testing

## Data structure
Define entities for:
- Portfolio and program financial containers
- Approved budget / envelope
- Disbursement or released funds
- Actuals
- Forecast / EAC
- Variance / drift
- Reserve / contingency
- Requests and approvals
- Fiscal timing
- Action history
- AI summary context

## Implementation order
1. Shell and product-shell scaffold
2. Finance schema and hierarchy logic
3. Summary state component and buckets
4. Views, filters, and actions
5. AI panel and Ask Altus
6. Responsive refinement and testing
