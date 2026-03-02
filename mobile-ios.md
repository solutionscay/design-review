# Mobile & iOS Design Reference

Read this file when building mobile interfaces, iOS apps, or evaluating mobile UI designs.

---

## Touch-First Fundamentals

### Target Sizes
Apple's Human Interface Guidelines specify a minimum 44x44pt tap target. But "minimum" is not "ideal." For primary actions, go larger — 48-56pt gives breathing room and reduces slip errors (Norman). Spacing between targets matters as much as size: 8pt minimum gap between tappable elements prevents accidental taps.

### Thumb Zones
On modern phones (6"+), the comfortable one-handed thumb reach covers roughly the bottom 60% of the screen. Place primary actions in the bottom third. Navigation and frequent controls belong at the bottom, not the top. iOS itself moved to this pattern with tab bars and bottom sheets.

The top of the screen is the "stretch zone" — put read-only information there (titles, status) and keep interactive elements lower.

### Gesture Design
Gestures are invisible affordances — powerful but discoverable only through convention or teaching.
- **Safe gestures** (users expect them): swipe to go back, pull to refresh, swipe to delete in lists, pinch to zoom on images/maps
- **Risky gestures** (need signifiers): swipe between tabs (add dots or peeking content), long press (add haptic hint or contextual menu indicator), custom gestures (always provide a visible alternative)

Never make a gesture the ONLY way to perform an action. Always provide a visible tap target as an alternative path.

---

## iOS Design Patterns

### Navigation Models

**Tab Bar (bottom)** — Best for 3-5 top-level sections of equal importance. Each tab maintains its own navigation stack. The active tab should be clearly distinguished (filled vs outline icon + color). Never use more than 5 tabs — if you need more, your information architecture needs restructuring.

**Navigation Stack (push/pop)** — Hierarchical drill-down. Always show a back button or back gesture. The title should update to reflect the current context. Use large titles for top-level screens, small titles for detail screens.

**Modal Sheets** — For focused tasks that interrupt the main flow: creating content, making selections, confirming destructive actions. Always provide a clear dismiss action (X button or "Done"). Partial-height sheets (`.medium()` detent) work well for quick selections without losing context.

**Search** — Put search where users expect it: top of lists and collections, in the navigation bar. Use search suggestions and recent searches to reduce typing (Nielsen #6: recognition over recall).

### Common Components

**Lists** — The workhorse of iOS. Use consistent row heights for scanability. Leading content (icon/avatar) helps differentiation. Swipe actions should follow platform conventions: swipe-left for destructive (red), swipe-right for constructive (green/blue). Group related items with section headers.

**Cards** — Good for heterogeneous content (mixed media types, varying lengths). Cards need clear tap targets — is the whole card tappable, or just elements within it? Don't leave this ambiguous. Use subtle shadows or borders to distinguish cards from the background (Gestalt: common region).

**Forms** — Group related fields (Gestalt: proximity). Use appropriate keyboard types (email keyboard for email, number pad for phone). Show validation inline, not at the top of the form. Disable the submit button until required fields are valid (Nielsen #5: error prevention). Preserve user input on errors — never clear the form.

**Empty States** — Every list, collection, and search result screen needs an empty state. It should: explain what will appear here, provide a clear action to get started, and feel intentional (not broken). A good empty state is an onboarding opportunity.

---

## Mobile-Specific Hierarchy

### Screen Real Estate Budget
Mobile screens are small. Every pixel must earn its place. Apply Krug's "omit needless words" philosophy to the entire screen — omit needless elements.

**Above the fold:** The most critical content and primary action. Users should understand the screen's purpose without scrolling.

**Progressive disclosure:** Show summary first, details on demand. Don't front-load complexity. Expandable sections, "Show more" links, and detail screens keep initial cognitive load low.

**Contextual actions:** Instead of showing all possible actions upfront, reveal them in context. Long-press menus, swipe actions, and action sheets reduce visual clutter while keeping functionality accessible.

### Typography on Mobile
Body text: 16-17pt minimum for comfortable reading. Don't go smaller for primary content — accessibility isn't optional, it's a design quality indicator.

Line length: 35-50 characters per line on mobile is the comfortable range. Full-width text blocks on larger phones exceed this — use horizontal padding.

Contrast: WCAG AA minimum (4.5:1 for body text, 3:1 for large text). Test with the actual device in sunlight conditions, not just your monitor.

---

## Performance as Design

On mobile, performance IS the user experience. A beautiful interface that takes 3 seconds to respond to a tap is a bad interface.

**Perceived performance:** Skeleton screens are better than spinners. Spinners are better than blank screens. Optimistic UI updates (showing the result before the server confirms) make actions feel instant.

**Interaction responsiveness:** Tap feedback must be immediate (<100ms). Use highlight states and haptic feedback. If a network request is needed, show the feedback instantly and the result asynchronously.

**Scroll performance:** Jank (dropped frames during scroll) is immediately noticeable and makes the app feel broken. Lazy-load images, avoid complex layouts in scroll views, and test on older devices.

---

## App-Specific Patterns (for camera/scan-based apps)

These are relevant when building apps like Junk Scan that use the camera, scanning, or image analysis.

**Camera viewfinder:** Keep the UI minimal — the camera feed is the content. Overlay controls should be translucent or positioned at the edges. A capture button should be large (minimum 60pt), centered at the bottom, and unmistakable.

**Scan results:** Show results near where the user was looking (the center of the screen, overlaid on the image) or animate them from the scanned area. Don't teleport results to a completely different layout — maintain spatial continuity.

**AI-generated content:** When showing AI results (like price estimates), clearly distinguish AI-generated content from factual data. Use hedging language ("estimated," "approximately") and show confidence levels when available. Users should never mistake an estimate for a guarantee.

**Loading during analysis:** Camera-to-result flows should show progress. A simple "Analyzing..." with a subtle animation is better than a blank wait. If processing takes >2 seconds, show intermediate feedback (e.g., "Found 3 items... estimating values...").

**Result actions:** After showing scan results, the obvious next actions should be prominent: save, share, scan another. Don't make the user hunt for what to do next.
