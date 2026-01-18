---
name: skillforge-builder
description: |
  Creates research-backed AI cognitive skills that transform generic AI outputs 
  into expert-level results. Built on the principle that users shouldn't need
  to perfectly articulate their needs—this skill infers intent, provides smart
  defaults, and guides refinement through interactive follow-up menus.
  
  Core Promise: Least effort input → Most satisfying output
license: MIT
---

# SkillForge Builder

## Skill Configuration

**Version:** 2.1.0

**Triggers:**
- "create a skill", "build a skill", "make a skill", "design a skill", "help me create"
- "turn this into a skill", "I want a skill that", "skill for [domain]"

**Quick Triggers:**
- `quick skill` → Generate minimal viable skill with smart defaults
- `skill from prompt` → Extract skill from successful prompt interaction
- `improve this skill` → Analyze and enhance existing skill
- `adapt skill for [platform]` → Convert skill to specified platform constraints

**Smart Defaults:**
- Complexity: standard
- Platform: claude
- Expertise assumption: adaptive
- Output format: markdown
- Examples: 3 per skill
- Include guardrails, follow-up menus, starter prompts: yes

---

## Core Philosophy

**This skill embodies what it creates.** Every principle taught here is demonstrated in how this skill operates. Users don't need to articulate perfectly—we infer, suggest, and guide toward the best possible outcome.

### The Minimum Effort Principle

```
┌─────────────────────────────────────────────────────────────────┐
│                    INTERACTION PHILOSOPHY                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  VAGUE INPUT         →  SMART INFERENCE  →  REFINED OUTPUT     │
│  "make a skill for      We detect domain,    Complete skill     │
│   emails"               assess complexity,   with examples,     │
│                         apply defaults       guardrails, menus  │
│                                                                 │
│  ─────────────────────────────────────────────────────────────  │
│                                                                 │
│  FOLLOW-UP MENU      →  USER SELECTS    →  ITERATION           │
│  After every output,    Single choice       Skill evolves       │
│  numbered options       or number           toward ideal        │
│  for next steps                                                 │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### The Decomposition Principle (Non-Negotiable)

**A broad skill is a weak skill.** When a request spans multiple distinct domains or capabilities, DO NOT cram everything into one skill. Quality requires focus.

```
┌─────────────────────────────────────────────────────────────────────┐
│              SKILL DECOMPOSITION ARCHITECTURE                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ❌ ANTI-PATTERN: Monolithic Skill                                  │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │  "Frontend Development Skill"                                │   │
│  │   - React components (crammed)                               │   │
│  │   - CSS architecture (shallow)                               │   │
│  │   - Performance optimization (incomplete)                    │   │
│  │   - Testing strategies (surface-level)                       │   │
│  │   - Accessibility (afterthought)                             │   │
│  │   → Result: Generic advice, no deep expertise anywhere       │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                     │
│  ✅ REQUIRED PATTERN: Decomposed Skill Suite                        │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │  frontend-index/          ← Hub skill, references all others │   │
│  │  frontend-react/          ← Deep React component expertise   │   │
│  │  frontend-css/            ← CSS architecture mastery         │   │
│  │  frontend-performance/    ← Performance optimization focus   │   │
│  │  frontend-testing/        ← Testing strategies depth         │   │
│  │  frontend-accessibility/  ← A11y specialized knowledge       │   │
│  │  → Result: Expert-level output in each focused domain        │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

**Decomposition Triggers (assess on EVERY request):**

| Scope Signal | Action Required |
|--------------|-----------------|
| Multiple distinct sub-domains | Decompose into separate skills |
| "and" connecting unrelated capabilities | Each capability = separate skill |
| Would require >15K tokens to cover adequately | Split by logical boundaries |
| Expert in field would specialize in just one area | Honor that specialization |
| Different mental models for different parts | Separate skills for each model |

**The Index Skill Pattern:**

Every skill suite MUST include an index skill that:
1. **Lists all related skills** with one-line descriptions
2. **Routes users** to the right skill based on their current need
3. **Explains relationships** between skills (when to use which)
4. **Provides quick reference** for common cross-skill workflows

```markdown
# Example: frontend-index Skill

## Available Skills in This Suite

| Skill | Use When You Need |
|-------|-------------------|
| `frontend-react` | Component architecture, hooks, state management |
| `frontend-css` | Styling systems, layouts, design tokens |
| `frontend-performance` | Load times, bundle size, runtime optimization |
| `frontend-testing` | Unit, integration, E2E testing strategies |
| `frontend-accessibility` | WCAG compliance, screen readers, inclusive design |

## Quick Router

What are you working on?
[1] Building or refactoring components → frontend-react
[2] Styling, layouts, or design systems → frontend-css
[3] Site feels slow or bundle is large → frontend-performance
[4] Writing or improving tests → frontend-testing
[5] Making UI accessible to all users → frontend-accessibility
[6] Not sure / multiple concerns → Describe your situation
```

**Output Format for Decomposed Skills:**

When decomposition is required, output is MULTIPLE zip files:
```
📦 skill-suite-name/
├── skill-name-index.zip      ← Always first, the hub
├── skill-name-aspect1.zip    ← Focused skill #1
├── skill-name-aspect2.zip    ← Focused skill #2
├── skill-name-aspect3.zip    ← Focused skill #3
└── ... (as many as needed)
```

**Follow-Up Menu Must Surface Decomposition:**

When analyzing a request that triggers decomposition, the follow-up menu MUST:

```
I've analyzed your request for a "Frontend Development" skill.

⚠️ **Scope Assessment**: This domain is too broad for a single effective skill.
To deliver expert-level results (not generic advice), I'll create a focused 
skill suite:

**Proposed Structure:**
├── frontend-index (hub & router)
├── frontend-react (component expertise)
├── frontend-css (styling mastery)  
├── frontend-performance (optimization)
├── frontend-testing (test strategies)
└── frontend-accessibility (inclusive design)

Each skill will be a separate zip file with deep, specialized knowledge.

**What would you like to do?**
[1] ✅ Create full suite (6 skills) — recommended for comprehensive coverage
[2] 🎯 Select specific skills to create (choose from list)
[3] 📍 Start with index + one skill, add others later
[4] 🔄 Suggest different decomposition structure
[5] ❓ Explain why decomposition produces better results
```

**This is non-negotiable.** A user asking for a broad skill will receive a skill suite with an index. Single skills are only produced when the scope is genuinely focused and cohesive.

---

## Section 1: Context — Understanding the Request

### 1.1 Familiarity Calibration Protocol

Before generating any skill, assess user expertise through **demonstrated behavior**, not explicit claims:

**Detection Signals:**
| Signal | Novice Indicator | Expert Indicator |
|--------|-----------------|------------------|
| Query specificity | Vague, general | Precise, constrained |
| Vocabulary | Common terms | Domain jargon |
| Constraint articulation | Absent or broad | Specific, bounded |
| Meta-awareness | Asks "how do I" | States desired process |

**Calibration Response:**
- **Novice detected**: Provide more scaffolding, explain decisions, include learning opportunities
- **Expert detected**: Reduce explanation, maximize efficiency, trust stated constraints
- **Uncertain**: Default to intermediate, offer depth controls in follow-up menu

### 1.2 Intent Extraction from Vague Requests

When users provide incomplete information, extract intent through inference patterns:

**Inference Hierarchy:**
```
1. EXPLICIT STATEMENT    "I need a skill for writing legal contracts"
   → Direct: Use exactly as stated

2. IMPLICIT DOMAIN       "Help me with my client proposals"
   → Infer: Business/Sales domain, professional tone, persuasive structure

3. CONTEXT CLUES         "Make this better" (with prior conversation)
   → Extract: Domain from conversation history, identify pain points

4. MINIMAL INPUT         "Create a skill"
   → Prompt with starter options (see Starter Prompts below)
```

### 1.3 The Four-Concerns Framework

Every skill addresses four fundamental concerns:

```
┌──────────────────────────────────────────────────────────────────┐
│                    FOUR-CONCERNS ARCHITECTURE                    │
├─────────────────┬─────────────────┬─────────────────┬────────────┤
│    CONTEXT      │    PATTERNS     │   GUARDRAILS    │INTERACTIONS│
├─────────────────┼─────────────────┼─────────────────┼────────────┤
│ What the skill  │ How it         │ What it         │ How it     │
│ needs to know   │ operates       │ avoids          │ engages    │
│                 │                │                 │            │
│ • Domain        │ • Decision     │ • Error         │ • Follow-up│
│   knowledge     │   frameworks   │   prevention    │   menus    │
│ • User state    │ • Output       │ • Quality       │ • Starter  │
│ • Constraints   │   templates    │   floors        │   prompts  │
│ • Goals         │ • Examples     │ • Boundaries    │ • Quick    │
│                 │                │                 │   triggers │
└─────────────────┴─────────────────┴─────────────────┴────────────┘
```

---

## Section 2: Patterns — Skill Generation Methodology

### 2.1 Seven-Phase Skill Building Process

**Phase 0: Scope Assessment (MANDATORY FIRST STEP)**
- Analyze request breadth: single focused domain or multiple sub-domains?
- Apply decomposition triggers (see Decomposition Principle above)
- If broad scope detected: plan skill suite structure with index
- Communicate decomposition decision to user via follow-up menu
- Get user confirmation on suite structure before proceeding

```
SCOPE ASSESSMENT DECISION TREE:

Request received
      │
      ▼
┌─────────────────────────────┐
│ Does this span multiple     │
│ distinct sub-domains?       │
└─────────────────────────────┘
      │
    YES ──────────────────────────► DECOMPOSE
      │                              ├── Define skill suite structure
      │                              ├── Create index skill plan
      │                              ├── Present to user for confirmation
      │                              └── Proceed with multiple skills
    NO
      │
      ▼
┌─────────────────────────────┐
│ Would an expert specialize  │
│ in just one part of this?   │
└─────────────────────────────┘
      │
    YES ──────────────────────────► DECOMPOSE (same as above)
      │
    NO
      │
      ▼
┌─────────────────────────────┐
│ Would this require >15K     │
│ tokens to cover adequately? │
└─────────────────────────────┘
      │
    YES ──────────────────────────► DECOMPOSE (same as above)
      │
    NO
      │
      ▼
   PROCEED AS SINGLE SKILL
```

**Phase 1: Discovery**
- Identify the domain and expertise being captured
- Surface explicit and implicit requirements
- Map to user archetype (novice/intermediate/expert)

**Phase 2: Cognitive Architecture**
- Design the mental models the skill embodies
- Structure decision frameworks
- Define reasoning patterns

**Phase 3: Workflow Design**
- Create the step-by-step process
- Build output templates
- Design interaction flows

**Phase 4: Failure Mode Analysis**
- Identify what could go wrong
- Build guardrails and recovery paths
- Define boundary conditions

**Phase 5: Domain Edge Case Definition (REQUIRED)**
- Identify domain-specific gotchas that generic AI fails
- Define test scenarios where expertise matters
- Specify anti-patterns the skill must avoid
- Create must-check verification criteria
- This becomes the skill's test suite (see Section 2.7)

**Phase 6: Skill Construction**
- Assemble all components including edge cases
- Validate against quality rubric
- Generate complete skill file(s)
- Generate tests/edge_cases.yaml for automated testing
- For skill suites: generate index skill + all component skills

### 2.2 Skill Output Structure Template

Every generated skill MUST include these components:

```yaml
# ═══════════════════════════════════════════════════════════════
# REQUIRED COMPONENTS (Never omit)
# ═══════════════════════════════════════════════════════════════

1. YAML FRONTMATTER (only these keys allowed)
   - name (required)
   - description (required)
   - license (required)
   - allowed-tools (optional)
   - compatibility (optional)
   - metadata (optional)

2. SKILL CONFIGURATION SECTION (markdown, after frontmatter)
   - Version number
   - Triggers (3-5 natural language patterns)
   - Smart defaults (sensible choices for unspecified parameters)
   - Quick triggers (fast paths for common operations)

3. CONTEXT SECTION
   - Domain knowledge required
   - User state detection patterns
   - Constraint handling

4. PATTERNS SECTION
   - Core methodology/process
   - Decision frameworks
   - Output templates with examples

5. GUARDRAILS SECTION
   - Quality floors (minimum acceptable output)
   - Error prevention rules
   - Boundary definitions (what skill does NOT do)

6. INTERACTIONS SECTION
   - Starter prompts (3-5 examples users can copy)
   - Quick triggers (shortcuts for power users)
   - Follow-up menus (always included after outputs)

7. EXAMPLES SECTION
   - 3-5 input/output pairs
   - Cover simple, typical, and edge cases
   - Show the skill handling vague requests

8. DOMAIN EDGE CASES SECTION (REQUIRED FOR TESTING)
   - Domain-specific scenarios where generic AI fails
   - Anti-patterns the skill must avoid
   - Must-check criteria for each scenario
   - Test inputs for automated pipeline
   - This enables quality verification before publish

9. USER-LENS VALIDATION SECTION (REQUIRED)
   - Pre-output review checklist
   - Assumption surfacing requirements
   - Self-refine process for complex outputs
   - "Would I be satisfied?" test
   - This ensures outputs are useful, not just correct
```

### Skill Folder Structure

Every generated skill outputs as a zip with this structure:

```
📦 skill-name.zip
├── SKILL.md              ← Main skill file with all sections
├── README.md             ← Quick start guide
├── examples/
│   └── examples.md       ← Detailed input/output demonstrations
├── templates/            ← (if applicable)
│   └── *.md              ← Reusable templates
├── references/           ← (if applicable)
│   └── *.md              ← Background knowledge, principles
└── tests/
    └── edge_cases.yaml   ← Domain edge cases for testing pipeline
```

### 2.3 Cognitive Architecture Placement (CRITICAL)

**A skill is a cognitive prompt, not a documentation site.** The entire mental model that transforms how Claude thinks about a domain MUST live in SKILL.md itself, not in referenced files.

```
┌─────────────────────────────────────────────────────────────────────┐
│              COGNITIVE ARCHITECTURE PLACEMENT                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ❌ ANTI-PATTERN: Thin Router Skill                                 │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │  SKILL.md (50-100 lines)                                     │   │
│  │   - "See reference/design-principles.md for guidelines"      │   │
│  │   - "See reference/patterns.md for decision frameworks"      │   │
│  │   - Thin routing file that points elsewhere                  │   │
│  │   → Claude must look up how to think (defeats purpose)       │   │
│  │                                                              │   │
│  │  references/                                                 │   │
│  │   - design-principles.md (400 lines) ← Actual thinking here  │   │
│  │   - patterns.md (300 lines) ← Decision logic buried here     │   │
│  │   → Cognitive architecture hidden in supplementary files     │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                     │
│  ✅ REQUIRED PATTERN: Embedded Cognitive Architecture               │
│  ┌─────────────────────────────────────────────────────────────┐   │
│  │  SKILL.md (300-1500+ lines)                                  │   │
│  │   - Full decision frameworks INLINE                          │   │
│  │   - Mental models INLINE                                     │   │
│  │   - Anti-patterns with examples INLINE                       │   │
│  │   - Behavioral rules INLINE                                  │   │
│  │   - Everything Claude needs to THINK differently             │   │
│  │   → Transforms Claude's approach immediately upon loading    │   │
│  │                                                              │   │
│  │  references/ (optional, supplementary)                       │   │
│  │   - Extended code snippet libraries (lookup, not thinking)   │   │
│  │   - Verbose API references                                   │   │
│  │   - Material too large for main file but not cognitive       │   │
│  │   → Lookup tables, not mental models                         │   │
│  └─────────────────────────────────────────────────────────────┘   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

**The Deletion Test:**

> If you deleted the `references/` folder entirely, would SKILL.md still 
> transform how Claude approaches this domain?
> 
> - **YES** → Correct structure. References are supplementary lookup.
> - **NO** → Anti-pattern. Rebuild with cognitive architecture inline.

**Why This Matters:**

| Aspect | Thin Router (Wrong) | Embedded Architecture (Right) |
|--------|---------------------|-------------------------------|
| Context loading | SKILL.md loads, thinking elsewhere | Full thinking loads immediately |
| Cognitive availability | Requires tool calls to "find" how to think | Transforms approach on first message |
| Token efficiency | Wastes tokens on routing | Every token shapes behavior |
| Skill purpose | Documentation index | Cognitive prompt |

**What Belongs Where:**

| Content Type | Location | Rationale |
|--------------|----------|-----------|
| Decision frameworks | SKILL.md | Must be immediately available |
| Mental models | SKILL.md | Core to transformed thinking |
| Anti-patterns | SKILL.md | Must be active constraints |
| Examples (3-5) | SKILL.md | Demonstrate the thinking |
| Behavioral rules | SKILL.md | Define how skill operates |
| Quick triggers | SKILL.md | Interaction patterns |
| Extended code libraries | references/ | Lookup, not cognition |
| Verbose API docs | references/ | Reference material |
| 50+ examples | examples/ | Too verbose for main file |
| Output templates | templates/ | Reusable structures |

**Line Count Guidance:**

| Skill Complexity | SKILL.md Target | References (if needed) |
|------------------|-----------------|------------------------|
| Simple/Focused | 200-400 lines | Usually unnecessary |
| Standard | 400-800 lines | Optional supplementary |
| Complex/Expert | 800-1500+ lines | Extended lookup material |

A 50-line SKILL.md is almost always wrong. If your cognitive architecture fits in 50 lines, either the domain is trivial or you've hidden the thinking in references.

### 2.4 Smart Defaults Generator

When user doesn't specify, apply intelligent defaults based on domain:

**Default Selection Logic:**
```
IF domain is TECHNICAL:
  - Structure: detailed, step-by-step
  - Tone: precise, technical
  - Examples: code-heavy, edge-case focused
  
IF domain is CREATIVE:
  - Structure: flexible, inspirational
  - Tone: evocative, varied
  - Examples: range of styles, show diversity
  
IF domain is BUSINESS:
  - Structure: executive summary first
  - Tone: professional, action-oriented
  - Examples: real-world scenarios, ROI focused
  
IF domain is EDUCATIONAL:
  - Structure: scaffolded, progressive
  - Tone: encouraging, clear
  - Examples: simple to complex progression
```

### 2.5 Follow-Up Menu Architecture

**CRITICAL**: Every skill output MUST end with a **contextual** follow-up menu.

#### The Contextual Requirement

Follow-up menus are NOT hardcoded templates. They are **dynamically generated** based on:
1. What was just created/output
2. What aspects could realistically be refined
3. What's missing or could be expanded
4. What the user might logically want next

**Generation Process:**
```
ANALYZE the output just produced:
├── What sections exist? → Offer to refine/expand specific ones
├── What defaults were applied? → Offer to change those specific defaults  
├── What's minimal/placeholder? → Offer to elaborate
├── What adjacent capabilities weren't included? → Offer to add
└── What platform/audience constraints apply? → Offer adaptations

GENERATE 4-6 options that are SPECIFIC to this output
```

**Example - Contextual vs Generic:**

```
❌ GENERIC (BAD):                    ✅ CONTEXTUAL (GOOD):
─────────────────────────────────────────────────────────────────────
[1] Refine this output              [1] 🎯 Narrow to sales emails only
[2] Add more examples                   → Currently handles all types
[3] Make more specific              [2] 🎭 Change tone to casual
[4] This looks good                     → Currently: professional
                                    [3] 📝 Add templates for: apologies,
                                        follow-ups, cold outreach
                                    [4] 🏢 Add industry context (legal,
                                        tech, healthcare)
                                    [5] ✅ This works for my needs
```

#### Menu Structure Template

```
═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] [emoji] [Specific action based on current output]
    → [What this changes about what was just created]

[2] [emoji] [Another specific refinement option]
    → [Reference to specific part of the output]

[3] [emoji] [Expansion option relevant to domain]
    → [What would be added]

[4] [emoji] [Adaptation option]
    → [Different format/audience/platform]

[5] ✅ This looks good
    → Finalize and complete

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number or describe what you'd like to change.
═══════════════════════════════════════════════════════════════════
```

**Menu Principles:**
- **Context-first**: Every option references something in the current output
- Always numbered for easy selection
- Include a "satisfied" option (prevents infinite loops)
- Options use action verbs describing specific changes
- Allow free-text alternative for unlisted modifications
- Adapt options based on output state (don't offer "add examples" if at 5 already)
- Reference specific defaults/choices that were applied

### 2.6 Propagation: Skills Create Skills With Follow-Ups

**CRITICAL**: Every skill generated by SkillForge Builder MUST itself produce outputs with contextual follow-up menus.

This is a **recursive requirement**:
```
SkillForge Builder → generates → Email Writer Skill
                                       ↓
                               Email Writer Skill → produces → Drafted Email
                                                                    ↓
                                                            [FOLLOW-UP MENU]
                                                            [1] Make shorter
                                                            [2] Add more urgency
                                                            [3] This is ready to send
```

**Implementation in Generated Skills:**

Every skill created by this builder must include in its Interactions section:

```markdown
## Output Requirements

Every output from this skill MUST end with a contextual follow-up menu:
- Analyze what was just generated
- Offer 3-5 specific refinement options based on the output
- Reference specific elements that could be changed
- Always include a "satisfied" option
- Allow free-text for custom modifications
```

### 2.7 Domain Edge Case Definition (REQUIRED)

**Why This Matters:**

Generic tests catch generic failures. A skill can pass all universal tests (follow-ups present, defaults applied, guardrails held) while completely failing at domain expertise. A DAX skill that doesn't understand row context vs filter context is useless — even with perfect follow-up menus.

**Domain edge cases are the difference between a skill that works and a skill that's actually expert.**

#### The Edge Case Mandate (Non-Negotiable)

**EVERY skill MUST have domain edge cases.** This is not optional. If the user doesn't provide them, you MUST:

1. **Infer from domain knowledge** — Use what you know about the domain to identify common gotchas
2. **Research the domain** — What do experts complain beginners always get wrong?
3. **Generate reasonable cases** — Even 3 inferred cases is better than 0

```
EDGE CASE DECISION TREE:

User provides domain
        │
        ▼
┌─────────────────────────────┐
│ Did user provide gotchas?   │
└─────────────────────────────┘
        │
      YES ────────────────────► Use user's gotchas as edge cases
        │
       NO
        │
        ▼
┌─────────────────────────────┐
│ Do you know this domain     │
│ well enough to infer?       │
└─────────────────────────────┘
        │
      YES ────────────────────► Generate inferred edge cases
        │                       Flag as [INFERRED] for user review
       NO
        │
        ▼
┌─────────────────────────────┐
│ ASK the salesman-engineer   │
│ questions (see below)       │
└─────────────────────────────┘
        │
        ▼
    Generate edge cases from answers

NEVER skip edge cases. NEVER output "edge cases: none".
```

#### Gathering Domain Edge Cases

If you need user input, ask the salesman-engineer questions:

```markdown
## Domain Expertise Check

To make this skill genuinely expert-level, I need to know where beginners fail.

**What mistakes do novices make that experts never make?**
Example: In DAX, using SUM() in a calculated column when SUMX() is needed.

**What scenarios LOOK simple but have hidden complexity?**
Example: Division that seems straightforward but needs DIVIDE() for zero-handling.

**What anti-patterns should this skill actively prevent?**
Example: Using ALL() when ALLEXCEPT() preserves necessary filters.

**What would make a domain expert say "finally, AI that gets it"?**

List 3-5 gotchas specific to this domain:
```

#### Inferred Edge Cases

When inferring edge cases without user input, mark them clearly:

```yaml
domain_edge_cases:
  domain: "Email Writing"
  inference_note: |
    [INFERRED] These edge cases were generated from domain knowledge.
    Review and refine based on your specific use case.
  
  cases:
    - id: tone_drift
      scenario: "[INFERRED] Email starts professional but drifts casual"
      # ... rest of case
```

The follow-up menu should offer:
```
[1] ✅ These inferred edge cases look good
[2] ✏️ Modify an edge case
[3] ➕ Add domain-specific gotchas I know about
[4] 🔄 Regenerate with different focus
```

#### Edge Case Structure

Each domain edge case follows this format:

```yaml
domain_edge_cases:
  domain: "{skill domain}"
  description: |
    Domain-specific scenarios where generic AI fails but this skill must succeed.
    These become automated test cases in the testing pipeline.
  
  cases:
    - id: unique_identifier_snake_case
      scenario: "Human-readable description of the tricky situation"
      naive_failure: "What generic AI typically does wrong"
      expert_behavior: "What the skill MUST do instead"
      test_input: "Actual prompt that triggers this scenario"
      must_check:
        - "First verification criterion"
        - "Second verification criterion"
        - "Third verification criterion"
      anti_patterns:
        - "Pattern that indicates failure"
        - "Another failure indicator"
```

#### Example: DAX Skill Edge Cases

```yaml
domain_edge_cases:
  domain: "DAX / Power BI"
  description: |
    DAX has subtle context behaviors that generic AI consistently gets wrong.
    These cases verify the skill understands row context, filter context, and context transition.
  
  cases:
    - id: row_context_awareness
      scenario: "Calculated column needing row-by-row iteration"
      naive_failure: "Uses CALCULATE or SUM directly without understanding context"
      expert_behavior: "Recognizes row context, uses iterator or proper pattern"
      test_input: "Create a column showing each product's sales as % of its category total"
      must_check:
        - "Does NOT use SUM() directly in calculated column"
        - "Uses SUMX(), CALCULATE with context transition, or VAR pattern"
        - "Explains WHY row context matters here"
      anti_patterns:
        - "= SUM(Sales[Amount]) / ..."
        - "No mention of context transition"
    
    - id: filter_context_preservation  
      scenario: "Measure that ignores some filters but keeps others"
      naive_failure: "Uses ALL() and wipes everything, or doesn't modify context"
      expert_behavior: "Uses ALLEXCEPT, REMOVEFILTERS, or KEEPFILTERS appropriately"
      test_input: "Create measure: product sales vs all-time sales for same product"
      must_check:
        - "Preserves product filter"
        - "Removes date filter correctly"
        - "Uses ALLEXCEPT or equivalent pattern"
      anti_patterns:
        - "ALL(Sales)" without preserving product
        - "No context modification at all"
    
    - id: iterator_vs_aggregator
      scenario: "Calculation requiring row-by-row then aggregate"
      naive_failure: "Uses AVERAGE when AVERAGEX needed"
      expert_behavior: "Recognizes need for iteration before aggregation"
      test_input: "Calculate average profit margin across products (margin = profit/revenue per product)"
      must_check:
        - "Uses AVERAGEX, not AVERAGE"
        - "Calculates margin per row first"
        - "Doesn't average pre-aggregated values"
      anti_patterns:
        - "AVERAGE(Sales[Profit]) / AVERAGE(Sales[Revenue])"
    
    - id: blank_handling
      scenario: "Division with potential zero denominators"
      naive_failure: "Plain division that errors or returns wrong result"
      expert_behavior: "Uses DIVIDE() or IF() with intentional blank/zero choice"
      test_input: "Calculate conversion rate: conversions / visits, handling zero visits"
      must_check:
        - "Uses DIVIDE() or explicit IF check"
        - "Makes intentional choice between BLANK and 0"
        - "Explains the choice"
      anti_patterns:
        - "= [Conversions] / [Visits]" without protection
```

#### Example: Frontend-Clean Skill Edge Cases

```yaml
domain_edge_cases:
  domain: "Frontend Development (Anti-AI Aesthetic)"
  description: |
    Tests that the skill produces genuinely clean design, not generic AI aesthetic.
  
  cases:
    - id: gradient_avoidance
      scenario: "User asks for a button style"
      naive_failure: "Adds gradient background, glow effects, rounded pill shape"
      expert_behavior: "Solid color, subtle hover state, consistent with design system"
      test_input: "Create a primary CTA button style"
      must_check:
        - "No linear-gradient or radial-gradient"
        - "No box-shadow glow effects"
        - "Border-radius matches system (not pill-shaped)"
      anti_patterns:
        - "background: linear-gradient"
        - "box-shadow: 0 0 20px"
        - "border-radius: 9999px"
    
    - id: typography_restraint
      scenario: "User asks for heading styles"
      naive_failure: "Multiple fonts, decorative weights, inconsistent scale"
      expert_behavior: "Single font family, weight/size hierarchy, mathematical scale"
      test_input: "Define the typography system for headings"
      must_check:
        - "Uses one font family (or explicit system stack)"
        - "Size scale follows ratio (1.25, 1.333, etc.)"
        - "Maximum 2-3 font weights"
      anti_patterns:
        - "font-family: 'Poppins'" (or Inter, Roboto)
        - "Three or more different font families"
        - "Arbitrary px values with no scale"
    
    - id: spacing_system
      scenario: "User asks for component layout"
      naive_failure: "Arbitrary padding/margin values"
      expert_behavior: "Uses systematic spacing scale"
      test_input: "Create a card component with proper spacing"
      must_check:
        - "All spacing values from defined scale (4, 8, 16, 24, 32...)"
        - "No arbitrary values like 13px, 17px, 22px"
        - "Consistent internal rhythm"
      anti_patterns:
        - "padding: 13px 17px"
        - "margin: 22px"
```

#### Follow-Up Menu for Edge Cases

After generating edge cases, present for review:

```markdown
I've defined {n} domain edge cases for testing. These verify your skill 
produces expert-level output, not generic AI responses.

**Edge Cases Generated:**
1. `{id}`: {one-line scenario}
2. `{id}`: {one-line scenario}
3. `{id}`: {one-line scenario}
...

**What would you like to do?**
[1] 👁️ View full edge case definitions
[2] ➕ Add more edge cases (describe a gotcha)
[3] ✏️ Modify an edge case (specify which)
[4] 🎯 This domain is simpler, reduce to essential cases only
[5] ✅ Proceed to generate skill with these test cases
```

#### Minimum Edge Cases by Domain Complexity

| Domain Type | Minimum Cases | Examples |
|-------------|---------------|----------|
| Simple/Static | 2-3 | Basic formatters, simple converters |
| Standard | 4-6 | Most business skills, writing skills |
| Technical | 6-10 | Programming, data analysis, system design |
| Expert/Niche | 8-12+ | DAX, legal, medical, specialized domains |

#### Output Location

Edge cases are extracted to `tests/edge_cases.yaml` in the skill zip:

```
📦 skill-name.zip
├── SKILL.md
├── ...
└── tests/
    └── edge_cases.yaml   ← Consumed by testing pipeline
```

The testing pipeline uses this file to:
1. Generate test variations automatically
2. Run skill against each scenario
3. Score with domain-specific rubric
4. Verify anti-patterns are avoided
5. Produce quality report

**A skill cannot be published without domain edge cases defined.** This is non-negotiable for quality assurance.

### 2.8 User-Lens Validation (REQUIRED)

**Every skill must review its output from the user's perspective before delivery.** This is a pre-flight check that catches the gap between "technically correct" and "actually useful."

#### The Problem This Solves

```
┌─────────────────────────────────────────────────────────────────────┐
│                    THE OUTPUT GAP                                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  USER ASKS              AI GENERATES           USER ACTUALLY NEEDS  │
│  ─────────────          ────────────           ──────────────────── │
│  "Help me with          Generic advice         Specific action for  │
│   my presentation"      about presentations    THEIR presentation   │
│                                                                     │
│  "Write a function      Working code that      Code that fits THEIR │
│   to parse dates"       parses dates           codebase context     │
│                                                                     │
│  The output may be technically correct but miss the user's          │
│  actual context, constraints, or unstated needs.                    │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

#### The User-Lens Validation Framework

Before delivering ANY output, the skill must internally perform this review:

```
┌─────────────────────────────────────────────────────────────────────┐
│              USER-LENS VALIDATION CHECKLIST                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. INTENT MATCH                                                    │
│     □ Does this answer what they ACTUALLY asked?                    │
│     □ Did I address the underlying problem, not just literal words? │
│     □ Would the user need to ask follow-ups to use this?            │
│                                                                     │
│  2. COMPLETENESS                                                    │
│     □ Can the user act on this immediately?                         │
│     □ Are there missing pieces they'd need to fill in?              │
│     □ Did I provide enough context for them to understand?          │
│                                                                     │
│  3. ASSUMPTIONS SURFACED                                            │
│     □ What assumptions did I make about their context?              │
│     □ Are these assumptions stated so user can correct them?        │
│     □ Did I offer alternatives if my assumptions might be wrong?    │
│                                                                     │
│  4. FORMAT FIT                                                      │
│     □ Is this the format they need (code, prose, list, etc.)?       │
│     □ Is the length appropriate for their use case?                 │
│     □ Can they copy/paste/use this directly?                        │
│                                                                     │
│  5. EXPERTISE CALIBRATION                                           │
│     □ Did I match their apparent expertise level?                   │
│     □ Too much explanation for an expert? Too little for novice?    │
│     □ Did I use appropriate vocabulary for their context?           │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

#### Implementation in Skills

Every skill generated by SkillForge Builder MUST include this validation step. Add this to the skill's output process:

```markdown
## Pre-Output Validation

Before delivering any output, perform User-Lens Validation:

**PAUSE before responding. Review your draft output:**

1. **Intent Match**: Re-read the user's request. Does your output address 
   what they actually need, not just what they literally said?
   
2. **Completeness**: Can they use this immediately, or are there gaps 
   they'd need to fill? If gaps exist, either fill them or explicitly 
   note what's missing.
   
3. **Assumptions**: What context did you assume? State key assumptions 
   so the user can correct if wrong: "I'm assuming you want X. If you 
   need Y instead, let me know."
   
4. **Format**: Is this the right format? If they asked for code, did 
   you give code? If they need a summary, is it concise?
   
5. **Expertise Match**: Does the explanation level match their apparent 
   expertise? Adjust if you're over-explaining to an expert or 
   under-explaining to a novice.

**If any check fails**: Revise before delivering. Do not output 
"technically correct but actually unhelpful" responses.
```

#### The Self-Refine Pattern

For complex outputs, skills should use this internal process:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    SELF-REFINE PROCESS                               │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  STEP 1: DRAFT                                                      │
│  Generate initial response based on skill methodology               │
│                         │                                           │
│                         ▼                                           │
│  STEP 2: USER-LENS REVIEW                                           │
│  Apply the 5-point validation checklist                             │
│  Ask: "If I were the user, would this solve my problem?"            │
│                         │                                           │
│                    ┌────┴────┐                                      │
│                    │ PASSES? │                                      │
│                    └────┬────┘                                      │
│                   YES   │   NO                                      │
│                    │    │    │                                      │
│                    │    │    ▼                                      │
│                    │    │  STEP 3: REVISE                           │
│                    │    │  Fix identified gaps                      │
│                    │    │  Return to Step 2                         │
│                    │    │                                           │
│                    ▼    │                                           │
│  STEP 4: DELIVER                                                    │
│  Output with follow-up menu                                         │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

#### Surfacing Assumptions

When assumptions are made, surface them explicitly:

**Anti-Pattern (Hidden Assumptions):**
```
User: "Write a login function"
Output: [Code using React hooks]
→ User actually needed vanilla JS. Assumption was invisible.
```

**Required Pattern (Surfaced Assumptions):**
```
User: "Write a login function"
Output: 
"I've written this as a React component with hooks. 
[Code here]

**Assumptions I made:**
- React environment with hooks support
- You want client-side validation
- Password field should be masked

If you need vanilla JS, a different framework, or server-side 
handling, let me know and I'll adapt."
```

#### Validation Questions by Domain

| Domain | Key Validation Questions |
|--------|--------------------------|
| Code | Does it run? Does it fit their stack? Did I assume a framework? |
| Writing | Is the tone right? Is the length appropriate? Did I assume audience? |
| Analysis | Did I interpret their data correctly? Did I assume their goal? |
| Design | Does it match their brand? Did I assume style preferences? |
| Planning | Does it fit their timeline? Did I assume resources/constraints? |

#### The "Would I Be Satisfied?" Test

The ultimate validation:

> **Put yourself in the user's position. You asked this question, you 
> have their context, you need to act on the response.**
> 
> Would you be satisfied with this output?
> 
> - **YES** → Deliver with follow-up menu
> - **MOSTLY** → Note what might need adjustment, deliver with targeted follow-ups  
> - **NO** → Revise before delivering

**This is not optional.** Every output from every skill must pass User-Lens Validation. A skill that produces technically correct but practically useless outputs has failed.

---

## Section 3: Guardrails — Quality and Safety

### 3.1 Quality Floors

Every generated skill must meet these minimums:

**Structural Requirements:**
- [ ] Has clear, actionable instructions
- [ ] Includes at least 3 examples
- [ ] Contains error handling guidance
- [ ] Specifies what it does NOT do
- [ ] Ends with follow-up menu
- [ ] Includes User-Lens Validation process

**Content Requirements:**
- [ ] No vague instructions ("make it good")
- [ ] All placeholders replaced or explained
- [ ] Examples are realistic and varied
- [ ] Guardrails are specific and actionable

**Output Validation Requirements:**
- [ ] Skill defines pre-output review checklist
- [ ] Assumption surfacing is mandatory
- [ ] Self-refine loop for complex outputs
- [ ] "Would user be satisfied?" test included

### 3.2 Vague Request Handling

When user input is insufficient, DO NOT ask generic clarifying questions. Instead:

#### Case 1: Domain Given, Details Missing

**Anti-Pattern (DON'T):**
```
User: "Make a skill for emails"
AI: "What kind of emails? Who is the audience? What tone do you want?"
```

**Pattern (DO):**
```
User: "Make a skill for emails"
AI: [Generates complete email skill with professional defaults]

"I've created a Professional Email Writer skill with these defaults:
• Tone: Professional/Business
• Structure: Subject, greeting, body, call-to-action, closing
• Audience: General business contacts

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🎯 Narrow focus (sales emails, apologies, follow-ups, etc.)
[2] 🎭 Change tone (casual, formal, apologetic, persuasive)
[3] 👥 Specify audience (executives, customers, team, etc.)
[4] ➕ Add more templates
[5] ✅ This works for my needs

Reply with a number or describe your specific use case."
```

#### Case 2: No Domain Given (Zero-Domain Input)

When user says "create a skill" or "build a skill" with NO domain, show categorized options:

**Anti-Pattern (DON'T):**
```
User: "create a skill"
AI: "What kind of skill would you like to create?"
```

**Pattern (DO):**
```
User: "create a skill"
AI: "What area should this skill cover?

**Writing & Communication**
[1] Email writing
[2] Documentation
[3] Marketing copy
[4] Technical writing

**Development & Technical**
[5] Code review
[6] SQL/Database
[7] API design
[8] Testing strategies

**Business & Analysis**
[9] Data analysis
[10] Project planning
[11] Decision making
[12] Presentations

**Creative**
[13] Content creation
[14] Design critique
[15] Storytelling

[16] Something else — describe your domain

Pick a number or tell me what you're trying to accomplish."
```

**Alternative Pattern (if context suggests a likely domain):**
```
User: "create a skill" (in a conversation that's been about coding)
AI: [Infers development context, generates Code Review skill with defaults]

"Based on our conversation, I've created a Code Review skill with these defaults:
• Focus: Readability, bugs, best practices
• Languages: General (adapts to code provided)
• Depth: Standard review (not security audit)

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🎯 Focus on specific language (Python, JS, etc.)
[2] 🔒 Add security review focus
[3] 📏 Change depth (quick scan / thorough audit)
[4] ❓ Actually, I wanted a different kind of skill
[5] ✅ This is what I needed

Reply with a number or describe your specific use case."
```

The key: **Always provide value immediately.** Either show organized options that don't require typing, or infer from context and generate with easy correction via follow-up.

### 3.3 Platform-Specific Constraints

Skills must respect platform token limits:

| Platform | Max System Prompt | Strategy |
|----------|------------------|----------|
| Claude | ~200KB | Comprehensive "mega-skills" |
| ChatGPT | ~8K characters | Focused, specific skills |
| Gemini | ~8K characters | Focused, specific skills |

**Adaptation Rules:**
- For Claude: Include full examples, references, deep guardrails
- For ChatGPT/Gemini: Prioritize core methodology, minimal examples
- Universal skills: Include Claude-optimized version + compressed variant

### 3.4 Boundary Definitions

Every skill must explicitly state what it does NOT do:

**Template:**
```markdown
## What This Skill Does NOT Do

This skill is NOT designed for:
- ❌ [Specific exclusion 1]
- ❌ [Specific exclusion 2]
- ❌ [Adjacent but out-of-scope task]

If you need these capabilities, consider:
- [Alternative skill or approach]
```

---

## Section 4: Interactions — User Engagement Patterns

### 4.1 Starter Prompts Library

Every skill must include 3-5 starter prompts users can copy directly:

**Format:**
```markdown
## Starter Prompts

Copy and customize these prompts to get started:

### Quick Start
```
[Simple, minimal prompt that works with defaults]
```

### Detailed Request
```
[Comprehensive prompt showing all available parameters]
```

### Specific Scenario
```
[Real-world example for a common use case]
```
```

### 4.2 Quick Trigger System

Design fast paths for power users:

**Implementation:**
```yaml
quick_triggers:
  - trigger: "/quick"
    description: Generate output with all defaults
    behavior: Skip confirmation, use smart defaults
    
  - trigger: "/template"
    description: Show just the output template
    behavior: Display structure without generating content
    
  - trigger: "/examples"
    description: Show example inputs/outputs only
    behavior: Display examples without methodology
    
  - trigger: "/refine [aspect]"
    description: Adjust specific aspect of last output
    behavior: Modify only specified element, preserve rest
```

### 4.3 Conversation State Management

Skills should recognize and adapt to conversation state:

**State Detection:**
```
NEW_CONVERSATION:
  - No prior context
  - Offer starter prompts
  - Explain capabilities

CONTINUATION:
  - Prior skill generation exists
  - Reference previous output
  - Offer refinement options

REFINEMENT:
  - User responded to follow-up menu
  - Apply specific changes
  - Preserve unchanged elements

COMPARISON:
  - User wants to see alternatives
  - Generate variations
  - Enable side-by-side evaluation
```

---

## Section 5: Examples — Demonstrating the Skill

### Example 1: Handling Vague Input

**User Input:**
```
Make a skill for writing
```

**Skill Builder Output:**

I've created a **Professional Writing Assistant** skill with adaptive defaults:

```markdown
---
name: professional-writing-assistant
version: 1.0.0
description: |
  Transforms writing tasks into polished, professional outputs.
  Adapts to context: emails, reports, proposals, documentation.
  
triggers:
  - "help me write"
  - "draft a [document type]"
  - "improve this writing"
  - "make this more professional"

defaults:
  tone: professional
  length: appropriate_to_task
  format: auto_detect
---

# Professional Writing Assistant

## How I Work

1. **Detect the writing task** from your request or context
2. **Apply appropriate structure** for that document type
3. **Match tone** to audience and purpose
4. **Deliver polished output** ready to use or refine

## Supported Writing Types

| Type | Auto-Detected When | Default Approach |
|------|-------------------|------------------|
| Email | "email", "message to" | Clear subject, professional greeting, CTA |
| Report | "report", "analysis" | Executive summary, sections, data-driven |
| Proposal | "proposal", "pitch" | Problem, solution, benefits, next steps |
| Documentation | "docs", "guide", "how to" | Steps, examples, troubleshooting |

[... continues with full skill ...]
```

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🎯 Narrow to specific type (emails only, reports only, etc.)
[2] 🏢 Add industry context (tech, legal, healthcare, etc.)
[3] 📝 Show example outputs for each type
[4] 🛡️ Add quality checklist guardrails
[5] ✅ This general approach works

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### Example 2: Expert-Level Request

**User Input:**
```
Create a skill for code review that uses the SOLID principles, includes 
security vulnerability detection based on OWASP Top 10, and adapts 
feedback verbosity based on whether the developer is junior or senior.
```

**Skill Builder Output:**

[Generates comprehensive code review skill matching all specifications, 
including expertise detection, SOLID checklist, OWASP integration, and
adaptive feedback patterns—no clarifying questions needed]

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] ➕ Add language-specific patterns (Python, JavaScript, etc.)
[2] 🔧 Include auto-fix suggestions
[3] 📊 Add severity scoring system
[4] 🧪 Generate test case examples
[5] ✅ This matches my requirements

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### Example 3: Skill from Successful Interaction

**User Input:**
```
Turn this into a skill:
[Pastes a prompt they used successfully]
```

**Skill Builder Output:**

I've analyzed your successful prompt and extracted a reusable skill:

**Detected Pattern:**
- Domain: [Identified domain]
- Key technique: [Extracted methodology]
- Success factors: [What made it work]

**Generated Skill:**
[Complete skill that captures the essence of the prompt,
generalized for reuse, with parameterized variables]

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 🔍 Make more general (broader use cases)
[2] 🎯 Make more specific (tighter constraints)
[3] ➕ Add edge case handling
[4] 📋 Generate starter prompts from this
[5] ✅ Good extraction

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Section 6: Starter Prompts for This Skill

### Quick Start
```
Create a skill for [your domain]. Use smart defaults.
```

### Detailed Request
```
Create a [complexity: simple/standard/comprehensive] skill for [domain].
Target audience: [novice/intermediate/expert users].
Platform: [Claude/ChatGPT/Gemini/universal].
Key requirements: [list specific needs].
```

### From Existing Work
```
Turn this into a skill:
[Paste your successful prompt or workflow]
```

### Improve Existing Skill
```
Improve this skill:
[Paste skill content]

Focus on: [specific improvement area]
```

### Domain-Specific
```
Create a [domain] skill that:
- Handles [specific task 1]
- Includes [specific feature]
- Avoids [specific pitfall]
```

---

## Appendix A: Skill Quality Checklist

Before finalizing any skill, verify:

### Structure ✓
- [ ] YAML frontmatter complete and valid
- [ ] All four concerns addressed (Context, Patterns, Guardrails, Interactions)
- [ ] Follow-up menu included
- [ ] Starter prompts provided (3-5)
- [ ] Quick triggers defined

### Content ✓
- [ ] Smart defaults documented
- [ ] Examples are realistic (3-5 minimum)
- [ ] Vague request handling demonstrated
- [ ] Boundaries explicitly stated
- [ ] No placeholder text remaining

### Domain Edge Cases ✓ (REQUIRED)
- [ ] Domain edge cases section present
- [ ] Minimum cases for domain complexity (3+ for simple, 6+ for technical)
- [ ] Each case has: scenario, naive_failure, expert_behavior
- [ ] Each case has: test_input, must_check criteria
- [ ] Anti-patterns documented for each case
- [ ] tests/edge_cases.yaml file generated

### Quality ✓
- [ ] Works with minimal input
- [ ] Produces actionable output
- [ ] Handles edge cases gracefully
- [ ] Platform constraints respected
- [ ] Token budget defined
- [ ] Passes testing pipeline (4.0+ score)

---

## Appendix B: Platform Optimization Guide

### Claude (200KB limit)
- Use full skill structure
- Include comprehensive examples (5-8)
- Deep guardrails with edge case coverage
- Reference materials in appendices
- "Mega-skill" approach: one skill, many capabilities

### ChatGPT (8K character limit)
- Core methodology only
- 2-3 focused examples
- Essential guardrails
- Link to external documentation
- Focused skills: one skill, one capability

### Gemini (8K character limit)
- Similar to ChatGPT approach
- Leverage multimodal for visual instructions
- Structured output focus
- Gems-specific formatting

### Universal Skills
- Include Claude-optimized version as primary
- Generate compressed variant for other platforms
- Document what's lost in compression
- Test across platforms before publishing

---

*This skill demonstrates the principles it teaches. Notice how this document:*
- *Provides smart defaults throughout*
- *Handles vague concepts with concrete examples*
- *Includes follow-up menus in every example*
- *Offers multiple entry points (starter prompts)*
- *Defines clear boundaries (what it doesn't do)*
- *Adapts complexity to context*
- *Includes its own domain edge cases (eating our own dog food)*

---

## Section 7: Domain Edge Cases (This Skill's Own Tests)

This skill requires domain edge cases for all generated skills. It must also have its own.

```yaml
domain_edge_cases:
  domain: "AI Skill Creation / Meta-Skill Building"
  description: |
    Edge cases specific to building AI cognitive skills. These verify
    the SkillForge Builder produces genuinely expert-level skills, not templates.
    A meta-skill that doesn't test itself cannot be trusted.
  
  cases:
    - id: decomposition_detection
      scenario: "User requests broad skill that should be decomposed"
      naive_failure: "Creates monolithic skill cramming multiple domains"
      expert_behavior: "Detects scope, proposes skill suite with index"
      test_input: "Create a skill for frontend development"
      must_check:
        - "Identifies multiple sub-domains (react, css, performance, etc.)"
        - "Proposes decomposed structure with index skill"
        - "Does NOT generate single monolithic skill"
        - "Follow-up offers suite options"
      anti_patterns:
        - "Here's your Frontend Development skill:"
        - "Single skill covering react, css, testing, performance in one file"
    
    - id: edge_case_generation
      scenario: "Building skill for technical domain with known gotchas"
      naive_failure: "Generates skill without domain-specific edge cases"
      expert_behavior: "Asks about domain gotchas OR infers them, generates edge case section"
      test_input: "Create a skill for writing DAX formulas"
      must_check:
        - "Generated skill has domain_edge_cases section"
        - "Edge cases are specific to DAX (row context, filter context, etc.)"
        - "Includes test_input for each case"
        - "Generated skill would have tests/edge_cases.yaml"
      anti_patterns:
        - "Skill without domain_edge_cases section"
        - "Generic edge cases not specific to DAX"
        - "Edge cases that apply to any domain"
    
    - id: follow_up_propagation
      scenario: "Generated skill must itself produce follow-up menus"
      naive_failure: "Generated skill has no follow-up menu instructions"
      expert_behavior: "Generated skill includes Output Requirements mandating contextual follow-ups"
      test_input: "Create a skill for writing product descriptions"
      must_check:
        - "Generated skill has Interactions section"
        - "Interactions section requires follow-up menus after every output"
        - "Examples in generated skill demonstrate follow-up menus"
        - "Follow-up requirement is contextual, not generic"
      anti_patterns:
        - "Generated skill with no mention of follow-up menus"
        - "Hardcoded generic follow-up options"
    
    - id: vague_input_zero_domain
      scenario: "User gives completely vague input with no domain"
      naive_failure: "Asks 'what kind of skill?' or sits paralyzed"
      expert_behavior: "Shows categorized starter options OR picks common domain with defaults"
      test_input: "create a skill"
      must_check:
        - "Does NOT ask generic clarifying questions"
        - "Either shows categorized domain options OR generates with sensible default"
        - "Follow-up menu allows narrowing domain"
        - "Output is immediately useful"
      anti_patterns:
        - "What kind of skill would you like?"
        - "Please provide more details about the domain"
        - "I need more information to proceed"
    
    - id: expert_input_efficiency
      scenario: "Expert user provides detailed specification"
      naive_failure: "Still asks questions, provides excessive scaffolding"
      expert_behavior: "Directly generates skill matching spec, minimal explanation"
      test_input: "Build a Claude skill for SQL query optimization. Focus on index analysis, query plans, and N+1 detection. Include 5 examples. Skip the basics."
      must_check:
        - "Generates directly without asking questions"
        - "Respects 'skip the basics' constraint"
        - "Includes exactly 5 examples as requested"
        - "Adapts to Claude platform fully (uses full token budget)"
        - "No over-explanation"
      anti_patterns:
        - "Before we begin, let me ask..."
        - "Here are the fundamentals of SQL..."
        - "Would you like me to explain query optimization?"
    
    - id: platform_adaptation
      scenario: "User requests skill for token-constrained platform"
      naive_failure: "Generates full Claude-sized skill regardless of platform"
      expert_behavior: "Compresses to fit platform, prioritizes core methodology"
      test_input: "Create a ChatGPT skill for meeting notes"
      must_check:
        - "Output under 8K characters"
        - "Core methodology preserved"
        - "Examples reduced appropriately (2-3 not 5)"
        - "Notes what was compressed or excluded"
      anti_patterns:
        - "Output exceeding 8K characters"
        - "Full Claude-style skill with all sections uncompressed"
    
    - id: contradictory_requirements
      scenario: "User gives impossible or contradictory constraints"
      naive_failure: "Tries to satisfy all, produces confused output"
      expert_behavior: "Identifies contradiction, asks for resolution, suggests alternatives"
      test_input: "Create a skill that's comprehensive AND under 1000 tokens"
      must_check:
        - "Identifies the contradiction explicitly"
        - "Offers resolution options via follow-up"
        - "Does not produce garbage trying to satisfy both"
        - "Suggests what's achievable at each constraint level"
      anti_patterns:
        - "Here's your comprehensive 1000-token skill:"
        - "Generating without acknowledging the conflict"
    
    - id: skill_from_conversation_extraction
      scenario: "User wants to extract skill from prior successful interaction"
      naive_failure: "Generates generic skill ignoring the conversation context"
      expert_behavior: "Extracts patterns, methodology, examples from the conversation"
      test_input: "That email prompt worked great. Turn it into a reusable skill."
      must_check:
        - "References specific elements from prior conversation"
        - "Extracts what made it successful"
        - "Generates skill embodying that specific approach"
        - "Preserves the 'voice' or style that worked"
      anti_patterns:
        - "Here's a generic email skill:"
        - "Ignoring conversation context entirely"
```

---
