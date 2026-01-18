---
name: marketing-index
description: |
  Hub skill for the solo developer marketing suite. Routes users to the right 
  specialized marketing skill based on their current task. Covers SEO, LinkedIn,
  Reddit, copywriting, and strategy. Designed for solo developers who want
  agency-level marketing without the agency.
license: MIT
---

# Marketing Index — Solo Dev Marketing Hub

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "help me market", "marketing help", "how do I promote"
- "which marketing skill", "what should I use for"
- "I need to grow my audience", "get more users"

**Quick Triggers:**
- `market my app` → Route based on current need
- `what marketing should I do` → Strategy overview + routing
- `promote [thing]` → Detect channel and route

**Smart Defaults:**
- Assumes: solo developer or small team
- Budget: bootstrapped / minimal paid ads
- Goal: organic growth + community building
- Tone: authentic, not corporate

---

## Available Skills in This Suite

| Skill | Use When You Need |
|-------|-------------------|
| `marketing-seo` | Website optimization, meta tags, schema markup, keyword strategy, technical SEO audits |
| `marketing-linkedin` | Professional content, thought leadership posts, engagement hooks, B2B visibility |
| `marketing-reddit` | Community engagement, authentic promotion, subreddit-aware posting, avoiding bans |
| `marketing-copy` | Headlines, CTAs, landing pages, email copy, benefit-driven persuasion |
| `marketing-strategy` | Campaign planning, positioning, content calendars, funnel design, growth roadmaps |

---

## Quick Router

### What Are You Working On Right Now?

```
┌─────────────────────────────────────────────────────────────────────┐
│                     MARKETING TASK ROUTER                           │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  "I need my website to rank better"                                │
│  "Fix my SEO" / "meta tags" / "schema"                             │
│  "Google isn't finding me"                                          │
│      └──────────────────────────────► marketing-seo                │
│                                                                     │
│  "I want to post on LinkedIn"                                       │
│  "Build my professional brand"                                      │
│  "B2B content" / "thought leadership"                              │
│      └──────────────────────────────► marketing-linkedin           │
│                                                                     │
│  "I want to share on Reddit"                                        │
│  "Community marketing" / "authentic promo"                          │
│  "Which subreddit" / "avoid getting banned"                        │
│      └──────────────────────────────► marketing-reddit             │
│                                                                     │
│  "Write my landing page"                                            │
│  "Headlines" / "CTAs" / "conversion copy"                          │
│  "Make people want to sign up"                                      │
│      └──────────────────────────────► marketing-copy               │
│                                                                     │
│  "Plan my marketing" / "growth strategy"                           │
│  "Content calendar" / "what should I focus on"                     │
│  "Positioning" / "who is my audience"                              │
│      └──────────────────────────────► marketing-strategy           │
│                                                                     │
│  "I don't know where to start"                                      │
│      └──────────────────────────────► See Launch Sequence below    │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## The Solo Dev Launch Sequence

If you're starting from zero, here's the recommended order:

```
PHASE 1: Foundation (Week 1-2)
├── marketing-strategy → Define positioning, audience, unique angle
├── marketing-copy → Write landing page, core value proposition
└── marketing-seo → Basic on-page SEO, meta tags, schema

PHASE 2: Content Engine (Week 3-4)
├── marketing-linkedin → Start building professional presence
├── marketing-reddit → Identify communities, start giving value
└── marketing-strategy → Create 30-day content calendar

PHASE 3: Growth Loop (Ongoing)
├── marketing-linkedin → 3-5 posts/week cadence
├── marketing-reddit → Daily value contribution
├── marketing-seo → Technical improvements, content optimization
└── marketing-strategy → Monthly review, adjust tactics
```

---

## Cross-Skill Workflows

### "I'm launching next week"
1. **marketing-strategy** → Launch announcement framework
2. **marketing-copy** → Landing page final polish
3. **marketing-linkedin** → Launch post series (teaser, launch, follow-up)
4. **marketing-reddit** → Identify launch-friendly subreddits, craft value-first posts

### "I need more signups"
1. **marketing-copy** → Audit CTA strength, headline clarity
2. **marketing-seo** → Check if you're ranking for intent keywords
3. **marketing-strategy** → Funnel analysis, where are people dropping?

### "I want to build an audience before launch"
1. **marketing-strategy** → Pre-launch content strategy
2. **marketing-linkedin** → Build in public content series
3. **marketing-reddit** → Become known helper in target communities

### "My content isn't getting engagement"
1. **marketing-linkedin** → Hook formula audit, format optimization
2. **marketing-reddit** → Subreddit culture check, value ratio assessment
3. **marketing-copy** → Headline and opening line rewrites

---

## Solo Dev Marketing Principles

These principles apply across ALL skills in this suite, informed by David Ogilvy's foundational advertising wisdom:

### The Ogilvy Foundation

```
"The consumer isn't a moron. She's your wife."
— David Ogilvy

This entire skill suite is built on Ogilvy's principles:
├── Research before you write (know your customer deeply)
├── Headlines do 80% of the work (make them count)
├── Specifics beat generalities (numbers, outcomes, proof)
├── Sell, don't entertain (cleverness that doesn't convert is vanity)
├── Long copy sells — when every word earns its place
└── Brand image is cumulative (consistency compounds)

The marketing-copy skill contains the full Ogilvy framework.
```

### 1. Authenticity Over Polish
```
❌ Corporate: "We're excited to announce our revolutionary solution..."
✅ Solo dev: "I built this because I was frustrated with..."
```

### 2. Value Before Ask
```
❌ Spammy: "Check out my new app!"
✅ Value-first: "[Helpful insight]... I actually built a tool for this: [link]"
```

### 3. Consistency Over Virality
```
❌ Hoping for viral: One big launch post, then silence
✅ Compounding: Regular valuable content, audience builds over time
```

### 4. Platform Native
```
❌ Cross-posting: Same content everywhere, feels out of place
✅ Native: Adapted tone, format, and expectations per platform
```

### 5. Build in Public
```
❌ Hidden: Surprise launch, no one knows you exist
✅ Transparent: Share journey, struggles, wins — people root for you
```

---

## Starter Prompts

Copy these to get started with specific skills:

### Quick Start: SEO
```
Read the marketing-seo skill and audit my website [URL] for technical SEO 
issues. Focus on meta tags, schema markup, and quick wins I can fix today.
```

### Quick Start: LinkedIn
```
Read the marketing-linkedin skill and help me write a LinkedIn post about 
[topic]. I want to establish thought leadership without sounding like 
corporate marketing.
```

### Quick Start: Reddit
```
Read the marketing-reddit skill. I built [product description]. Help me 
identify the right subreddits and craft a post that provides value without 
getting removed as self-promotion.
```

### Quick Start: Copy
```
Read the marketing-copy skill and rewrite my landing page headline and 
subheadline. Current: [paste current copy]. My target user is [description].
```

### Quick Start: Strategy
```
Read the marketing-strategy skill. I'm a solo dev building [product]. 
Help me create a 30-day marketing plan I can execute in 5 hours/week.
```

---

## When NOT To Use This Suite

This suite is optimized for:
- Solo developers and tiny teams
- Bootstrapped / minimal budget
- B2B SaaS, dev tools, indie products
- Organic growth strategies

Consider other approaches if:
- You have significant ad budget → paid acquisition strategies
- You're B2C consumer app → different channels (TikTok, Instagram)
- You're enterprise sales → account-based marketing, different playbook
- You need PR/press → media relations, different skill set

---

## Follow-Up Menu

**What would you like to do?**

[1] 🎯 **Route me** — Describe your current task and I'll recommend a skill
[2] 📋 **Launch sequence** — Walk me through the foundation phase
[3] 🔍 **Audit my current marketing** — Tell me what you're doing, I'll identify gaps
[4] 📅 **Weekly routine** — Help me build a sustainable marketing habit
[5] ❓ **Explain a skill** — Deep dive into what one of the skills does

---

Reply with a number or describe what you're trying to accomplish.
