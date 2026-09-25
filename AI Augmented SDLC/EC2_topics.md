# AI-Augmented SDLC (SE ZG534): Topics Discussed in Class

Compiled from the lecture slides and class transcripts. Sessions CS1–CS7 are in the EC2 syllabus. CS8 is not; it goes to EC3.

---

## CS1: Introduction *(Module 1)*
- Course, program and evaluation overview: EC1 quiz and assignment, EC2 mid-sem (closed book), EC3 comprehensive exam (open book)
- SDLC phases and the roles responsible for each
- State of AI adoption (PwC report)
    - AI work is surging on GitHub and Python has overtaken JavaScript
    - AI tools are mainstream, but teams avoid them for high-risk SDLC steps (deployment, monitoring, planning)
    - METR study: experienced developers were 19% slower with early AI tools
    - Third-party AI tools and AI-native products are spreading
- Anthropic Economic Index: 36%, 4% and 57% figures; AI augments rather than replaces
- AI capability vs productivity (deployed value) gap: the "fast car in a traffic jam" metaphor
- The 40/60 split: core feature work vs "everything else"
- AI as an amplifier of strong engineering foundations, not a replacement for them
- Traditional SDLC vs AI-driven SDLC; new challenges and constraints

## CS2: Evolution of SDLC Models *(Module 1)*
- Definition and goal of the SDLC
- The models: Waterfall (1970), V-model (1980), Iterative (1975), Incremental (1978), Agile/Scrum, DevOps and CI/CD
- Comparison table of SDLC eras
    - Covers Waterfall, Agile, DevOps and AI-native/agentic
    - Compares paradigm, iteration cycle, bottleneck, output and AI impact
- Is the SDLC still relevant? Choosing a model for a project
- Key factors driving SDLC evolution
- AI impact across SDLC phases
    - Coding: copilots evolving into autonomous agents
    - Testing: self-healing test suites and autonomous edge-case generation
    - Code review: static and semantic AI reviewers
    - Operations: AIOps and autonomous remediation
- Technical debt: what it is (with examples such as hard-coding and skipped tests), and how it differs from refactoring
- Infrastructure as code and environment parity
- Deployment vs release; deployment strategies (blue-green, A/B)
- Intro to the major shifts; AI slop

## CS3: Paradigm Shifts *(Module 1)*
- The five major shifts in software engineering
    1. Dev effort is no longer the bottleneck
        - MVP scope-cutting gives way to parallel prototypes
        - Design docs become machine specifications
    2. Roles are less siloed (PM/Dev and Dev/QA/SRE blur)
    3. Decisions are less "hard to change" (disposable microservices)
    4. Accountability is foggier when AI authors artefacts (supply-chain attacks, compliance)
    5. Outcomes are probabilistic, not guaranteed
- Rethinking software engineering: the enduring value of software engineers
- Inversion of engineering value: authorship becomes orchestration, and writing becomes verification
- The new core competencies of software engineering
- Four dimensions of the transition: education, tooling, processes, professional practice
- Shifts in software economics
    - Zero marginal cost; CAPEX becomes OPEX
    - Build vs buy becomes token cost vs human labour
    - Task–model mismatch
    - Seat-based pricing gives way to outcome- or usage-based pricing
    - The 80/20 cost inversion
- Risks across the SDLC
    - Code quality and security: insecure code, hallucinated packages, missing edge cases, architectural drift, code slop, code bloat, context blindness
    - Human factors: reviewer fatigue, skill atrophy
    - Legal, IP and compliance
    - Economic and operational: vendor lock-in, token explosion

## CS4: Fundamentals of AI *(Module 2)*
- The four core capabilities of AI: learning, reasoning, problem-solving, perception
- Machine learning types: supervised, unsupervised, reinforcement, deep learning
- Rule-based AI vs ML ("all ML is AI, not all AI is ML")
- Narrow/weak AI vs general/strong AI (AGI)
- Symbolic AI vs neural AI
- Approaches to reasoning: symbolic/knowledge graphs, probabilistic inference, chain-of-thought
- Approaches to problem-solving: search (A*, MCTS), agentic planning, constraint satisfaction
- Approaches to perception: computer vision, speech processing, multimodal fusion
- Evolution of AI: symbolic, then traditional ML, then deep learning and LLMs, then reasoning models
- Large language models: statistical language models, self-supervision, parameters
- Masked language models (BERT) vs autoregressive language models
- From LLMs to foundation models (multimodal)
- The transformer architecture and self-attention
- Reasoning models and reasoning traces
- System 1 vs System 2 thinking; System 2 Attention (S2A)
- Use case: bug fixing with traditional ML vs a standard LLM vs a reasoning model
- Intro to tokenization

## CS5: Tokenization and Context Window *(Module 2)*
- Tokens and tokenization; the rule of thumb 1 token ≈ 4 characters ≈ 0.75 words
- Why models use tokens instead of words or characters
- Tokenization techniques: word, character, subword (BPE, SentencePiece), morphological
- Highly inflected vs weakly inflected languages
- How the model "sees" code
    - Identifier splitting
    - Indentation bloat
    - Minified code
    - Split URLs
    - Special characters
- Re-engineered, code-aware tokenizers: positional metadata, syntax-guided (AST) pre-training
- System-level interventions: code interpreters and delegating to tools; structured output and constrained decoding (logits masking)
- Context window: what counts toward it, and context window vs token limit
- Context window sizes of current models
- Why token limits matter: cost, latency, accuracy ("lost in the middle")
- Context limit failures: silent degradation, attention dilution, inconsistent behaviour, cascading failures
- Tokenomics: AI billing, hidden costs, ROI, model routing, the Tokenomics Foundation

## CS6: AI Agents and Harness Engineering *(Module 2)*
- What an AI agent is; agents vs chat-based tools
- Example: SWE-agent (a coding agent working with terminal and file system)
- Types of AI agents: simple reflex, model-based reflex, goal-based, utility-based, learning
- Single-task autonomous agents vs multi-agent networks
    - Multi-agent patterns: linear, parallel, hierarchical/controller
    - Example: AWS Kiro
- Classifying Claude Code and Copilot among the agent types
- Harness engineering: Agent = Model + Harness
- Vibe coding and the failures it has caused
- Components of a production-ready harness
    - Guardrails, including human-in-the-loop gates and budget ceilings
    - Tool orchestration
    - Context and memory
    - Observability
- Harness layers: coding harness, user harness, team/org/SDLC harness
- Feedforward vs feedback controls (guides vs sensors)
- Computational vs inferential controls
- Worked examples
    - Coding conventions
    - Project bootstrap
    - Codemods and ASTs
    - Structural tests with ArchUnit
    - Review instructions
- "More autonomy means more harness"; revisiting the harness when scope changes
- Where harness engineering fits across Plan, Build, Review and Deploy
- Intro to context engineering

## CS7: Context, Prompt and AI Layers *(Module 2)*
- Context engineering: definition, Karpathy's CPU/RAM analogy, why it matters
- Steps of context engineering
    - Selection, structuring, prompt design, compression, sequencing, tool and memory integration
    - Grouped as retrieval, generation, processing and management
- Databases and data formats as a context-engineering skill
- Prompt engineering as a subset of context engineering
- Prompting techniques: zero-shot, one-shot/few-shot, chain-of-thought, zero-shot CoT, the CRISP framework
- System prompt vs user prompt, and which takes priority
- Prompt caching (KV cache)
- Retrieval-augmented generation (RAG): ingestion, retrieval, augmentation, generation; types of RAG
- RAG vs transfer learning vs fine-tuning; treating the model as a black box
- The three phases of AI engineering maturity: prompt, context, harness
- Loop engineering and graph engineering
- The layers of AI in the SDLC
- The three-layer operating model: spec, harness, loop
- The three gates of agent autonomy: human-in-the-loop, human-on-the-loop, autonomous
- Prompt engineering vs fine-tuning
- Prompt vs context vs harness (comparison table)
- AI engineering vs ML engineering
- Model Context Protocol (MCP)
    - Host, client and server
    - JSON-RPC 2.0 over stdio or SSE
    - Worked example of the flow
- The three layers of the AI stack: application, model, infrastructure
- The AI complexity matrix (CMU SEI AI Adoption Maturity Model)
- Engineering AI-enabled systems: data centricity; new quality attributes (explainability, verifiability, change propagation)

## CS8: Traditional to AI-Native SDLC *(Module 3; not in EC2)*
- Exam format briefing for the mid-sem
- The traditional six-phase SDLC and why it is process-heavy
- The bottleneck moving from build to review, testing and governance
- Translation loss at handoffs: stakeholder to requirements to design to implementation to validation
- Spec-driven development (SDD) and how it shifts where teams spend effort
- SDD toolkits and frameworks
    - Workflow: constitution, specify, clarify, plan
    - The PRD excludes technical decisions
- intent.md, skills (advisory) vs hooks (deterministic)
- SDD compared with model-driven, test-driven and behaviour-driven development
- Test cases generated from specs, not from code
- Assignment briefing: an end-to-end AI-augmented SDLC project