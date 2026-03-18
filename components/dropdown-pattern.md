# Dropdown Pattern

## Purpose
This file defines the reusable dropdown menu pattern for contextual actions across Altus components.

## Version 1: Group Menu

### Pattern Overview

Provides contextual actions for entities (cards, list items, table rows, etc.) through a clean dropdown menu interface.

### Implementation Foundation

**Library:** Radix UI DropdownMenu  
**Package:** `@radix-ui/react-dropdown-menu`

**Why Radix UI:**
- Accessible by default (ARIA, keyboard nav, focus management)
- Portal-based rendering (proper z-index layering)
- Controlled or uncontrolled state management
- Consistent with existing Altus component patterns

### Standard Structure

```tsx
<DropdownMenu.Root open={dropdownOpen} onOpenChange={setDropdownOpen}>
  <DropdownMenu.Trigger asChild>
    {/* Trigger button (usually three-dots icon) */}
  </DropdownMenu.Trigger>

  <DropdownMenu.Portal>
    <DropdownMenu.Content>
      {/* Menu items */}
      <DropdownMenu.Item onSelect={handleAction}>
        {/* Icon + Label */}
      </DropdownMenu.Item>
    </DropdownMenu.Content>
  </DropdownMenu.Portal>
</DropdownMenu.Root>
```

### Component Breakdown

#### 1. Root Component
- `<DropdownMenu.Root>` - Container and state manager
- Props: `open`, `onOpenChange` (for controlled state)
- Use `useState` to manage open/closed state

#### 2. Trigger Button
- `<DropdownMenu.Trigger asChild>` - Button that opens menu
- Use `asChild` to pass styling to child button
- Common icon: `MoreVertical` (three-dots)
- Must include `aria-label` for accessibility

#### 3. Portal
- `<DropdownMenu.Portal>` - Renders menu at document root
- Ensures proper layering and z-index
- Prevents overflow/clipping issues

#### 4. Content
- `<DropdownMenu.Content>` - The dropdown menu container
- Props: `sideOffset`, `align`, `side`
- Contains all menu items

#### 5. Menu Items
- `<DropdownMenu.Item>` - Individual action items
- Props: `onSelect` - callback when item clicked
- Contains icon + label

### Styling Rules

#### Menu Container (`Content`)
- **Background:** `theme.backgroundSurface1`
- **Border:** `theme.borderDefault` (1px solid)
- **Shadow:** `shadow-lg` (elevation effect)
- **Padding:** `p-1` (4px)
- **Border radius:** `rounded-lg`
- **Min width:** `200px`
- **Z-index:** `z-50` or higher

#### Menu Items (`Item`)
- **Text color:** `theme.textPrimary`
- **Padding:** `px-3 py-2` (12px horizontal, 8px vertical)
- **Font size:** `text-sm` (14px)
- **Border radius:** `rounded`
- **Cursor:** `cursor-pointer`
- **Outline:** `outline-none` (Radix handles focus)

#### Hover State
- **Background:** `theme.backgroundSurface2`
- **Transition:** Smooth color change
- Use `onMouseEnter`/`onMouseLeave` for dynamic styling

#### Icons
- **Size:** `w-4 h-4` (16px)
- **Color:** `theme.textSecondary`
- **Position:** Left of label with gap

#### Trigger Button
- **Default color:** `theme.textSecondary`
- **Hover color:** `theme.textPrimary`
- **Transition:** `transition-colors`
- **Accessibility:** Include `aria-label="More actions"`

### Standard Menu Item Structure

Each menu item should include:
1. Icon (from lucide-react)
2. Label (action name)
3. Unique ID (for action handling)

```tsx
const dropdownItems = [
  { id: 'action-id', label: 'Action Name', icon: IconComponent },
  // ... more items
];
```

### Action Handling

#### Callback Pattern
- Use `onAction(itemId, actionId)` callback pattern
- Pass entity ID and action ID to parent
- Parent component handles actual action logic

#### Close Behavior
- Menu auto-closes on item select (Radix default)
- Can manually close with `setDropdownOpen(false)`
- ESC key closes menu (Radix default)

### Accessibility Features

**Built-in (Radix UI):**
- ✅ Keyboard navigation (Arrow keys, Enter, ESC)
- ✅ Focus management (auto-focus first item)
- ✅ ARIA attributes (role="menu", aria-expanded, etc.)
- ✅ Screen reader announcements

**Developer Requirements:**
- ✅ Add `aria-label` to trigger button
- ✅ Use semantic action names in labels
- ✅ Ensure sufficient color contrast

### Theme Awareness

All dropdown menus must:
- ✅ Use theme tokens (no hardcoded colors)
- ✅ Reference `useTheme()` hook
- ✅ Support all theme variants (blue, emerald, purple)
- ✅ Update dynamically when theme changes

### Interaction Guidelines

**Click/Tap:**
- Click trigger → menu opens
- Click item → action fires, menu closes
- Click outside → menu closes

**Keyboard:**
- Focus trigger, press Enter/Space → menu opens
- Arrow keys → navigate items
- Enter → select item
- ESC → close menu

**Touch (Mobile):**
- Tap trigger → menu opens
- Tap item → action fires
- Tap outside → menu closes

### Common Use Cases

#### 1. Card Actions (ActionItemCard)
- Three-dots button in card header
- Menu with entity-specific actions
- See: `/src/app/v2/components/bucket/ActionItemCard.tsx`

#### 2. List Row Actions
- Three-dots at end of each row
- Quick access to row-level actions

#### 3. Table Row Actions
- Icon button in action column
- Contextual menu for table rows

#### 4. Toolbar Overflow
- More options button in toolbars
- Secondary actions that don't fit in main toolbar

### Implementation Example

**From ActionItemCard.tsx:**
```tsx
// State management
const [dropdownOpen, setDropdownOpen] = useState(false);

// Menu configuration
const dropdownItems = [
  { id: 'send-nudge', label: 'Send Nudge', icon: Send },
  { id: 'mark-reviewed', label: 'Mark Reviewed', icon: Eye },
  // ... more items
];

// Render
<DropdownMenu.Root open={dropdownOpen} onOpenChange={setDropdownOpen}>
  <DropdownMenu.Trigger asChild>
    <button aria-label="More actions">
      <MoreVertical className="w-4 h-4" />
    </button>
  </DropdownMenu.Trigger>

  <DropdownMenu.Portal>
    <DropdownMenu.Content
      style={{
        backgroundColor: theme.backgroundSurface1,
        border: `1px solid ${theme.borderDefault}`,
      }}
      sideOffset={5}
    >
      {dropdownItems.map((item) => (
        <DropdownMenu.Item
          key={item.id}
          onSelect={() => onAction(entityId, item.id)}
        >
          <item.icon className="w-4 h-4" />
          <span>{item.label}</span>
        </DropdownMenu.Item>
      ))}
    </DropdownMenu.Content>
  </DropdownMenu.Portal>
</DropdownMenu.Root>
```

### Future Versions

**Planned Enhancements:**
- V2: Grouped menu items (with separators)
- V3: Sub-menus (nested actions)
- V4: Menu items with keyboard shortcuts display
- V5: Danger actions (red highlighting)
- V6: Disabled items with tooltips

### Design Principles

1. **Consistency:** Same pattern across all components
2. **Accessibility:** Keyboard and screen reader friendly
3. **Performance:** Lightweight, no re-renders on hover
4. **Theming:** Fully theme-aware
5. **Simplicity:** Easy to implement and maintain

### Rules for Using Dropdown Pattern

When adding dropdowns to new components:
1. ✅ Use Radix UI DropdownMenu (already installed)
2. ✅ Manage state with `useState`
3. ✅ Use `MoreVertical` icon for trigger
4. ✅ Include `aria-label` on trigger
5. ✅ Use theme tokens for all colors
6. ✅ Follow standard item structure (icon + label)
7. ✅ Use callback pattern: `onAction(id, action)`
8. ❌ Do NOT hardcode colors
9. ❌ Do NOT create custom dropdown from scratch

### Related Patterns

- **Card Pattern:** `/docs/components/card-pattern.md`
- **View Patterns:** `/docs/global/07_view-patterns.md`
- **Theme System:** `/docs/global/00_design-system.md`

---

**Last Updated:** 2026-03-17  
**Version:** 1.0 (Group Menu)
