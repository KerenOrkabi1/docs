# PM Landing — Implementation PRD

## Implementation relationship to the global system
Build this initiative using:
- `/docs/global/00_design-system.md`
- `/docs/global/01_shell-rules.md`
- `/docs/global/03_operational-overview-family.md`
- `/docs/global/05_ai-behavior.md`
- `/docs/global/06_visualization-rules.md`
- `/docs/global/07_view-patterns.md`
- `/docs/personas/pm.md`

## Technical stack
- Frontend: React + TypeScript + Tailwind CSS
- Backend: Lovable Cloud (Supabase)
- Auth: Managed authentication

## Core features (priority order)
### Feature 1
PM landing canvas inside the Altus shell
- [ ] Shell integration
- [ ] Welcome / summary region
- [ ] Responsive behavior
- [ ] Testing

### Feature 2
Multi-project intervention workspace for PM-owned projects
- [ ] Data model
- [ ] Ownership logic
- [ ] UI components
- [ ] Testing

### Feature 3
Fixed urgency buckets with Needs Action Now selected by default
- [ ] Bucket logic
- [ ] Counts / summaries
- [ ] Default state handling
- [ ] Testing

### Feature 4
Board/card and list views using the same underlying data
- [ ] Shared data source
- [ ] View toggle
- [ ] Presentation parity
- [ ] Testing

### Feature 5
Search, filter, and sort controls
- [ ] Filter model
- [ ] Search behavior
- [ ] Sort behavior
- [ ] Testing

### Feature 6
Actionable item cards/rows with delivery signals
- [ ] Item schema
- [ ] Card pattern
- [ ] List row pattern
- [ ] Testing

### Feature 7
Lightweight in-context actions for rapid follow-up
- [ ] Action menu
- [ ] Permission checks
- [ ] Feedback states
- [ ] Testing

### Feature 8
Always-visible AI insight panel with maturity switching
- [ ] Panel integration
- [ ] Maturity switch behavior
- [ ] Page-context data feed
- [ ] Testing

### Feature 9
Ask Altus entry point for broader AI tasks and generated outputs
- [ ] Trigger / entry point
- [ ] Generated output state
- [ ] Return-to-page behavior
- [ ] Testing

## Data structure
Define entities for:
- PM-owned intervention items
- Projects
- Item type
- Owner
- Dates and urgency
- Impact signals
- Action history
- AI summary context

## Implementation order
1. Shell and page scaffold
2. Data schema and ownership logic
3. Bucket logic and view switching
4. Filters and actions
5. AI panel and Ask Altus
6. Responsive refinement and testing
