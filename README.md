# Design Review

Principled design critique grounded in Dieter Rams, Don Norman, Steve Krug, and Jakob Nielsen. Evaluates any UI — web or mobile — against established design theory, not personal taste.

## The Problem

AI design feedback is vague. "Looks clean." "Maybe add more whitespace." "The colors feel off." None of that is actionable. It doesn't name the element, the principle violated, or a concrete fix.

## The Fix

`/design-review` applies four foundational frameworks to produce specific, grounded critique:

- **Dieter Rams** — 10 Principles of Good Design. #4 (Understandable) and #6 (Honest) are blocking; the rest are quality gradients.
- **Don Norman** — Affordances, signifiers, mapping, feedback, conceptual models. Closes the gap between user mental models and actual system behavior.
- **Steve Krug** — Don't Make Me Think. The trunk test, satisficing, omit needless words.
- **Jakob Nielsen** — 10 Usability Heuristics. Scored 0-4; anything 3+ is a blocking issue.

Every critique names the element, references the violated principle, and suggests a fix.

## Usage

```
/design-review
```

Works on any UI code — components, pages, layouts, full applications. No prerequisites.

## What It Produces

A **timestamped markdown document** saved to the project directory:

```
{Subject}-Design-Review-{YYYY-MM-DD}.md
```

The document follows a fixed structure:

1. **Purpose & Context** — What is the user trying to accomplish? What's the ONE most important action?
2. **Structure** — Is content organized by user goals? Can a user orient themselves instantly? (trunk test)
3. **Hierarchy** — Clear visual priority? Does hierarchy match task priority? (squint test)
4. **Interaction** — Clear affordances and signifiers? Feedback for every action? Errors recoverable?
5. **Polish** — Consistent spacing? Intentional typography? Edge cases handled?
6. **Summary Scorecard** — Nielsen's 10 heuristics scored 0-4 in a table
7. **Concrete Recommendations** — Numbered, actionable fixes with principle references

Every section ends with a `> **Summary:**` blockquote — a standalone paragraph so someone reading only the summaries gets the full picture.

## When It Triggers

- "Does this look good?"
- "Design review" / "UI feedback"
- "Improve the design" / "Make it look better"
- Any request involving visual quality, usability, or design decisions

## Reference Files

| File | When to read |
|---|---|
| `SKILL.md` | Always — core principles, critique framework, anti-patterns |
| `web-patterns.md` | Web apps, dashboards, SaaS interfaces |
| `mobile-ios.md` | Mobile interfaces, iOS apps, touch-first design |
| `typography.md` | Typography decisions, font pairing, type scales, grid systems |

## Relationship to Other Skills

`/design-review` is standalone — it works on any frontend code, anytime.

It also serves as a **companion to `/design-builder`**. After generating a design system, run `/design-review` on any page or component to validate the output against design theory.

```
/prd-builder        → defines what to build
/design-builder     → generates the design system
/design-review      → validates design quality  ← you are here
```

## Anti-Patterns It Flags

- **Mystery meat navigation** — Icons without labels, ambiguous symbols
- **Ghost affordances** — Interactive elements that look static
- **Zombie toggles** — Settings that don't visibly do anything
- **False floors** — Content below the fold with no scroll signal
- **The paradox of choice** — Equal-weight options that paralyze users
- **Disabled without explanation** — Grayed-out buttons with no hint why
- **Modals on modals** — Stacked contexts that destroy spatial orientation
- **Scroll kidnapping** — Custom scroll that fights muscle memory
- **Junk drawer settings** — Every option dumped on one screen
