---
name: uiux-index
description: |
  Hub skill for the comprehensive UI/UX design suite. Routes users to the right 
  specialized skill based on their current task. Covers design systems, visual design,
  interaction, usability, and accessibility. Defaults to Swiss design principles
  and React Bits components.
license: MIT
---

# UI/UX Design Suite — Index & Router

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "help me with UI", "help me with UX", "design help"
- "I need to design", "fix my interface", "improve this UI"
- "where do I start with design", "which skill should I use"

**Quick Triggers:**
- `uiux` → Show skill router
- `design from scratch` → Route to uiux-systems
- `fix existing` → Route to uiux-usability
- `make it pretty` → Route to uiux-visual
- `add animations` → Route to uiux-interaction
- `accessibility check` → Route to uiux-a11y

**Smart Defaults:**
- Design philosophy: Swiss (International Typographic Style)
- Component source: React Bits (reactbits.dev)
- Framework assumption: React (state if different)
- Styling: Tailwind CSS preferred, vanilla CSS supported
- Responsive: Mobile-first approach

---

## Available Skills in This Suite

| Skill | Use When You Need | Key Capabilities |
|-------|-------------------|------------------|
| `uiux-systems` | Building foundations from scratch | Design tokens, spacing scales, component APIs, theming |
| `uiux-visual` | Styling, visual polish, brand alignment | Swiss grids, typography, color theory, composition |
| `uiux-interaction` | Adding motion and interactivity | React Bits components, animations, micro-interactions |
| `uiux-usability` | Auditing or improving existing UIs | Heuristic evaluation, user flows, UX fixes |
| `uiux-a11y` | Making interfaces accessible | WCAG compliance, screen readers, keyboard nav |

---

## Quick Router

**What are you working on?**

```
[1] 🏗️  Starting a new project from scratch
    → uiux-systems (foundations first, then others)

[2] 🎨  Making something look better / applying Swiss design
    → uiux-visual

[3] ✨  Adding animations, interactions, React Bits components
    → uiux-interaction

[4] 🔧  Fixing or improving an existing interface
    → uiux-usability

[5] ♿  Making an interface accessible / WCAG audit
    → uiux-a11y

[6] 🤔  Not sure / multiple concerns
    → Describe your situation below
```

---

## Cross-Skill Workflows

### New Project (Complete Path)
```
uiux-systems → uiux-visual → uiux-interaction → uiux-a11y
     │              │              │               │
  Tokens,       Swiss grid,    React Bits,    WCAG audit,
  spacing,      typography,    animations,    final polish
  foundations   color          micro-fx
```

### Redesign Existing UI
```
uiux-usability → uiux-visual → uiux-a11y
      │              │             │
  Audit current,  Apply Swiss   Accessibility
  identify gaps   principles    verification
```

### Quick Enhancement
```
uiux-interaction (standalone)
      │
  Add React Bits components
  to existing interface
```

---

## Swiss Design Principles (Applied Across All Skills)

Every skill in this suite defaults to Swiss/International Typographic Style:

### Core Principles
1. **Mathematical Grid System** — All layouts built on modular grids
2. **Sans-Serif Typography** — Clean, legible typefaces (not Inter/Roboto)
3. **Asymmetrical Balance** — Left-aligned, ragged-right text
4. **Objective Photography** — Images serve information, not decoration
5. **Minimal Ornamentation** — Every element must earn its place
6. **Clarity Over Cleverness** — Communication first, style second

### Visual Markers
- Flush-left text alignment
- Strong visual hierarchy through scale
- Generous whitespace
- Limited color palette with intentional accents
- Grid-breaking elements used sparingly for emphasis

---

## React Bits Integration (Across All Skills)

Components sourced from reactbits.dev are the default for:
- Text animations (SplitText, BlurText, etc.)
- UI components (AnimatedList, Dock, etc.)
- Background effects (Particles, Aurora, etc.)
- Interactive elements (Magnet, Tilt, etc.)

**Installation patterns supported:**
```bash
# shadcn CLI
npx shadcn@latest add @react-bits/ComponentName-TS-TW

# jsrepo CLI  
npx jsrepo add https://reactbits.dev/ts/tailwind/Component

# Manual copy-paste (always available)
```

**Variants available:**
- JS-CSS (JavaScript + Plain CSS)
- JS-TW (JavaScript + Tailwind)
- TS-CSS (TypeScript + Plain CSS)
- TS-TW (TypeScript + Tailwind) ← default recommendation

---

## Routing Logic

When user request is ambiguous, apply this decision tree:

```
User Request
     │
     ▼
┌─────────────────────────────────────┐
│ Does request mention "from scratch" │
│ "new project" or "foundations"?     │
└─────────────────────────────────────┘
     │
   YES → uiux-systems
     │
    NO
     │
     ▼
┌─────────────────────────────────────┐
│ Does request mention "fix", "audit" │
│ "improve", or "existing"?           │
└─────────────────────────────────────┘
     │
   YES → uiux-usability
     │
    NO
     │
     ▼
┌─────────────────────────────────────┐
│ Does request mention "animation",   │
│ "motion", "interactive", "React     │
│ Bits", or specific component?       │
└─────────────────────────────────────┘
     │
   YES → uiux-interaction
     │
    NO
     │
     ▼
┌─────────────────────────────────────┐
│ Does request mention "accessible",  │
│ "WCAG", "screen reader", "a11y"?    │
└─────────────────────────────────────┘
     │
   YES → uiux-a11y
     │
    NO
     │
     ▼
┌─────────────────────────────────────┐
│ Does request involve visual styling │
│ typography, color, or layout?       │
└─────────────────────────────────────┘
     │
   YES → uiux-visual
     │
    NO → Ask clarifying question with numbered options
```

---

## What This Suite Does NOT Do

This suite is NOT designed for:
- ❌ Backend development or API design
- ❌ Database schema or data modeling
- ❌ DevOps, deployment, or CI/CD
- ❌ Native mobile development (iOS/Android specific)
- ❌ Game UI or 3D interface design
- ❌ Print design or non-digital media

If you need these capabilities, consider other specialized skills.

---

## Starter Prompts

### Route Me to the Right Skill
```
I need to [describe your task]. Which UI/UX skill should I use?
```

### Start a New Project
```
I'm building a [type of application] from scratch. 
Walk me through the design process.
```

### Fix Something Existing
```
Here's my current interface: [paste code or describe].
It has these problems: [list issues].
Help me fix it.
```

---

## Follow-Up Menu Template

After routing, always offer:

```
═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🚀 Proceed with [recommended skill]
[2] 📚 Learn more about what [skill] covers
[3] 🔄 Actually, I need a different skill
[4] 🎯 Show me an example of [skill] output first
[5] 🤔 I have a complex project spanning multiple skills

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════
```

---

## Pre-Output Validation

Before delivering any routing recommendation:

1. **Intent Match**: Did I understand what they're actually trying to accomplish?
2. **Skill Fit**: Is the recommended skill genuinely the best fit?
3. **Assumptions Surfaced**: Did I state what I assumed about their project?
4. **Actionable**: Can they immediately proceed with my recommendation?
5. **Alternatives Offered**: Did I mention when another skill might also help?

**If any check fails** → Revise recommendation before delivering.

---

## Examples

### Example 1: Ambiguous Request → Clarified Routing

**Input:**
```
I need help with my website design
```

**Output:**
```
I can help with your website design! To route you to the right skill:

**What's your current situation?**

[1] 🏗️ Starting fresh — need to set up design foundations
    → I'll use uiux-systems

[2] 🎨 Have a working site, want it to look better
    → I'll use uiux-visual (Swiss design principles)

[3] ✨ Want to add animations or interactive components
    → I'll use uiux-interaction (React Bits)

[4] 🔧 Site has UX problems I need to fix
    → I'll use uiux-usability

[5] ♿ Need to make it accessible
    → I'll use uiux-a11y

Pick a number or tell me more about what you're working on.
```

### Example 2: Clear Request → Direct Routing

**Input:**
```
I want to add some animated text effects to my landing page
```

**Output:**
```
Perfect — that's an **uiux-interaction** task.

I'll help you add animated text effects using React Bits components. 
The library has several text animation options:

- **SplitText** — Character-by-character reveal
- **BlurText** — Blur-in effect
- **GradientText** — Animated gradient fill
- **RotatingText** — Word rotation/swap

**Assumptions I'm making:**
- You're using React
- You want Tailwind + TypeScript variant
- Landing page is already built, just adding effects

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] ✨ Show me SplitText implementation
[2] 📋 Compare all text animation options
[3] 🔧 I'm using vanilla JS, not React
[4] 🎨 I also want to improve the overall visual design
[5] ✅ Proceed with your assumptions

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════
```

---

## Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "UI/UX Skill Routing"
  description: |
    Edge cases for correctly routing users to the right specialized skill.
  
  cases:
    - id: multi_concern_request
      scenario: "User has overlapping needs spanning multiple skills"
      naive_failure: "Picks one skill arbitrarily, ignores other needs"
      expert_behavior: "Identifies all relevant skills, suggests sequence"
      test_input: "I need to redesign my dashboard - it's ugly and has usability issues"
      must_check:
        - "Identifies both uiux-visual AND uiux-usability needs"
        - "Recommends starting with usability audit"
        - "Suggests visual polish after UX fixes"
      anti_patterns:
        - "Just use uiux-visual"
        - "Ignoring the usability concern"
    
    - id: wrong_skill_assumption
      scenario: "User uses wrong terminology for their actual need"
      naive_failure: "Routes based on words used, not actual need"
      expert_behavior: "Clarifies actual need before routing"
      test_input: "I need a design system" (but they actually mean visual styling)
      must_check:
        - "Asks clarifying question about scope"
        - "Distinguishes system foundations from visual styling"
        - "Offers both interpretations"
      anti_patterns:
        - "Immediately routing to uiux-systems"
        - "Not clarifying what 'design system' means to them"
    
    - id: technology_mismatch
      scenario: "User's tech stack differs from defaults"
      naive_failure: "Assumes React when user has Vue/vanilla"
      expert_behavior: "Asks about tech stack, adjusts recommendations"
      test_input: "Add animations to my Vue app"
      must_check:
        - "Notes that React Bits is React-specific"
        - "Offers alternatives for Vue (Vue Bits or manual)"
        - "Doesn't blindly recommend React Bits"
      anti_patterns:
        - "Here's how to use React Bits in Vue"
        - "Ignoring the Vue mention"
```
