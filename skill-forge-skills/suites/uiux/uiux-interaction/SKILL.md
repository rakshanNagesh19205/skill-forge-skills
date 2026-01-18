---
name: uiux-interaction
description: |
  Interaction design skill for adding motion, animations, and interactive components.
  Primary source: React Bits (reactbits.dev) with 110+ animated components.
  Applies Swiss-appropriate purposeful motion, not decorative animation.
  Works for both new features and enhancing existing interfaces.
license: MIT
---

# UI/UX Interaction Design — Motion & React Bits

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "add animation", "make it interactive", "add motion"
- "React Bits", "animated component", "text animation"
- "micro-interaction", "hover effect", "transition"
- "loading animation", "scroll effect", "parallax"

**Quick Triggers:**
- `animate` → Add purposeful animation to element
- `reactbits` → Browse React Bits component options
- `text-fx` → Text animation options
- `background` → Background effect options
- `hover` → Hover interaction patterns

**Smart Defaults:**
- Component source: React Bits (reactbits.dev)
- Variant: TS-TW (TypeScript + Tailwind)
- Animation philosophy: Purposeful, not decorative
- Duration: 200-400ms for micro-interactions
- Easing: ease-out for entering, ease-in for exiting

---

## React Bits Component Library

React Bits provides 110+ animated components across categories:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    REACT BITS CATEGORIES                             │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  TEXT ANIMATIONS                                                    │
│  ───────────────                                                    │
│  SplitText      — Character-by-character reveal                     │
│  BlurText       — Blur-in/out effect                                │
│  GradientText   — Animated gradient fill                            │
│  RotatingText   — Word rotation/swap                                │
│  ShinyText      — Shimmer/shine effect                              │
│  VariableProximity — Text reacts to cursor                          │
│  TextMorph      — Morphing between words                            │
│  CountUp        — Animated number counting                          │
│  ScrollReveal   — Reveal on scroll                                  │
│                                                                     │
│  UI COMPONENTS                                                      │
│  ─────────────                                                      │
│  AnimatedList   — Staggered list animations                         │
│  Dock           — macOS-style dock                                  │
│  TiltCard       — 3D tilt on hover                                  │
│  GlowCard       — Glow effect on hover                              │
│  Magnet         — Magnetic cursor attraction                        │
│  InfiniteScroll — Continuous scrolling content                      │
│  Accordion      — Animated expand/collapse                          │
│  Tabs           — Animated tab transitions                          │
│                                                                     │
│  BACKGROUNDS                                                        │
│  ───────────                                                        │
│  Particles      — Interactive particle field                        │
│  Aurora         — Northern lights effect                            │
│  Waves          — Animated wave patterns                            │
│  GridPattern    — Animated grid background                          │
│  Noise          — Subtle noise texture                              │
│  GradientMesh   — Flowing gradient mesh                             │
│                                                                     │
│  EFFECTS                                                            │
│  ───────                                                            │
│  Spotlight      — Cursor spotlight effect                           │
│  Ripple         — Click ripple effect                               │
│  Cursor         — Custom cursor styles                              │
│  Trail          — Cursor trail effect                               │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 1: Installation Methods

### shadcn CLI (Recommended)

```bash
# Pattern: @react-bits/ComponentName-LANGUAGE-STYLE
npx shadcn@latest add @react-bits/SplitText-TS-TW

# Examples
npx shadcn@latest add @react-bits/BlurText-TS-TW
npx shadcn@latest add @react-bits/AnimatedList-TS-TW
npx shadcn@latest add @react-bits/Particles-TS-TW
```

### jsrepo CLI

```bash
# Pattern: https://reactbits.dev/VARIANT/Category/Component
npx jsrepo add https://reactbits.dev/ts/tailwind/TextAnimations/SplitText

# Variants available:
# - default (JavaScript + CSS)
# - tailwind (JavaScript + Tailwind)
# - ts/default (TypeScript + CSS)
# - ts/tailwind (TypeScript + Tailwind)
```

### Manual Copy-Paste

Visit reactbits.dev, select component, choose variant, copy code directly.

---

## Section 2: Swiss-Appropriate Animation Principles

```
┌─────────────────────────────────────────────────────────────────────┐
│                    MOTION PHILOSOPHY                                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ✅ PURPOSEFUL MOTION (Swiss-Approved)                              │
│  ─────────────────────────────────────                              │
│  • State transitions (hover, focus, active)                         │
│  • Feedback (button press, form submit)                             │
│  • Orientation (page transitions, navigation)                       │
│  • Hierarchy (draw attention to important info)                     │
│  • Loading states (progress, skeleton screens)                      │
│                                                                     │
│  ❌ DECORATIVE MOTION (Avoid)                                       │
│  ────────────────────────────                                       │
│  • Bouncing elements for no reason                                  │
│  • Constant wiggling/pulsing                                        │
│  • Gratuitous parallax on everything                                │
│  • Animation that distracts from content                            │
│  • Motion that delays user tasks                                    │
│                                                                     │
│  DURATION GUIDELINES                                                │
│  ───────────────────                                                │
│  Micro-interactions:  150-300ms   (hovers, toggles)                 │
│  UI transitions:      200-400ms   (modals, panels)                  │
│  Page transitions:    300-500ms   (route changes)                   │
│  Complex animations:  500-1000ms  (orchestrated sequences)          │
│                                                                     │
│  EASING GUIDELINES                                                  │
│  ─────────────────                                                  │
│  Entering:    ease-out    (fast start, slow end)                    │
│  Exiting:     ease-in     (slow start, fast end)                    │
│  Moving:      ease-in-out (smooth both ends)                        │
│  Emphasizing: cubic-bezier(0.34, 1.56, 0.64, 1) (slight overshoot)  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 3: Text Animations

### SplitText — Character Reveal

Best for: Headlines, hero text, page titles

```tsx
import { SplitText } from '@/components/ui/split-text';

// Basic usage
<SplitText 
  text="Welcome to our platform"
  className="text-4xl font-bold"
/>

// With configuration
<SplitText 
  text="Design with purpose"
  className="text-5xl font-bold tracking-tight"
  delay={50}           // ms between each character
  duration={0.5}       // animation duration per character
  ease="easeOut"
  startOnView={true}   // trigger when scrolled into view
/>
```

### BlurText — Blur Reveal

Best for: Subtle introductions, secondary headlines

```tsx
import { BlurText } from '@/components/ui/blur-text';

<BlurText 
  text="Clarity through simplicity"
  className="text-2xl text-gray-600"
  delay={100}
  duration={0.8}
/>
```

### RotatingText — Word Swap

Best for: Dynamic value propositions, feature highlights

```tsx
import { RotatingText } from '@/components/ui/rotating-text';

<div className="flex items-center gap-2 text-3xl">
  <span>Build</span>
  <RotatingText 
    words={['faster', 'smarter', 'better']}
    className="font-bold text-accent"
    duration={2000}    // ms per word
  />
  <span>products</span>
</div>
```

### CountUp — Number Animation

Best for: Statistics, metrics, dashboards

```tsx
import { CountUp } from '@/components/ui/count-up';

<div className="text-5xl font-bold">
  <CountUp 
    end={99.9}
    decimals={1}
    suffix="%"
    duration={2}
  />
</div>
```

---

## Section 4: UI Components

### AnimatedList — Staggered List

Best for: Feature lists, notification feeds, timelines

```tsx
import { AnimatedList } from '@/components/ui/animated-list';

const features = [
  { title: 'Fast', description: 'Optimized performance' },
  { title: 'Secure', description: 'Enterprise-grade security' },
  { title: 'Scalable', description: 'Grows with your needs' },
];

<AnimatedList
  items={features}
  delay={100}        // stagger delay between items
  className="space-y-4"
  renderItem={(item, index) => (
    <div className="p-4 border rounded-lg">
      <h3 className="font-bold">{item.title}</h3>
      <p className="text-gray-600">{item.description}</p>
    </div>
  )}
/>
```

### TiltCard — 3D Hover Effect

Best for: Feature cards, portfolio items, product showcases

```tsx
import { TiltCard } from '@/components/ui/tilt-card';

<TiltCard
  className="p-6 bg-white border rounded-lg"
  maxTilt={10}       // maximum tilt angle
  scale={1.02}       // scale on hover
  speed={400}        // transition speed
>
  <h3 className="text-xl font-bold">Interactive Card</h3>
  <p className="text-gray-600">Hover to see the effect</p>
</TiltCard>
```

### Dock — macOS-Style Dock

Best for: Navigation, tool palettes, action bars

```tsx
import { Dock, DockItem } from '@/components/ui/dock';

<Dock>
  <DockItem icon={<HomeIcon />} label="Home" />
  <DockItem icon={<SearchIcon />} label="Search" />
  <DockItem icon={<SettingsIcon />} label="Settings" />
</Dock>
```

### Accordion — Animated Expand/Collapse

Best for: FAQs, settings panels, nested content

```tsx
import { Accordion, AccordionItem } from '@/components/ui/accordion';

<Accordion>
  <AccordionItem title="What is Swiss design?">
    Swiss design emphasizes clarity, readability, and objectivity...
  </AccordionItem>
  <AccordionItem title="Why use React Bits?">
    React Bits provides production-ready animated components...
  </AccordionItem>
</Accordion>
```

---

## Section 5: Background Effects

### Particles — Interactive Particle Field

Best for: Hero sections, landing pages, visual interest

```tsx
import { Particles } from '@/components/ui/particles';

<div className="relative h-screen">
  <Particles
    className="absolute inset-0"
    quantity={50}
    color="#3b82f6"
    size={2}
    speed={0.5}
    connectDistance={150}
    interactive={true}   // react to cursor
  />
  <div className="relative z-10">
    {/* Your content */}
  </div>
</div>
```

### Aurora — Northern Lights Effect

Best for: Ambient backgrounds, dark themes

```tsx
import { Aurora } from '@/components/ui/aurora';

<div className="relative min-h-screen bg-gray-900">
  <Aurora
    className="absolute inset-0 opacity-50"
    colors={['#3b82f6', '#8b5cf6', '#06b6d4']}
    speed={0.5}
  />
  <div className="relative z-10 text-white">
    {/* Your content */}
  </div>
</div>
```

### GridPattern — Animated Grid

Best for: Technical/developer themes, minimalist backgrounds

```tsx
import { GridPattern } from '@/components/ui/grid-pattern';

<div className="relative">
  <GridPattern
    className="absolute inset-0 opacity-20"
    cellSize={40}
    strokeWidth={1}
    animated={true}
  />
  <div className="relative z-10">
    {/* Your content */}
  </div>
</div>
```

---

## Section 6: Micro-Interactions

### Button Interactions (Swiss-Appropriate)

```tsx
// Simple, purposeful button transition
<button className="
  px-4 py-2 
  bg-accent text-white 
  rounded-md
  transition-colors duration-200 ease-out
  hover:bg-accent-dark
  active:scale-[0.98]
  focus:ring-2 focus:ring-accent focus:ring-offset-2
">
  Submit
</button>
```

### Link Underline Animation

```tsx
// Animated underline on hover
<a className="
  relative
  after:absolute after:bottom-0 after:left-0
  after:h-[2px] after:w-0 after:bg-current
  after:transition-all after:duration-300 after:ease-out
  hover:after:w-full
">
  Learn more
</a>
```

### Card Hover Lift

```tsx
// Subtle lift on hover
<div className="
  p-6 bg-white border rounded-lg
  transition-all duration-200 ease-out
  hover:shadow-md hover:-translate-y-1
">
  Card content
</div>
```

### Form Input Focus

```tsx
// Clear focus state transition
<input className="
  px-4 py-2
  border border-gray-200 rounded-md
  transition-all duration-200 ease-out
  focus:border-accent focus:ring-2 focus:ring-accent/20
  focus:outline-none
"/>
```

---

## Section 7: Page Transitions

### Fade In on Load

```tsx
// CSS-only fade in
<div className="
  animate-in fade-in duration-500
">
  Page content
</div>
```

### Staggered Section Reveal

```tsx
// Using React Bits ScrollReveal
import { ScrollReveal } from '@/components/ui/scroll-reveal';

<div>
  <ScrollReveal delay={0}>
    <section>First section</section>
  </ScrollReveal>
  <ScrollReveal delay={100}>
    <section>Second section</section>
  </ScrollReveal>
  <ScrollReveal delay={200}>
    <section>Third section</section>
  </ScrollReveal>
</div>
```

---

## Output Requirements

Every interaction design output MUST:

1. **Be purposeful** — Animation serves a function, not decoration
2. **Include implementation** — Working code, not just description
3. **Specify installation** — shadcn/jsrepo command or manual steps
4. **Define timing** — Duration and easing specified
5. **Consider reduced motion** — prefers-reduced-motion fallback

---

## Pre-Output Validation (User-Lens Review)

Before delivering any interaction/animation:

```
┌─────────────────────────────────────────────────────────────────────┐
│              INTERACTION DESIGN VALIDATION CHECKLIST                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. PURPOSE CHECK                                                   │
│     □ Does this animation serve a function?                         │
│     □ Does it provide feedback, orientation, or hierarchy?          │
│     □ Would removing it harm the user experience?                   │
│     □ Is it Swiss-appropriate (not decorative)?                     │
│                                                                     │
│  2. TIMING CHECK                                                    │
│     □ Duration is appropriate (not too slow)?                       │
│     □ Easing matches the action (enter/exit/move)?                  │
│     □ Animation doesn't block user tasks?                           │
│                                                                     │
│  3. IMPLEMENTATION CHECK                                            │
│     □ Installation command provided?                                │
│     □ All props/configuration documented?                           │
│     □ Code is copy-paste ready?                                     │
│     □ Works with their tech stack (React/Tailwind)?                 │
│                                                                     │
│  4. ACCESSIBILITY CHECK                                             │
│     □ prefers-reduced-motion fallback mentioned?                    │
│     □ Animation doesn't cause vestibular issues?                    │
│     □ Essential information not conveyed by motion alone?           │
│                                                                     │
│  5. PERFORMANCE CHECK                                               │
│     □ Uses transform/opacity (not layout properties)?               │
│     □ Doesn't cause excessive repaints?                             │
│     □ Works smoothly on mobile devices?                             │
│                                                                     │
│  IF ANY CHECK FAILS → Revise before delivering                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Starter Prompts

### Add Text Animation
```
Add a [SplitText/BlurText/etc.] animation to my headline.
Current code: [paste code]
```

### Browse Component Options
```
What React Bits components would work for [use case]?
```

### Add Hover Effect
```
Add a Swiss-appropriate hover effect to this [card/button/link].
Current code: [paste code]
```

### Background Effect
```
Add a subtle background effect to my hero section.
Theme: [light/dark]
Style: [technical/organic/minimal]
```

---

## Examples

### Example 1: Add Hero Text Animation

**Input:**
```
Add an animated text effect to my hero headline:

<h1 className="text-5xl font-bold">
  Build products faster
</h1>
```

**Output:**
```tsx
// Install the component
// npx shadcn@latest add @react-bits/SplitText-TS-TW

import { SplitText } from '@/components/ui/split-text';

<h1 className="text-5xl font-bold">
  <SplitText 
    text="Build products faster"
    delay={30}              // 30ms between each character
    duration={0.4}          // 400ms per character animation
    ease="easeOut"
    className="inline-block"
  />
</h1>

// Reduced motion fallback (add to global CSS)
@media (prefers-reduced-motion: reduce) {
  .split-text-char {
    animation: none !important;
    opacity: 1 !important;
  }
}
```

**Why SplitText:**
- Creates visual interest without being decorative
- Draws attention to the primary message (purposeful)
- Character-by-character reveal is readable, not distracting
- Swiss-appropriate: emphasis through timing, not flashiness

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] ✨ Add a rotating word to "faster" → [faster, smarter, better]
[2] 📐 Adjust timing (slower/faster reveal)
[3] 🎯 Add scroll-trigger (animate when scrolled into view)
[4] 🔄 Show BlurText alternative
[5] ✅ This works, what else can I animate?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════

---

## Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "Interaction Design / Animation"
  description: |
    Edge cases for implementing purposeful, Swiss-appropriate animations.
  
  cases:
    - id: decorative_animation_request
      scenario: "User wants gratuitous animation"
      naive_failure: "Implements whatever flashy animation requested"
      expert_behavior: "Suggests purposeful alternative, explains Swiss philosophy"
      test_input: "Make the logo bounce continuously"
      must_check:
        - "Explains why continuous animation is problematic"
        - "Suggests purposeful alternative (hover state, load animation)"
        - "References Swiss motion philosophy"
      anti_patterns:
        - "Here's a bouncing logo animation"
        - "No mention of purpose or restraint"
    
    - id: non_react_environment
      scenario: "User isn't using React"
      naive_failure: "Provides React Bits code anyway"
      expert_behavior: "Offers CSS/vanilla JS alternatives"
      test_input: "Add SplitText to my vanilla JS site"
      must_check:
        - "Notes React Bits requires React"
        - "Provides CSS-only or vanilla JS alternative"
        - "Achieves similar effect without React"
      anti_patterns:
        - "Just install React Bits"
        - "Ignoring the vanilla JS constraint"
    
    - id: missing_reduced_motion
      scenario: "Animation without accessibility consideration"
      naive_failure: "Provides animation without reduced motion fallback"
      expert_behavior: "Always includes prefers-reduced-motion handling"
      test_input: "Add a page transition animation"
      must_check:
        - "Animation code includes reduced motion media query"
        - "Explains why this matters"
        - "Fallback doesn't break the UI"
      anti_patterns:
        - "Animation with no accessibility mention"
        - "Assuming all users want motion"
    
    - id: slow_animation
      scenario: "Animation timing is too slow"
      naive_failure: "Uses arbitrary slow duration"
      expert_behavior: "Follows duration guidelines, explains timing"
      test_input: "Add a 3 second fade in to this card"
      must_check:
        - "Suggests more appropriate duration"
        - "Explains why 3s is too slow for UI"
        - "Provides timing guidelines"
      anti_patterns:
        - "Here's your 3 second animation"
        - "No mention of duration best practices"
    
    - id: performance_heavy_animation
      scenario: "Animation affects layout properties"
      naive_failure: "Animates width, height, margin, etc."
      expert_behavior: "Uses transform/opacity for performance"
      test_input: "Animate the card width on hover"
      must_check:
        - "Suggests transform: scale instead of width"
        - "Explains performance implications"
        - "Provides performant alternative"
      anti_patterns:
        - "transition: width 300ms"
        - "No performance consideration"
```
