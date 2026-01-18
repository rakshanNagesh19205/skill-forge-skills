---
name: uiux-systems
description: |
  Design system foundations skill. Creates and manages design tokens, spacing scales,
  typography systems, color palettes, and component APIs. Use when building from scratch
  or establishing consistent design foundations. Defaults to Swiss design principles.
license: MIT
---

# UI/UX Design Systems — Foundations & Architecture

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "create design tokens", "set up design system", "build foundations"
- "spacing scale", "typography system", "color palette"
- "component API", "theming", "design variables"
- "start from scratch", "new project setup"

**Quick Triggers:**
- `tokens` → Generate complete token system
- `spacing` → Create spacing scale
- `typography` → Build type system
- `colors` → Design color palette
- `theme` → Set up theming architecture

**Smart Defaults:**
- Design philosophy: Swiss (International Typographic Style)
- Spacing base: 4px (mathematical progression)
- Type scale ratio: 1.25 (Major Third)
- Color model: HSL for systematic variations
- Output format: CSS custom properties + Tailwind config
- Naming convention: Semantic (not descriptive)

---

## Core Mental Model: Systems Thinking

```
┌─────────────────────────────────────────────────────────────────────┐
│                    DESIGN SYSTEM ARCHITECTURE                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  LAYER 1: PRIMITIVES (Raw Values)                                   │
│  ─────────────────────────────────                                  │
│  Colors: hsl(220, 13%, 18%)                                         │
│  Sizes: 4, 8, 12, 16, 24, 32, 48, 64, 96                           │
│  Fonts: "Söhne", system-ui                                          │
│                         │                                           │
│                         ▼                                           │
│  LAYER 2: TOKENS (Named Abstractions)                               │
│  ─────────────────────────────────────                              │
│  --color-surface-primary                                            │
│  --space-md                                                         │
│  --font-family-body                                                 │
│                         │                                           │
│                         ▼                                           │
│  LAYER 3: COMPONENTS (Composed Patterns)                            │
│  ─────────────────────────────────────────                          │
│  Button uses: surface-primary, space-md, font-body                  │
│  Card uses: surface-secondary, space-lg, radius-md                  │
│                         │                                           │
│                         ▼                                           │
│  LAYER 4: LAYOUTS (Page Compositions)                               │
│  ───────────────────────────────────────                            │
│  Swiss grid, component placement, responsive rules                  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

**Key Principle:** Changes at Layer 1 cascade through all layers. This is the power of systematic design.

---

## Section 1: Spacing System

### The 4px Base Unit (Swiss Grid Foundation)

Swiss design relies on mathematical grids. We use 4px as the atomic unit:

```
SPACING SCALE (4px base):

--space-0:   0px      (none)
--space-1:   4px      (tight)
--space-2:   8px      (compact)
--space-3:   12px     (snug)
--space-4:   16px     (base)
--space-5:   20px     (comfortable)
--space-6:   24px     (relaxed)
--space-8:   32px     (loose)
--space-10:  40px     (spacious)
--space-12:  48px     (airy)
--space-16:  64px     (section)
--space-20:  80px     (hero)
--space-24:  96px     (dramatic)
```

### Semantic Spacing Aliases

```css
:root {
  /* Component spacing */
  --space-component-padding: var(--space-4);
  --space-component-gap: var(--space-3);
  
  /* Section spacing */
  --space-section-padding: var(--space-12);
  --space-section-gap: var(--space-8);
  
  /* Inline spacing */
  --space-inline-xs: var(--space-1);
  --space-inline-sm: var(--space-2);
  --space-inline-md: var(--space-3);
  --space-inline-lg: var(--space-4);
}
```

### Tailwind Integration

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    spacing: {
      '0': '0px',
      '1': '4px',
      '2': '8px',
      '3': '12px',
      '4': '16px',
      '5': '20px',
      '6': '24px',
      '8': '32px',
      '10': '40px',
      '12': '48px',
      '16': '64px',
      '20': '80px',
      '24': '96px',
    }
  }
}
```

---

## Section 2: Typography System

### Swiss Typography Principles

1. **Sans-serif only** — Clarity over decoration
2. **Limited weights** — Maximum 3 (regular, medium, bold)
3. **Mathematical scale** — Ratio-based sizing
4. **Flush-left alignment** — Ragged right edge
5. **Generous line-height** — Readability first

### Type Scale (1.25 Major Third)

```
BASE: 16px

--text-xs:    12.80px  (0.8rem)    — Fine print
--text-sm:    14.40px  (0.9rem)    — Secondary
--text-base:  16.00px  (1rem)      — Body
--text-lg:    20.00px  (1.25rem)   — Lead
--text-xl:    25.00px  (1.563rem)  — H4
--text-2xl:   31.25px  (1.953rem)  — H3
--text-3xl:   39.06px  (2.441rem)  — H2
--text-4xl:   48.83px  (3.052rem)  — H1
--text-5xl:   61.04px  (3.815rem)  — Display
```

### Font Stack Recommendations (NOT Inter/Roboto)

**Swiss-Appropriate Sans-Serif Options:**

```css
/* Option 1: Söhne (Klim Type) — Modern Swiss */
--font-family-sans: "Söhne", system-ui, sans-serif;

/* Option 2: Helvetica Neue — Classic Swiss */
--font-family-sans: "Helvetica Neue", Helvetica, Arial, sans-serif;

/* Option 3: Untitled Sans — Contemporary Swiss */
--font-family-sans: "Untitled Sans", system-ui, sans-serif;

/* Option 4: Akzidenz-Grotesk — Historical Swiss */
--font-family-sans: "Akzidenz-Grotesk", system-ui, sans-serif;

/* Option 5: Univers — Frutiger's Masterpiece */
--font-family-sans: "Univers", system-ui, sans-serif;

/* Free Alternative: IBM Plex Sans */
--font-family-sans: "IBM Plex Sans", system-ui, sans-serif;
```

**Anti-Pattern Fonts (Avoid):**
- ❌ Inter (overused AI aesthetic)
- ❌ Roboto (Google generic)
- ❌ Open Sans (dated)
- ❌ Poppins (trendy, not Swiss)

### Complete Typography Tokens

```css
:root {
  /* Font Families */
  --font-family-sans: "IBM Plex Sans", system-ui, sans-serif;
  --font-family-mono: "IBM Plex Mono", ui-monospace, monospace;
  
  /* Font Sizes */
  --text-xs: 0.8rem;
  --text-sm: 0.9rem;
  --text-base: 1rem;
  --text-lg: 1.25rem;
  --text-xl: 1.563rem;
  --text-2xl: 1.953rem;
  --text-3xl: 2.441rem;
  --text-4xl: 3.052rem;
  --text-5xl: 3.815rem;
  
  /* Font Weights */
  --font-weight-regular: 400;
  --font-weight-medium: 500;
  --font-weight-bold: 700;
  
  /* Line Heights */
  --leading-none: 1;
  --leading-tight: 1.25;
  --leading-snug: 1.375;
  --leading-normal: 1.5;
  --leading-relaxed: 1.625;
  --leading-loose: 2;
  
  /* Letter Spacing */
  --tracking-tighter: -0.05em;
  --tracking-tight: -0.025em;
  --tracking-normal: 0;
  --tracking-wide: 0.025em;
  --tracking-wider: 0.05em;
}
```

---

## Section 3: Color System

### Swiss Color Philosophy

Swiss design uses color **purposefully**, not decoratively:
- Limited palette (3-5 colors maximum)
- High contrast for legibility
- Color indicates meaning, not style
- Neutral base with intentional accents

### HSL-Based Color Architecture

```css
:root {
  /* 
   * NEUTRALS (Swiss gray scale)
   * Using HSL for systematic light/dark variations
   */
  --gray-50:  hsl(220, 13%, 95%);
  --gray-100: hsl(220, 13%, 91%);
  --gray-200: hsl(220, 13%, 82%);
  --gray-300: hsl(220, 13%, 69%);
  --gray-400: hsl(220, 13%, 55%);
  --gray-500: hsl(220, 13%, 42%);
  --gray-600: hsl(220, 13%, 33%);
  --gray-700: hsl(220, 13%, 25%);
  --gray-800: hsl(220, 13%, 18%);
  --gray-900: hsl(220, 13%, 11%);
  --gray-950: hsl(220, 13%, 6%);
  
  /*
   * ACCENT (Single intentional color)
   * Swiss design: one accent, used sparingly
   */
  --accent-hue: 220;
  --accent-sat: 65%;
  --accent: hsl(var(--accent-hue), var(--accent-sat), 50%);
  --accent-light: hsl(var(--accent-hue), var(--accent-sat), 65%);
  --accent-dark: hsl(var(--accent-hue), var(--accent-sat), 35%);
  
  /*
   * SEMANTIC COLORS
   * Meaning-based, not appearance-based
   */
  --color-success: hsl(142, 71%, 45%);
  --color-warning: hsl(38, 92%, 50%);
  --color-error: hsl(0, 84%, 60%);
  --color-info: hsl(200, 98%, 39%);
}
```

### Semantic Surface & Text Tokens

```css
:root {
  /* Surface colors (backgrounds) */
  --surface-primary: var(--gray-50);
  --surface-secondary: var(--gray-100);
  --surface-tertiary: var(--gray-200);
  --surface-inverse: var(--gray-900);
  
  /* Text colors */
  --text-primary: var(--gray-900);
  --text-secondary: var(--gray-600);
  --text-tertiary: var(--gray-500);
  --text-inverse: var(--gray-50);
  --text-accent: var(--accent);
  
  /* Border colors */
  --border-default: var(--gray-200);
  --border-strong: var(--gray-300);
  --border-focus: var(--accent);
}

/* Dark theme override */
[data-theme="dark"] {
  --surface-primary: var(--gray-900);
  --surface-secondary: var(--gray-800);
  --surface-tertiary: var(--gray-700);
  --surface-inverse: var(--gray-50);
  
  --text-primary: var(--gray-50);
  --text-secondary: var(--gray-400);
  --text-tertiary: var(--gray-500);
  --text-inverse: var(--gray-900);
  
  --border-default: var(--gray-700);
  --border-strong: var(--gray-600);
}
```

---

## Section 4: Component Architecture

### Component Token Pattern

Every component should reference tokens, not raw values:

```css
/* ❌ WRONG: Raw values */
.button {
  padding: 12px 24px;
  background: #3b82f6;
  font-size: 14px;
}

/* ✅ CORRECT: Token references */
.button {
  padding: var(--space-3) var(--space-6);
  background: var(--accent);
  font-size: var(--text-sm);
}
```

### Button Component Token Map

```css
:root {
  /* Button tokens */
  --button-padding-y: var(--space-2);
  --button-padding-x: var(--space-4);
  --button-font-size: var(--text-sm);
  --button-font-weight: var(--font-weight-medium);
  --button-border-radius: var(--radius-sm);
  
  /* Button variants */
  --button-primary-bg: var(--accent);
  --button-primary-text: white;
  --button-primary-hover-bg: var(--accent-dark);
  
  --button-secondary-bg: transparent;
  --button-secondary-text: var(--text-primary);
  --button-secondary-border: var(--border-strong);
  --button-secondary-hover-bg: var(--surface-secondary);
}
```

### Radius Tokens

```css
:root {
  --radius-none: 0;
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-full: 9999px;
}
```

### Shadow Tokens (Swiss: Subtle)

Swiss design uses shadow sparingly for subtle elevation:

```css
:root {
  --shadow-xs: 0 1px 2px hsl(220 13% 20% / 0.05);
  --shadow-sm: 0 2px 4px hsl(220 13% 20% / 0.05);
  --shadow-md: 0 4px 8px hsl(220 13% 20% / 0.08);
  --shadow-lg: 0 8px 16px hsl(220 13% 20% / 0.1);
  --shadow-xl: 0 16px 32px hsl(220 13% 20% / 0.12);
}
```

---

## Section 5: Grid System (Swiss Foundation)

### Modular Grid Architecture

```css
:root {
  /* Grid fundamentals */
  --grid-columns: 12;
  --grid-gutter: var(--space-6);
  --grid-margin: var(--space-8);
  
  /* Container widths */
  --container-sm: 640px;
  --container-md: 768px;
  --container-lg: 1024px;
  --container-xl: 1280px;
  --container-2xl: 1536px;
}

/* Swiss grid container */
.swiss-grid {
  display: grid;
  grid-template-columns: repeat(var(--grid-columns), 1fr);
  gap: var(--grid-gutter);
  max-width: var(--container-xl);
  margin: 0 auto;
  padding: 0 var(--grid-margin);
}
```

### Responsive Breakpoints

```css
:root {
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
  --breakpoint-2xl: 1536px;
}
```

---

## Section 6: Complete Token Export

### Full CSS Custom Properties File

```css
/* tokens.css — Swiss Design System */

:root {
  /* ═══════════════════════════════════════════════════════════════
     SPACING
     ═══════════════════════════════════════════════════════════════ */
  --space-0: 0px;
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;

  /* ═══════════════════════════════════════════════════════════════
     TYPOGRAPHY
     ═══════════════════════════════════════════════════════════════ */
  --font-family-sans: "IBM Plex Sans", system-ui, sans-serif;
  --font-family-mono: "IBM Plex Mono", ui-monospace, monospace;
  
  --text-xs: 0.8rem;
  --text-sm: 0.9rem;
  --text-base: 1rem;
  --text-lg: 1.25rem;
  --text-xl: 1.563rem;
  --text-2xl: 1.953rem;
  --text-3xl: 2.441rem;
  --text-4xl: 3.052rem;
  --text-5xl: 3.815rem;
  
  --font-weight-regular: 400;
  --font-weight-medium: 500;
  --font-weight-bold: 700;
  
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.625;

  /* ═══════════════════════════════════════════════════════════════
     COLORS
     ═══════════════════════════════════════════════════════════════ */
  --gray-50: hsl(220, 13%, 95%);
  --gray-100: hsl(220, 13%, 91%);
  --gray-200: hsl(220, 13%, 82%);
  --gray-300: hsl(220, 13%, 69%);
  --gray-400: hsl(220, 13%, 55%);
  --gray-500: hsl(220, 13%, 42%);
  --gray-600: hsl(220, 13%, 33%);
  --gray-700: hsl(220, 13%, 25%);
  --gray-800: hsl(220, 13%, 18%);
  --gray-900: hsl(220, 13%, 11%);
  
  --accent: hsl(220, 65%, 50%);
  --accent-light: hsl(220, 65%, 65%);
  --accent-dark: hsl(220, 65%, 35%);
  
  /* Semantic */
  --surface-primary: var(--gray-50);
  --surface-secondary: var(--gray-100);
  --text-primary: var(--gray-900);
  --text-secondary: var(--gray-600);
  --border-default: var(--gray-200);

  /* ═══════════════════════════════════════════════════════════════
     RADIUS & SHADOW
     ═══════════════════════════════════════════════════════════════ */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  
  --shadow-sm: 0 2px 4px hsl(220 13% 20% / 0.05);
  --shadow-md: 0 4px 8px hsl(220 13% 20% / 0.08);
  --shadow-lg: 0 8px 16px hsl(220 13% 20% / 0.1);

  /* ═══════════════════════════════════════════════════════════════
     GRID
     ═══════════════════════════════════════════════════════════════ */
  --grid-columns: 12;
  --grid-gutter: var(--space-6);
  --container-max: 1280px;
}
```

---

## Output Requirements

Every design system output MUST:

1. **Use token references** — Never raw values in final output
2. **Include semantic layer** — Both primitive and semantic tokens
3. **Support theming** — Dark mode ready from start
4. **Export multiple formats** — CSS variables + Tailwind config
5. **Document decisions** — Why these values were chosen

---

## Pre-Output Validation (User-Lens Review)

Before delivering any design system output:

```
┌─────────────────────────────────────────────────────────────────────┐
│              DESIGN SYSTEMS VALIDATION CHECKLIST                     │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. MATHEMATICAL CONSISTENCY                                        │
│     □ Spacing follows 4px base progression?                         │
│     □ Type scale uses consistent ratio?                             │
│     □ No arbitrary "magic numbers"?                                 │
│                                                                     │
│  2. SWISS DESIGN COMPLIANCE                                         │
│     □ Sans-serif font selected (not Inter/Roboto)?                  │
│     □ Color palette is restrained (≤5 colors)?                      │
│     □ Grid system is modular?                                       │
│                                                                     │
│  3. COMPLETENESS                                                    │
│     □ Tokens cover: spacing, type, color, radius, shadow?           │
│     □ Semantic aliases provided?                                    │
│     □ Dark theme tokens included?                                   │
│                                                                     │
│  4. USABILITY                                                       │
│     □ Can developer copy-paste and use immediately?                 │
│     □ Naming is intuitive?                                          │
│     □ Output format matches their stack (CSS/Tailwind)?             │
│                                                                     │
│  5. ASSUMPTIONS SURFACED                                            │
│     □ Stated the base unit (4px)?                                   │
│     □ Stated the type scale ratio?                                  │
│     □ Stated font recommendations?                                  │
│                                                                     │
│  IF ANY CHECK FAILS → Revise before delivering                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Starter Prompts

### Generate Complete Token System
```
Create a complete design token system for my [project type].
I'm using [React/Vue/vanilla] with [Tailwind/CSS].
```

### Spacing Scale Only
```
Generate a spacing scale for my project.
Base unit: [4px/8px]
```

### Typography System Only
```
Set up a typography system.
Font: [font name or "recommend one"]
Scale ratio: [1.25/1.333/1.5]
```

### Color Palette Only
```
Create a Swiss-style color palette.
Primary accent: [color or "your choice"]
Theme: [light only/dark only/both]
```

---

## Examples

### Example 1: Complete Token System Request

**Input:**
```
Create design tokens for a SaaS dashboard. React + Tailwind.
```

**Output:**
```typescript
// tokens.ts — SaaS Dashboard Design System

export const tokens = {
  // Spacing (4px base)
  space: {
    0: '0px',
    1: '4px',
    2: '8px',
    3: '12px',
    4: '16px',
    6: '24px',
    8: '32px',
    12: '48px',
    16: '64px',
  },
  
  // Typography (1.25 scale)
  fontSize: {
    xs: '0.8rem',
    sm: '0.9rem',
    base: '1rem',
    lg: '1.25rem',
    xl: '1.563rem',
    '2xl': '1.953rem',
    '3xl': '2.441rem',
  },
  
  // Colors (Swiss restrained palette)
  colors: {
    gray: {
      50: 'hsl(220, 13%, 95%)',
      100: 'hsl(220, 13%, 91%)',
      // ... full scale
      900: 'hsl(220, 13%, 11%)',
    },
    accent: {
      DEFAULT: 'hsl(220, 65%, 50%)',
      light: 'hsl(220, 65%, 65%)',
      dark: 'hsl(220, 65%, 35%)',
    },
  },
} as const;

// tailwind.config.ts integration
export const tailwindConfig = {
  theme: {
    extend: {
      spacing: tokens.space,
      fontSize: tokens.fontSize,
      colors: tokens.colors,
    },
  },
};
```

**Assumptions I made:**
- 4px base unit for spacing
- 1.25 (Major Third) type scale
- Blue accent (hue 220) — adjust if brand requires different
- IBM Plex Sans as font recommendation

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 📝 Generate the CSS custom properties version
[2] 🎨 Change the accent color to [specify]
[3] 📐 Add component-specific tokens (buttons, cards, etc.)
[4] 🌙 Add dark theme tokens
[5] ✅ This works, move to visual design (uiux-visual)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════

---

## Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "Design Systems / Tokens"
  description: |
    Edge cases specific to building design systems and token architectures.
  
  cases:
    - id: arbitrary_values
      scenario: "User provides inconsistent spacing values"
      naive_failure: "Uses the arbitrary values as-is"
      expert_behavior: "Maps to nearest systematic value, explains why"
      test_input: "My spacing needs: 7px, 13px, 22px, 47px"
      must_check:
        - "Maps to systematic 4px-based values"
        - "Explains why systematic > arbitrary"
        - "Shows the mapping (7→8, 13→12, etc.)"
      anti_patterns:
        - "Using 7px, 13px directly in tokens"
        - "No explanation of systematic approach"
    
    - id: overused_fonts
      scenario: "User requests Inter or Roboto"
      naive_failure: "Uses Inter/Roboto without comment"
      expert_behavior: "Suggests Swiss-appropriate alternatives"
      test_input: "Use Inter for the typography"
      must_check:
        - "Acknowledges the request"
        - "Suggests alternatives (IBM Plex, Söhne, etc.)"
        - "Explains why Swiss design avoids overused fonts"
      anti_patterns:
        - "Silently using Inter"
        - "No mention of Swiss typography principles"
    
    - id: too_many_colors
      scenario: "User wants extensive color palette"
      naive_failure: "Generates 20+ color variations"
      expert_behavior: "Constrains to Swiss-appropriate palette size"
      test_input: "I need colors for every emotion and state"
      must_check:
        - "Limits to core neutral + 1 accent"
        - "Semantic colors for states (success, error)"
        - "Explains Swiss color restraint"
      anti_patterns:
        - "Here's your 50 color palette"
        - "Purple, teal, orange, pink all as primaries"
    
    - id: missing_semantic_layer
      scenario: "User only wants primitive tokens"
      naive_failure: "Only provides gray-100, gray-200, etc."
      expert_behavior: "Includes semantic layer for maintainability"
      test_input: "Just give me the raw color values"
      must_check:
        - "Provides primitives as requested"
        - "Also includes semantic aliases"
        - "Explains why semantic layer matters"
      anti_patterns:
        - "Only primitive tokens, no semantic layer"
        - "User must figure out when to use gray-600 vs gray-700"
```
