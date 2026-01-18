---
name: uiux-visual
description: |
  Visual design skill applying Swiss/International Typographic Style principles.
  Handles grids, typography, color application, whitespace, and visual composition.
  Use for making interfaces beautiful, applying brand styling, or visual polish.
  Works for both new designs and improving existing UIs.
license: MIT
---

# UI/UX Visual Design — Swiss Style Mastery

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "make it look better", "visual design", "styling"
- "apply Swiss design", "grid layout", "typography"
- "color scheme", "whitespace", "composition"
- "polish the UI", "make it beautiful"

**Quick Triggers:**
- `swiss` → Apply full Swiss design treatment
- `grid` → Set up Swiss grid layout
- `type` → Apply typography hierarchy
- `color` → Apply Swiss color principles
- `whitespace` → Optimize spacing and breathing room

**Smart Defaults:**
- Design philosophy: Swiss (International Typographic Style)
- Typography: Flush-left, sans-serif, hierarchical scale
- Grid: 12-column modular, asymmetric layouts
- Color: Restrained palette, intentional accents
- Whitespace: Generous, purposeful negative space

---

## Swiss Design Philosophy

```
┌─────────────────────────────────────────────────────────────────────┐
│                    SWISS DESIGN PRINCIPLES                           │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  "The grid system is an aid, not a guarantee. It permits a number   │
│   of possible uses and each designer can look for a solution        │
│   appropriate to his personal style."                               │
│                                    — Josef Müller-Brockmann         │
│                                                                     │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. CLARITY OVER CLEVERNESS                                         │
│     Design serves communication. Every element must earn its place. │
│                                                                     │
│  2. MATHEMATICAL ORDER                                              │
│     Grids, scales, and ratios create harmony.                       │
│                                                                     │
│  3. OBJECTIVE PRESENTATION                                          │
│     Information speaks; decoration distracts.                       │
│                                                                     │
│  4. ASYMMETRIC BALANCE                                              │
│     Dynamic tension through unequal distribution.                   │
│                                                                     │
│  5. PURPOSEFUL RESTRAINT                                            │
│     Limited palette, limited elements, maximum impact.              │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 1: Grid System (The Foundation)

### Swiss Grid Architecture

The grid is not a constraint—it's a framework for freedom within structure.

```
┌─────────────────────────────────────────────────────────────────────┐
│  12-COLUMN SWISS GRID                                               │
├──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬─────────────────────────────────┤
│ 1│ 2│ 3│ 4│ 5│ 6│ 7│ 8│ 9│10│11│12│  ← Columns                      │
├──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┤                                 │
│▓▓▓▓▓▓▓▓▓░░░░░░░░░░░░░░░░░░░░░░░░░░│  ← 4-col sidebar               │
│░░░░░░░░░░░░░░░░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓│  ← 8-col content (offset)      │
│▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░░░░░│  ← 8-col hero                  │
│░░░░░░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░│  ← 6-col centered (asymmetric) │
└─────────────────────────────────────────────────────────────────────┘
```

### Grid Implementation

```css
/* Swiss Grid Container */
.swiss-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--space-6);
  max-width: var(--container-xl);
  margin: 0 auto;
  padding: 0 var(--space-8);
}

/* Asymmetric Layout Patterns */
.layout-sidebar {
  grid-column: 1 / 5;   /* 4 columns */
}

.layout-main {
  grid-column: 5 / 13;  /* 8 columns, offset */
}

.layout-narrow {
  grid-column: 3 / 11;  /* 8 columns, centered but asymmetric */
}

.layout-wide {
  grid-column: 1 / 10;  /* 9 columns, left-heavy */
}
```

### Grid-Breaking Elements

Swiss design uses **intentional grid breaks** for emphasis:

```css
/* Element that breaks the grid for visual impact */
.grid-breaker {
  grid-column: 1 / -1;           /* Full width */
  margin-left: calc(-1 * var(--space-8));
  margin-right: calc(-1 * var(--space-8));
  padding: var(--space-12) var(--space-8);
  background: var(--surface-secondary);
}

/* Overlapping elements for dynamic tension */
.overlap-left {
  margin-left: calc(-1 * var(--space-16));
}
```

---

## Section 2: Typography in Practice

### The Hierarchy Principle

Swiss typography creates clear information architecture through scale and weight alone:

```
┌─────────────────────────────────────────────────────────────────────┐
│  TYPOGRAPHY HIERARCHY                                                │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  DISPLAY          48px / Bold / -0.02em tracking                    │
│  ───────────────────────────────────────────────                    │
│  The primary statement. One per page. Demands attention.            │
│                                                                     │
│  HEADLINE         31px / Bold / -0.01em tracking                    │
│  ─────────────────────────────────────                              │
│  Section headers. Creates content blocks.                           │
│                                                                     │
│  SUBHEAD          20px / Medium / 0 tracking                        │
│  ───────────────────────────────                                    │
│  Secondary divisions within sections.                               │
│                                                                     │
│  Body             16px / Regular / 0 tracking / 1.5 line-height     │
│  The primary reading text. Optimized for extended reading.          │
│                                                                     │
│  Caption          14px / Regular / 0.01em tracking                  │
│  Supporting information, metadata, secondary content.               │
│                                                                     │
│  OVERLINE         12px / MEDIUM / 0.1EM TRACKING / UPPERCASE        │
│  Labels, categories, eyebrows above headlines.                      │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Typography CSS Implementation

```css
/* Display — Hero text */
.text-display {
  font-size: var(--text-4xl);
  font-weight: var(--font-weight-bold);
  letter-spacing: -0.02em;
  line-height: var(--leading-tight);
}

/* Headline — Section headers */
.text-headline {
  font-size: var(--text-2xl);
  font-weight: var(--font-weight-bold);
  letter-spacing: -0.01em;
  line-height: var(--leading-tight);
}

/* Subhead — Subsection headers */
.text-subhead {
  font-size: var(--text-lg);
  font-weight: var(--font-weight-medium);
  line-height: var(--leading-snug);
}

/* Body — Reading text */
.text-body {
  font-size: var(--text-base);
  font-weight: var(--font-weight-regular);
  line-height: var(--leading-relaxed);
}

/* Caption — Secondary text */
.text-caption {
  font-size: var(--text-sm);
  font-weight: var(--font-weight-regular);
  color: var(--text-secondary);
}

/* Overline — Labels */
.text-overline {
  font-size: var(--text-xs);
  font-weight: var(--font-weight-medium);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-tertiary);
}
```

### Flush-Left Text (Swiss Standard)

```css
/* Swiss text alignment */
.swiss-text {
  text-align: left;              /* Always flush-left */
  hyphens: none;                 /* No hyphenation */
  text-wrap: pretty;             /* Modern: avoid orphans */
}

/* Measure (line length) for readability */
.readable-measure {
  max-width: 65ch;               /* Optimal line length */
}
```

---

## Section 3: Color Application

### The Restraint Principle

Swiss design uses color **purposefully**, not decoratively:

```
┌─────────────────────────────────────────────────────────────────────┐
│  SWISS COLOR PHILOSOPHY                                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  NEUTRAL BASE        90% of the interface                           │
│  ────────────────────────────────────                               │
│  Grays provide the foundation. Content lives here.                  │
│                                                                     │
│  SINGLE ACCENT       10% of the interface                           │
│  ───────────────────                                                │
│  One color for: primary actions, links, emphasis.                   │
│  Used sparingly = maximum impact.                                   │
│                                                                     │
│  SEMANTIC COLORS     Only when meaning requires                     │
│  ──────────────────────────────────────────────                     │
│  Success (green), Error (red), Warning (yellow)                     │
│  Never decorative. Always informational.                            │
│                                                                     │
│  ❌ ANTI-PATTERNS:                                                  │
│  • Gradients for decoration                                         │
│  • Multiple accent colors competing                                 │
│  • Color coding everything                                          │
│  • "Colorful" UI with no hierarchy                                  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Color Application Rules

```css
/* Surface hierarchy (subtle variation) */
.surface-page     { background: var(--gray-50); }   /* Page background */
.surface-card     { background: white; }             /* Elevated cards */
.surface-sunken   { background: var(--gray-100); }  /* Inset areas */

/* Text hierarchy (3 levels maximum) */
.text-emphasis    { color: var(--gray-900); }       /* Headlines, key info */
.text-default     { color: var(--gray-700); }       /* Body text */
.text-subdued     { color: var(--gray-500); }       /* Secondary info */

/* Accent usage (sparingly) */
.accent-interactive { color: var(--accent); }        /* Links, buttons */
.accent-highlight   { background: var(--accent); }   /* Primary CTA only */
```

### Contrast Requirements

```
WCAG AA Contrast Minimums:
─────────────────────────
Normal text:   4.5:1 minimum
Large text:    3:1 minimum
UI components: 3:1 minimum

Swiss approach: Exceed minimums. Clarity is paramount.
```

---

## Section 4: Whitespace (Negative Space)

### The Breathing Room Principle

Whitespace is not empty—it's active. It creates:
- Visual hierarchy
- Content grouping
- Reading rhythm
- Perceived quality

```
┌─────────────────────────────────────────────────────────────────────┐
│  WHITESPACE HIERARCHY                                                │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  MICRO SPACE (4-8px)                                                │
│  Between related inline elements: icon + label, input + helper      │
│                                                                     │
│  COMPONENT SPACE (12-24px)                                          │
│  Within components: card padding, button padding                    │
│                                                                     │
│  SECTION SPACE (32-64px)                                            │
│  Between content groups: card to card, section to section           │
│                                                                     │
│  PAGE SPACE (64-96px)                                               │
│  Major divisions: hero to content, footer separation                │
│                                                                     │
│  PRINCIPLE: Related things are close. Unrelated things are far.     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Spacing Implementation

```css
/* Micro spacing */
.space-inline-tight { gap: var(--space-1); }   /* 4px */
.space-inline       { gap: var(--space-2); }   /* 8px */

/* Component spacing */
.space-component    { padding: var(--space-4); }        /* 16px */
.space-component-lg { padding: var(--space-6); }        /* 24px */

/* Section spacing */
.space-section      { margin-bottom: var(--space-12); } /* 48px */
.space-section-lg   { margin-bottom: var(--space-16); } /* 64px */

/* Page spacing */
.space-page         { padding-top: var(--space-20); }   /* 80px */
.space-page         { padding-bottom: var(--space-24); }/* 96px */
```

---

## Section 5: Visual Composition Patterns

### Asymmetric Balance

Swiss design favors asymmetry over centered layouts:

```
❌ CENTERED (Passive, Static)          ✅ ASYMMETRIC (Dynamic, Active)
┌────────────────────────────────┐    ┌────────────────────────────────┐
│                                │    │                                │
│         [ HEADLINE ]           │    │  [ HEADLINE ]                  │
│                                │    │                                │
│      [ centered content ]      │    │  [ content aligned left ]      │
│      [ sits in the middle ]    │    │  [ creates visual tension ]    │
│                                │    │                    [ element ] │
│         [ BUTTON ]             │    │  [ BUTTON ]                    │
│                                │    │                                │
└────────────────────────────────┘    └────────────────────────────────┘
```

### The Z-Pattern and F-Pattern

```
Z-PATTERN (Landing pages)        F-PATTERN (Content pages)
┌────────────────────────┐       ┌────────────────────────┐
│ LOGO ──────────▶ NAV  │       │ ████████████████████  │
│   ╲                    │       │ ████████████████████  │
│     ╲                  │       │ ████████████          │
│       ╲                │       │ ████████████████      │
│         ╲              │       │ ████████              │
│ CTA ◀─────────────────│       │ ████████████████████  │
└────────────────────────┘       └────────────────────────┘
```

### Component Composition

```css
/* Card with Swiss composition */
.swiss-card {
  display: grid;
  grid-template-rows: auto 1fr auto;
  gap: var(--space-4);
  padding: var(--space-6);
  background: white;
  border: 1px solid var(--border-default);
  
  /* Subtle elevation, not dramatic shadow */
  box-shadow: var(--shadow-sm);
}

.swiss-card__overline {
  font-size: var(--text-xs);
  font-weight: var(--font-weight-medium);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-tertiary);
}

.swiss-card__title {
  font-size: var(--text-xl);
  font-weight: var(--font-weight-bold);
  line-height: var(--leading-tight);
}

.swiss-card__body {
  color: var(--text-secondary);
  line-height: var(--leading-relaxed);
}
```

---

## Section 6: Anti-Patterns (What NOT to Do)

```
┌─────────────────────────────────────────────────────────────────────┐
│  SWISS DESIGN ANTI-PATTERNS                                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ❌ GRADIENTS FOR DECORATION                                        │
│     No linear-gradient backgrounds on buttons, headers              │
│     Exception: Data visualization where gradient = meaning          │
│                                                                     │
│  ❌ DROP SHADOWS EVERYWHERE                                         │
│     No box-shadow: 0 10px 40px rgba(0,0,0,0.3)                     │
│     Use: Subtle elevation (shadow-sm, shadow-md) sparingly          │
│                                                                     │
│  ❌ CENTERED EVERYTHING                                             │
│     No text-align: center on body text, cards, sections             │
│     Exception: Single-line CTAs, modal dialogs                      │
│                                                                     │
│  ❌ DECORATIVE ICONS                                                │
│     No icons that don't add meaning                                 │
│     Every icon must serve communication                             │
│                                                                     │
│  ❌ ROUNDED PILL SHAPES                                             │
│     No border-radius: 9999px on everything                          │
│     Use: Consistent, subtle radius from token system                │
│                                                                     │
│  ❌ MULTIPLE COMPETING ACCENTS                                      │
│     No purple AND teal AND orange                                   │
│     Use: Single accent color, semantic colors for meaning           │
│                                                                     │
│  ❌ DECORATIVE ANIMATIONS                                           │
│     No bouncing, wiggling, attention-grabbing for no reason         │
│     Use: Purposeful motion (state changes, feedback)                │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Output Requirements

Every visual design output MUST:

1. **Follow Swiss grid** — 12-column modular structure
2. **Use typography hierarchy** — Clear display → headline → body → caption
3. **Apply restrained color** — Neutral base + single accent
4. **Include generous whitespace** — Breathing room between elements
5. **Prefer asymmetry** — Flush-left, dynamic balance

---

## Pre-Output Validation (User-Lens Review)

Before delivering any visual design:

```
┌─────────────────────────────────────────────────────────────────────┐
│              VISUAL DESIGN VALIDATION CHECKLIST                      │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. SWISS COMPLIANCE                                                │
│     □ Grid-based layout (not arbitrary positioning)?                │
│     □ Typography is flush-left (not centered body text)?            │
│     □ Color palette is restrained (neutral + 1 accent)?             │
│     □ No decorative gradients or excessive shadows?                 │
│                                                                     │
│  2. HIERARCHY                                                       │
│     □ Clear visual hierarchy (what's most important is obvious)?    │
│     □ Typography scale creates information architecture?            │
│     □ Whitespace groups related content?                            │
│                                                                     │
│  3. CONTRAST & LEGIBILITY                                           │
│     □ Text meets WCAG contrast requirements?                        │
│     □ Interactive elements are clearly distinct?                    │
│     □ Nothing relies on color alone for meaning?                    │
│                                                                     │
│  4. COMPLETENESS                                                    │
│     □ All states covered (hover, focus, active, disabled)?          │
│     □ Responsive considerations mentioned?                          │
│     □ Dark theme variant addressed?                                 │
│                                                                     │
│  5. PRACTICAL                                                       │
│     □ Code is copy-paste ready?                                     │
│     □ Uses token references (not magic numbers)?                    │
│     □ Works with their stated tech stack?                           │
│                                                                     │
│  IF ANY CHECK FAILS → Revise before delivering                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Starter Prompts

### Apply Swiss Design to Existing UI
```
Here's my current component: [paste code]
Apply Swiss design principles to improve it.
```

### Design a Page Layout
```
Create a Swiss-style layout for a [page type].
Key content: [list main elements]
```

### Typography System Application
```
Apply proper typography hierarchy to this content:
[paste content structure]
```

### Color Scheme Application
```
My brand color is [color]. 
Create a Swiss-style color application for my interface.
```

---

## Examples

### Example 1: Improve Existing Card Component

**Input:**
```
Fix this card to follow Swiss design:

<div style="text-align: center; padding: 20px; 
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 20px; box-shadow: 0 10px 40px rgba(0,0,0,0.3);">
  <h3 style="color: white; font-family: Poppins;">✨ Amazing Feature</h3>
  <p style="color: white;">This feature is really great and you should use it!</p>
  <button style="background: white; border-radius: 50px; padding: 10px 30px;">
    Learn More
  </button>
</div>
```

**Output:**
```jsx
// Swiss-redesigned card component

<div className="swiss-card">
  <span className="text-overline">Feature</span>
  <h3 className="text-headline">Streamlined Workflows</h3>
  <p className="text-body text-secondary">
    Reduce complexity and focus on what matters. 
    Our approach eliminates unnecessary steps.
  </p>
  <button className="button-primary">
    Learn more
  </button>
</div>

<style>
.swiss-card {
  padding: var(--space-6);
  background: white;
  border: 1px solid var(--border-default);
  box-shadow: var(--shadow-sm);
  text-align: left;                    /* Flush-left, not centered */
  display: flex;
  flex-direction: column;
  gap: var(--space-3);
}

.text-overline {
  font-size: var(--text-xs);
  font-weight: var(--font-weight-medium);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-tertiary);
}

.text-headline {
  font-size: var(--text-xl);
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
}

.text-body {
  line-height: var(--leading-relaxed);
}

.text-secondary {
  color: var(--text-secondary);
}

.button-primary {
  align-self: flex-start;             /* Left-aligned, not centered */
  padding: var(--space-2) var(--space-4);
  background: var(--accent);
  color: white;
  border: none;
  border-radius: var(--radius-sm);
  font-weight: var(--font-weight-medium);
  cursor: pointer;
}

.button-primary:hover {
  background: var(--accent-dark);
}
</style>
```

**What changed:**
- Removed gradient background → Clean white surface
- Removed excessive shadow → Subtle elevation
- Removed centered text → Flush-left alignment
- Removed decorative emoji → Clear overline label
- Removed pill-shaped button → Consistent border-radius
- Removed Poppins → Uses system tokens
- Added proper spacing using token references

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🌙 Show dark theme variant
[2] 📱 Add responsive breakpoint styles
[3] ✨ Add subtle hover animation (Swiss-appropriate)
[4] 🎨 Adjust accent color to [specify your brand color]
[5] ✅ This works, move to interactions (uiux-interaction)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════

---

## Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "Visual Design / Swiss Style"
  description: |
    Edge cases for applying Swiss design principles correctly.
  
  cases:
    - id: gradient_removal
      scenario: "User has gradient backgrounds"
      naive_failure: "Keeps gradients or replaces with boring solid"
      expert_behavior: "Removes gradient, creates interest through typography/spacing"
      test_input: "Make this Swiss: background: linear-gradient(to right, #ff6b6b, #feca57)"
      must_check:
        - "Gradient is removed"
        - "Replaced with solid color from palette"
        - "Visual interest created through other Swiss means"
      anti_patterns:
        - "Keeping the gradient"
        - "Just making it gray with no visual interest"
    
    - id: centered_text_fix
      scenario: "User has center-aligned body text"
      naive_failure: "Keeps centered text"
      expert_behavior: "Converts to flush-left with proper measure"
      test_input: "Fix: text-align: center on a paragraph"
      must_check:
        - "Changed to text-align: left"
        - "Added max-width for readable measure"
        - "Explained Swiss typography principle"
      anti_patterns:
        - "Keeping text-align: center"
        - "No mention of flush-left principle"
    
    - id: too_many_fonts
      scenario: "User has multiple font families"
      naive_failure: "Keeps multiple fonts"
      expert_behavior: "Consolidates to single Swiss-appropriate font"
      test_input: "I'm using Poppins for headings, Open Sans for body, Lobster for accents"
      must_check:
        - "Recommends single font family"
        - "Creates hierarchy through weight/size, not font changes"
        - "Suggests Swiss-appropriate font option"
      anti_patterns:
        - "Keeping three different fonts"
        - "Suggesting Inter or Roboto"
    
    - id: excessive_shadow
      scenario: "User has dramatic drop shadows"
      naive_failure: "Keeps heavy shadows"
      expert_behavior: "Replaces with subtle elevation or border"
      test_input: "Fix: box-shadow: 0 20px 60px rgba(0,0,0,0.4)"
      must_check:
        - "Shadow reduced significantly or removed"
        - "Subtle alternative provided (shadow-sm or border)"
        - "Explained Swiss approach to elevation"
      anti_patterns:
        - "Keeping dramatic shadow"
        - "Just making shadow slightly smaller"
```
