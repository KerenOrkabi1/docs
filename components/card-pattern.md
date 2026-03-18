# Card Pattern

## Purpose
This file defines the reusable card pattern for displaying entities in board/bucket views across Altus.

## Version 1: ActionItemCard

### Pattern Rules

**Structural Requirements:**
- Cards display entity information in board/bucket views
- Cards do NOT have bottom action buttons
- Cards have a three-dots menu button (top-right corner)
- Three-dots menu always opens a dropdown with grouped actions

### Standard Layout

1. **Header Row**
   - Left: Type icon + type label (uppercase, small text)
   - Right: Three-dots menu button (MoreVertical icon)

2. **Title Section**
   - Entity title (font-semibold, line-clamp-2 for overflow)
   - Primary information display

3. **Project Section**
   - Project name with icon (FolderKanban)
   - Secondary context information

4. **Metadata Row**
   - Owner (User icon + name)
   - Due date (Clock icon + date)
   - Other contextual metadata as needed

5. **Status Row**
   - Priority badge (colored background + border)
   - Status indicators (e.g., overdue with AlertCircle icon)

### Interaction Pattern

**Three-Dots Menu:**
- Click three-dots button → opens dropdown menu
- Dropdown contains grouped actions (see dropdown-pattern.md)
- No quick action buttons at card bottom
- All actions accessed through dropdown for consistency

**Hover Behavior:**
- Card displays shadow effect on hover
- Three-dots button changes color on hover

### Theme Requirements

**Card Background:**
- Background: `theme.backgroundSurface1`
- Border: `theme.borderSubtle`
- Hover shadow: `0 4px 6px -1px rgba(0, 0, 0, 0.1)`

**Text Colors:**
- Title: `theme.textPrimary`
- Metadata: `theme.textSecondary`
- Type label: `theme.textSecondary`

**Priority Badges:**
- High: `theme.colorDanger` (text), light red background + border
- Medium: `theme.colorWarning` (text), light yellow background + border
- Low: `theme.colorInfo` (text), light blue background + border

**Three-Dots Button:**
- Default: `theme.textSecondary`
- Hover: `theme.textPrimary`

### Implementation Reference

**Current Implementation:**
- `/src/app/v2/components/bucket/ActionItemCard.tsx` - PM action items
- `/src/app/v2/components/bucket/FinanceItemCard.tsx` - Finance items

**Related Patterns:**
- Dropdown pattern: `/docs/components/dropdown-pattern.md`
- Board view pattern: `/docs/global/07_view-patterns.md`

### Dropdown Menu Actions (V1)

**ActionItemCard actions:**
1. Send Nudge
2. Mark Reviewed
3. Update Status
4. Mark Complete
5. Resolve / Close
6. Reassign Owner
7. Add Note
8. Escalate
9. Open Full Record

**FinanceItemCard actions:**
1. Approve
2. Request Review
3. Update Amount
4. Add Comment
5. Reject
6. Request Info
7. Escalate
8. View History
9. Open Full Record

### Design Principles

1. **Consistency:** All cards follow same structure
2. **Cleanliness:** No bottom button clutter
3. **Accessibility:** Menu accessible via keyboard and screen readers
4. **Theme-Aware:** All colors from theme tokens
5. **Scannable:** Quick visual hierarchy for rapid review

### Future Variants

As new card types are added (FinanceItemCard, RiskCard, etc.):
- Follow same structural pattern
- Use three-dots dropdown for actions
- Adapt metadata sections to entity type
- Maintain theme-aware approach

### Rules for New Card Components

When creating new card components:
1. ✅ Use three-dots menu in top-right
2. ✅ Implement dropdown for all actions
3. ❌ Do NOT add bottom action buttons
4. ✅ Follow standard layout sections
5. ✅ Use theme tokens for all colors
6. ✅ Include hover shadow effect
7. ✅ Make title line-clamp-2
8. ✅ Reference dropdown-pattern.md for menu implementation

---

**Last Updated:** 2026-03-17  
**Version:** 1.0
