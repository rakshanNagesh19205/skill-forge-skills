---
name: marketing-copy
description: |
  Conversion copywriting skill for solo developers. Covers headlines, CTAs,
  landing pages, email copy, and benefit-driven persuasion. Designed for
  devs who build great products but struggle to explain why anyone should care.
license: MIT
---

# Marketing Copy — Conversion Copywriting for Solo Developers

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "write copy", "landing page copy", "headline"
- "CTA", "call to action", "conversion copy"
- "make people want to sign up", "explain my product"
- "benefit-driven", "value proposition"

**Quick Triggers:**
- `headline for [product]` → Generate 10 headline variations
- `cta for [action]` → Generate CTA button copy options
- `landing page for [product]` → Full landing page copy structure
- `rewrite [copy]` → Improve existing copy

**Smart Defaults:**
- Voice: clear, direct, benefit-focused
- Length: concise (devs write too much, not too little)
- Focus: what user gets, not what product does
- Tone: confident without hype

---

## Core Philosophy: The Ogilvy Foundation

This skill is built on David Ogilvy's advertising principles — proven frameworks from the "Father of Advertising" that work whether you have a $10M budget or $0.

```
┌─────────────────────────────────────────────────────────────────────┐
│                    OGILVY'S CORE PRINCIPLES                         │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  1. "THE CONSUMER ISN'T A MORON. SHE'S YOUR WIFE."                 │
│     └── Respect intelligence. No hype. No manipulation.            │
│     └── Write like you're explaining to a smart friend.            │
│                                                                     │
│  2. RESEARCH BEFORE YOU WRITE                                       │
│     └── "Advertising people who ignore research are as dangerous   │
│          as generals who ignore decodes of enemy signals."         │
│     └── Know your customer better than they know themselves.       │
│                                                                     │
│  3. THE HEADLINE IS 80% OF YOUR AD                                 │
│     └── "On average, five times as many people read the headline   │
│          as read the body copy."                                   │
│     └── If your headline doesn't sell, you've wasted 80%.          │
│                                                                     │
│  4. SELL, DON'T ENTERTAIN                                          │
│     └── "When I write an advertisement, I don't want you to tell   │
│          me that you find it 'creative.' I want you to find it     │
│          so interesting that you buy the product."                 │
│     └── Cleverness that doesn't convert is vanity.                 │
│                                                                     │
│  5. SPECIFICS BEAT GENERALITIES                                    │
│     └── "The more informative your advertising, the more           │
│          persuasive it will be."                                   │
│     └── "37% faster" beats "blazing fast" every time.              │
│                                                                     │
│  6. THE BIG IDEA                                                   │
│     └── "You will never win fame and fortune unless you invent     │
│          big ideas. It takes a big idea to attract the attention   │
│          of consumers and get them to buy your product."           │
│     └── What's the ONE compelling truth about your product?        │
│                                                                     │
│  7. BRAND IMAGE IS CUMULATIVE                                      │
│     └── "Every advertisement should be thought of as a             │
│          contribution to the brand image."                         │
│     └── Consistency compounds. Every touchpoint matters.           │
│                                                                     │
│  8. LONG COPY SELLS (WHEN RELEVANT)                                │
│     └── "All my experience says that for a great many products,    │
│          long copy sells more than short."                         │
│     └── Don't be brief for brevity's sake. Be complete.            │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Ogilvy's Headline Rules (Embedded in All Output)

Every headline this skill produces follows these principles:

```
OGILVY HEADLINE CHECKLIST:
├── □ Contains the benefit (what's in it for the reader?)
├── □ Targets the right audience (self-selecting)
├── □ Specific over vague (numbers, outcomes)
├── □ News value when possible (new, introducing, now)
├── □ Avoids cleverness that obscures meaning
├── □ Works in isolation (most won't read body copy)
└── □ No negativity or wordplay that requires thought

WORDS OGILVY FOUND MOST POWERFUL:
├── Free, New, How to, Suddenly, Now, Announcing
├── Introducing, It's here, Just arrived, Improvement
├── Amazing, Sensational, Remarkable, Revolutionary
├── Startling, Miracle, Magic, Offer, Quick, Easy
├── Wanted, Challenge, Compare, Bargain, Hurry
└── Use sparingly and honestly — never as hype
```

### The Ogilvy Brief (Use Before Writing)

Before writing any copy, answer these questions (Ogilvy's research framework):

```
1. WHAT IS THE PRODUCT?
   └── Describe it as if to someone who's never heard of it.

2. WHO IS THE CUSTOMER?
   └── Demographics, psychographics, what keeps them up at night?

3. WHAT DO THEY CURRENTLY BELIEVE?
   └── About the problem, about solutions, about products like yours?

4. WHAT DO YOU WANT THEM TO BELIEVE?
   └── After reading your copy, what should change in their mind?

5. WHAT IS THE SINGLE MOST PERSUASIVE THING YOU CAN SAY?
   └── The Big Idea. One thing. Not five.

6. WHY SHOULD THEY BELIEVE IT?
   └── Proof: testimonials, data, demonstrations, guarantees.

7. WHAT IS THE TONE?
   └── How should this feel? Professional? Friendly? Urgent?
```

---

## Features vs Benefits (The Ogilvy Way)

```
┌─────────────────────────────────────────────────────────────────────┐
│                THE FUNDAMENTAL COPY MISTAKE                         │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  DEVELOPERS WRITE:                                                  │
│  "Built with React, Node.js, and PostgreSQL with 99.9% uptime      │
│   and real-time WebSocket connections"                              │
│                                                                     │
│  WHAT USERS HEAR:                                                   │
│  "Technical words I don't care about"                               │
│                                                                     │
│  ─────────────────────────────────────────────────────────────────  │
│                                                                     │
│  GOOD COPY WRITES:                                                  │
│  "Your team stays in sync without constant meetings.                │
│   See updates the moment they happen."                              │
│                                                                     │
│  WHAT USERS HEAR:                                                   │
│  "This solves my problem"                                           │
│                                                                     │
│  ─────────────────────────────────────────────────────────────────  │
│                                                                     │
│  THE CONVERSION:                                                    │
│                                                                     │
│  FEATURE                        →  BENEFIT                          │
│  ───────────────────────────────────────────────────────────────   │
│  Real-time sync                 →  Never work on outdated info     │
│  AI-powered                     →  Get results without the work     │
│  256-bit encryption             →  Your data stays yours            │
│  One-click integration          →  Set up in 2 minutes, not 2 days │
│  Mobile app                     →  Work from anywhere               │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 1: The Copy Framework

### The AIDA Structure
```
ATTENTION → INTEREST → DESIRE → ACTION

ATTENTION (Headline)
├── Stop the scroll
├── Target the right person
└── Create curiosity or recognition

INTEREST (Subheadline + Opening)
├── Expand on the promise
├── Show you understand their problem
└── Introduce the solution

DESIRE (Body)
├── Benefits, not features
├── Social proof
├── Remove objections
└── Make it feel achievable

ACTION (CTA)
├── Clear next step
├── Low friction
├── Urgency (if genuine)
└── Risk reversal
```

### The PAS Structure (Problem-Agitate-Solution)
```
PROBLEM
├── Name the pain point directly
├── Show you understand it intimately
└── Make them nod in recognition

AGITATE
├── Dig into the consequences
├── What happens if they don't solve it?
├── Make the pain vivid

SOLUTION
├── Introduce your product as relief
├── Show how it addresses the pain
└── Make the path forward clear
```

---

## Section 2: Headline Formulas

### Formula 1: [Outcome] Without [Pain Point]
```
Template: "[Desired outcome] without [thing they want to avoid]"

Examples:
- "Ship code faster without breaking production"
- "Build an audience without posting daily"
- "Track expenses without manual data entry"
- "Learn piano without boring exercises"
```

### Formula 2: [Outcome] for [Specific Audience]
```
Template: "[Outcome] for [who this is for]"

Examples:
- "Code reviews for solo developers"
- "SEO made simple for non-marketers"
- "Invoice automation for freelancers"
- "Project management for remote teams"
```

### Formula 3: The "[Do X] Like [Aspirational Reference]" 
```
Template: "[Action] like [someone they aspire to be like]"

Examples:
- "Write emails like a professional copywriter"
- "Manage projects like a Fortune 500 PM"
- "Debug code like a senior engineer"
- "Present data like a data scientist"
```

### Formula 4: From [Bad State] to [Good State]
```
Template: "From [current painful state] to [desired state]"

Examples:
- "From chaotic spreadsheets to organized dashboards"
- "From inbox zero impossible to inbox zero daily"
- "From 'what did we decide?' to searchable decisions"
- "From manual deploys to push-button shipping"
```

### Formula 5: The Specific Number
```
Template: "[Specific outcome] in [specific timeframe/amount]"

Examples:
- "Set up CI/CD in under 10 minutes"
- "Reduce page load time by 40%"
- "Save 5 hours a week on reporting"
- "Get your first customer in 30 days"
```

### Formula 6: The Question
```
Template: Question that highlights their pain point

Examples:
- "Still manually testing in production?"
- "Tired of rewriting the same email 50 times?"
- "Where did that conversation happen again?"
- "How long since you shipped without anxiety?"
```

### Formula 7: The "What If"
```
Template: "What if [pain point] just... worked?"

Examples:
- "What if deployments just... worked?"
- "What if finding that file took 2 seconds?"
- "What if your code documented itself?"
- "What if meetings had a point?"
```

---

## Section 3: Subheadline Patterns

The subheadline expands on the headline and clarifies who this is for.

### Pattern: Headline Promise + How
```
Headline: "Ship code faster without breaking production"
Subheadline: "Automated testing that catches bugs before your 
              users do. Set up in 5 minutes."
```

### Pattern: Headline + Audience
```
Headline: "Finally, an invoicing tool that doesn't suck"
Subheadline: "Built for freelancers who'd rather work on projects 
              than chase payments."
```

### Pattern: Headline + Social Proof
```
Headline: "The code review tool for solo devs"
Subheadline: "Join 5,000+ developers who ship better code 
              without waiting for teammates."
```

### Pattern: Headline + Problem Acknowledgment
```
Headline: "SEO made simple"
Subheadline: "Because you shouldn't need a marketing degree to 
              rank on Google."
```

---

## Section 4: CTA Copy Patterns

### The Action-Oriented CTA
```
WEAK:                      STRONG:
Submit                  →  Get my free report
Click here              →  Start saving time
Sign up                 →  Create my account
Download                →  Grab the template
Learn more              →  See how it works
```

### The Benefit-First CTA
```
Template: "[Get/Start] + [benefit]"

Examples:
- "Start shipping faster"
- "Get my free audit"
- "See your savings"
- "Try it free for 14 days"
- "Build my first workflow"
```

### The Low-Friction CTA
```
When conversion is the goal, reduce perceived commitment:

HIGH FRICTION:              LOW FRICTION:
"Buy now"               →  "Start free trial"
"Create account"        →  "Try it free — no credit card"
"Subscribe"             →  "Get free updates"
"Get started"           →  "Watch 2-minute demo"
```

### CTA Button Hierarchy
```
PRIMARY (One per page, above fold):
├── Most important action
├── High contrast, visually prominent
└── Benefit-focused text

SECONDARY (Supporting action):
├── Lower commitment alternative
├── Less prominent styling
└── "Learn more", "See demo", "Read docs"

TERTIARY (Navigation):
├── Links, not buttons
├── For already-convinced visitors
└── Pricing, Documentation, About
```

---

## Section 5: Landing Page Structure (Ogilvy-Informed)

### The Ogilvy Landing Page Philosophy

```
"I do not regard advertising as entertainment or an art form, 
 but as a medium of information."
 
Your landing page is a salesperson in print. It should:
├── Open with a compelling promise (headline)
├── Prove the promise (evidence, specifics)
├── Make it easy to act (clear CTA)
└── Remove risk (guarantee, social proof)
```

### The Minimum Viable Landing Page
```
┌─────────────────────────────────────────────────────────────────────┐
│                         ABOVE THE FOLD                              │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  HEADLINE: Clear outcome they'll get                                │
│  SUBHEADLINE: How + who this is for                                │
│  PRIMARY CTA: Start free / Try it / Get started                    │
│  SECONDARY CTA: Watch demo / See how it works                      │
│                                                                     │
│  Optional: Hero image/screenshot/video                              │
│                                                                     │
├─────────────────────────────────────────────────────────────────────┤
│                      BELOW THE FOLD                                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  SECTION 1: THE PROBLEM (2-3 sentences)                            │
│  "You know that feeling when..." / "If you've ever..."              │
│                                                                     │
│  SECTION 2: THE SOLUTION (3 key benefits)                          │
│  Benefit 1 → Supporting detail                                      │
│  Benefit 2 → Supporting detail                                      │
│  Benefit 3 → Supporting detail                                      │
│                                                                     │
│  SECTION 3: SOCIAL PROOF                                           │
│  Testimonials / logos / numbers                                     │
│                                                                     │
│  SECTION 4: HOW IT WORKS (3 simple steps)                          │
│  Step 1 → Step 2 → Step 3 → Result                                 │
│                                                                     │
│  SECTION 5: OBJECTION HANDLING / FAQ                               │
│  Address top 3-5 concerns                                           │
│                                                                     │
│  SECTION 6: FINAL CTA                                              │
│  Repeat primary action with urgency/benefit                         │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Section-by-Section Copy Guide

#### Above the Fold (5-second test)
```
The user should understand in 5 seconds:
1. What this product does
2. Who it's for  
3. What they should do next

TEST: Cover everything below the fold. Would a stranger understand?
```

#### Problem Section
```
✅ DO:
- Name the problem they experience
- Use their language (not yours)
- Be specific about the pain

❌ DON'T:
- Be vague ("things are hard")
- Insult them ("you're doing it wrong")
- Dwell too long (1-2 paragraphs max)

EXAMPLE:
"You've got 47 browser tabs open. Slack is pinging. Your teammate just 
asked 'where's that document again?' for the third time today.

You know there's a better way. You just don't have time to find it."
```

#### Benefits Section
```
FORMULA: [Benefit headline] + [Supporting detail]

EXAMPLE:
"Find any file in seconds
Stop digging through folders. Just describe what you're looking for
and it's there."

"Stay in sync without meetings
See what everyone's working on in real-time. Async updates that 
actually work."

"Never lose a decision
Every choice, captured. Every context, searchable. No more 
'wait, why did we do it that way?'"
```

#### How It Works Section
```
KEEP IT SIMPLE: 3 steps max

FORMULA:
Step 1: [Easy action] → [Immediate result]
Step 2: [Natural next step] → [Value delivered]
Step 3: [Ongoing usage] → [Long-term benefit]

EXAMPLE:
"1. Connect your tools (2 minutes)
   Link Slack, Notion, and Google Drive with one click.

2. Ask anything
   'What did we decide about pricing?' Get instant answers.

3. Stay organized automatically
   Everything searchable, nothing lost."
```

#### Social Proof Section
```
HIERARCHY OF PROOF (strongest to weakest):
1. Specific results ("Saved 5 hours/week on reporting")
2. Named testimonials with titles/photos
3. Company logos
4. Generic metrics ("1,000+ users")
5. Vague quotes ("Great product!")

IF YOU DON'T HAVE SOCIAL PROOF:
- Use beta tester feedback
- Share your own results using the product
- "Join 47 early adopters testing the future of [category]"
- Skip the section (empty proof is worse than no proof)
```

---

## Section 6: Ogilvy's Body Copy Principles

### The Long Copy Doctrine

Ogilvy proved that long copy outsells short copy — when every word earns its place.

```
WHEN TO USE LONG COPY:
├── High-consideration purchases (SaaS, expensive tools)
├── Complex products that need explanation
├── When building trust is essential
├── Direct response / conversion pages
└── When you have genuine proof to share

WHEN TO USE SHORT COPY:
├── Brand awareness (they already know you)
├── Simple, obvious products
├── Impulse purchases
├── When the visual does the selling
└── Follow-up communications to existing customers

THE RULE: "The more you tell, the more you sell" — but only if 
every sentence adds value. Long AND boring is death.
```

### Ogilvy's Body Copy Rules

```
1. WRITE IN THE PRESENT TENSE
   ❌ "You will save time"
   ✅ "You save time"

2. USE SINGULAR, NOT PLURAL
   ❌ "Developers love it"
   ✅ "You'll love it" (speak to ONE reader)

3. AVOID SUPERLATIVES WITHOUT PROOF
   ❌ "The best code review tool"
   ✅ "Catches 47% more bugs than manual review"

4. INCLUDE A STORY WHEN POSSIBLE
   └── Stories are 22x more memorable than facts alone
   └── "I built this because I shipped a bug that cost me a client..."

5. USE SUBHEADS GENEROUSLY
   └── 5x more people read subheads than body copy
   └── Make subheads tell the story on their own

6. START WITH YOUR STRONGEST POINT
   └── Don't "save the best for last" — they won't get there
   └── First paragraph must reward continuing to read

7. END WITH ACTION
   └── Tell them exactly what to do next
   └── Make the next step obvious and low-risk
```

### The Ogilvy Image Principles

```
FOR HERO IMAGES / SCREENSHOTS:
├── Show the product in use (not abstract graphics)
├── People looking at product draw eyes to product
├── Faces get attention (use testimonial photos)
├── Captions under images are read 2x more than body copy
└── Before/after images are highly effective

FOR SCREENSHOTS:
├── Show the "aha moment" — the key value delivered
├── Annotate with benefit callouts
├── Show real data (anonymized if needed) — not empty states
└── Mobile-first if audience is mobile-heavy

OGILVY'S WARNING:
"Never use tricky or irrelevant photographs. They may capture 
attention but they don't sell."
```

### The Proof Stack (Ogilvy's Credibility Framework)

Ogilvy believed in overwhelming proof. Stack these in order of strength:

```
TIER 1: DEMONSTRATED RESULTS
├── Specific numbers: "Reduced deploy time from 2 hours to 4 minutes"
├── Before/after: "Before: 47 bugs per release. After: 3."
├── Customer results: "Acme Corp saved $50K in the first quarter"
└── Case studies: Detailed story of transformation

TIER 2: THIRD-PARTY VALIDATION  
├── Press mentions: "Featured in TechCrunch"
├── Awards: "Product Hunt #1 Product of the Day"
├── Expert endorsements: "Recommended by [respected name]"
└── Certifications: "SOC 2 compliant"

TIER 3: SOCIAL PROOF
├── Number of users: "Join 10,000+ developers"
├── Named testimonials with photos/titles
├── Company logos (if B2B)
└── Ratings: "4.9/5 on G2"

TIER 4: RISK REMOVAL
├── Money-back guarantee: "30-day full refund"
├── Free trial: "Try free for 14 days"
├── No commitment: "Cancel anytime"
└── Support promise: "Real human support, always"

STACK MULTIPLE TIERS. One testimonial isn't enough.
```

---

## Section 7: Email Copy Patterns

### Welcome Email
```
Subject: Welcome to [Product] — here's what's next

Hey [Name],

You're in. 

Here's the one thing I'd do first:
[Single, specific action with link]

It takes about [time] and [benefit they'll get].

If you hit any snags, just reply to this email. I read everything.

[Your name]
Founder, [Product]

P.S. [Bonus resource or tip]
```

### Onboarding Email (Day 3)
```
Subject: Did [Product] click for you yet?

Hey [Name],

Some people get [Product] immediately.

Others need a few days to see how it fits their workflow.

If you're in the second group, here's what usually helps:
[Specific use case with brief how-to]

Real question: What are you hoping [Product] will help you do?

Hit reply — I'm genuinely curious and it helps me make this better.

[Your name]
```

### Re-engagement Email
```
Subject: It's been a while

Hey [Name],

Noticed you haven't logged into [Product] recently.

Totally fine — maybe it wasn't the right fit, or maybe life got busy.

Quick question: Was there something that didn't work for you?

I'm always trying to improve, and "it didn't do X" or "I couldn't 
figure out Y" is genuinely helpful feedback.

Either way, your account is still here if you want to pick it back up.

[Your name]
```

### Upgrade/Conversion Email
```
Subject: [Free trial ending] You've got 3 days left

Hey [Name],

Your [Product] trial ends in 3 days.

In the past [trial length], you've:
- [Specific metric from their usage]
- [Another usage highlight]
- [Benefit they've received]

To keep [primary benefit], you can upgrade here: [Link]

Questions about plans? Just reply — happy to help you pick the right one.

[Your name]

P.S. If [Product] isn't right for you, no worries. Would love to know 
what would've made it more useful.
```

---

## Section 8: Copy Anti-Patterns (What Ogilvy Would Hate)

Ogilvy famously said: "Never write an advertisement which you wouldn't want your family to read." These anti-patterns violate that principle.

### ❌ Feature Vomit
```
WRONG:
"Built with React 18, Node.js 20, PostgreSQL 15, Redis 7, deployed 
on AWS with Kubernetes, featuring REST and GraphQL APIs, OAuth 2.0 
authentication, real-time WebSocket connections..."

RIGHT:
"Get answers in milliseconds, even with millions of records."

(The tech only matters if it enables a benefit they care about)
```

### ❌ Weasel Words
```
WEAK:                           STRONG:
"Helps you to..."           →   "You will..."
"Allows you to..."          →   "[Direct action]"
"Enables..."                →   "[What it does]"
"Solutions for..."          →   "[Specific outcome]"
"Best-in-class..."          →   "[Specific differentiator]"
"Innovative..."             →   "[What makes it different]"
"Cutting-edge..."           →   "[Specific capability]"
```

### ❌ Hyperbole Without Substance
```
WRONG:
"Revolutionary AI-powered solution that will transform your workflow 
and disrupt the industry"

RIGHT:
"Find any email in 2 seconds. Type what you remember, get what you need."
```

### ❌ Talking About Yourself
```
WRONG:
"We are proud to announce our new feature..."
"Our team has worked hard to..."
"We believe that..."

RIGHT:
"You can now..."
"New: [benefit]"
"[Benefit] is here"
```

### ❌ Assuming Knowledge
```
WRONG:
"Integrates with your CI/CD pipeline for automated deployments"
(assumes they have a CI/CD pipeline and know what it is)

RIGHT:
"Push code, it goes live. No complicated setup."
(benefit-first, jargon-free)
```

---

## Section 9: Guardrails

### What This Skill Does NOT Do
- Write manipulative or high-pressure copy
- Make false claims or promises
- Create FOMO-based urgency that isn't real
- Produce generic "fill in the blank" templates
- Ignore the actual product when writing benefits

### Quality Floors
- Every headline must be testable (could be A/B tested)
- Every benefit must be tied to a real capability
- Every CTA must have low friction
- Copy must be shorter than user expects, not longer

### Boundaries
- Will not write deceptive countdown timers
- Will not create fake scarcity
- Will not promise results the product can't deliver
- Will suggest when product positioning needs work, not just copy

---

## Section 10: Examples

### Example 1: Landing Page Hero

**Input:** "Write hero section copy for my API monitoring tool for solo devs"

**Output:**
```
HEADLINE:
Your API went down at 3 AM.
Did you know?

SUBHEADLINE:
Simple monitoring for solo developers. Get alerted the moment 
something breaks — not hours later from angry users.

PRIMARY CTA: Start monitoring free
SECONDARY CTA: See how it works (2 min)

[Below hero]
✓ 1-minute checks  ✓ Slack/email/SMS alerts  ✓ Free for up to 5 endpoints
```

### Example 2: Feature → Benefit Translation

**Input:** "Translate these features into benefits: 
- Real-time collaboration
- AI-powered search  
- SSO integration"

**Output:**
```
FEATURE: Real-time collaboration
BENEFIT: "See edits as they happen. No more 'wait, I was working on 
          that' moments."

FEATURE: AI-powered search
BENEFIT: "Describe what you're looking for in plain English. 
          Find it in seconds, not minutes."

FEATURE: SSO integration
BENEFIT: "One login, all your tools. No new password to forget."
```

### Example 3: CTA Variations

**Input:** "Give me CTA options for a free trial signup"

**Output:**
```
BENEFIT-FOCUSED:
- Start building faster
- See it in action
- Get my free account

LOW-FRICTION:
- Try free for 14 days
- No credit card required
- Start free — upgrade anytime

ACTION-SPECIFIC:
- Create my first [thing]
- Launch my dashboard
- Connect my tools

URGENCY (only if genuine):
- Claim my early access
- Join the beta
- Lock in founder pricing
```

---

## Section 11: Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "Conversion Copywriting / Landing Page Copy"
  description: |
    Copywriting edge cases where generic advice fails. These verify the skill
    produces conversion-focused copy, not just grammatically correct text.
  
  cases:
    - id: feature_benefit_translation
      scenario: "User provides technical features, needs benefit copy"
      naive_failure: "Rewrites features more clearly but still as features"
      expert_behavior: "Translates to user-facing benefits with outcomes"
      test_input: "Write copy for: '256-bit AES encryption'"
      must_check:
        - "Does NOT lead with '256-bit' or 'AES'"
        - "Focuses on what encryption GIVES the user"
        - "Example: 'Your data stays yours' or 'Bank-level security'"
      anti_patterns:
        - "Featuring 256-bit AES encryption"
        - "Uses advanced encryption technology"
    
    - id: vague_product_handling
      scenario: "User has unclear product positioning"
      naive_failure: "Writes generic copy that could apply to anything"
      expert_behavior: "Asks clarifying questions OR writes multiple options for different angles"
      test_input: "Write copy for my productivity app"
      must_check:
        - "Asks what specific problem it solves OR"
        - "Provides multiple versions for different angles"
        - "Does NOT write generic 'boost your productivity' copy"
      anti_patterns:
        - "Boost your productivity with our innovative solution"
        - "The ultimate productivity app"
    
    - id: cta_specificity
      scenario: "User needs CTA button copy"
      naive_failure: "Generic 'Sign Up' or 'Get Started'"
      expert_behavior: "Provides benefit-focused, action-specific options"
      test_input: "What should my CTA button say?"
      must_check:
        - "Asks about the action OR product context"
        - "Provides options that include benefits"
        - "Varies friction level"
      anti_patterns:
        - "Just use 'Sign Up'"
        - "Click Here"
        - "Submit"
    
    - id: social_proof_absence
      scenario: "User has no testimonials or social proof"
      naive_failure: "Suggests fake or vague social proof"
      expert_behavior: "Provides alternatives or suggests skipping section"
      test_input: "I don't have any customers yet, what do I put for social proof?"
      must_check:
        - "Does NOT suggest fake testimonials"
        - "Offers alternatives (beta testers, own results, early adopter framing)"
        - "Notes that no proof is better than fake proof"
      anti_patterns:
        - "Write some testimonials"
        - "1000s of happy customers"
    
    - id: jargon_audience_mismatch
      scenario: "Copy uses jargon user's audience won't understand"
      naive_failure: "Keeps technical jargon for non-technical audience"
      expert_behavior: "Translates to audience-appropriate language"
      test_input: "Our CI/CD pipeline enables continuous deployment" 
                  (for non-developer audience)
      must_check:
        - "Identifies jargon mismatch"
        - "Translates to benefit"
        - "Uses language the audience would use"
      anti_patterns:
        - "Keeping CI/CD terminology for non-devs"
        - "Adding more jargon to explain jargon"
```

---

## Section 12: Output Requirements

Every copy output MUST include:
1. **Multiple variations** — At least 3 options for headlines/CTAs
2. **Benefit focus** — Features translated to outcomes
3. **Appropriate length** — Concise, not verbose
4. **Testability** — Could be A/B tested as-is

Every output MUST end with a contextual follow-up menu.

---

## Follow-Up Menu

**What would you like to do next?**

[1] 📝 **Write headlines** — Generate 10 headline options for your product
[2] 🎯 **Write CTAs** — Button copy options for your conversion goal
[3] 📄 **Full landing page** — Complete landing page copy structure
[4] 🔄 **Rewrite copy** — Improve existing copy you're not happy with
[5] ✉️ **Email copy** — Welcome, onboarding, or conversion emails
[6] 🔍 **Audit my copy** — Review and improve what you have

---

Reply with a number or paste copy you want to improve.
