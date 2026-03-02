# Web App UI Patterns Reference

Read this file when building web applications, dashboards, SaaS interfaces, or evaluating web-based UI patterns.

---

## Layout Patterns

### The Sidebar + Content Pattern
The most common web app layout: fixed sidebar navigation on the left, scrollable content area on the right. Works because it follows reading direction (scan nav → focus on content) and keeps navigation persistently visible.

**Keys to doing it well:**
- Sidebar width: 240–280px. Narrower feels cramped; wider wastes content space.
- Collapsible to icon-only (48–64px) on smaller viewports or user preference
- Active state in nav should be unmistakable — background highlight, not just text color change
- Group nav items by category with subtle section dividers or labels
- Keep the most-used items at the top; settings and account at the bottom

### The Top Nav + Content Pattern
Better for content-focused sites with fewer navigation items (5–7 max). Maximizes vertical content space. Use when horizontal navigation categories are at the same level of importance.

### The Dashboard Grid
For data-heavy interfaces. Use cards or panels in a responsive grid. Each card answers one question or shows one metric.

**Dashboard hierarchy:**
1. Key metrics at the top (the numbers someone checks first)
2. Trends and charts in the middle (context for the metrics)
3. Detail tables or lists at the bottom (drill-down data)

Don't make dashboards that require scrolling to find the most important number. If your key metric is below the fold, your layout priorities are wrong.

### Content Density
Some interfaces need to be dense (data tables, admin panels, trading platforms). Others need to breathe (onboarding, marketing, consumer apps). Neither is inherently better — it depends on the user's task and expertise.

**Dense UI guidelines:**
- Reduce spacing (use 4pt and 8pt base units instead of 8pt and 16pt)
- Smaller font sizes are acceptable for expert users (13-14px body)
- Use borders and subtle backgrounds to separate regions instead of whitespace
- Information-dense doesn't mean cluttered — alignment and consistency matter even more at high density

**Spacious UI guidelines:**
- Generous whitespace signals quality and confidence
- Larger type (18-20px body) for readability and approachability
- Fewer items per screen, with clear calls to action
- Progressive disclosure: summary → detail on demand

---

## Component Patterns

### Tables
Tables are the right choice when users need to compare values across rows, sort or filter data, or perform actions on multiple items.

**Good table design:**
- Right-align numbers (they scan better when decimal points line up)
- Left-align text
- Consistent row height — don't let content push rows to different heights unless necessary
- Sticky headers for scrollable tables
- Zebra striping OR subtle row borders — not both. Pick one for row differentiation.
- Row hover states if rows are clickable
- Pagination or virtual scrolling for large datasets — never dump 10,000 rows into the DOM
- Sort indicators should be visible and intuitive (arrow direction matching sort order)

### Forms
Forms are where most web apps succeed or fail. Users abandon forms that feel burdensome.

**Form design principles:**
- Single-column layout. Multi-column forms increase completion time and error rates. The only exception: closely related short fields (city/state/zip).
- Label placement: above the field (fastest scanning) or left-aligned (more compact). Placeholder text is NOT a label — it disappears on focus and fails accessibility.
- Group related fields and separate groups with spacing, not lines (Gestalt: proximity)
- Inline validation: show errors as the user leaves each field, not on submit. Use green checkmarks sparingly — they add visual noise for expected behavior.
- Required vs optional: mark the minority. If most fields are required, mark the optional ones. If most are optional, mark the required ones.
- Submit button text should describe the action ("Create Account," "Send Message") not be generic ("Submit")

### Modals and Dialogs
Modals are interruptions. Use them only when you need the user to make a decision or complete a focused task before continuing.

**When to use a modal:** Confirming destructive actions, creating/editing a single item, login/authentication, critical alerts.

**When NOT to use a modal:** Showing information that doesn't require action, multi-step workflows (use a dedicated page instead), content the user might want to reference while doing other things.

**Modal design rules:**
- Always provide a visible close mechanism (X button + click outside + Escape key)
- Focus trap: keyboard focus should stay inside the modal while it's open
- Size: as small as the content allows. Don't use a full-screen modal for a yes/no question.
- Backdrop: dim the background to establish figure-ground separation (Gestalt)

### Notifications and Toasts
Feedback mechanisms for non-blocking information.

**Toast notifications:** Brief, auto-dismissing messages for confirmations ("Saved," "Copied to clipboard"). Position consistently — top-right or bottom-center are conventions. Stack multiple toasts vertically. Auto-dismiss after 3-5 seconds. Always include a manual dismiss option.

**Inline notifications:** For contextual information that relates to a specific part of the page. Use color to indicate severity: info (blue), success (green), warning (yellow), error (red). These are near-universal conventions — don't fight them.

---

## State Management in UI

Every component has states. Designing only the "happy path" default state is one of the most common quality failures.

### The Five States Every Component Needs

1. **Empty state** — No data yet. Should explain what goes here and how to add content. An empty table that just says "No results" is a missed opportunity. "No projects yet. Create your first project to get started." with a button is design.

2. **Loading state** — Data is being fetched. Skeleton screens are better than spinners for known layouts. Show the structure of what's coming. Avoid layout shift when data arrives — the skeleton should match the loaded layout.

3. **Partial state** — Some data, but not much. One item in a list. Half-completed profile. The UI should work and look intentional with minimal data, not just with 50+ items.

4. **Ideal state** — Full data, everything working. This is what mockups usually show. But it's only ONE of the five states.

5. **Error state** — Something went wrong. Network failure, validation error, permission denied. Error states need: what happened (in plain language), why (if relevant), what to do about it (retry, contact support, try different input), and a recovery action (retry button, back navigation).

### Overflow and Edge Cases
- Long text: truncate with ellipsis or wrap? Decide per component, be consistent.
- Long names/emails: test with 40+ character inputs
- Many items: what happens at 100? 1,000? 10,000?
- No image: have a default avatar, thumbnail placeholder, or graceful absence
- Slow network: does the UI remain usable with 3-second response times?
- Offline: can the user at least see cached data?

---

## Responsive Design

### Breakpoint Strategy
Don't design for specific devices. Design for content breakpoints — the points where your layout needs to change because the content no longer fits well.

Common breakpoints (as starting points, not rules):
- 640px — small mobile to large mobile
- 768px — mobile to tablet
- 1024px — tablet to small desktop
- 1280px — small desktop to full desktop
- 1536px — full desktop to wide desktop

### What Changes at Breakpoints
- **Navigation:** sidebar → bottom nav or hamburger on mobile
- **Grid columns:** 12 → 8 → 4 as viewport shrinks
- **Typography:** heading sizes can reduce 10-15% on mobile
- **Content priority:** on mobile, ruthlessly cut secondary content. Show only what's essential for the task at hand.
- **Touch targets:** increase interactive element sizes on touch viewports
- **Images:** different crops, not just scaled-down. A landscape hero image might need a square or portrait crop on mobile.

### Mobile-First vs Desktop-First
Build mobile layouts first, then enhance for larger screens. Mobile forces you to prioritize content (there's no room for clutter) and ensures touch interactions work. Enhancing upward (adding columns, showing more options) is easier than stripping down.

---

## Performance as Design (Web)

### Core Web Vitals as Design Metrics
Google's Core Web Vitals aren't just SEO metrics — they measure UX:
- **LCP (Largest Contentful Paint)** — How quickly does the main content appear? The "hero" element should load fast.
- **FID / INP (Interaction to Next Paint)** — How quickly does the page respond to interaction? Perceived slowness = bad design.
- **CLS (Cumulative Layout Shift)** — Does the page jump around as it loads? Layout shift is disorienting and erodes trust.

### Design Choices That Kill Performance
- Hero images without defined dimensions (cause layout shift)
- Web fonts that flash or swap (FOUT/FOIT) — use `font-display: swap` and preload critical fonts
- Carousels and sliders that load all slides upfront
- Third-party widgets (chat bubbles, analytics overlays) that block rendering
- Animations that trigger layout recalculation (animate `transform` and `opacity`, not `width` and `height`)

Design with performance in mind from the start. A fast, simple interface almost always beats a slow, elaborate one.
