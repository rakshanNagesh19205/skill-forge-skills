---
name: uiux-a11y
description: |
  Accessibility skill for WCAG compliance, screen reader support, keyboard navigation,
  and inclusive design patterns. Use for auditing accessibility, fixing a11y issues,
  or building accessible components from scratch. Essential final step for any UI.
license: MIT
---

# UI/UX Accessibility — WCAG & Inclusive Design

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "accessibility", "a11y", "WCAG"
- "screen reader", "keyboard navigation"
- "accessible component", "aria labels"
- "color contrast", "focus states"

**Quick Triggers:**
- `a11y-audit` → Full accessibility audit
- `contrast` → Check color contrast
- `keyboard` → Keyboard navigation review
- `aria` → ARIA implementation help
- `focus` → Focus management patterns

**Smart Defaults:**
- Standard: WCAG 2.1 Level AA
- Testing: Automated + manual checks
- Output: Issues with code fixes
- Priority: Critical → Serious → Moderate → Minor

---

## Section 1: WCAG 2.1 Principles (POUR)

```
┌─────────────────────────────────────────────────────────────────────┐
│                    WCAG POUR PRINCIPLES                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  P — PERCEIVABLE                                                    │
│  ────────────────                                                   │
│  Information must be presentable in ways users can perceive.        │
│  • Text alternatives for images                                     │
│  • Captions for video/audio                                         │
│  • Content adaptable to different presentations                     │
│  • Distinguishable (contrast, resize, audio control)                │
│                                                                     │
│  O — OPERABLE                                                       │
│  ─────────────                                                      │
│  Interface components must be operable by all users.                │
│  • Keyboard accessible                                              │
│  • Enough time to read/use content                                  │
│  • No seizure-inducing content                                      │
│  • Navigable (skip links, focus order, clear purpose)               │
│                                                                     │
│  U — UNDERSTANDABLE                                                 │
│  ──────────────────                                                 │
│  Information and operation must be understandable.                  │
│  • Readable (language, abbreviations)                               │
│  • Predictable (consistent navigation, no surprises)                │
│  • Input assistance (error prevention, suggestions)                 │
│                                                                     │
│  R — ROBUST                                                         │
│  ──────────                                                         │
│  Content must work with current and future technologies.            │
│  • Compatible (valid HTML, ARIA properly used)                      │
│  • Works with assistive technologies                                │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 2: Critical Accessibility Requirements

### Color Contrast (WCAG 1.4.3, 1.4.11)

```
MINIMUM CONTRAST RATIOS (Level AA):

Normal text (<18pt or <14pt bold):     4.5:1
Large text (≥18pt or ≥14pt bold):      3:1
UI components and graphics:            3:1

ENHANCED CONTRAST (Level AAA):
Normal text:  7:1
Large text:   4.5:1
```

**Testing:**
```javascript
// Use contrast checking tools:
// - WebAIM Contrast Checker
// - Chrome DevTools (Inspect > Accessibility)
// - Figma A11y plugins

// CSS custom properties for accessible colors
:root {
  /* These pairs meet 4.5:1 minimum */
  --text-on-light: hsl(220, 13%, 18%);    /* #2d3142 on white = 12.6:1 */
  --text-on-dark: hsl(220, 13%, 95%);     /* #f0f1f4 on #2d3142 = 12.6:1 */
  --text-secondary: hsl(220, 13%, 42%);   /* #5c6378 on white = 5.7:1 */
}
```

### Keyboard Navigation (WCAG 2.1.1, 2.1.2)

```
ALL INTERACTIVE ELEMENTS MUST BE:
✓ Focusable (reachable via Tab)
✓ Operable (activatable via Enter/Space)
✓ Escapable (can exit with Escape)
✓ Visible when focused (clear focus indicator)

KEYBOARD PATTERNS:
Tab           → Move to next focusable element
Shift + Tab   → Move to previous focusable element
Enter/Space   → Activate buttons, links
Arrow keys    → Navigate within components (menus, tabs)
Escape        → Close modals, dropdowns, cancel
```

**Focus Indicator CSS:**
```css
/* NEVER do this */
*:focus {
  outline: none;  /* ❌ Removes focus indicator */
}

/* DO this instead */
:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 2px;
}

/* Custom focus ring */
.focus-ring {
  @apply focus:outline-none focus-visible:ring-2 
         focus-visible:ring-accent focus-visible:ring-offset-2;
}
```

### Screen Reader Support

```
ESSENTIAL PRACTICES:

1. SEMANTIC HTML
   Use the right elements for the job:
   <button> not <div onclick>
   <nav> not <div class="navigation">
   <h1>-<h6> in logical order

2. ALT TEXT FOR IMAGES
   <img src="chart.png" alt="Sales increased 25% in Q4" />
   Not: alt="chart" or alt="image" or alt=""
   Decorative images: alt="" (empty, not missing)

3. FORM LABELS
   <label for="email">Email</label>
   <input id="email" type="email" />
   OR
   <label>
     Email
     <input type="email" />
   </label>

4. ARIA WHEN NEEDED
   Only when HTML semantics aren't sufficient
   aria-label, aria-describedby, aria-expanded, etc.
```

---

## Section 3: Common Accessibility Issues & Fixes

### Issue: Missing Alt Text

```html
<!-- ❌ WRONG -->
<img src="product.jpg" />
<img src="icon.svg" alt="icon" />

<!-- ✅ CORRECT -->
<img src="product.jpg" alt="Blue wireless headphones with cushioned ear cups" />
<img src="icon.svg" alt="" role="presentation" />  <!-- Decorative -->
```

### Issue: Non-Semantic Buttons

```html
<!-- ❌ WRONG: Not keyboard accessible -->
<div class="button" onclick="submit()">Submit</div>
<span class="link" onclick="navigate()">Click here</span>

<!-- ✅ CORRECT: Native semantics -->
<button type="submit">Submit</button>
<a href="/page">Go to page</a>

<!-- If you MUST use div (rare), add full a11y -->
<div 
  role="button" 
  tabindex="0" 
  onclick="submit()"
  onkeydown="if(e.key==='Enter'||e.key===' ')submit()"
>
  Submit
</div>
```

### Issue: Missing Form Labels

```html
<!-- ❌ WRONG -->
<input type="email" placeholder="Email" />

<!-- ✅ CORRECT -->
<div>
  <label for="email">Email</label>
  <input id="email" type="email" placeholder="you@example.com" />
</div>

<!-- If label must be visually hidden -->
<label for="search" class="sr-only">Search</label>
<input id="search" type="search" placeholder="Search..." />

/* sr-only utility */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

### Issue: Missing Focus States

```css
/* ❌ WRONG: No visible focus */
button:focus {
  outline: none;
}

/* ✅ CORRECT: Clear focus indicator */
button:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 2px;
}

/* Tailwind version */
<button className="focus:outline-none focus-visible:ring-2 focus-visible:ring-accent focus-visible:ring-offset-2">
  Click me
</button>
```

### Issue: Color-Only Information

```html
<!-- ❌ WRONG: Status conveyed by color only -->
<span class="text-red-500">Error</span>
<span class="text-green-500">Success</span>

<!-- ✅ CORRECT: Icon + text + color -->
<span class="text-red-500 flex items-center gap-1">
  <svg><!-- error icon --></svg>
  Error: Please enter a valid email
</span>

<span class="text-green-500 flex items-center gap-1">
  <svg><!-- checkmark icon --></svg>
  Success: Your changes have been saved
</span>
```

### Issue: Missing Skip Link

```html
<!-- Add at very start of <body> -->
<a href="#main-content" class="skip-link">
  Skip to main content
</a>

<!-- Target element -->
<main id="main-content" tabindex="-1">
  ...
</main>

<style>
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  padding: 8px 16px;
  background: var(--accent);
  color: white;
  z-index: 100;
}

.skip-link:focus {
  top: 0;
}
</style>
```

---

## Section 4: ARIA Patterns

### When to Use ARIA

```
FIRST RULE OF ARIA:
Don't use ARIA if you can use native HTML.

<button> is better than <div role="button">
<nav> is better than <div role="navigation">

USE ARIA WHEN:
• Native HTML doesn't provide the semantics needed
• Building custom interactive components
• Providing additional context for screen readers
```

### Common ARIA Attributes

```html
<!-- Label for elements without visible text -->
<button aria-label="Close">
  <svg><!-- X icon --></svg>
</button>

<!-- Reference another element for description -->
<input 
  aria-describedby="password-hint"
  type="password" 
/>
<p id="password-hint">Must be at least 8 characters</p>

<!-- State attributes -->
<button aria-expanded="false" aria-controls="menu">
  Menu
</button>
<ul id="menu" aria-hidden="true">...</ul>

<!-- Live regions (announce changes) -->
<div aria-live="polite" aria-atomic="true">
  {statusMessage}
</div>
```

### Modal Dialog Pattern

```tsx
// Accessible modal implementation
function Modal({ isOpen, onClose, title, children }) {
  const modalRef = useRef(null);
  
  // Trap focus inside modal
  useEffect(() => {
    if (isOpen) {
      modalRef.current?.focus();
      document.body.style.overflow = 'hidden';
    }
    return () => {
      document.body.style.overflow = '';
    };
  }, [isOpen]);
  
  // Close on Escape
  useEffect(() => {
    const handleEscape = (e) => {
      if (e.key === 'Escape') onClose();
    };
    document.addEventListener('keydown', handleEscape);
    return () => document.removeEventListener('keydown', handleEscape);
  }, [onClose]);
  
  if (!isOpen) return null;
  
  return (
    <div 
      className="fixed inset-0 bg-black/50 flex items-center justify-center"
      onClick={onClose}
      role="presentation"
    >
      <div
        ref={modalRef}
        role="dialog"
        aria-modal="true"
        aria-labelledby="modal-title"
        tabIndex={-1}
        className="bg-white rounded-lg p-6 max-w-md"
        onClick={(e) => e.stopPropagation()}
      >
        <h2 id="modal-title" className="text-xl font-bold">
          {title}
        </h2>
        {children}
        <button 
          onClick={onClose}
          className="mt-4"
        >
          Close
        </button>
      </div>
    </div>
  );
}
```

---

## Section 5: Accessibility Audit Checklist

```
┌─────────────────────────────────────────────────────────────────────┐
│              ACCESSIBILITY AUDIT CHECKLIST                           │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  PERCEIVABLE                                                        │
│  □ All images have appropriate alt text                             │
│  □ Color contrast meets 4.5:1 (text) / 3:1 (UI)                    │
│  □ Content doesn't rely on color alone                              │
│  □ Text can be resized to 200% without loss                         │
│  □ Video has captions (if applicable)                               │
│                                                                     │
│  OPERABLE                                                           │
│  □ All functionality available via keyboard                         │
│  □ Focus order is logical                                           │
│  □ Focus indicator is visible                                       │
│  □ No keyboard traps                                                │
│  □ Skip link provided                                               │
│  □ No content flashes more than 3 times/second                      │
│                                                                     │
│  UNDERSTANDABLE                                                     │
│  □ Page language is specified (<html lang="en">)                    │
│  □ Form inputs have labels                                          │
│  □ Error messages are clear and helpful                             │
│  □ Navigation is consistent                                         │
│                                                                     │
│  ROBUST                                                             │
│  □ HTML is valid                                                    │
│  □ ARIA is used correctly (if used)                                 │
│  □ Works with screen readers                                        │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 6: Testing Tools

### Automated Testing

```bash
# axe-core (most popular)
npm install @axe-core/react

# In development
import { axe } from '@axe-core/react';
axe(React, ReactDOM, 1000);

# Lighthouse (Chrome DevTools)
# DevTools > Lighthouse > Accessibility

# eslint-plugin-jsx-a11y
npm install eslint-plugin-jsx-a11y
```

### Manual Testing

```
KEYBOARD TESTING:
1. Unplug your mouse
2. Navigate entire page with Tab
3. Activate elements with Enter/Space
4. Close overlays with Escape
5. Check focus is always visible

SCREEN READER TESTING:
• macOS: VoiceOver (Cmd + F5)
• Windows: NVDA (free) or JAWS
• Test: headings, links, forms, images

ZOOM TESTING:
1. Zoom browser to 200%
2. Check nothing breaks or overflows
3. Text should remain readable
```

---

## Section 7: Reduced Motion

```css
/* Respect user preference for reduced motion */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}

/* Or target specific animations */
.animated-element {
  animation: slideIn 300ms ease-out;
}

@media (prefers-reduced-motion: reduce) {
  .animated-element {
    animation: none;
  }
}
```

---

## Output Requirements

Every accessibility output MUST:

1. **Reference WCAG criteria** — Specific success criteria cited
2. **Explain impact** — How issue affects users with disabilities
3. **Provide code fixes** — Working implementation
4. **Include testing steps** — How to verify the fix works
5. **Consider multiple disabilities** — Visual, motor, cognitive

---

## Pre-Output Validation (User-Lens Review)

Before delivering any accessibility analysis:

```
┌─────────────────────────────────────────────────────────────────────┐
│              ACCESSIBILITY VALIDATION CHECKLIST                      │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. COMPLETENESS                                                    │
│     □ All POUR principles considered?                               │
│     □ Both automated and manual checks mentioned?                   │
│     □ Multiple disability types considered?                         │
│                                                                     │
│  2. SPECIFICITY                                                     │
│     □ WCAG success criteria referenced?                             │
│     □ Exact elements with issues identified?                        │
│     □ Impact on specific user groups explained?                     │
│                                                                     │
│  3. ACTIONABILITY                                                   │
│     □ Every issue has a code fix?                                   │
│     □ Fixes follow best practices (semantic HTML first)?            │
│     □ Testing method provided to verify fix?                        │
│                                                                     │
│  4. PRIORITIZATION                                                  │
│     □ Critical issues (blockers) identified first?                  │
│     □ Level A issues before Level AA/AAA?                           │
│     □ Quick wins highlighted?                                       │
│                                                                     │
│  5. COMPLETENESS OF FIXES                                           │
│     □ Fixes don't break other functionality?                        │
│     □ Reduced motion preferences addressed?                         │
│     □ Fixes work across assistive technologies?                     │
│                                                                     │
│  IF ANY CHECK FAILS → Revise before delivering                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Starter Prompts

### Full Accessibility Audit
```
Audit this component/page for accessibility:
[paste code]
```

### Fix Specific Issue
```
This [element] isn't accessible to [keyboard users/screen readers].
Current code: [paste code]
```

### Make Component Accessible
```
Make this custom [dropdown/modal/tabs] accessible:
[paste code]
```

### Check Contrast
```
Are these colors accessible?
Background: [color]
Text: [color]
```

---

## Examples

### Example 1: Button Accessibility Fix

**Input:**
```
Fix this button for accessibility:

<div class="btn" onclick="handleClick()">
  <img src="cart.svg" />
</div>
```

**Output:**

### Accessibility Issues Found

#### Issue 1: Non-semantic element
**WCAG:** 4.1.2 Name, Role, Value (Level A)  
**Impact:** Screen readers won't announce as button; keyboard users can't access it.

#### Issue 2: Missing accessible name
**WCAG:** 1.1.1 Non-text Content (Level A)  
**Impact:** Screen readers will say nothing or "image" — users won't know the purpose.

#### Issue 3: No keyboard support
**WCAG:** 2.1.1 Keyboard (Level A)  
**Impact:** Keyboard-only users cannot activate this control.

---

### Fixed Code

```tsx
<button 
  type="button"
  onClick={handleClick}
  aria-label="Add to cart"
  className="btn focus-visible:ring-2 focus-visible:ring-accent focus-visible:ring-offset-2"
>
  <img src="cart.svg" alt="" aria-hidden="true" />
</button>
```

**What changed:**
1. `<div>` → `<button>` — Native semantics, keyboard accessible
2. Added `aria-label="Add to cart"` — Screen readers announce purpose
3. `alt=""` on icon — Decorative image hidden from screen readers
4. Added focus-visible styles — Keyboard users see focus indicator
5. Removed inline onclick — Using React onClick handler properly

---

### Testing Steps

1. **Keyboard:** Tab to button, press Enter/Space — should trigger action
2. **Screen reader:** Should announce "Add to cart, button"
3. **Focus:** Should see visible focus ring when tabbed to

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🎨 Also add hover/active states
[2] 📱 Show touch target size requirements
[3] 🔍 Audit more components on this page
[4] 📋 Generate full page accessibility checklist
[5] ✅ This fixes my issue

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════

---

## Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "Accessibility / WCAG Compliance"
  description: |
    Edge cases for implementing accessible interfaces.
  
  cases:
    - id: aria_overuse
      scenario: "ARIA used when native HTML would work"
      naive_failure: "Adds role='button' to everything"
      expert_behavior: "Uses native HTML first, ARIA only when necessary"
      test_input: "Make this div accessible: <div onclick='click()'>Submit</div>"
      must_check:
        - "Recommends <button> instead of div+role"
        - "Explains first rule of ARIA"
        - "Only uses ARIA when HTML insufficient"
      anti_patterns:
        - "<div role='button' tabindex='0'>"
        - "Adding ARIA without mentioning native alternative"
    
    - id: decorative_vs_meaningful_images
      scenario: "Alt text needed for some images, not others"
      naive_failure: "Adds alt text to everything, or leaves all empty"
      expert_behavior: "Distinguishes decorative from meaningful images"
      test_input: "Add alt text: <img src='icon.svg'/><img src='product.jpg'/>"
      must_check:
        - "Decorative icon gets alt='' or aria-hidden"
        - "Product image gets descriptive alt text"
        - "Explains the difference"
      anti_patterns:
        - "alt='icon' on decorative image"
        - "Empty alt on meaningful image"
    
    - id: color_contrast_edge
      scenario: "Colors close to but not meeting contrast"
      naive_failure: "Says 'looks fine' without checking"
      expert_behavior: "Calculates exact ratio, suggests fix"
      test_input: "Is #767676 on white accessible?"
      must_check:
        - "Calculates actual contrast ratio (4.48:1)"
        - "Notes it fails AA for normal text (needs 4.5:1)"
        - "Suggests darker alternative"
      anti_patterns:
        - "Looks accessible to me"
        - "Should be fine"
    
    - id: focus_trap_in_modal
      scenario: "Modal doesn't trap focus"
      naive_failure: "Just adds tabindex without trap"
      expert_behavior: "Implements full focus trap pattern"
      test_input: "Make this modal accessible"
      must_check:
        - "Focus trapped inside modal"
        - "Focus returns to trigger on close"
        - "Escape key closes modal"
        - "Background content is inert"
      anti_patterns:
        - "Just add tabindex"
        - "Focus trap not mentioned"
    
    - id: reduced_motion_ignored
      scenario: "Animation without motion preference check"
      naive_failure: "Adds animation without prefers-reduced-motion"
      expert_behavior: "Always includes reduced motion media query"
      test_input: "Add a slide-in animation"
      must_check:
        - "Animation code includes prefers-reduced-motion"
        - "Explains why this matters (vestibular disorders)"
        - "Provides non-animated fallback"
      anti_patterns:
        - "Animation with no motion preference check"
        - "Assuming everyone wants animation"
```
