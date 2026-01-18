---
name: marketing-seo
description: |
  Technical and on-page SEO skill for solo developers. Covers meta tags, schema 
  markup, keyword optimization, site structure, and Core Web Vitals. Produces
  actionable checklists and code snippets, not generic SEO advice.
license: MIT
---

# Marketing SEO — Technical SEO for Solo Developers

## Skill Configuration

**Version:** 1.0.0

**Triggers:**
- "SEO audit", "fix my SEO", "optimize for search"
- "meta tags", "schema markup", "structured data"
- "why am I not ranking", "Google can't find me"
- "keyword research", "on-page SEO"

**Quick Triggers:**
- `seo audit [url]` → Full technical audit
- `meta tags for [page]` → Generate optimized meta tags
- `schema for [type]` → Generate JSON-LD schema
- `keywords for [topic]` → Keyword research framework

**Smart Defaults:**
- Focus: technical SEO solo devs can implement themselves
- Output: code snippets, not just advice
- Priority: quick wins before deep optimization
- Tooling: free tools (Google Search Console, PageSpeed Insights)

---

## Core Philosophy: Developer-First SEO

```
┌─────────────────────────────────────────────────────────────────────┐
│                    SEO FOR PEOPLE WHO CODE                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  Traditional SEO advice: "Optimize your meta descriptions"          │
│  This skill: Here's the exact HTML, JSON-LD, and checklist          │
│                                                                     │
│  Traditional SEO advice: "Improve your Core Web Vitals"             │
│  This skill: Here's the Lighthouse audit + specific code fixes      │
│                                                                     │
│  Traditional SEO advice: "Build quality backlinks"                  │
│  This skill: Here's what you can actually control as a solo dev     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Section 1: The SEO Hierarchy for Solo Devs

Focus your limited time on what matters most:

```
PRIORITY 1: Foundation (Do First) ─────────────────────────────────────
│
├── Technical crawlability
│   ├── Valid sitemap.xml at /sitemap.xml
│   ├── robots.txt not blocking important pages
│   ├── No broken internal links (404s)
│   └── HTTPS everywhere
│
├── Core meta tags (every page)
│   ├── <title> — unique, keyword-included, under 60 chars
│   ├── <meta name="description"> — compelling, under 155 chars
│   └── <link rel="canonical"> — self-referencing canonical
│
└── Mobile-friendly
    └── Responsive design, readable without zoom

PRIORITY 2: Enhancement (Do Second) ───────────────────────────────────
│
├── Schema markup (JSON-LD)
│   ├── Organization/Person schema on homepage
│   ├── Product/SoftwareApplication schema on product page
│   └── FAQ schema if you have FAQ content
│
├── Open Graph tags (social sharing)
│   ├── og:title, og:description, og:image
│   └── twitter:card, twitter:image
│
└── Page speed (Core Web Vitals)
    ├── LCP (Largest Contentful Paint) < 2.5s
    ├── FID (First Input Delay) < 100ms
    └── CLS (Cumulative Layout Shift) < 0.1

PRIORITY 3: Growth (Ongoing) ──────────────────────────────────────────
│
├── Content targeting keywords
│   ├── Blog posts for informational queries
│   ├── Landing pages for commercial queries
│   └── Documentation for technical queries
│
├── Internal linking
│   └── Logical hierarchy, important pages get more links
│
└── Earning backlinks (not building)
    ├── Create genuinely useful content/tools
    ├── Get listed in directories (dev tool lists, etc.)
    └── Write guest posts on relevant blogs
```

---

## Section 2: Meta Tag Templates

### Homepage Meta Tags
```html
<!-- Primary Meta Tags -->
<title>[Product Name] — [Primary Benefit] | [Category]</title>
<meta name="description" content="[Product Name] helps [target audience] [achieve outcome] with [key differentiator]. [Social proof or CTA].">
<link rel="canonical" href="https://yourdomain.com/">

<!-- Open Graph / Facebook -->
<meta property="og:type" content="website">
<meta property="og:url" content="https://yourdomain.com/">
<meta property="og:title" content="[Product Name] — [Primary Benefit]">
<meta property="og:description" content="[Compelling description for social shares]">
<meta property="og:image" content="https://yourdomain.com/og-image.png">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:url" content="https://yourdomain.com/">
<meta name="twitter:title" content="[Product Name] — [Primary Benefit]">
<meta name="twitter:description" content="[Compelling description for Twitter]">
<meta name="twitter:image" content="https://yourdomain.com/twitter-image.png">
```

### Blog Post Meta Tags
```html
<title>[Post Title] — [Brand Name]</title>
<meta name="description" content="[What reader will learn]. [Key takeaway or hook]. [Time estimate or scope].">
<link rel="canonical" href="https://yourdomain.com/blog/[slug]/">
<meta property="article:published_time" content="[ISO 8601 date]">
<meta property="article:author" content="[Author Name]">
```

### Product/Pricing Page Meta Tags
```html
<title>[Product Name] Pricing — [Value Statement]</title>
<meta name="description" content="[Product Name] plans start at $[price]. [Key features included]. [Risk reversal: free trial, money-back].">
<link rel="canonical" href="https://yourdomain.com/pricing/">
```

---

## Section 3: Schema Markup Templates (JSON-LD)

### SoftwareApplication Schema (For Dev Tools/SaaS)
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "[Product Name]",
  "description": "[One-sentence description]",
  "url": "https://yourdomain.com",
  "applicationCategory": "[Category: DeveloperApplication, BusinessApplication, etc.]",
  "operatingSystem": "[Web, Windows, macOS, Linux, iOS, Android]",
  "offers": {
    "@type": "Offer",
    "price": "[Starting price or 0 for free]",
    "priceCurrency": "USD"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "[Rating]",
    "ratingCount": "[Number of ratings]"
  },
  "author": {
    "@type": "Person",
    "name": "[Your Name]",
    "url": "https://yourpersonalsite.com"
  }
}
</script>
```

### Organization Schema (For Company/Brand)
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "[Company/Product Name]",
  "url": "https://yourdomain.com",
  "logo": "https://yourdomain.com/logo.png",
  "description": "[What you do]",
  "founder": {
    "@type": "Person",
    "name": "[Your Name]"
  },
  "sameAs": [
    "https://twitter.com/[handle]",
    "https://linkedin.com/company/[company]",
    "https://github.com/[org]"
  ]
}
</script>
```

### FAQ Schema (For FAQ Pages/Sections)
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[Question 1]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 1]"
      }
    },
    {
      "@type": "Question", 
      "name": "[Question 2]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 2]"
      }
    }
  ]
}
</script>
```

### BreadcrumbList Schema
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://yourdomain.com"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "[Section]",
      "item": "https://yourdomain.com/[section]/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "[Current Page]",
      "item": "https://yourdomain.com/[section]/[page]/"
    }
  ]
}
</script>
```

---

## Section 4: Technical SEO Checklist

### Crawlability Checklist
```
□ sitemap.xml exists at /sitemap.xml
□ sitemap.xml is submitted to Google Search Console
□ robots.txt exists and doesn't block important pages
□ No pages return 5xx errors
□ No important pages return 404
□ All pages accessible within 3 clicks from homepage
□ No orphan pages (pages with no internal links)
□ HTTPS on all pages (no mixed content)
□ www and non-www redirect to one version
□ Trailing slash consistency (pick one, redirect the other)
```

### On-Page Checklist (Per Page)
```
□ Unique <title> tag (50-60 characters)
□ Unique meta description (120-155 characters)
□ Self-referencing canonical tag
□ One H1 tag containing primary keyword
□ Logical heading hierarchy (H1 → H2 → H3)
□ Images have descriptive alt text
□ Internal links to related pages
□ External links to authoritative sources (where relevant)
□ URL is short, descriptive, contains keyword
□ Content matches search intent for target keyword
```

### Core Web Vitals Checklist
```
□ LCP (Largest Contentful Paint) < 2.5 seconds
  └── Optimize hero images, preload critical resources
□ FID (First Input Delay) < 100ms
  └── Minimize JavaScript, defer non-critical scripts
□ CLS (Cumulative Layout Shift) < 0.1
  └── Set dimensions on images/embeds, avoid layout shifts
□ Mobile PageSpeed score > 80
□ Desktop PageSpeed score > 90
```

### Schema Validation Checklist
```
□ Test schema at: https://search.google.com/test/rich-results
□ No errors in structured data
□ Schema type matches page content
□ Required fields populated (varies by schema type)
□ Schema visible in Google Search Console enhancements
```

---

## Section 5: Keyword Research Framework

### Step 1: Seed Keywords
```
YOUR PRODUCT: [What you built]
PROBLEM SOLVED: [Pain point you address]
TARGET USER: [Who uses this]

Generate seed keywords:
├── [problem] + solution → "automate invoice tracking"
├── [problem] + tool → "invoice tracking tool"
├── [competitor] + alternative → "freshbooks alternative"
├── how to + [task] → "how to track invoices"
├── best + [category] → "best invoicing software"
└── [task] + for [audience] → "invoicing for freelancers"
```

### Step 2: Keyword Intent Classification
```
INFORMATIONAL (Blog content)
├── "how to...", "what is...", "why does..."
├── "guide to...", "tutorial...", "examples of..."
└── Goal: Build authority, capture early-stage awareness

COMMERCIAL (Comparison pages, features)
├── "best...", "top...", "vs...", "alternative to..."
├── "review...", "comparison...", "pricing..."
└── Goal: Capture evaluation-stage searchers

TRANSACTIONAL (Landing pages, pricing)
├── "[product] pricing", "[product] free trial"
├── "buy...", "sign up...", "download..."
└── Goal: Capture ready-to-convert searchers

NAVIGATIONAL (Brand pages)
├── "[your brand name]", "[product name] login"
└── Goal: Own your brand searches
```

### Step 3: Keyword Prioritization Matrix
```
                    HIGH RELEVANCE              LOW RELEVANCE
                ┌─────────────────────────┬─────────────────────────┐
   LOW          │                         │                         │
   COMPETITION  │  ★★★ PRIORITY 1         │  ★☆☆ MAYBE LATER        │
                │  Quick wins, target now │  Easy but off-topic     │
                ├─────────────────────────┼─────────────────────────┤
   HIGH         │                         │                         │
   COMPETITION  │  ★★☆ PRIORITY 2         │  ☆☆☆ SKIP               │
                │  Important but harder   │  Hard and irrelevant    │
                └─────────────────────────┴─────────────────────────┘
```

---

## Section 6: Common SEO Mistakes (Anti-Patterns)

### ❌ Duplicate Title Tags
```html
<!-- WRONG: Same title on multiple pages -->
<title>My Awesome App</title>  <!-- On every page -->

<!-- RIGHT: Unique, descriptive titles -->
<title>My Awesome App — Automate Your Invoicing</title>  <!-- Homepage -->
<title>Pricing — My Awesome App</title>  <!-- Pricing -->
<title>How to Track Invoices — My Awesome App</title>  <!-- Blog -->
```

### ❌ Missing or Duplicate Canonicals
```html
<!-- WRONG: No canonical (Google guesses) -->
<!-- No canonical tag -->

<!-- WRONG: Wrong canonical (pointing to different page) -->
<link rel="canonical" href="https://example.com/other-page/">

<!-- RIGHT: Self-referencing canonical -->
<link rel="canonical" href="https://example.com/this-page/">
```

### ❌ Blocking JS/CSS in robots.txt
```
# WRONG: Blocking resources Google needs to render
User-agent: *
Disallow: /js/
Disallow: /css/

# RIGHT: Only block what shouldn't be indexed
User-agent: *
Disallow: /admin/
Disallow: /api/
```

### ❌ Images Without Alt Text
```html
<!-- WRONG: Empty or missing alt -->
<img src="dashboard.png" alt="">
<img src="dashboard.png">

<!-- RIGHT: Descriptive alt text -->
<img src="dashboard.png" alt="Invoice tracking dashboard showing monthly revenue chart">
```

### ❌ Thin Content Targeting Competitive Keywords
```
WRONG APPROACH:
├── Target: "best CRM software" (extremely competitive)
├── Content: 300-word page with feature list
└── Result: Page 10+ of Google, no traffic

RIGHT APPROACH:
├── Target: "CRM for freelance designers" (long-tail, specific)
├── Content: 1500-word guide with specific use cases
└── Result: Page 1 potential, qualified traffic
```

---

## Section 7: Quick Wins Audit Process

When auditing a site, check these first (highest impact, easiest fixes):

```
AUDIT SEQUENCE:
│
├── 1. Run Google PageSpeed Insights
│      └── Note: LCP, FID, CLS scores
│
├── 2. Check Google Search Console
│      ├── Coverage: Any errors or warnings?
│      ├── Enhancements: Schema issues?
│      └── Core Web Vitals: Any failing URLs?
│
├── 3. View page source on homepage
│      ├── <title> present and descriptive?
│      ├── <meta description> present?
│      ├── <link canonical> present?
│      └── Schema markup present?
│
├── 4. Check /sitemap.xml
│      └── Exists? Contains all important pages?
│
├── 5. Check /robots.txt
│      └── Blocking anything important?
│
└── 6. Mobile test
       └── Google Mobile-Friendly Test: pass?
```

---

## Section 8: Guardrails

### What This Skill Does NOT Do
- Guarantee rankings (no one can)
- Build backlinks through spammy tactics
- Keyword stuff or create thin content
- Promise quick results (SEO compounds over months)
- Replace a dedicated SEO tool for large sites

### Quality Floors
- Every meta tag recommendation includes character count
- Every schema recommendation is valid JSON-LD
- Every technical fix includes the actual code/config
- Never recommend tactics that could trigger penalties

### Boundaries
- For sites with 500+ pages → recommend dedicated SEO tools
- For highly competitive keywords → recommend content strategy first
- For local businesses → note that local SEO has additional requirements
- For e-commerce → note that product schema has specific requirements

---

## Section 9: Examples

### Example 1: Homepage Meta Tags Request

**Input:** "Write meta tags for my SaaS homepage. Product: CodeReview Pro - AI code review tool for solo developers."

**Output:**
```html
<!-- Primary Meta Tags -->
<title>CodeReview Pro — AI Code Reviews for Solo Developers</title>
<meta name="description" content="Get instant AI-powered code reviews without waiting for teammates. CodeReview Pro catches bugs, suggests improvements, and helps solo devs ship better code. Free tier available.">
<link rel="canonical" href="https://codereviewpro.com/">

<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:url" content="https://codereviewpro.com/">
<meta property="og:title" content="CodeReview Pro — AI Code Reviews for Solo Developers">
<meta property="og:description" content="Ship better code without waiting for PR reviews. AI-powered feedback in seconds.">
<meta property="og:image" content="https://codereviewpro.com/og-image.png">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="CodeReview Pro — AI Code Reviews for Solo Developers">
<meta name="twitter:description" content="Ship better code without waiting for PR reviews. AI-powered feedback in seconds.">
<meta name="twitter:image" content="https://codereviewpro.com/twitter-image.png">
```

**Character counts:**
- Title: 52 chars ✓ (under 60)
- Description: 154 chars ✓ (under 155)

---

### Example 2: Schema Markup Request

**Input:** "Generate schema for my developer tool's pricing page"

**Output:**
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "Pricing — CodeReview Pro",
  "description": "CodeReview Pro pricing plans for solo developers and teams",
  "url": "https://codereviewpro.com/pricing/",
  "mainEntity": {
    "@type": "SoftwareApplication",
    "name": "CodeReview Pro",
    "applicationCategory": "DeveloperApplication",
    "operatingSystem": "Web",
    "offers": [
      {
        "@type": "Offer",
        "name": "Free",
        "price": "0",
        "priceCurrency": "USD",
        "description": "For hobby projects"
      },
      {
        "@type": "Offer",
        "name": "Pro",
        "price": "19",
        "priceCurrency": "USD",
        "priceSpecification": {
          "@type": "UnitPriceSpecification",
          "price": "19",
          "priceCurrency": "USD",
          "billingDuration": "P1M"
        },
        "description": "For professional developers"
      }
    ]
  }
}
</script>
```

**Validation:** Test at https://search.google.com/test/rich-results

---

### Example 3: Quick SEO Audit

**Input:** "Quick SEO audit for https://example.com"

**Output:**
```
SEO QUICK AUDIT: example.com
═══════════════════════════════════════════════════════════════════

PRIORITY 1 ISSUES (Fix This Week)
─────────────────────────────────────────────────────────────────────
❌ Title tag: "Home" — Not descriptive, missing keywords
   → Recommendation: "[Product] — [Primary Benefit]"

❌ Meta description: Missing
   → Recommendation: Add 120-155 char description with value prop

❌ Canonical tag: Missing
   → Recommendation: Add <link rel="canonical" href="https://example.com/">

⚠️ H1 tag: "Welcome" — Generic, no keywords
   → Recommendation: "[Product]: [What It Does]"

PRIORITY 2 ISSUES (Fix This Month)
─────────────────────────────────────────────────────────────────────
⚠️ Schema markup: None detected
   → Recommendation: Add SoftwareApplication schema

⚠️ Open Graph tags: Missing
   → Recommendation: Add og:title, og:description, og:image

✓ Core Web Vitals: Passing (LCP: 1.8s, CLS: 0.05)
✓ Mobile-friendly: Yes
✓ HTTPS: Yes
✓ sitemap.xml: Present
✓ robots.txt: Present, not blocking content

QUICK WINS (Copy-Paste Ready)
─────────────────────────────────────────────────────────────────────
[Provides actual HTML code to add]
```

---

## Section 10: Domain Edge Cases

```yaml
domain_edge_cases:
  domain: "SEO / Search Engine Optimization"
  description: |
    SEO edge cases where generic advice fails. These verify the skill
    provides technically accurate, implementable guidance.
  
  cases:
    - id: canonical_pagination
      scenario: "Paginated content (blog page 2, 3, etc.)"
      naive_failure: "Self-referencing canonical on each page"
      expert_behavior: "Explains rel=prev/next deprecated, recommends view-all or self-canonical"
      test_input: "How should I handle canonical tags for my paginated blog archive?"
      must_check:
        - "Acknowledges Google deprecated rel=prev/next"
        - "Recommends self-referencing canonicals OR view-all page"
        - "Does NOT recommend pointing all pages to page 1"
      anti_patterns:
        - "Point all paginated pages to the first page canonical"
        - "Use rel=prev and rel=next" (without noting deprecation)
    
    - id: javascript_rendering
      scenario: "SPA/JavaScript-heavy site SEO"
      naive_failure: "Generic 'add meta tags' advice without addressing rendering"
      expert_behavior: "Addresses SSR/SSG, dynamic rendering, or prerendering needs"
      test_input: "My React app doesn't show up in Google, just blank page"
      must_check:
        - "Identifies JS rendering as likely issue"
        - "Recommends SSR (Next.js), SSG, or prerendering"
        - "Explains how to verify with 'View Rendered HTML' in Search Console"
      anti_patterns:
        - "Just add meta tags"
        - "No mention of server-side rendering"
    
    - id: trailing_slash_consistency
      scenario: "URL structure with inconsistent trailing slashes"
      naive_failure: "Ignores trailing slash issues"
      expert_behavior: "Identifies potential duplicate content, recommends redirect strategy"
      test_input: "Does it matter if my URLs have trailing slashes or not?"
      must_check:
        - "Explains duplicate content risk if both versions exist"
        - "Recommends picking one and 301 redirecting the other"
        - "Notes canonical tags as backup, not primary solution"
      anti_patterns:
        - "It doesn't matter"
        - "Just use canonical tags" (without redirect recommendation)
    
    - id: international_seo
      scenario: "Multi-language or multi-region site"
      naive_failure: "Standard meta tag advice without hreflang"
      expert_behavior: "Introduces hreflang, x-default, and proper implementation"
      test_input: "I'm launching my site in English and Spanish, what do I need for SEO?"
      must_check:
        - "Mentions hreflang tags"
        - "Explains x-default for fallback"
        - "Recommends URL structure (subdirectory vs subdomain vs ccTLD)"
      anti_patterns:
        - "Just translate your meta tags"
        - "No mention of hreflang"
    
    - id: soft_404_detection
      scenario: "Pages returning 200 but showing 'not found' content"
      naive_failure: "Only checks HTTP status codes"
      expert_behavior: "Explains soft 404s, how Google detects them, how to fix"
      test_input: "Google Search Console shows soft 404 errors, what does that mean?"
      must_check:
        - "Explains soft 404 = 200 status but empty/error content"
        - "Recommends returning proper 404 status code"
        - "Suggests checking for pages with thin/no content"
      anti_patterns:
        - "Your pages are returning 404 errors" (misunderstanding)
        - "Just ignore it"
```

---

## Section 11: Output Requirements

Every output from this skill MUST include:
1. **Actual code/config** — Not just "add meta tags" but the actual HTML
2. **Character counts** — For title/description recommendations
3. **Validation method** — How to verify the fix works
4. **Priority indicator** — Is this critical, important, or nice-to-have?

Every output MUST end with a contextual follow-up menu.

---

## Follow-Up Menu

**What would you like to do next?**

[1] 🔍 **Audit a specific URL** — Paste URL for quick SEO check
[2] 📝 **Generate meta tags** — For homepage, blog post, or product page
[3] 🏗️ **Generate schema markup** — Product, Organization, FAQ, etc.
[4] 🔑 **Keyword research** — Find keywords for your product/content
[5] ⚡ **Fix Core Web Vitals** — Specific performance recommendations
[6] 📋 **Full checklist** — Complete technical SEO audit checklist

---

Reply with a number or describe what you need help with.
