---
name: uiux-usability
description: |
  Usability and UX evaluation skill. Audits existing interfaces using Nielsen's
  heuristics and other frameworks. Identifies problems and provides actionable fixes.
  Use for improving existing UIs, conducting heuristic evaluations, or fixing UX issues.
license: MIT
---

# UI/UX Usability — Audits & Improvements

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "fix my UI", "improve UX", "usability audit"
- "what's wrong with this", "heuristic evaluation"
- "user flow", "friction points", "conversion"
- "why isn't this working", "users are confused"

**Quick Triggers:**
- `audit` → Full heuristic evaluation
- `fix` → Quick fixes for specific issues
- `flow` → User flow analysis
- `friction` → Identify friction points
- `compare` → Before/after comparison

**Smart Defaults:**
- Framework: Nielsen's 10 Heuristics (primary)
- Output: Problem → Impact → Fix (actionable)
- Priority: Severity-based ranking
- Fixes: Swiss design principles applied

---

## Section 1: Nielsen's 10 Heuristics

```
┌─────────────────────────────────────────────────────────────────────┐
│                    NIELSEN'S 10 USABILITY HEURISTICS                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. VISIBILITY OF SYSTEM STATUS                                     │
│     Keep users informed about what's happening through              │
│     appropriate feedback within reasonable time.                    │
│     Examples: Loading states, progress bars, success messages       │
│                                                                     │
│  2. MATCH BETWEEN SYSTEM AND REAL WORLD                            │
│     Speak the users' language with familiar words, phrases,         │
│     and concepts. Follow real-world conventions.                    │
│     Examples: Shopping cart (not "item aggregator")                 │
│                                                                     │
│  3. USER CONTROL AND FREEDOM                                        │
│     Support undo and redo. Provide emergency exits.                 │
│     Examples: Cancel buttons, back navigation, undo actions         │
│                                                                     │
│  4. CONSISTENCY AND STANDARDS                                       │
│     Follow platform conventions. Same words mean same things.       │
│     Examples: Consistent button styles, predictable navigation      │
│                                                                     │
│  5. ERROR PREVENTION                                                │
│     Prevent problems before they occur. Confirm risky actions.      │
│     Examples: Disable invalid options, confirmation dialogs         │
│                                                                     │
│  6. RECOGNITION RATHER THAN RECALL                                  │
│     Minimize memory load. Make options visible.                     │
│     Examples: Visible labels, recent items, autocomplete            │
│                                                                     │
│  7. FLEXIBILITY AND EFFICIENCY OF USE                               │
│     Accelerators for experts. Customizable shortcuts.               │
│     Examples: Keyboard shortcuts, power user features               │
│                                                                     │
│  8. AESTHETIC AND MINIMALIST DESIGN                                 │
│     Only show relevant information. Every element earns its place.  │
│     Examples: Clean interfaces, focused content                     │
│                                                                     │
│  9. HELP USERS RECOGNIZE, DIAGNOSE, RECOVER FROM ERRORS            │
│     Error messages in plain language. Suggest solutions.            │
│     Examples: "Email format invalid" not "Error 422"                │
│                                                                     │
│  10. HELP AND DOCUMENTATION                                         │
│      Easy to search, focused on tasks, concrete steps.              │
│      Examples: Contextual help, searchable docs                     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 2: Audit Methodology

### Step 1: Inventory

```
┌─────────────────────────────────────────────────────────────────────┐
│  INTERFACE INVENTORY CHECKLIST                                       │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  □ What is the primary user goal?                                   │
│  □ What are the key user flows?                                     │
│  □ What are the critical actions (CTAs)?                            │
│  □ What feedback mechanisms exist?                                  │
│  □ What error states are handled?                                   │
│  □ What's the information hierarchy?                                │
│  □ How is navigation structured?                                    │
│  □ What's the visual consistency?                                   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Step 2: Heuristic Walkthrough

For each of the 10 heuristics, evaluate:
1. Does the interface satisfy this heuristic?
2. Where does it violate this heuristic?
3. What's the severity of each violation?

### Step 3: Severity Rating

```
SEVERITY SCALE:

[0] Not a usability problem
[1] Cosmetic — Fix if time permits
[2] Minor — Low priority fix
[3] Major — High priority fix  
[4] Catastrophic — Must fix before release

SEVERITY FACTORS:
• Frequency: How often does the problem occur?
• Impact: How hard is it to overcome?
• Persistence: Is it a one-time or repeated problem?
```

### Step 4: Prioritized Recommendations

Output format for each issue:

```
┌─────────────────────────────────────────────────────────────────────┐
│  ISSUE: [Brief description]                                          │
│  HEURISTIC: #[number] — [name]                                       │
│  SEVERITY: [1-4] — [label]                                           │
├─────────────────────────────────────────────────────────────────────┤
│  PROBLEM:                                                           │
│  [What's wrong and where]                                           │
│                                                                     │
│  IMPACT:                                                            │
│  [How this affects users]                                           │
│                                                                     │
│  FIX:                                                               │
│  [Specific, actionable solution]                                    │
│                                                                     │
│  CODE (if applicable):                                              │
│  [Implementation snippet]                                           │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 3: Common Usability Problems

### Navigation Issues

```
PROBLEM: Hidden or unclear navigation
SYMPTOMS:
• Users can't find key features
• High bounce rate
• Support tickets asking "where is X?"

FIXES:
• Persistent navigation bar
• Clear, descriptive labels
• Breadcrumbs for deep pages
• Search functionality
```

### Form Problems

```
PROBLEM: Frustrating form experiences
SYMPTOMS:
• High form abandonment
• Validation errors after submit
• Users don't know what's required

FIXES:
• Inline validation (as you type)
• Clear required field indicators
• Helpful error messages
• Smart defaults and autofill
• Progress indicators for long forms
```

### Feedback Gaps

```
PROBLEM: No system status visibility
SYMPTOMS:
• Users click buttons multiple times
• Users don't know if action succeeded
• Users abandon during loading

FIXES:
• Loading states on all async actions
• Success/error confirmations
• Progress indicators for long operations
• Disabled states during processing
```

### Cognitive Overload

```
PROBLEM: Too much information at once
SYMPTOMS:
• Users feel overwhelmed
• Decision paralysis
• Important actions missed

FIXES:
• Progressive disclosure
• Clear visual hierarchy
• Chunked content
• Focused, single-purpose screens
```

---

## Section 4: User Flow Analysis

### Flow Mapping Template

```
START → [Entry Point]
         │
         ▼
    ┌─────────┐
    │ Step 1  │ ─── Friction? ─── Fix?
    └────┬────┘
         │
         ▼
    ┌─────────┐
    │ Step 2  │ ─── Friction? ─── Fix?
    └────┬────┘
         │
         ▼
    ┌─────────┐
    │ Step 3  │ ─── Friction? ─── Fix?
    └────┬────┘
         │
         ▼
   [Goal Achieved]
```

### Friction Point Categories

```
FRICTION TYPES:

1. COGNITIVE FRICTION
   • Confusing labels or instructions
   • Unclear next steps
   • Too many choices
   
2. INTERACTION FRICTION
   • Too many clicks/taps
   • Small touch targets
   • Hidden actions
   
3. VISUAL FRICTION
   • Poor hierarchy
   • Unclear CTAs
   • Distracting elements
   
4. TECHNICAL FRICTION
   • Slow load times
   • Broken functionality
   • Unresponsive interactions
```

---

## Section 5: Quick Fix Patterns

### Improving CTAs

```
BEFORE (Weak CTA):
┌─────────────────────────┐
│  [ Submit ]             │  ← Generic, passive
└─────────────────────────┘

AFTER (Strong CTA):
┌─────────────────────────┐
│  [ Create Account → ]   │  ← Specific, action-oriented
└─────────────────────────┘

RULES:
• Use action verbs (Create, Start, Get)
• Be specific about outcome
• One primary CTA per screen
• High contrast, visually prominent
```

### Improving Error Messages

```
BEFORE (Unhelpful):
❌ "Error: Invalid input"
❌ "Something went wrong"
❌ "Error code: 422"

AFTER (Helpful):
✅ "Please enter a valid email address (e.g., name@example.com)"
✅ "We couldn't save your changes. Check your connection and try again."
✅ "This email is already registered. Sign in or use a different email."

RULES:
• Explain what went wrong
• Suggest how to fix it
• Use plain language
• Position near the problem
```

### Improving Loading States

```
BEFORE (No feedback):
[ Submit ] → (nothing happens) → (confusion)

AFTER (Clear feedback):
[ Submit ] → [ Saving... ] → [ ✓ Saved ]

IMPLEMENTATION:
<button 
  disabled={isLoading}
  className={isLoading ? 'opacity-50 cursor-wait' : ''}
>
  {isLoading ? 'Saving...' : 'Submit'}
</button>
```

### Improving Forms

```
BEFORE (Frustrating):
• All fields look the same
• Errors only show after submit
• No indication of required fields

AFTER (User-friendly):
• Required fields marked with *
• Inline validation as you type
• Clear error states with red border
• Helper text under complex fields
• Logical tab order

IMPLEMENTATION:
<div className="space-y-1">
  <label className="text-sm font-medium">
    Email <span className="text-red-500">*</span>
  </label>
  <input 
    type="email"
    className={`
      border rounded-md px-3 py-2
      ${error ? 'border-red-500' : 'border-gray-200'}
      focus:ring-2 focus:ring-accent
    `}
  />
  {error && (
    <p className="text-sm text-red-500">{error}</p>
  )}
</div>
```

---

## Section 6: Before/After Framework

When presenting fixes, always show transformation:

```
┌─────────────────────────────────────────────────────────────────────┐
│  BEFORE                          │  AFTER                          │
├─────────────────────────────────────────────────────────────────────┤
│  [Screenshot/Code showing        │  [Screenshot/Code showing        │
│   the problem]                   │   the solution]                  │
│                                  │                                  │
│  PROBLEMS:                       │  IMPROVEMENTS:                   │
│  • Issue 1                       │  • Fix for issue 1               │
│  • Issue 2                       │  • Fix for issue 2               │
│  • Issue 3                       │  • Fix for issue 3               │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Output Requirements

Every usability output MUST:

1. **Identify specific problems** — Not vague criticisms
2. **Reference heuristics** — Which principle is violated
3. **Rate severity** — Prioritize what matters
4. **Provide actionable fixes** — Code when applicable
5. **Explain impact** — Why this matters to users

---

## Pre-Output Validation (User-Lens Review)

Before delivering any usability analysis:

```
┌─────────────────────────────────────────────────────────────────────┐
│              USABILITY AUDIT VALIDATION CHECKLIST                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. COMPLETENESS                                                    │
│     □ All 10 heuristics considered?                                 │
│     □ Key user flows analyzed?                                      │
│     □ Both positive and negative findings noted?                    │
│                                                                     │
│  2. SPECIFICITY                                                     │
│     □ Problems are specific, not vague?                             │
│     □ Location of issues clearly identified?                        │
│     □ Examples provided where relevant?                             │
│                                                                     │
│  3. ACTIONABILITY                                                   │
│     □ Every problem has a suggested fix?                            │
│     □ Fixes are implementable (not just "make it better")?          │
│     □ Code provided for technical fixes?                            │
│                                                                     │
│  4. PRIORITIZATION                                                  │
│     □ Severity ratings assigned?                                    │
│     □ Most critical issues highlighted first?                       │
│     □ Quick wins identified?                                        │
│                                                                     │
│  5. USER FOCUS                                                      │
│     □ Impact on actual users explained?                             │
│     □ User goals considered?                                        │
│     □ Fixes serve user needs (not just aesthetics)?                 │
│                                                                     │
│  IF ANY CHECK FAILS → Revise before delivering                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Starter Prompts

### Full Usability Audit
```
Audit this interface for usability issues:
[paste code or describe interface]
```

### Quick Fix Request
```
Users are having trouble with [specific area].
Here's the current implementation: [paste code]
```

### User Flow Analysis
```
Analyze the user flow for [task].
Current steps: [list steps]
```

### Before/After Review
```
I fixed [issue]. Does this solve the problem?
Before: [paste old code]
After: [paste new code]
```

---

## Examples

### Example 1: Form Usability Audit

**Input:**
```
Audit this signup form:

<form>
  <input type="text" placeholder="Name" />
  <input type="text" placeholder="Email" />
  <input type="text" placeholder="Password" />
  <button>Go</button>
</form>
```

**Output:**

### Usability Audit: Signup Form

**Overall Score: 4/10** — Multiple critical issues

---

#### Issue 1: No visible labels
**Heuristic:** #6 Recognition Rather Than Recall  
**Severity:** [3] Major

**Problem:** Placeholder text disappears when user starts typing, forcing recall.

**Impact:** Users forget what field they're filling, especially on longer forms.

**Fix:**
```html
<div className="space-y-1">
  <label htmlFor="name" className="text-sm font-medium">
    Name
  </label>
  <input 
    id="name"
    type="text" 
    className="border rounded-md px-3 py-2 w-full"
  />
</div>
```

---

#### Issue 2: Wrong input types
**Heuristic:** #5 Error Prevention  
**Severity:** [3] Major

**Problem:** Email and password use `type="text"` instead of proper types.

**Impact:** No email validation, password visible, no autofill support.

**Fix:**
```html
<input type="email" />  <!-- Enables email validation -->
<input type="password" />  <!-- Masks input, enables password managers -->
```

---

#### Issue 3: Weak CTA
**Heuristic:** #2 Match Between System and Real World  
**Severity:** [2] Minor

**Problem:** "Go" is vague and doesn't indicate the action outcome.

**Impact:** Users uncertain what will happen when clicked.

**Fix:**
```html
<button type="submit">Create Account</button>
```

---

#### Issue 4: No required field indicators
**Heuristic:** #1 Visibility of System Status  
**Severity:** [2] Minor

**Problem:** No indication which fields are required.

**Impact:** Users may submit incomplete forms, causing frustration.

**Fix:**
```html
<label>
  Email <span className="text-red-500">*</span>
</label>
```

---

#### Issue 5: No validation feedback
**Heuristic:** #9 Help Users Recover from Errors  
**Severity:** [3] Major

**Problem:** No visible validation or error messaging.

**Impact:** Users don't know why submission failed or how to fix.

**Fix:** Add inline validation with clear error messages.

---

### Complete Fixed Form

```tsx
<form className="space-y-4">
  <div className="space-y-1">
    <label htmlFor="name" className="text-sm font-medium">
      Full Name <span className="text-red-500">*</span>
    </label>
    <input 
      id="name"
      type="text"
      required
      className="border border-gray-200 rounded-md px-3 py-2 w-full
        focus:ring-2 focus:ring-accent focus:border-transparent"
    />
  </div>
  
  <div className="space-y-1">
    <label htmlFor="email" className="text-sm font-medium">
      Email <span className="text-red-500">*</span>
    </label>
    <input 
      id="email"
      type="email"
      required
      className="border border-gray-200 rounded-md px-3 py-2 w-full
        focus:ring-2 focus:ring-accent focus:border-transparent"
    />
  </div>
  
  <div className="space-y-1">
    <label htmlFor="password" className="text-sm font-medium">
      Password <span className="text-red-500">*</span>
    </label>
    <input 
      id="password"
      type="password"
      required
      minLength={8}
      className="border border-gray-200 rounded-md px-3 py-2 w-full
        focus:ring-2 focus:ring-accent focus:border-transparent"
    />
    <p className="text-xs text-gray-500">Minimum 8 characters</p>
  </div>
  
  <button 
    type="submit"
    className="w-full bg-accent text-white py-2 px-4 rounded-md
      font-medium hover:bg-accent-dark transition-colors"
  >
    Create Account
  </button>
</form>
```

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 📝 Add inline validation with error messages
[2] 🔄 Add loading state to submit button
[3] 🎨 Apply Swiss design styling (uiux-visual)
[4] ♿ Check accessibility compliance (uiux-a11y)
[5] ✅ This fixes my main issues

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you need.
═══════════════════════════════════════════════════════════════════

---

## Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "Usability / UX Auditing"
  description: |
    Edge cases for conducting usability audits and providing fixes.
  
  cases:
    - id: vague_criticism
      scenario: "Audit produces vague feedback"
      naive_failure: "Says 'the UI is confusing' without specifics"
      expert_behavior: "Identifies exact elements and specific issues"
      test_input: "This dashboard feels off, what's wrong?"
      must_check:
        - "Specific elements identified"
        - "Heuristics referenced for each issue"
        - "Location of problems clearly stated"
      anti_patterns:
        - "The dashboard is confusing"
        - "It doesn't feel right"
        - "Generic criticism without specifics"
    
    - id: no_fixes_provided
      scenario: "Identifies problems without solutions"
      naive_failure: "Lists problems but no actionable fixes"
      expert_behavior: "Every problem has a specific, implementable fix"
      test_input: "What's wrong with this form?"
      must_check:
        - "Every identified problem has a fix"
        - "Fixes include code where applicable"
        - "Fixes are specific, not 'make it better'"
      anti_patterns:
        - "This has poor usability"
        - "You should improve the labels"
        - "Criticism without solutions"
    
    - id: ignoring_context
      scenario: "Audit ignores user context"
      naive_failure: "Applies generic rules without considering use case"
      expert_behavior: "Considers the specific user goals and context"
      test_input: "Audit my internal admin tool"
      must_check:
        - "Considers that it's for internal users"
        - "Adjusts recommendations for expert users"
        - "Different standards than consumer app"
      anti_patterns:
        - "Treating admin tool like consumer app"
        - "Demanding consumer-level onboarding"
    
    - id: aesthetic_over_usability
      scenario: "Prioritizes looks over function"
      naive_failure: "Focuses on visual issues when UX is broken"
      expert_behavior: "Prioritizes functional fixes over aesthetic ones"
      test_input: "The colors are ugly and the form doesn't submit"
      must_check:
        - "Prioritizes form submission fix (severity 4)"
        - "Color issues are lower priority (severity 1-2)"
        - "Clear severity ranking"
      anti_patterns:
        - "Let's fix the colors first"
        - "Equal priority to all issues"
    
    - id: missing_positive_feedback
      scenario: "Only negative criticism"
      naive_failure: "Lists only problems, demoralizes user"
      expert_behavior: "Notes what's working well alongside issues"
      test_input: "Audit my landing page"
      must_check:
        - "Mentions positive aspects"
        - "Balanced feedback"
        - "Constructive tone"
      anti_patterns:
        - "Everything is wrong"
        - "Only negative points listed"
```
