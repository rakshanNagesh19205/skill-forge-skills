# Skill Template

Use this template as a starting point for creating new skills. All sections marked [REQUIRED] must be completed. Sections marked [RECOMMENDED] should be included for production-quality skills.

## YAML Frontmatter [REQUIRED]

Copy this frontmatter to the top of your SKILL.md file. 

**Allowed keys only:** `name`, `description`, `license`, `allowed-tools`, `compatibility`, `metadata`

```yaml
---
name: your-skill-name
description: |
  One paragraph describing what this skill does.
  Include: primary use case, key benefit, when to use it.
license: MIT
---
```

**Note:** Triggers, defaults, quick_triggers, and version go in the Skill Configuration section (markdown), NOT in the YAML frontmatter.

## Skill Configuration Section [REQUIRED]

Add this section after your frontmatter to define triggers, defaults, and other configuration:

```markdown
## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "primary trigger phrase"
- "secondary trigger phrase"
- "variation 1"

**Quick Triggers:**
- `/quick` → Description of quick action
- `/template` → Show structure only
- `/example` → Show example output

**Smart Defaults:**
- parameter_1: default_value
- parameter_2: default_value
- parameter_3: default_value

**Tags:** primary-category, secondary-category, use-case
```

---

# Skill Name

## Overview [REQUIRED]

Brief description of what this skill does and when to use it.

---

## Section 1: Context [REQUIRED]

### What This Skill Needs to Know

**Domain Knowledge:**
- [Key concept 1 the skill must understand]
- [Key concept 2]
- [Key concept 3]

**User State Detection:**
| Signal | Interpretation | Response Adaptation |
|--------|---------------|---------------------|
| [Observable signal] | [What it means] | [How to adapt] |

**Constraints:**
- Default constraint: [value]
- Adjustable via: [how user can change it]

---

## Section 2: Patterns [REQUIRED]

### Core Methodology

**Process:**
1. **Step 1**: [Description]
2. **Step 2**: [Description]
3. **Step 3**: [Description]
4. **Step 4**: [Description]

### Output Template

```
[Template structure here]

Example:
─────────────────────────────────────────
[Filled example of the template]
─────────────────────────────────────────
```

### Decision Framework

When [condition], do [action]:
- If [scenario A]: [approach A]
- If [scenario B]: [approach B]
- If uncertain: [default approach]

---

## Section 3: Guardrails [REQUIRED]

### Quality Floors

Every output must:
- [ ] [Minimum requirement 1]
- [ ] [Minimum requirement 2]
- [ ] [Minimum requirement 3]

### Error Prevention

**Never:**
- ❌ [Thing to avoid 1]
- ❌ [Thing to avoid 2]

**Always:**
- ✅ [Thing to ensure 1]
- ✅ [Thing to ensure 2]

### What This Skill Does NOT Do

This skill is NOT designed for:
- ❌ [Explicit exclusion 1]
- ❌ [Explicit exclusion 2]
- ❌ [Adjacent but out-of-scope task]

If you need these, consider: [alternative approaches]

---

## Section 4: Interactions [REQUIRED]

### Starter Prompts

Copy and customize these to get started:

#### Quick Start
```
[Minimal prompt that works with all defaults]
```

#### Detailed Request
```
[Comprehensive prompt showing available parameters]
Example: "[action] with [parameter_1: value], [parameter_2: value]"
```

#### Specific Scenario
```
[Real-world example for a common use case]
```

### Quick Triggers

| Trigger | What It Does |
|---------|--------------|
| `/quick` | [Generates output with all defaults] |
| `/template` | [Shows structure without content] |
| `/example` | [Shows example input and output] |

### Follow-Up Menu Template

Include this at the end of every output:

```
═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

What would you like to do next?

  [1] 🔄 [Refinement option]
      → [Brief description]
  
  [2] ➕ [Expansion option]  
      → [Brief description]
  
  [3] 🎯 [Specification option]
      → [Brief description]
  
  [4] 🛡️ [Quality option]
      → [Brief description]
  
  [5] ✅ This looks good
      → Finalize and complete

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number (1-5) or describe what you'd like to change.
═══════════════════════════════════════════════════════════════════
```

---

## Section 5: Examples [REQUIRED]

Include 3-5 examples covering:
1. Simple/typical case
2. Complex case
3. Edge case or vague input handling

### Example 1: [Simple Case]

**Input:**
```
[User input]
```

**Output:**
```
[Skill output]

═══ FOLLOW-UP MENU ═══
[1] ...
[2] ...
[3] This works
```

### Example 2: [Complex Case]

**Input:**
```
[User input with multiple requirements]
```

**Output:**
```
[Comprehensive skill output]

═══ FOLLOW-UP MENU ═══
[1] ...
[2] ...
[3] This works
```

### Example 3: [Vague Input Handling]

**Input:**
```
[Vague or minimal user input]
```

**Output:**
```
[Skill generates useful default output]

I've created [description] with these defaults:
• [Default 1]
• [Default 2]

═══ FOLLOW-UP MENU ═══
[1] Narrow focus
[2] Change defaults
[3] Add more
[4] This works
```

---

## Section 6: Domain Edge Cases [REQUIRED]

Domain-specific scenarios where generic AI fails but this skill must succeed.
These become automated test cases in the testing pipeline.

```yaml
domain_edge_cases:
  domain: "[Your skill domain]"
  description: |
    [Brief explanation of why these cases matter for this domain]
  
  cases:
    - id: edge_case_1
      scenario: "[Human-readable description of tricky situation]"
      naive_failure: "[What generic AI typically does wrong]"
      expert_behavior: "[What this skill MUST do instead]"
      test_input: "[Actual prompt that triggers this scenario]"
      must_check:
        - "[First verification criterion]"
        - "[Second verification criterion]"
        - "[Third verification criterion]"
      anti_patterns:
        - "[Pattern indicating failure]"
        - "[Another failure indicator]"
    
    - id: edge_case_2
      scenario: "[Description]"
      naive_failure: "[Wrong behavior]"
      expert_behavior: "[Correct behavior]"
      test_input: "[Test prompt]"
      must_check:
        - "[Criterion]"
      anti_patterns:
        - "[Anti-pattern]"
    
    - id: edge_case_3
      scenario: "[Description]"
      naive_failure: "[Wrong behavior]"
      expert_behavior: "[Correct behavior]"
      test_input: "[Test prompt]"
      must_check:
        - "[Criterion]"
      anti_patterns:
        - "[Anti-pattern]"
    
    # Add more cases as needed (minimum 3, scale with domain complexity)
```

### Edge Case Guidelines

| Domain Complexity | Minimum Cases |
|-------------------|---------------|
| Simple/Static | 2-3 |
| Standard | 4-6 |
| Technical | 6-10 |
| Expert/Niche | 8-12+ |

**Questions to Surface Edge Cases:**
1. What mistakes do novices make that experts never make?
2. What scenarios LOOK simple but have hidden complexity?
3. What anti-patterns should this skill actively prevent?
4. What would make a domain expert say "finally, AI that gets it"?

---

## Appendix: Platform Variations [RECOMMENDED]

### Claude Version (Full)
Use the complete skill as written above.

### ChatGPT/Gemini Version (Compressed)
[Include a compressed version under 8K characters if needed]

---

## Quality Checklist [REQUIRED - Complete before publishing]

### Structure
- [ ] YAML frontmatter complete and valid
- [ ] All four concerns addressed (Context, Patterns, Guardrails, Interactions)
- [ ] Follow-up menu included
- [ ] Starter prompts provided (3+)
- [ ] Quick triggers defined

### Content
- [ ] Smart defaults documented
- [ ] Examples are realistic (3+ minimum)
- [ ] Vague request handling demonstrated
- [ ] Boundaries explicitly stated
- [ ] No placeholder text remaining

### Domain Edge Cases (REQUIRED)
- [ ] Minimum edge cases defined (based on domain complexity)
- [ ] Each case has: scenario, naive_failure, expert_behavior
- [ ] Each case has: test_input, must_check criteria
- [ ] Anti-patterns documented for each case
- [ ] Cases extracted to tests/edge_cases.yaml

### Quality
- [ ] Works with minimal input
- [ ] Produces actionable output
- [ ] Handles edge cases gracefully
- [ ] Token budget defined
- [ ] Passes testing pipeline (4.0+ score)
