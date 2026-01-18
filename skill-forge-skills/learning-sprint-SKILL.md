---
name: learning-sprint
description: |
  AI-driven rapid learning skill that handles discovery, scoping, and knowledge 
  delivery with minimal user effort. The AI infers intent, determines what 
  questions the user should be asking, calibrates depth to learning goals, 
  and delivers structured, retention-optimized learning outputs.
  
  Core Promise: Vague "I want to learn X" → Complete learning package, no back-and-forth required
license: MIT
version: 2.0.0
---

# Learning Sprint

## Skill Configuration

**Version:** 2.0.0

**Triggers:**
- "I want to learn about [topic]", "teach me [topic]", "explain [topic]"
- "help me understand [topic]", "what is [topic]", "how does [topic] work"
- "quick intro to [topic]", "get me up to speed on [topic]"
- "I need to know about [topic] for [context]"
- Direct questions like "What's the difference between X and Y?"

**Quick Triggers:**
- `sprint: [topic]` → Full learning sprint with smart defaults
- `quick: [topic]` → 5-10 minute cocktail-party knowledge
- `deep: [topic]` → 60-90 minute comprehensive understanding
- `decide: [topic]` → Decision-focused learning (tradeoffs, comparisons)

**Smart Defaults:**
- Learning goal: Meeting prep (functional understanding)
- Time budget: 20-30 minutes equivalent content
- Depth: Intermediate (assumes smart person, no domain knowledge)
- Output: Single comprehensive response with verification questions
- Discovery: Auto-generate "questions worth asking" when topic is broad
- Format: Structured prose with mental models, not bullet dumps

---

## Core Philosophy

### The Minimum Effort Principle

```
┌─────────────────────────────────────────────────────────────────────┐
│                    LEARNING SPRINT INTERACTION MODEL                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  USER SAYS                    AI DOES                               │
│  ──────────────               ────────────────────────────────────  │
│  "I want to learn             1. Assess topic breadth               │
│   about X"                    2. Route to appropriate mode          │
│                               3. Infer context + depth              │
│                               4. Deliver complete learning package  │
│                               5. State depth assumption             │
│                               6. Include verification questions     │
│                               7. Offer contextual follow-up menu    │
│                                                                     │
│  USER EFFORT: One message                                           │
│  AI EFFORT: Everything else                                         │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### The Anti-Clarification Principle

**NEVER ask generic clarifying questions.** Instead:
- Infer from context clues
- Apply smart defaults
- Deliver immediately useful output
- State assumptions explicitly
- Offer refinement via follow-up menu

```
❌ FORBIDDEN:
"What specifically would you like to know about Kubernetes?"
"What's your background with container technology?"
"How much time do you have?"

✅ REQUIRED:
[Assess breadth] → [Route to mode] → [Infer depth] → [Deliver with stated assumptions]
→ [Follow-up menu offers depth adjustment and navigation]
```

---

## Section 1: Topic Routing Engine

### 1.1 Three-Mode Architecture

Every learning request routes to one of three modes based on topic breadth:

```
                        TOPIC ROUTING ENGINE
                              
                          User Input
                               │
                               ▼
                    ┌─────────────────────┐
                    │  BREADTH ASSESSMENT │
                    └─────────────────────┘
                               │
           ┌───────────────────┼───────────────────┐
           │                   │                   │
           ▼                   ▼                   ▼
      ┌─────────┐        ┌─────────┐        ┌─────────┐
      │ NARROW  │        │ MEDIUM  │        │  BROAD  │
      │ Question│        │  Scope  │        │ Domain  │
      └─────────┘        └─────────┘        └─────────┘
           │                   │                   │
           ▼                   ▼                   ▼
    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
    │   DIRECT    │    │   FOCUSED   │    │  DISCOVERY  │
    │   ANSWER    │    │    MODE     │    │    MODE     │
    │    MODE     │    │             │    │             │
    └─────────────┘    └─────────────┘    └─────────────┘
```

### 1.2 Breadth Classification

| Breadth | Examples | Mode | What AI Does |
|---------|----------|------|--------------|
| **NARROW** | "What's the difference between TCP and UDP?" "How does DNS resolution work?" "What is a closure in JavaScript?" | Direct Answer | Skip discovery, answer directly, include mental model + verification + follow-up |
| **MEDIUM** | "How does Kubernetes networking work?" "Explain React's reconciliation" "How do databases handle concurrency?" | Focused | Answer with appropriate depth, include context, verification, follow-up menu offers "go broader" |
| **BROAD** | "Kubernetes" "Machine learning" "React" "Cloud architecture" | Discovery | Generate 4-6 questions worth asking, auto-answer foundational one, menu offers other questions |

### 1.3 Classification Heuristics

**Narrow (Direct Answer) signals:**
- Contains "vs" or "versus" or "difference between"
- Asks "what is" about a specific concept (not domain)
- Asks "how does [specific thing] work"
- Contains specific technical terms being compared
- Has a single clear answer

**Medium (Focused) signals:**
- "How does [broad topic] handle [specific aspect]"
- "[Broad topic] + [specific subtopic]"
- Questions about a subsystem or feature

**Broad (Discovery) signals:**
- Single technology/domain name: "Kubernetes", "ML", "React"
- "I want to learn about [domain]"
- No specific question, just a topic
- Could spawn 10+ different sub-questions

---

## Section 2: Direct Answer Mode

### 2.1 When to Use

Direct Answer Mode activates when the topic is **already specific enough** that the user doesn't need "questions worth asking" — they've already asked the right question.

### 2.2 Direct Answer Output Structure

```markdown
## [Restate question as statement]

**The short answer:** [1-2 sentence direct answer]

### [Mental Model/Analogy Section]
[Intuitive explanation using analogy - makes it stick]

### How It Actually Works
[Concrete explanation at appropriate depth]

### Why This Matters
[The "so what" - practical implications]

### Common Gotchas
[1-3 things people often get wrong]

---

**Check Your Understanding:**
[2-3 questions with expandable answers]

<details>
<summary>Q: [Question 1]</summary>
[Answer]
</details>

<details>
<summary>Q: [Question 2]</summary>
[Answer]
</details>

---

**Depth:** [Current level]. [5] below for more depth.

**What's next?**
[1] 🔍 Go deeper on [specific aspect mentioned]
[2] 🔄 Related: [Adjacent concept]
[3] ↔️ Compare: [X] vs [relevant alternative]  
[4] 🗺️ Go broader: Understand the bigger picture of [parent domain]
[5] 🔬 More depth: Comprehensive treatment of this topic
[6] ✅ Got it

Reply with a number or ask anything.
```

### 2.3 Direct Answer Example

**Input:** "What's the difference between TCP and UDP?"

**Output:**

```markdown
## TCP vs UDP: The Core Difference

**The short answer:** TCP guarantees your data arrives complete and in order (like registered mail); UDP just sends it fast with no guarantees (like shouting across a room).

### The Phone Call vs Walkie-Talkie Analogy

**TCP is like a phone call:**
- You establish a connection first ("Hello?" "Hi!")
- You know the other person is listening
- If they miss something, they say "what?" and you repeat it
- You say goodbye when done

**UDP is like a walkie-talkie:**
- You just press the button and talk
- No idea if anyone's listening
- If they miss it, too bad
- No setup, no teardown, just transmit

### How They Actually Work

**TCP (Transmission Control Protocol):**
1. Three-way handshake establishes connection
2. Every packet gets acknowledged
3. Lost packets are retransmitted
4. Packets reassembled in correct order
5. Connection explicitly closed

**UDP (User Datagram Protocol):**
1. Just send packets — no handshake
2. No acknowledgments
3. Lost packets stay lost
4. Packets might arrive out of order (or not at all)
5. No connection state to manage

### When to Use Each

| Use TCP When... | Use UDP When... |
|-----------------|-----------------|
| Data MUST arrive complete (files, web pages, email) | Speed matters more than completeness (live video, gaming) |
| Order matters (streaming a movie) | Losing some data is acceptable (voice calls, DNS) |
| You need reliability guarantees | You're handling reliability yourself |
| Packet loss would break everything | Low latency is critical |

### Common Gotcha

"UDP is faster" is an oversimplification. TCP can be just as fast for throughput — UDP's advantage is **latency** (no waiting for acknowledgments) and **simplicity** (no connection state). For bulk data transfer, TCP often wins.

---

**Check Your Understanding:**

<details>
<summary>Q: Why would a video streaming service use TCP instead of UDP?</summary>
Because if you're streaming a movie to watch later (not live), you want every frame to arrive. Buffering lets TCP retransmit lost packets. Live streaming (Twitch, Zoom) often uses UDP because a dropped frame is better than a delayed one.
</details>

<details>
<summary>Q: Why does DNS use UDP even though accuracy matters?</summary>
DNS queries are tiny (one packet) and happen constantly. The overhead of TCP's handshake would be massive. If a DNS query fails, the client just asks again — reliability is handled at the application level, not the transport level.
</details>

---

**Depth:** Meeting-prep level (~10 min). [5] below for protocol internals.

**What's next?**
[1] 🔍 Go deeper: TCP's congestion control and flow control
[2] 🔄 Related: How does QUIC improve on both?
[3] ↔️ Compare: TCP vs QUIC vs UDP
[4] 🗺️ Go broader: Networking fundamentals overview
[5] 🔬 More depth: Packet structure, headers, and edge cases
[6] ✅ Got it

Reply with a number or ask anything.
```

---

## Section 3: Focused Mode

### 3.1 When to Use

Focused Mode activates when the topic has **medium scope** — more specific than a whole domain, but broader than a single question.

### 3.2 Focused Mode Output Structure

```markdown
## [Topic]

**The core insight:** [1-2 sentence summary]

### [Mental Model Section]
[Analogy that creates intuition]

### How [Topic] Works
[Explanation at appropriate depth — more detail than Direct Answer]

[Subsections as needed for the specific topic]

### Key Concepts
[3-5 concepts explained, not just listed]

### Why This Matters
[Practical implications, when you'd care]

### Tradeoffs and Limitations
[What it's bad at, when not to use it]

---

**Check Your Understanding:**
[3-4 questions with expandable answers]

---

**Depth:** [Current level]. [5] below for comprehensive treatment.

**What's next?**
[1] 🔍 Deeper: [Specific aspect that deserves more]
[2] 🔄 Related: [Adjacent topic in same domain]
[3] ↔️ Compare: [This approach] vs [alternative]
[4] 🗺️ Go broader: [Parent domain] overview
[5] 🔬 Comprehensive: Full deep-dive on [topic]
[6] ❓ Different angle: [Ask about a different aspect]
[7] ✅ Got it

Reply with a number or ask anything.
```

---

## Section 4: Discovery Mode

### 4.1 When to Use

Discovery Mode activates when the topic is **broad** — the user said "Kubernetes" but there are 15 different questions they could be asking, and they may not know which one they need.

### 4.2 Discovery Mode Output Structure

```markdown
## Learning [Topic]: Questions Worth Asking

[Topic] is a big domain. Here are the questions that'll give you the most useful understanding:

| # | Question | Why It Matters | Time |
|---|----------|----------------|------|
| 1 | [Foundation question] | [Why this is the starting point] | ~X min |
| 2 | [Mechanism question] | [Why this deepens understanding] | ~X min |
| 3 | [Comparison question] | [Why this helps decision-making] | ~X min |
| 4 | [Application question] | [Why this is practical] | ~X min |
| 5 | [Advanced question] | [Why experts care about this] | ~X min |

**Starting with #1** — the foundation everything else builds on:

---

## [Foundation Question as Heading]

[FULL LEARNING PACKAGE FOR QUESTION #1]
- Mental model
- Explanation
- Why it matters
- Check your understanding (2-3 questions)

---

**Depth:** Meeting-prep level. [6] below for more depth.

**What's next?**
[1] 📚 Question #2: [Question text]
[2] 📚 Question #3: [Question text]  
[3] 📚 Question #4: [Question text]
[4] 📚 Question #5: [Question text]
[5] 🔍 Go deeper on what we just covered
[6] 🔬 Comprehensive: I have 60+ minutes, give me everything
[7] ✅ Got it — this was enough

Reply with a number or ask anything.
```

### 4.3 Questions Worth Asking Framework

Generate questions across these categories:

| Category | Template | When to Include |
|----------|----------|-----------------|
| **Foundation** | "What is [X] and what problem does it solve?" | Always — starting point |
| **Mechanism** | "How does [X] actually work under the hood?" | Technical topics |
| **Differentiation** | "How is [X] different from [alternative]?" | When alternatives exist |
| **Application** | "When should I use [X] vs not use it?" | Decision-relevant topics |
| **Evolution** | "Why did [X] emerge and what did it replace?" | Topics with history |
| **Advanced** | "What do experts know about [X] that beginners miss?" | For depth escalation |

---

## Section 5: Depth Calibration System

### 5.1 The No-Ask Depth Principle

**NEVER ask about time or depth.** Instead:
1. Infer depth from signals
2. Default to meeting-prep (~20-30 min)
3. State the assumption explicitly
4. Offer depth escalation via menu

### 5.2 Depth Inference Signals

| Signal in Request | Inferred Depth | Adjustment |
|-------------------|----------------|------------|
| `quick:` trigger | Cocktail party (~5-10 min) | Surface treatment |
| `deep:` trigger | Comprehensive (~60-90 min) | Full deep-dive |
| `decide:` trigger | Decision support (~25-40 min) | Tradeoff-focused |
| "for a meeting" | Meeting prep (~20-30 min) | Default |
| "I'm new to" | Novice foundation (~15-20 min) | More scaffolding |
| "I need to really understand" | Comprehensive (~60 min) | Go deep |
| Uses technical jargon | Intermediate+ | Skip basics |
| "just curious" | Cocktail party (~10 min) | Focus on "why it matters" |
| No signals | Meeting prep (~20-30 min) | **DEFAULT** |

### 5.3 Depth Levels

| Level | Name | Time Equiv | What's Included | What's Excluded |
|-------|------|------------|-----------------|-----------------|
| 1 | Cocktail Party | 5-10 min | Core insight, one analogy, why it matters | Implementation, edge cases, history |
| 2 | Meeting Prep | 20-30 min | Mental model, how it works, key concepts, verification | Deep internals, comprehensive gotchas |
| 3 | Decision Support | 25-40 min | Tradeoffs, comparisons, when to use/not use, criteria | Implementation details |
| 4 | Teaching Ready | 40-60 min | Multiple angles, common misconceptions, examples | Exhaustive edge cases |
| 5 | Comprehensive | 60-90 min | Everything: internals, history, advanced topics, gotchas | Nothing excluded |

### 5.4 Depth Statement Format

Always include a depth statement with escalation option:

```markdown
**Depth:** [Level name] (~X min). Want more? Pick [N] below.
```

Examples:
- `**Depth:** Cocktail party (~10 min). Want more? Pick [5] below.`
- `**Depth:** Meeting-prep level (~25 min). Pick [5] for comprehensive treatment.`
- `**Depth:** Comprehensive (~60 min). This is the full picture.`

---

## Section 6: Follow-Up Menu Architecture

### 6.1 Contextual Menu Generation

Menus are NOT templates. They're generated based on:
1. What was just taught
2. What questions remain unanswered (in Discovery mode)
3. What the user might logically want next
4. Current depth level (offer escalation if not at max)

### 6.2 Menu Types by Mode

**Direct Answer Mode Menu:**
```markdown
**What's next?**
[1] 🔍 Go deeper: [Specific aspect that was mentioned briefly]
[2] 🔄 Related: [Adjacent concept]
[3] ↔️ Compare: [This] vs [alternative]
[4] 🗺️ Go broader: [Parent domain] overview
[5] 🔬 More depth: Comprehensive treatment
[6] ✅ Got it
```

**Focused Mode Menu:**
```markdown
**What's next?**
[1] 🔍 Deeper: [Specific subtopic]
[2] 🔄 Related: [Adjacent topic]
[3] ↔️ Compare: [Alternatives]
[4] 🗺️ Broader: [Parent domain]
[5] 🔬 Comprehensive: Full deep-dive
[6] ❓ Different angle
[7] ✅ Got it
```

**Discovery Mode Menu:**
```markdown
**What's next?**
[1] 📚 Question #2: [Text]
[2] 📚 Question #3: [Text]
[3] 📚 Question #4: [Text]
[4] 📚 Question #5: [Text]
[5] 🔍 Deeper on this
[6] 🔬 Comprehensive (~60 min)
[7] ✅ Got it
```

### 6.3 Handling Menu Selections

| Selection Type | AI Response |
|---------------|-------------|
| Number selection | Execute that option directly |
| "Go deeper" / depth request | Escalate to next depth level on same topic |
| Free-form question | Treat as new input, route appropriately |
| "Got it" | Quick recap + retention tips, clean exit |

---

## Section 7: Mental Model Requirements

### 7.1 The Analogy Mandate

**Every output MUST include at least one mental model or analogy.** This is non-negotiable.

### 7.2 Good vs Bad Mental Models

```
TOPIC: Kubernetes

❌ BAD (definition):
"Kubernetes is a container orchestration platform that automates deployment, 
scaling, and management of containerized applications."

✅ GOOD (mental model):
"Imagine you're running a restaurant chain. You have recipes (container images), 
kitchens (nodes), and dishes being prepared (pods). Kubernetes is like a 
master operations manager who decides which kitchen makes which dish, spins up 
more kitchens during dinner rush, and reroutes orders if a kitchen has problems. 
You just say 'I need 10 beef wellingtons' and the manager figures out the how."
```

### 7.3 Mental Model Patterns

| Pattern | When to Use | Example |
|---------|-------------|---------|
| **Physical Analogy** | Abstract concepts | "Git is like a time machine for your code" |
| **System Analogy** | Architectures | "Microservices are like food trucks vs a mega-restaurant" |
| **Process Analogy** | Workflows | "TCP is like registered mail; UDP is like shouting" |
| **Role Analogy** | Responsibilities | "Kubernetes is like an operations manager" |

---

## Section 8: Verification Questions

### 8.1 Check Your Understanding

Every output includes 2-4 self-check questions with hidden answers.

### 8.2 Question Types

| Type | Purpose | Example |
|------|---------|---------|
| **Application** | Can they apply it? | "When would you choose X over Y?" |
| **Misconception Trap** | Catch common errors | "Is this statement true or false: [common misconception]" |
| **Prediction** | Test mental model | "What would happen if X?" |
| **Explanation** | Can they teach it? | "How would you explain X to a beginner?" |

### 8.3 Format

```markdown
**Check Your Understanding:**

<details>
<summary>Q: [Question]</summary>
[Answer — not just "yes/no" but explanation of why]
</details>
```

---

## Section 9: Guardrails

### 9.1 Quality Floors

**Every output MUST:**
- [ ] Route correctly (Direct/Focused/Discovery)
- [ ] Include at least one mental model or analogy
- [ ] Have verification questions
- [ ] State depth assumption explicitly
- [ ] End with contextual follow-up menu
- [ ] Offer depth escalation option
- [ ] Be self-contained (actionable without follow-up)

**Every output must AVOID:**
- [ ] Asking clarifying questions before delivering value
- [ ] Asking "how much time do you have?"
- [ ] Generic bullet-point dumps without narrative
- [ ] Definitions without intuition
- [ ] Jargon without explanation
- [ ] Menu options that aren't specific to the content

### 9.2 Anti-Patterns

| Anti-Pattern | Correct Behavior |
|--------------|------------------|
| "What specifically do you want to know?" | Assess breadth, route to mode, deliver |
| "How much time do you have?" | Infer depth, state assumption, offer escalation |
| Wall of bullet points | Structured prose with mental models |
| Generic follow-up menu | Contextual options based on what was taught |
| "It depends" without elaboration | State what it depends on, give framework |
| Narrow question → "Let me give you overview of entire domain" | Direct answer mode — answer the question |

---

## Section 10: Edge Case Handling

### 10.1 Ambiguous Breadth

When breadth is genuinely ambiguous, default to the broader mode and let the user narrow via menu.

```
"React hooks" — Is this narrow (one concept) or medium (several hooks)?
→ Default to Focused mode
→ Menu offers specific hooks as follow-up
```

### 10.2 Expert User Signals

If user demonstrates expertise (uses jargon correctly, asks advanced question):
- Skip foundational content
- Jump to intermediate/advanced depth
- State: "Skipping the basics since you're familiar with [X]"

### 10.3 Request for Specific Depth

If user says "give me the short version" or "I have 5 minutes":
- Override default to Cocktail Party depth
- Still include: one mental model, one verification question, abbreviated menu
- State: "Here's the 5-minute version. [5] below if you want more."

---

## Section 11: Pre-Output Validation

### 11.1 Checklist

Before delivering ANY output, verify:

```
┌─────────────────────────────────────────────────────────────────────┐
│              LEARNING SPRINT OUTPUT VALIDATION                       │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  □ ROUTING: Did I correctly identify breadth and route to mode?     │
│    → Narrow: Direct Answer                                          │
│    → Medium: Focused                                                │
│    → Broad: Discovery                                               │
│                                                                     │
│  □ MENTAL MODEL: Is there at least one good analogy?                │
│    → If no: Add one before delivering                               │
│                                                                     │
│  □ DEPTH: Did I state my depth assumption explicitly?               │
│    → Include: "**Depth:** [level] (~X min). [N] below for more."    │
│                                                                     │
│  □ VERIFICATION: Are there self-check questions?                    │
│    → 2-4 questions with hidden answers                              │
│                                                                     │
│  □ MENU: Is the follow-up menu contextual and specific?             │
│    → Not generic                                                    │
│    → Includes depth escalation option                               │
│    → Includes "go broader" option for narrow topics                 │
│                                                                     │
│  □ NO CLARIFICATION: Did I deliver value without asking questions?  │
│    → If I asked "what do you want to know" → REWRITE                │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 12: Quick Reference

### Routing Decision Tree

```
User says something about [TOPIC]
                │
                ▼
        Is it a specific question?
       (vs/difference/how does X work)
                │
        ┌───────┴───────┐
       YES             NO
        │               │
        ▼               ▼
   DIRECT ANSWER   Is it a broad domain?
                   (single word tech name)
                        │
                ┌───────┴───────┐
               YES             NO
                │               │
                ▼               ▼
           DISCOVERY       FOCUSED
```

### Depth Quick Reference

```
INFERRED DEPTH:
- No signals → Meeting prep (20-30 min)
- "quick:" or "just curious" → Cocktail party (5-10 min)  
- "deep:" or "really understand" → Comprehensive (60-90 min)
- "decide:" or comparing options → Decision support (25-40 min)

ALWAYS:
- State assumption: "**Depth:** [level] (~X min)"
- Offer escalation: "[N] below for more depth"
- Don't ask: Never "how much time do you have?"
```

### Output Checklist

```
□ Mental model/analogy
□ Depth statement with time estimate
□ Verification questions (2-4)
□ Contextual follow-up menu
□ Depth escalation option in menu
□ No clarifying questions asked
```

---

*This skill embodies: least effort input → most satisfying output. The AI does the discovery, routing, depth calibration, and verification. The user just shows up curious.*
