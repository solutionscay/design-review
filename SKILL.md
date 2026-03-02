---
name: design-principles
description: Apply world-class design principles when building, reviewing, or critiquing UI and frontend interfaces. Use this skill whenever creating components, screens, layouts, or applications — and especially when the user asks for design feedback, critique, or review of any visual interface. Also trigger when the user mentions "does this look good", "design review", "UI feedback", "improve the design", "make it look better", or any request involving visual quality, usability, or design decisions for web or mobile interfaces. This skill complements frontend-design by adding a principled design evaluation layer rooted in the work of the field's most influential practitioners.
---

# Design Principles Skill

This skill encapsulates foundational design principles from the most influential designers and researchers in the field. Use it as a decision-making framework — not a checklist — when building or evaluating interfaces.

When this skill triggers, read the core principles below. Then, depending on the task:
- **Building mobile/iOS UI** → also read `mobile-ios.md`
- **Working on typography, type pairing, or layout grids** → also read `typography.md`
- **Building web app patterns or dashboards** → also read `web-patterns.md`

---

## The Foundation: Dieter Rams' 10 Principles of Good Design

Every design decision should pass through these filters. They were written for industrial design but apply universally to digital interfaces.

1. **Innovative** — Don't copy patterns blindly. Each interface has a unique context; find the form that serves it.
2. **Useful** — A design that doesn't help someone accomplish a goal is decoration, not design.
3. **Aesthetic** — Visual quality affects usability. People perceive well-designed things as easier to use (the aesthetic-usability effect, confirmed by Norman).
4. **Understandable** — The interface should explain itself. If you need a tutorial, you have a design problem.
5. **Unobtrusive** — The UI should serve the content, not compete with it. Design is a frame, not the painting.
6. **Honest** — Don't make elements look clickable when they aren't. Don't hide costs. Don't use dark patterns.
7. **Long-lasting** — Chase clarity over trends. Trends expire; clear hierarchies don't.
8. **Thorough** — Every detail matters. Padding, alignment, loading states, empty states, error states — nothing is too small.
9. **Environmentally friendly** — In digital: respect bandwidth, battery, attention, and screen real estate.
10. **As little design as possible** — Remove until it breaks. Then add back the last thing you removed.

**Application rule:** When evaluating a design, mentally walk through each principle. If a design violates #6 (Honest) or #4 (Understandable), that's a blocking issue. The others are quality gradients.

---

## Don Norman: How People Actually Think

Norman's core insight is that users build **mental models** of how things work — and those models are often wrong. Your job is to close the gap between the user's model and the system's actual behavior.

### The Five Key Concepts

**Affordances** — What actions does the element invite? A button affords pressing. A slider affords dragging. If a text field looks like a label, you've broken its affordance.

**Signifiers** — Affordances are possibilities; signifiers communicate them. An underline on a link is a signifier. A subtle shadow on a card that lifts on hover is a signifier. Ask: "Would a first-time user know they can interact with this?"

**Mapping** — The relationship between controls and outcomes. Natural mapping means the layout of controls mirrors the layout of what they affect. A volume slider that goes up to increase volume has good mapping. A settings page where "Delete Account" is next to "Save" has catastrophic mapping.

**Feedback** — Every action needs a visible reaction. Tap a button → it depresses. Submit a form → show a spinner, then confirmation. No feedback = user anxiety = repeated taps = broken state.

**Conceptual Models** — The story the user tells themselves about how this works. A trash can icon communicates "deleted items go here and can be recovered." If your trash can permanently deletes, your conceptual model is lying.

### Norman's Error Framework
People make two kinds of errors:
- **Slips** — Right intention, wrong action (tapping the wrong button because it's too close to another). Fix with better layout and spacing.
- **Mistakes** — Wrong intention (user doesn't understand what a feature does). Fix with better signifiers and information architecture.

Design for slips with undo. Design for mistakes with clarity.

---

## Steve Krug: Don't Make Me Think

Krug's law is simple: every element on a screen should be self-evident. If it's not self-evident, it should at least be self-explanatory. If it requires thought, it's a design failure.

### Key Principles

**Satisficing over optimizing** — Users don't read pages. They scan. They don't choose the best option; they choose the first reasonable one. Design for scanning: clear headlines, visual hierarchy, obvious CTAs.

**The "trunk test"** — Drop a user on any page with no context. Can they answer: Where am I? What are the major sections? What can I do here? Where's home? How do I search? If not, your navigation and information architecture need work.

**Omit needless words** — Cut your copy in half. Then cut it in half again. Instructions nobody reads are worse than no instructions — they add visual noise without adding clarity.

**Don't punish exploration** — Users learn by clicking around. Make it safe to explore: clear back buttons, undo support, non-destructive defaults.

### Krug's Usability Hierarchy
1. **Useful** — Does it do something people need?
2. **Learnable** — Can people figure out how to use it?
3. **Memorable** — Can they remember how to use it next time?
4. **Effective** — Does it get the job done?
5. **Efficient** — Does it get the job done without wasting time?
6. **Desirable** — Do people want to use it?
7. **Delightful** — Does it make them smile?

Build from the top down. Don't chase delight before nailing useful and learnable.

---

## Jakob Nielsen: The 10 Usability Heuristics

These are the industry-standard evaluation framework. Use them as a diagnostic tool when reviewing any interface.

1. **Visibility of system status** — Always show what's happening. Loading indicators, progress bars, active states, selected states.
2. **Match between system and real world** — Use the user's language, not engineering jargon. Follow real-world conventions (calendar icon for dates, envelope for email).
3. **User control and freedom** — Support undo and redo. Provide clear exits. Never trap users in flows.
4. **Consistency and standards** — Same action, same result, everywhere. Follow platform conventions unless you have a very good reason not to.
5. **Error prevention** — Better than good error messages is preventing errors in the first place. Disable invalid actions. Confirm destructive ones.
6. **Recognition over recall** — Show options instead of requiring users to remember them. Autocomplete, recent items, visible navigation.
7. **Flexibility and efficiency** — Support both novice (guided) and expert (shortcuts) paths. Keyboard shortcuts, bulk actions, customizable workflows.
8. **Aesthetic and minimalist design** — Every extra element competes with the relevant ones. Information density should be intentional, not accidental.
9. **Help users recognize, diagnose, and recover from errors** — Error messages should: say what went wrong (in plain language), suggest how to fix it, and never blame the user.
10. **Help and documentation** — Should be searchable, task-focused, and concise. But if you need extensive docs, revisit #4 and #6.

**How to use these:** When reviewing a design, score each heuristic 0-4 (0 = no issue, 4 = usability catastrophe). Anything scoring 3+ is a blocking issue.

---

## Visual Hierarchy & Gestalt Principles

These are the physics of visual perception — how the human eye groups and prioritizes information.

### Gestalt Principles (the ones that matter most for UI)

**Proximity** — Elements near each other are perceived as related. This is the single most powerful grouping tool. Use spacing, not boxes, to create groups.

**Similarity** — Elements that look alike are perceived as related. Consistent styling for interactive elements (all links one color, all buttons one shape) creates implicit categories.

**Continuity** — The eye follows lines and curves. Alignment creates invisible lines that guide scanning. Break alignment only with intention.

**Closure** — The brain completes incomplete shapes. You don't need full borders around cards — a shadow on two sides implies the rest. Use this to reduce visual clutter.

**Figure-Ground** — Users need to instantly distinguish foreground (content) from background (chrome). Low contrast between content and background is one of the most common design failures.

**Common Region** — Elements within a boundary are grouped. Cards, panels, and containers leverage this. But too many containers create visual noise — use sparingly.

### Building Visual Hierarchy

Hierarchy is how you tell the user "look here first, then here, then here." You have exactly four tools:

1. **Size** — Bigger = more important. This is the bluntest tool; use it for headlines and primary CTAs.
2. **Weight** — Bolder = more important. More nuanced than size. Use for emphasis within text.
3. **Color/Contrast** — Higher contrast = more attention. Your primary action should have the highest contrast on the page. Use this to create a clear "what do I do next?" signal.
4. **Space** — More whitespace around an element = more prominence. This is the most sophisticated tool and the one most often neglected.

**The squint test:** Blur your eyes (or blur the screenshot). Can you still tell what's most important? If everything looks the same when blurred, your hierarchy is flat.

---

## Review Output Format

When performing a design review, **always produce a timestamped markdown document**. Save it to the
project directory or a location the user specifies.

### File Naming

```
{Subject}-Design-Review-{YYYY-MM-DD}.md
```

Examples:
- `Dashboard-Design-Review-2026-03-02.md`
- `Craigslist-Design-Review-2026-03-02.md`
- `Checkout-Flow-Design-Review-2026-03-02.md`

Use the current date. Use PascalCase with hyphens for the subject. If the user specifies a path,
save there. Otherwise save in the current working directory.

### Document Structure

Every review document follows this exact structure:

```markdown
# Design Review: {Subject}
*Reviewed: {YYYY-MM-DD}*

{1-2 sentence context about what's being reviewed and why it's interesting.}

---

## 1. Purpose & Context
{Analysis...}

> **Summary:** {One paragraph distilling the key finding from this section.}

---

## 2. Structure (Information Architecture)
{Analysis with ### What works and ### What fails subsections...}

> **Summary:** {One paragraph.}

---

## 3. Hierarchy (Visual Communication)
{Analysis. Include the squint test result. Use a table for specific issues
with columns: Problem | Principle Violated | Severity (0-4).}

> **Summary:** {One paragraph.}

---

## 4. Interaction (Behavioral Design)
{Analysis with ### What works and ### What fails subsections...}

> **Summary:** {One paragraph.}

---

## 5. Polish (Craft Quality)
{Analysis of spacing, typography, color, edge cases...}

> **Summary:** {One paragraph.}

---

## 6. Summary Scorecard (Nielsen's Heuristics)

| Heuristic | Score (0-4) | Notes |
|---|---|---|
| 1. Visibility of system status | {n} | {brief note} |
| 2. Match real world | {n} | {brief note} |
| 3. User control & freedom | {n} | {brief note} |
| 4. Consistency | {n} | {brief note} |
| 5. Error prevention | {n} | {brief note} |
| 6. Recognition over recall | {n} | {brief note} |
| 7. Flexibility & efficiency | {n} | {brief note} |
| 8. Aesthetic & minimalist | {n} | {brief note} |
| 9. Error recovery | {n} | {brief note} |
| 10. Help & documentation | {n} | {brief note} |

> **Summary:** {One paragraph highlighting the worst scores and best scores.}

---

## Concrete Recommendations
{Numbered list of specific, actionable fixes. Each recommendation names
the element, the change, and the principle it addresses.}

> **Summary:** {One paragraph distilling the recommendations.}
```

### Section Summary Rules

- Every section (1-6, scorecard, recommendations) ends with a blockquote summary
- Format: `> **Summary:** {paragraph}`
- The summary should stand alone — someone reading only the summaries should understand the full review
- Be specific, not vague. Name elements, reference principles, state severity.
- Write in plain language. No jargon without explanation.

### Severity Scoring

Use Nielsen's 0-4 scale consistently throughout:
- **0** — No issue
- **1** — Cosmetic issue only
- **2** — Minor usability issue
- **3** — Major usability issue (blocking)
- **4** — Usability catastrophe (must fix)

### Optional: The Honest Counter-Argument

If the design has a legitimate reason for its choices (performance, brand identity, specific user
context), include a final section acknowledging that tension:

```markdown
## The Honest Counter-Argument
{Why this design might work despite the issues found...}

> **Summary:** {One paragraph.}
```

---

## Design Critique Framework

When evaluating (whether for the review document or inline feedback), follow this order:

### 1. Purpose & Context (before looking at pixels)
- What is the user trying to accomplish?
- What's the one most important action on this screen?
- Who is the user and what do they know?

### 2. Structure (information architecture)
- Is the content organized by user goals or by system structure?
- Can a user orient themselves instantly? (Krug's trunk test)
- Is the navigation predictable?

### 3. Hierarchy (visual communication)
- Is there a clear visual priority? (squint test)
- Does the hierarchy match the task priority?
- Are related elements grouped? (proximity)

### 4. Interaction (behavioral design)
- Do interactive elements have clear affordances and signifiers? (Norman)
- Is there feedback for every action?
- Are errors prevented, and when they occur, are they recoverable?

### 5. Polish (craft quality)
- Is spacing consistent?
- Is typography intentional? (not just "a font was chosen")
- Do colors serve a purpose or just decorate?
- Are edge cases handled? (empty states, loading, errors, overflow text)

### 6. Specificity over "taste"
Never say "it doesn't feel right" or "it needs more polish" without saying exactly what and why. Good critique names the element, the principle it violates, and a concrete fix.

**Bad:** "The button doesn't feel right."
**Good:** "The primary CTA has the same visual weight as the secondary action — they're the same size and similar colors. The primary button needs higher contrast or larger size to establish hierarchy (Rams #4, Nielsen #8)."

---

## Anti-Patterns to Flag

When building or reviewing, watch for these common failures:

- **Mystery meat navigation** — Icons without labels, ambiguous symbols, clever-but-unclear metaphors
- **Zombie toggles** — Settings that exist but don't visibly do anything (violates feedback principle)
- **The paradox of choice** — Too many options with equal visual weight paralyze users. Reduce options or create clear hierarchy.
- **Scroll kidnapping** — Custom scroll behavior that fights the user's muscle memory
- **Modals on modals** — Stacking contexts destroys spatial orientation
- **Ghost affordances** — Interactive elements that look like static content (flat design's worst sin)
- **Junk drawer settings** — Dumping every option into one screen instead of surfacing the important ones contextually
- **False floors** — Content exists below the fold but there's no visual signal to scroll
- **Disabled without explanation** — Grayed-out buttons with no tooltip or hint about what's missing

---

## Applying These Principles

When building: Use the principles proactively. Before writing any UI code, identify the primary user goal, the one most important action, and the information hierarchy. Build from that foundation.

When critiquing: Use the critique framework and produce a review document. Be specific. Reference the principle by name. Suggest a fix, not just a problem.

When in doubt: Remove elements until the design breaks. The version right before it broke is probably correct (Rams #10).
