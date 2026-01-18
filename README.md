# SkillForge Skills Repository

Private repository for SkillForge cognitive skills and foundational research.

---

## Repository Structure

```
skill-forge-skills/
├── README.md
├── suites/
│   ├── marketing/              # Marketing Suite (6 skills)
│   │   ├── marketing-index/
│   │   ├── marketing-strategy/
│   │   ├── marketing-linkedin/
│   │   ├── marketing-reddit/
│   │   ├── marketing-copy/
│   │   └── marketing-seo/
│   │
│   └── uiux/                   # UI/UX Suite (6 skills)
│       ├── uiux-index/
│       ├── uiux-systems/
│       ├── uiux-visual/
│       ├── uiux-interaction/
│       ├── uiux-usability/
│       └── uiux-a11y/
│
├── standalone/
│   └── skillforge-builder/     # Internal meta-skill
│
└── research/                   # Foundational research (42 documents)
    ├── skills-architecture/
    ├── routing-runtime/
    ├── testing-evaluation/
    ├── decision-frameworks/
    ├── prompting-optimization/
    ├── user-interaction/
    ├── failure-analysis/
    ├── domain-patterns/
    ├── cognitive-skills/
    └── metrics-evolution/
```

---

## Skills Summary

| Suite | Skills | Status |
|-------|--------|--------|
| Marketing | 6 | ✅ Complete |
| UI/UX | 6 | ✅ Complete |
| SkillForge Builder | 1 | ✅ Internal |
| **Total** | **13** | |

### Each Skill Contains

- `SKILL.md` — Main cognitive architecture
- `README.md` — Public description
- `tests/` — Test cases for evaluation
- `examples/` — Usage examples (where applicable)
- `references/` — Supporting materials (where applicable)
- `templates/` — Output templates (where applicable)

---

## Research Documentation

The `/research` directory contains 42 foundational research documents that inform SkillForge's cognitive architecture. Documents marked with `_perplexity` or `_pplx` were synthesized via Perplexity AI; those with `_claude` were developed with Claude.

### 1. Skills Architecture & Design (8 documents)

Core architectural patterns for building token-efficient skill systems.

| File | Description | Size |
|------|-------------|------|
| `skills_system_architecture.md` | Two-stage retrieval architecture with metadata-only loading for 50-100 skill registries | 47KB |
| `skills_system_research.md` | Research synthesis on skill system patterns from ChatGPT, Claude MCP, and RAG systems | 21KB |
| `skills_system_guide_perplexity.md` | Comprehensive guide to skill system implementation patterns | 46KB |
| `skill_system_design-perplexity.md` | Design patterns for modular, composable cognitive skills | 41KB |
| `skills-system-design-research.md` | Research on skill decomposition and lazy loading strategies | 23KB |
| `composable_skills_research.md` | Patterns for skill composition, chaining, and orchestration | 29KB |
| `skills_composition_design-perplexity.md` | Architecture for combining skills into coherent workflows | 42KB |
| `PromptStudio-Skills-Marketplace-Strategy_perplexity.md` | Market analysis and competitive positioning for skills marketplace | 44KB |

### 2. Skill Routing & Runtime (6 documents)

Intelligent routing, model selection, and runtime execution patterns.

| File | Description | Size |
|------|-------------|------|
| `skills_routing_architecture_research_claude.md` | Semantic routing architecture for skill selection | 38KB |
| `promptstudio-routing-perplexity.md` | Router design patterns and intent classification | 46KB |
| `skill-runtime-engine-architecture.md` | Runtime engine design for skill execution and state management | 63KB |
| `skill-runtime-engine-perplexity.md` | Execution patterns, error handling, and recovery strategies | 60KB |
| `gemma-ft-skill-routing-perplexity.md` | Fine-tuning Gemma models for skill routing classification | 47KB |
| `fine_tuning_gemma_research.md` | Technical guide for Gemma fine-tuning on routing tasks | 24KB |

### 3. Testing & Evaluation (2 documents)

Quality assurance, evaluation frameworks, and LLM-as-judge methodologies.

| File | Description | Size |
|------|-------------|------|
| `skill_testing_evaluation_research.md` | Comprehensive testing framework with promptfoo integration | 86KB |
| `skills_system_testing_perplexity.md` | Evaluation rubrics and quality thresholds for skill validation | 25KB |

### 4. Decision Frameworks (6 documents)

Cognitive architectures for AI decision-making based on expert exemplars.

| File | Description | Size |
|------|-------------|------|
| `consolidated_research_exemplar.md` | 7 core principles from Musk, Bezos, Dalio, Toyota — the definitive synthesis | 42KB |
| `decision_making_frameworks.md` | Comprehensive decision framework taxonomy | 43KB |
| `decision_frameworks_perplexity.md` | Research on reversibility, decomposition, and explicit reasoning | 16KB |
| `decision_frameworks_analysis.md` | Analysis of decision patterns across domains | 36KB |
| `ai_decision_engine_perplexity.md` | Architecture for AI decision engines with confidence calibration | 46KB |
| `unified_decision_engine_v2.md` | Unified decision engine integrating multiple frameworks | 44KB |

### 5. Prompting & Model Optimization (4 documents)

Strategies for effective prompting and model capability optimization.

| File | Description | Size |
|------|-------------|------|
| `AI_Prompting_Strategies_Taxonomy.md` | Comprehensive taxonomy of prompting techniques | 23KB |
| `prompting_taxonomy.md` | Categorization of prompting strategies by use case | 41KB |
| `AI_Model_Capabilities_and_Optimization_Guide.md` | Guide to model capabilities and optimization patterns | 18KB |
| `ai-model-guide_pplx.md` | Model selection and capability matching strategies | 28KB |

### 6. User Interaction & UX (4 documents)

Human factors, user archetypes, and conversational design patterns.

| File | Description | Size |
|------|-------------|------|
| `user_ai_interaction_research.md` | Research synthesis on novice-expert continuum and cognitive styles | 29KB |
| `user-archetypes-perplexity.md` | User archetype definitions and adaptive interaction strategies | 43KB |
| `conversational_ux_patterns.md` | Conversational UX patterns for natural AI interaction | 24KB |
| `conversational_ux_interaction_patterns.md` | Interaction patterns including progressive disclosure and smart defaults | 23KB |

### 7. Failure Analysis & Outlier Handling (4 documents)

Error detection, failure modes, and edge case handling.

| File | Description | Size |
|------|-------------|------|
| `AI_Failure_Analysis_Perplexity.md` | Taxonomy of AI failure modes and detection strategies | 53KB |
| `ai_interaction_failure_analysis.md` | Analysis of failure patterns in human-AI interaction | 20KB |
| `outlier-handling-research.md` | Comprehensive research on detecting and handling outlier inputs | 81KB |
| `outlier-handling-perplexity.md` | Strategies for graceful degradation and edge case management | 78KB |

### 8. Domain-Specific Patterns (2 documents)

Specialized patterns for different professional domains.

| File | Description | Size |
|------|-------------|------|
| `Domain-Specific-Patterns-Perplexity.md` | Domain patterns for development, marketing, finance, legal | 25KB |
| `domain_specific_patterns_research.md` | Research on domain adaptation and vertical skill specialization | 24KB |

### 9. Cognitive & Meta-Skills (2 documents)

Expert cognitive patterns and meta-skill architectures.

| File | Description | Size |
|------|-------------|------|
| `expert_cognitive_skills_research_perplexity.md` | Research on expert cognition and deliberate practice patterns | 53KB |
| `cognitive-meta-skills-research_claude.md` | Meta-cognitive skills for reasoning, planning, and self-correction | 43KB |

### 10. Metrics & System Evolution (4 documents)

Success measurement, learning systems, and evolutionary architectures.

| File | Description | Size |
|------|-------------|------|
| `success-metrics-measurement-framework.md` | Framework for measuring skill effectiveness and user outcomes | 22KB |
| `success-metrics-measurement_perplexity.md` | KPIs and measurement strategies for cognitive skills | 40KB |
| `system-learning-evolution-research.md` | Research on self-improving skill systems | 182KB |
| `evolution_architecture_perplexity.md` | Architecture for skill evolution and continuous improvement | 63KB |

---

## Research Summary Statistics

| Category | Documents | Total Size |
|----------|-----------|------------|
| Skills Architecture & Design | 8 | 293KB |
| Skill Routing & Runtime | 6 | 278KB |
| Testing & Evaluation | 2 | 111KB |
| Decision Frameworks | 6 | 227KB |
| Prompting & Model Optimization | 4 | 110KB |
| User Interaction & UX | 4 | 119KB |
| Failure Analysis & Outlier Handling | 4 | 232KB |
| Domain-Specific Patterns | 2 | 49KB |
| Cognitive & Meta-Skills | 2 | 96KB |
| Metrics & System Evolution | 4 | 307KB |
| **Total** | **42** | **~1.8MB** |

---

## Key Research Themes

### Four Concerns Architecture

All skills follow the cognitive architecture organizing content by:
- **Context** — What the AI needs to know
- **Patterns** — What the AI should do  
- **Guardrails** — What the AI should avoid
- **Interactions** — How to guide users

### Skills-in-Action Principle

The platform embodies a "generate first, ask second" philosophy—handling vague requests by immediately producing output using smart defaults rather than interrogating users with questions.

### Cross-Platform Optimization

Research addresses critical platform constraints:
- **Claude**: Up to 200KB per skill, 20-skill upload limit
- **ChatGPT/Gemini**: Constrained to ~8,000 characters
- **Solution**: Slot-efficient mega-skills for Claude; compressed versions for other platforms

---

## Usage

### For Skill Development

1. Review relevant research documents before building new skills
2. Apply the Four Concerns architecture to all cognitive frameworks
3. Test against evaluation frameworks in `skill_testing_evaluation_research.md`

### For Platform Integration

1. Consult `skills_system_architecture.md` for lazy loading patterns
2. Use routing research for intent classification
3. Apply failure analysis for robust error handling

---

*Last updated: January 2026*
