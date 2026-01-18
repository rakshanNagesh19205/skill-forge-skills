# SkillForge Builder

## Transform AI Potential into Expert Results

A meta-skill for creating AI cognitive skills that embody research-backed principles for minimum user effort and maximum output quality.

---

## Quick Start

### Use the Skill Builder Immediately

Copy this prompt into Claude:

```
Create a skill for [your domain]. Use smart defaults.
```

The skill builder will:
1. Generate a complete skill with intelligent defaults
2. Show you what it created
3. Offer a follow-up menu for refinement

### From Existing Success

```
Turn this into a skill:
[Paste your successful prompt or workflow]
```

---

## What's Included

```
skillforge-builder/
├── SKILL.md                              # The complete skill builder (60KB)
├── README.md                             # This file
├── examples/
│   └── examples.md                       # 5 input/output demonstrations
├── templates/
│   └── skill-template.md                 # Blank template with all sections
├── references/
│   └── design-principles.md              # Philosophy and research basis
└── tests/
    ├── edge_cases.yaml                   # 16 domain-specific test cases
    └── TEST_REPORT.md                    # Self-audit results
```

---

## Core Philosophy

### The Minimum Effort Principle

**Problem**: Users can't always articulate exactly what they need. Traditional approaches ask endless clarifying questions, frustrating users before providing any value.

**Solution**: Generate immediately with smart defaults, then refine.

```
❌ WRONG: "What tone? What audience? What length? What format?"
✅ RIGHT: [Generates professional email with defaults]
          "Here's what I created. Want to adjust?"
```

### The Four-Concerns Framework

Every skill addresses four fundamental concerns:

| Concern | Question | Contents |
|---------|----------|----------|
| **Context** | What do I need to know? | Domain knowledge, user state, constraints |
| **Patterns** | How do I operate? | Process, templates, examples, decisions |
| **Guardrails** | What do I avoid? | Quality floors, boundaries, error handling |
| **Interactions** | How do I engage? | Follow-up menus, starter prompts, quick triggers |

### Mandatory Components

Every generated skill includes:

1. **Smart Defaults** - Sensible choices for unspecified parameters
2. **Starter Prompts** - Copy-paste examples to get started
3. **Quick Triggers** - Fast paths for power users
4. **Follow-Up Menus** - Always show what's possible next
5. **Quality Floors** - Minimum acceptable output standards
6. **Explicit Boundaries** - What the skill does NOT do

---

## How It Works

### For Vague Requests

```
User: "make a skill for meetings"

Skill Builder: [Generates complete Meeting Facilitator skill]

"I've created a Meeting Facilitator skill with these defaults:
• Type: General team meetings
• Output: Structured notes with action items
• Features: Agenda generation, summary extraction

═══════════════════════════════════════════════════════════════
                      FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════
[1] 🎯 Specialize (standups, 1:1s, all-hands)
[2] 📋 Add agenda templates
[3] ✅ Include action item tracking
[4] ✓ This general approach works
═══════════════════════════════════════════════════════════════"
```

### For Specific Requests

```
User: "Create a skill for financial modeling using DCF methodology 
with sensitivity analysis for PE associates"

Skill Builder: [Generates comprehensive PE Financial Modeling skill
               matching all specifications - no clarifying questions]
```

### For Extracting Skills from Success

```
User: "Turn this into a skill: [pastes successful prompt]"

Skill Builder: [Analyzes the prompt, extracts the reusable pattern,
               generates a skill that captures the methodology]
```

---

## Research Foundation

This framework synthesizes insights from:

**Cognitive Science**
- Cognitive Load Theory (minimize decisions)
- Dual-Process Theory (System 1/System 2 routing)
- Expertise research (adapt to user level)

**UX Research**
- Progressive Disclosure (hide complexity)
- Choice Architecture (smart defaults)
- Recognition Over Recall (show options)

**AI Interaction Studies**
- The 3% productivity gap (why AI tools underdeliver)
- Vague request handling patterns
- Conversation repair and recovery

See `/references/design-principles.md` for complete citations.

---

## Creating Your Own Skills

### Using the Template

1. Copy `/templates/skill-template.md`
2. Fill in all [REQUIRED] sections
3. Complete the quality checklist
4. Test with vague inputs to ensure it handles them

### Using the Skill Builder

Simply ask:
```
Create a skill for [your domain] that [specific requirements]
```

Then iterate using the follow-up menu until satisfied.

---

## Platform Considerations

| Platform | Max Size | Approach |
|----------|----------|----------|
| Claude | ~200KB | Comprehensive "mega-skills" |
| ChatGPT | ~8K chars | Focused, essential-only |
| Gemini | ~8K chars | Focused, essential-only |

The skill builder can generate platform-specific versions:
```
Adapt [skill name] for ChatGPT
```

---

## Quality Standards

Every skill must pass this checklist:

### Structure
- [ ] YAML frontmatter complete
- [ ] Four concerns addressed
- [ ] Follow-up menu included
- [ ] Starter prompts provided (3+)
- [ ] Quick triggers defined

### Content
- [ ] Smart defaults documented
- [ ] Examples realistic (3+ minimum)
- [ ] Vague request handling shown
- [ ] Boundaries explicit
- [ ] No placeholders remaining

### Function
- [ ] Works with minimal input
- [ ] Output is actionable
- [ ] Edge cases handled
- [ ] Token budget defined

---

## Automated Testing

Every skill generated by this builder includes domain edge cases that feed into the automated testing pipeline.

### Edge Cases Are Mandatory

Phase 5 of the skill building process is **Domain Edge Case Definition (REQUIRED)**. Every generated skill includes:

- `domain_edge_cases` section in SKILL.md
- `tests/edge_cases.yaml` file for pipeline consumption
- Minimum cases based on domain complexity (3-6 for simple, 6-12 for technical)

### Testing Pipeline

A separate n8n workflow package (`skillforge-testing-pipeline`) validates skills:

1. **Parse skills** and extract edge cases
2. **Generate test cases** (universal + domain-specific)
3. **Execute tests** against Claude, GPT, Gemini
4. **Evaluate responses** using LLM-as-judge
5. **Generate quality reports** with pass/fail verdicts

### Publish Criteria

| Criterion | Threshold |
|-----------|-----------|
| Overall Score | ≥ 4.0/5.0 |
| Critical Test Pass Rate | 100% |
| Total Pass Rate | ≥ 85% |

---

## Contributing

To improve this skill builder:

1. Use it to create skills
2. Note where it falls short
3. Suggest improvements via follow-up menu option
4. Test changes against the quality checklist

---

## License

MIT License - Use freely, improve openly.
