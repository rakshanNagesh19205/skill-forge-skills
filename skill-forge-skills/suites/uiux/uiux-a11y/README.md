# UI/UX Accessibility — WCAG & Inclusive Design

## Quick Start

This skill audits and fixes accessibility issues for WCAG 2.1 Level AA compliance.

## When to Use

- Auditing interfaces for accessibility
- Fixing screen reader issues
- Implementing keyboard navigation
- Checking color contrast
- Building accessible components

## WCAG POUR Principles

- **Perceivable** — Can users perceive all content?
- **Operable** — Can users operate all controls?
- **Understandable** — Is content understandable?
- **Robust** — Does it work with assistive tech?

## Quick Triggers

```
a11y-audit  → Full accessibility audit
contrast    → Check color contrast
keyboard    → Keyboard navigation review
aria        → ARIA implementation help
focus       → Focus management patterns
```

## Critical Requirements

- **Contrast:** 4.5:1 for text, 3:1 for UI
- **Keyboard:** All functionality via keyboard
- **Focus:** Visible focus indicator
- **Alt text:** Meaningful images described
- **Labels:** All form inputs labeled
- **Semantics:** Proper HTML elements

## Testing Tools

- axe DevTools (browser extension)
- Lighthouse (Chrome DevTools)
- VoiceOver (macOS) / NVDA (Windows)
- Keyboard-only navigation

## First Rule of ARIA

Don't use ARIA if you can use native HTML.

`<button>` is better than `<div role="button">`
