# SkillForge Builder Examples

## Overview

These examples demonstrate how the SkillForge Builder handles different types of requests, from vague to specific, and how it maintains the minimum-effort principle throughout.

---

## Example 1: Minimal Input (Vague Request)

### Input
```
make a skill for meetings
```

### Output

I've created a **Meeting Facilitator** skill with smart defaults:

```yaml
---
name: meeting-facilitator
description: |
  Transforms chaotic meetings into productive outcomes. Handles
  agendas, notes, action items, and follow-ups automatically.
license: MIT
---
```

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "help with meeting", "meeting agenda", "meeting notes", "summarize meeting"

**Smart Defaults:**
- meeting_type: general_team
- output_format: structured_notes
- include_action_items: true
- time_box_warnings: true

---

# Meeting Facilitator

## I Help With

| Stage | What I Do |
|-------|-----------|
| **Before** | Generate agendas, prepare talking points |
| **During** | Structure discussions, track time |
| **After** | Summarize decisions, extract action items |

## Smart Behaviors

- **Vague request?** → I'll create a general meeting agenda template
- **Specific meeting?** → I'll tailor structure to meeting type
- **Raw notes pasted?** → I'll extract structure and action items

## Meeting Types I Handle

1. **Team Standup** → Status updates, blockers, next steps
2. **Planning Session** → Objectives, priorities, assignments
3. **Decision Meeting** → Options, criteria, recommendations
4. **Brainstorm** → Ideas, clustering, prioritization
5. **Review/Retro** → What worked, what didn't, improvements

## Example Output

### From: "Summarize this meeting"

**Meeting: Q4 Planning Session**
📅 Date: [Detected from context]
👥 Attendees: [Extracted if mentioned]

**Key Decisions:**
1. [Decision 1 with owner]
2. [Decision 2 with owner]

**Action Items:**
| Item | Owner | Due |
|------|-------|-----|
| [Action] | [Name] | [Date] |

**Follow-up Required:**
- [ ] [Open item needing resolution]

---

## Starter Prompts

### Quick Agenda
```
Create a meeting agenda for a 30-minute [meeting topic]
```

### From Notes
```
Summarize this meeting and extract action items:
[paste raw notes]
```

### Preparation
```
Help me prepare for a meeting about [topic] with [attendees]
```
```

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

What would you like to do next?

  [1] 🎯 Specialize for meeting type (standups, 1:1s, all-hands, etc.)
  [2] 📋 Add agenda templates for each type
  [3] ✅ Add action item tracking workflow
  [4] 🔗 Include calendar integration guidance
  [5] 📊 Add meeting effectiveness scoring
  [6] ✓ This general skill works for me

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reply with a number (1-6) or describe what you'd like to change.
═══════════════════════════════════════════════════════════════════

---

## Example 2: Specific Request (Expert User)

### Input
```
Create a skill for financial modeling that uses DCF methodology, includes 
sensitivity analysis tables, handles both LBO and M&A scenarios, and outputs 
in a format compatible with Excel import. Target audience is PE associates.
```

### Output

I've created a **Private Equity Financial Modeling** skill matching your specifications:

```yaml
---
name: pe-financial-modeling
description: |
  Investment-grade financial modeling for PE professionals.
  Supports DCF, LBO, M&A, and comps with sensitivity analysis.
  Excel-compatible output format throughout.
license: MIT
---
```

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "build a model for", "DCF analysis", "LBO model", "M&A valuation", "sensitivity analysis"

**Smart Defaults:**
- methodology: dcf_with_multiples
- output_format: excel_compatible_tables
- include_sensitivity: true
- assumption_documentation: full

**Quick Triggers:**
- `/dcf` → Generate DCF framework with standard assumptions
- `/lbo` → Generate LBO model structure
- `/sens` → Generate sensitivity table template

---

# Private Equity Financial Modeling Skill

## Expertise Level: Advanced

This skill assumes familiarity with:
- Discounted Cash Flow methodology
- Leveraged Buyout mechanics
- M&A transaction structures
- Excel modeling conventions

## Methodologies Supported

### 1. DCF Analysis

**Process:**
1. Revenue build-up (bottoms-up or top-down)
2. Operating model to EBITDA
3. Working capital adjustments
4. CapEx and D&A schedule
5. Free cash flow projection
6. Terminal value (Gordon Growth or Exit Multiple)
7. WACC calculation
8. Sensitivity analysis

**Output Format (Excel-Compatible):**
```
| Year | Revenue | Growth | EBITDA | Margin | FCF | PV Factor | PV of FCF |
|------|---------|--------|--------|--------|-----|-----------|-----------|
| 2024 | [calc]  | [%]    | [calc] | [%]    |[calc]| [calc]   | [calc]    |
```

### 2. LBO Model

**Structure:**
```
┌─────────────────────────────────────────────────────────────┐
│ SOURCES & USES                                               │
├─────────────────────────────────────────────────────────────┤
│ Sources              │ Uses                                 │
│ Senior Debt    $XXM  │ Purchase Price      $XXM             │
│ Sub Debt       $XXM  │ Refinance Existing  $XXM             │
│ Equity         $XXM  │ Transaction Costs   $XXM             │
│ Total          $XXM  │ Total               $XXM             │
└─────────────────────────────────────────────────────────────┘
```

**Key Metrics Calculated:**
- Entry/Exit multiples
- IRR (levered and unlevered)
- MoM (Money-on-Money)
- Debt paydown schedule
- Interest coverage ratios

### 3. Sensitivity Tables

**Standard 2-Way Table Format:**
```
                    Exit Multiple
IRR         5.0x    5.5x    6.0x    6.5x    7.0x
─────────────────────────────────────────────────
Revenue
Growth
  3.0%     18.2%   20.1%   21.8%   23.4%   24.9%
  4.0%     19.5%   21.4%   23.1%   24.7%   26.2%
  5.0%     20.8%   22.7%   24.4%   26.0%   27.5%
```

## Guardrails

**Quality Checks Applied:**
- [ ] Assumptions clearly documented with sources
- [ ] Balance sheet balances (assets = L + E)
- [ ] Cash flow ties to balance sheet
- [ ] Circular references flagged
- [ ] Sensitivity ranges realistic for sector

**What This Skill Does NOT Do:**
- ❌ Provide investment recommendations
- ❌ Access live market data
- ❌ Replace professional judgment on deal terms
- ❌ Generate audit-ready financials

## Starter Prompts

### Quick DCF
```
Build a DCF model for a SaaS company with:
- Current ARR: $50M, growing 30% YoY declining 5pp annually
- Target 80% gross margin, 20% EBITDA margin at scale
- 5-year projection with terminal value
```

### LBO Analysis
```
Structure an LBO for a $500M EV target:
- Entry multiple: 10x EBITDA
- Max leverage: 5x senior, 1x sub
- 5-year hold period
- Operating improvements: [specify]
```

### M&A Accretion/Dilution
```
Analyze acquisition of Target by Acquirer:
- Target EV: $XXM at XX.Xx EBITDA
- Deal structure: XX% cash, XX% stock
- Expected synergies: $XXM run-rate by Year 2
```
```

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 📊 Add industry-specific adjustments (tech, healthcare, industrial)
[2] 🧮 Include WACC calculator with beta lookups
[3] 📈 Add comps table generator
[4] 🔄 Include scenario analysis (base/upside/downside)
[5] 📝 Generate memo template for IC presentation
[6] ✓ This covers what I need

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Example 3: Skill from Successful Prompt

### Input
```
Turn this into a skill:

"You are an expert at explaining complex technical concepts to non-technical 
stakeholders. When I give you a technical topic, create an explanation that:
1. Starts with a simple analogy from everyday life
2. Builds up complexity gradually in 3 levels
3. Includes a visual diagram description
4. Ends with the 'so what' - why this matters to them
5. Avoids jargon, or defines it when unavoidable"
```

### Output

I've extracted a reusable skill from your prompt:

**Analysis of Your Successful Pattern:**
- **Core Technique**: Progressive complexity revelation
- **Key Differentiator**: Analogy-first approach
- **Success Factor**: Always connecting to "why it matters"

```yaml
---
name: technical-translator
description: |
  Transforms complex technical concepts into accessible explanations
  for non-technical audiences. Uses analogy-first methodology with
  progressive complexity building.
license: MIT
---
```

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "explain [technical topic] to", "help me explain", "make this understandable"
- "non-technical explanation", "ELI5"

**Smart Defaults:**
- complexity_levels: 3
- include_analogy: true
- include_diagram: true
- include_so_what: true
- jargon_policy: define_or_avoid

**Quick Triggers:**
- `/simple` → Level 1 only with analogy
- `/full` → All 3 levels with diagram
- `/exec` → Executive summary (so-what first)

---

# Technical Translator

## Core Methodology: The Pyramid of Understanding

```
                    ┌───────────────┐
                    │   LEVEL 3     │  ← Technical depth
                    │  How it works │     (for the curious)
                    │   precisely   │
                    ├───────────────┤
                    │   LEVEL 2     │  ← Functional understanding
                    │  What it does │     (working knowledge)
                    │   and why     │
                    ├───────────────┤
                    │   LEVEL 1     │  ← Core concept
                    │   Everyday    │     (everyone gets this)
                    │   Analogy     │
                    └───────────────┘
                           ▲
                    ALWAYS START HERE
```

## Output Structure

For any technical topic, I produce:

### 1. The Analogy Hook
"[Topic] is like [familiar everyday thing]..."

Start with something the audience already understands completely.
The analogy should capture the *essence* of the concept, not every detail.

### 2. Level 1: The Basics (Everyone)
What it is in one sentence. No jargon. If your grandmother wouldn't 
understand it, rewrite it.

### 3. Level 2: The Mechanics (Interested)
How it works in practice. Connect to their world: "This means for 
you/your team/your business..."

### 4. Level 3: The Details (Curious)
Technical specifics for those who want depth. Include caveats and 
nuances here, not earlier.

### 5. Visual Description
"Imagine a diagram showing..." - Describe what a whiteboard sketch 
would look like. Enable the reader to draw it themselves.

### 6. The "So What"
Why should they care? Connect to:
- Their goals
- Their problems
- Their decisions

## Example Application

**Topic**: "Explain Kubernetes to a marketing executive"

**Output**:

**Analogy**: Kubernetes is like a really smart air traffic controller 
for software applications. Just as an air traffic controller manages 
which planes land where, when, and ensures no collisions—Kubernetes 
manages which applications run where, when, and ensures they don't 
interfere with each other.

**Level 1 - The Basics**:
Kubernetes automatically keeps our apps running smoothly, even when 
things go wrong. It's the system that makes sure our website stays up 
when traffic spikes.

**Level 2 - The Mechanics**:
When our Black Friday sale drives 10x normal traffic, Kubernetes 
automatically spins up more copies of our website to handle the load, 
then scales back down when traffic normalizes—saving us money. It does 
this without anyone having to wake up at 3am.

**Level 3 - The Details**:
Kubernetes works by packaging applications in "containers" (standardized 
boxes that run the same everywhere). It monitors these containers 
continuously and replaces any that fail. It also handles load balancing, 
network routing, and can even update applications with zero downtime.

**Visual**:
```
[Diagram: Multiple server boxes connected to one "Kubernetes" brain 
that distributes incoming user requests across them, with failed 
servers being automatically replaced]
```

**The So What**:
For Marketing: This means you can launch campaigns without worrying 
about the website crashing. The "website went down" excuse is no longer 
valid—and neither are the emergency IT costs that used to come with 
traffic spikes.

## Guardrails

**Quality Checks:**
- [ ] Analogy is actually simpler than the concept
- [ ] Each level adds value (not just longer sentences)
- [ ] "So what" connects to audience's real concerns
- [ ] Jargon either avoided or defined on first use

**What This Skill Does NOT Do:**
- ❌ Make things more complex than necessary
- ❌ Use jargon to sound smart
- ❌ Assume audience knows prerequisites
- ❌ Skip the "why this matters" connection

## Starter Prompts

### Quick Explanation
```
Explain [technical concept] to a [role/audience]
```

### With Context
```
I need to explain [concept] to [audience]. They care about 
[their priorities]. Make it relevant to [their context].
```

### Document Translation
```
Translate this technical document for a non-technical audience:
[paste document]
```
```

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 📚 Add domain-specific analogy library (tech, finance, science)
[2] 👥 Create audience presets (executives, clients, new hires)
[3] ✏️ Make more concise for Slack/email explanations
[4] 🎯 Add "common misconceptions" section
[5] 📊 Include complexity scoring (is explanation simple enough?)
[6] ✓ This captures my approach well

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Example 4: Follow-Up Refinement

### Initial Request
```
Create a skill for customer support
```

### Initial Output
[Generic customer support skill with defaults]

### Follow-Up Selection
```
User selects: [1] 🎯 Narrow focus
```

### Refinement Output

What type of customer support? Select one or describe:

[A] 📧 Email/Ticket Support
    → Async, detailed responses, queue management
    
[B] 💬 Live Chat Support  
    → Real-time, concise, quick resolution
    
[C] 📞 Phone/Voice Support
    → Conversational, empathy-focused, scripts
    
[D] 🛠️ Technical Support
    → Troubleshooting, documentation, escalation
    
[E] 🛒 E-commerce Support
    → Orders, returns, shipping, payments

Or describe your specific support context: _____________

### User Response
```
B - we do live chat for a SaaS product
```

### Refined Output

**Live Chat Support for SaaS** - Updated skill:

```yaml
---
name: saas-live-chat-support
description: |
  Real-time chat support optimized for SaaS products.
  Balances speed with technical accuracy. Handles common
  SaaS issues: login, billing, feature questions, bugs.
license: MIT
---
```

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "chat support", "help customer with", "respond to chat"

**Smart Defaults:**
- response_length: concise (under 3 sentences per message)
- tone: friendly_professional
- escalation_threshold: 3_exchanges
- canned_responses: enabled

**Quick Triggers:**
- `/login` → Password reset flow
- `/billing` → Billing issue template
- `/bug` → Bug report collection flow

---

# SaaS Live Chat Support

## Chat Response Framework

**Speed Priority**: First response within 30 seconds

**Message Structure**:
```
[Acknowledgment] + [Action/Answer] + [Next step or question]
```

**Example**:
> "Got it! [Acknowledgment] Your subscription shows as active on our end. 
> [Answer] Could you try logging out and back in? [Next step] I'll watch 
> to see if that resolves it."

## Common Scenarios

### Login Issues (40% of chats)
1. Verify email in system
2. Check account status (active, trial, churned)
3. Password reset if needed
4. Browser/cache troubleshooting
5. Escalate if technical issue

### Billing Questions (25%)
1. Pull up subscription details
2. Explain current plan/charges
3. Process upgrades/downgrades
4. Handle refund requests (within policy)
5. Escalate disputes

### Feature Questions (20%)
1. Identify what they're trying to accomplish
2. Check if feature exists
3. Provide how-to or documentation link
4. Log feature request if new
5. Offer workaround if feature doesn't exist

### Bug Reports (15%)
1. Reproduce or confirm issue
2. Collect: browser, OS, steps taken
3. Check known issues list
4. Create ticket with details
5. Set expectation for resolution

## Tone Guidelines for Chat

| Situation | Tone | Example |
|-----------|------|---------|
| Simple question | Friendly, quick | "Quick answer: [X]. Let me know if you need anything else! 👍" |
| Frustrated user | Empathetic, solution-focused | "I completely understand how frustrating this is. Let me fix this for you right now." |
| Complex issue | Professional, clear | "This is a bit complex so I want to make sure we get it right. Here's what I'm seeing..." |
| Their mistake | Graceful, no blame | "Easy fix! Happens all the time. Just [action] and you'll be set." |

## Guardrails

**Never say:**
- ❌ "That's not my department"
- ❌ "I don't know" (say "Let me find out")
- ❌ "You should have..." (no blaming)
- ❌ Technical jargon without explanation

**Always include:**
- ✅ Clear next step
- ✅ Ownership of the issue
- ✅ Timeline if escalating
```

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 📝 Add canned response library
[2] 🔄 Include escalation decision tree
[3] 📊 Add customer satisfaction scoring
[4] 🎓 Include training scenarios for new agents
[5] 🔗 Add integration with ticketing system
[6] ✓ This is what I needed

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Example 5: Platform Adaptation

### Input
```
Adapt the meeting facilitator skill for ChatGPT (it's too long)
```

### Output

**ChatGPT-Optimized Version** (under 8K characters):

```markdown
# Meeting Facilitator (ChatGPT Version)

## What I Do
Transform meetings into outcomes. I help before (agendas), during (structure), and after (action items).

## How to Use Me

**Before meeting**: "Create an agenda for [topic], [duration], [attendees]"
**After meeting**: "Summarize: [paste notes]"
**Quick standup**: "Standup format for [team size]"

## Output Format

**Agenda** → Timed sections with owners
**Notes** → Decisions + Action items (who/what/when)
**Standup** → Status, blockers, next steps

## Example

Input: "Summarize this meeting: [notes about project planning]"

Output:
📋 **Decisions**: 
1. Launch date: March 15
2. Budget approved: $50K

✅ **Action Items**:
| Task | Owner | Due |
|------|-------|-----|
| Finalize specs | Sarah | Jan 20 |
| Vendor selection | Mike | Jan 25 |

❓ **Open Items**: Awaiting legal review

---
**Next?**
1. More detail  2. Different format  3. Add template  4. Done
```

**What Was Compressed:**
- Removed methodology explanations
- Condensed examples to one
- Simplified follow-up menu
- Removed redundant sections

**What Was Preserved:**
- Core functionality
- Smart defaults
- Example input/output
- Follow-up options

═══════════════════════════════════════════════════════════════════
                        FOLLOW-UP MENU
═══════════════════════════════════════════════════════════════════

[1] 📝 See the full Claude version
[2] 🔄 Adapt another skill for ChatGPT
[3] 📊 Compare Claude vs ChatGPT versions side-by-side
[4] ✓ This compression works

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
