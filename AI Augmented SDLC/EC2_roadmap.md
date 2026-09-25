# EC2 Exam Roadmap: AI-Augmented SDLC (SE ZG534)

As of 25 Sep 2026 · Sources: lecture decks CS1–CS7, class transcripts CS1–CS8, Sample Questions sheet, course handout (v1, 01/07/2026)

---

## 1. Overview

EC2 covers **Contact Sessions 1–7 only**. That means **Module 1 (Foundations & Paradigm Shift)** and **Module 2 (Fundamentals of AI & Prompt Engineering)**. Session 8 (spec-driven development and requirements) is **excluded** and moves to EC3.

| Item | Detail |
| --- | --- |
| Component | EC2 – Mid-Semester Test |
| Type | Closed book, no materials |
| Weight / duration | 30% · 2 hours |
| Syllabus (handout) | Contact Sessions 1–8 |
| Syllabus (faculty, said in CS7 and CS8) | CS1–CS7 only, i.e. Modules 1 and 2. Applies to regular and make-up exams |
| Paper format (CS8) | 5–6 questions of about 5 marks each. Each question is one scenario with 2 sub-parts, marks split equally. No MCQs, no 1-mark questions, no choice |
| Question style | Scenario-based and applied. "No remembering or recall kind of questions." You justify what fits and why |
| Answer style | Short, crisp points that answer only the sub-parts asked. "Not evaluated on number of lines" |

**How to use this roadmap:**
- Section 3 has the key points for each session.
- Section 4 lists the topics the faculty stressed most.
- Section 6 has scenario practice and answer outlines.

---

## 2. Syllabus coverage map

Classes ran slower than the handout plan. CS1–CS7 covered only the content the handout planned for CS1–CS4 (Modules 1–2). Modules 3–4 are not in EC2.

| Session | Actual lecture topics | Handout module / planned session |
| --- | --- | --- |
| CS1 | Course intro. State of AI adoption (PwC, Stack Overflow 2025, METR study, Anthropic Economic Index). Capability vs productivity gap. 40/60 split. SDLC phases and roles | M1 · CS1 |
| CS2 | SDLC evolution: Waterfall, V-model, Iterative/Incremental, Agile, DevOps, AI-native. Comparison table. Drivers of evolution. AI impact per phase. Technical debt. Deployment vs release | M1 · CS1 |
| CS3 | Five major shifts. Rethinking SE. Inversion of engineering value. New core competencies. Four transition dimensions. Economics shifts. Risk catalogue | M1 · CS2 |
| CS4 | AI capabilities. ML types. Symbolic vs neural AI. Evolution of AI. LLMs, masked vs autoregressive models. Foundation models. Transformers. Reasoning models. System 1/2 thinking and S2A | M2 · CS3 |
| CS5 | Tokenization: why tokens, techniques, BPE, how models see code, code-aware tokenizers. System interventions. Context window and token limit. Failure modes. Tokenomics | M2 · CS4 |
| CS6 | AI agents and agent types. Single vs multi-agent. Harness engineering. Harness layers. Guides vs sensors. Computational vs inferential controls. Harness across the SDLC. Context engineering steps | M2 · CS3 + CS4 |
| CS7 | Context engineering. Prompt engineering. RAG. Maturity phases (prompt, context, harness, loop, graph). Spec/harness/loop layers. Three gates of autonomy. Prompting vs fine-tuning. AI vs ML engineering. MCP. AI stack. AI-enabled systems | M2 · CS4 |
| CS8 *(not in EC2)* | Traditional to AI-native SDLC. Review becomes the bottleneck. Translation loss. Spec-driven development (constitution, specify, clarify, plan). Skills vs hooks. Assignment briefing | M3 · moved to EC3 |

---

## 3. Key points by topic

### Module 1: Foundations and paradigm shift

#### CS1 · State of AI adoption

- **AI is an amplifier, not a replacement.** ROI only appears when strong engineering foundations exist: code standards, quality gates, platform engineering and clear workflows. Without them, "AI is not going to do any magic."
- **Four realities (PwC report):**
    1. **AI work is surging.** Python overtook JavaScript on GitHub. The three drivers are velocity, an AI-literate developer base, and a stack drift from CRUD apps to ML and agentic apps.
    2. **AI tools are mainstream but not trusted for high-risk steps.** 84% use or plan to use them and 51% use them daily. But teams avoid AI for high-risk SDLC steps: 76% resist it for deployment and monitoring, and 69% for project planning. The cause is a governance and trust gap.
    3. **Speed gains are not guaranteed.** In the METR study, 16 experienced maintainers were **19% slower** with early-2025 AI tools. Prompt iteration, verification and fixing add overhead.
    4. **AI is being embedded in products.** 80% of companies permit third-party AI tools. This adds non-determinism, so the SDLC must include the model lifecycle, observability and runtime evaluation loops.
- **Anthropic Economic Index.** 36% of software roles use AI for at least 25% of their tasks, and 4% use it across most of their work. 57% of usage is augmentative, which is why the course is called "AI-Augmented".
- **Capability vs productivity gap.** Model capability is exploding but deployed productivity gains are small. The faculty's metaphor is a fast car in a traffic jam: flaky tests, legacy docs and manual review block the value.
- **40/60 split.** About 40% of a developer's time goes to core feature work. The other 60% goes to:
    - learning and searching docs
    - context switching
    - waiting for pipelines and PR reviews
    - coordination friction
    - building a mental model of the architecture

  AI coding tools speed up only the 40%.
- **SDLC phases and roles:** Planning (PM), Requirements (BA/PO), Design (Architect), Implementation (Devs), Testing (QA), Deployment (DevOps/SRE), Maintenance (SRE/Ops).

#### CS2 · Evolution of SDLC models

| Era | Paradigm | Cycle | Bottleneck | AI impact |
| --- | --- | --- | --- | --- |
| Waterfall (1970s–90s), V-model (1980) | Sequential and document-heavy. The V-model pairs each dev stage with a test phase | Months to years | Rigid handoffs, no early feedback | AI turns spec docs into code and tests |
| Iterative (1975), Incremental (1978), Agile/Scrum (2000s–10s) | Iterative, driven by customer feedback | Weeks (sprints) | Communication overhead, context switching, manual story writing | AI writes user stories, estimates velocity, drafts PRs |
| DevOps & CI/CD (2010s–20s) | Automation, CI/CD, infrastructure as code | Days to hours | Ops handoffs, manual testing, deployment risk | AI diagnoses pipeline failures, auto-remediates, predicts risk |
| AI-native / agentic (2020s+) | Autonomous agents, intent-driven | Real-time | **Human verification, architectural governance, hallucination** | The human moves from **author/builder to orchestrator/reviewer** |

- **Drivers of SDLC evolution:** faster time to market, customer feedback, lower risk and cost, productivity, quality and security, zero-downtime updates, automation, skill shortage, fast-moving technology.
- **AI impact per phase:**
    - Coding: copilots grow into autonomous agents that edit many files at once.
    - Testing: **self-healing test suites** and edge-case generation.
    - Review: semantic AI reviewers flag OWASP issues before a human sees the code.
    - Operations: **AIOps** correlates logs with PRs, then auto-fixes or rolls back.
- **Technical debt** is a shortcut or skipped best practice taken for speed. Examples: skipping a test suite, hard-coded config or passwords, API URLs outside a config file. It is not the same as refactoring.
- **Pain points by model:**
    - Waterfall: long requirement phases.
    - Agile: communication and documentation across large teams.
    - DevOps: solved environment parity through infrastructure as code.
- **Deployment vs release.** Deployment puts code into an environment (blue-green, A/B). Release makes it available to users after sign-off and versioning.

#### CS3 · The five major shifts

| Shift | Old world | New world |
| --- | --- | --- |
| 1. Dev effort is no longer the bottleneck | Effort was scarce, so teams cut MVP scope and prioritised hard | **Parallel exploratory prototypes.** Design docs become **machine specifications**, so precision of intent beats implementation speed. Docs written for AI must state the small best practices humans left implicit, such as a central API config |
| 2. Roles are less siloed | PM writes the PRD, Dev codes, QA tests, SRE deploys | PM/Dev and Dev/QA/SRE roles blur. The handoff is an **executable prototype**, not a document. Problem-solving matters more than syntax. Skill shelf-life is short |
| 3. Decisions are less "hard to change" | Architecture decisions are one-way doors | **Disposable microservices.** Regeneration is cheap and code is a disposable commodity. The risk is that nobody refactors |
| 4. Accountability is foggier | "You built it, you run it" | Supply-chain attacks and compliance audits. **"We can never say AI wrote it."** You need checkpoints (SonarQube, pen tests, PMD). Compliance needs evidence, not intent. Faculty metaphor: airport security checkpoints |
| 5. Outcomes are probabilistic | Engineers programmed certainty | Engineers now engineer **confidence**: validators, rate limiters, permission systems, classifiers, evals, guardrails. **Prompts alone are not the architecture** |

- **Inversion of engineering value** (arXiv 2604.10599):
    - The primary artefact moves from scarcity to abundance.
    - The role moves from **authorship to orchestration**.
    - The bottleneck moves from **writing to verification**.
    - Accountability stays human.
    - The faculty calls this an **elevation of the profession, not its elimination**.
- **New core competencies:** intent articulation and architectural control, systematic verification and QA, multi-agent orchestration, human judgment and accountability.
- **Four transition dimensions:**
    - Education: from syntax mastery to systems curation.
    - Tooling: orchestration and verification infrastructure.
    - Process: verification-first and human-in-the-loop.
    - Professional practice: new roles, metrics and governance.
- **Economics shifts:**
    - **Build vs buy** is replaced by **inference cost + human verification cost vs full human execution cost** (tokens vs human labour).
    - **Task–model mismatch.** A high-tier reasoning model on a simple UI wastes money. An underpowered model wastes developer time fixing hallucinations.
    - Fixed CAPEX becomes dynamic OPEX, so every query has a running cost.
    - Seat-based pricing gives way to outcome-based or usage-based pricing.
    - **80/20 cost inversion.** Generating the first 80% of a feature is cheap. The last 20% (edge cases, zero hallucination, compliance) eats most of the budget, which shifts to verification and security audit.
- **Risk catalogue:**
    - **Code quality and security:** plausible but insecure code, **hallucinated packages and supply-chain attacks**, missing edge cases in tests, **architectural drift and code slop**, code bloat, **context blindness** (the model sees one function or file at a time).
    - **Human factors:** **reviewer fatigue** (the "rubber stamper") and atrophy of fundamental skills.
    - **Legal, IP and compliance** exposure.
    - **Economic and operational:** vendor lock-in, the review bottleneck, token explosion ("token maxing").

### Module 2: Fundamentals of AI and prompt engineering

#### CS4 · AI fundamentals and LLMs

- **Four capabilities of AI:** learning, reasoning, perception, and problem-solving/action.
- **ML types:**
    - Supervised: learns from labelled data (e.g. spam filters).
    - Unsupervised: finds clusters and associations (e.g. Amazon recommendations).
    - Reinforcement: learns from rewards and penalties.
    - Deep learning: neural networks with forward and backpropagation. The slides class it under unsupervised.
- **Rule-based / symbolic AI vs ML.** All ML is AI, but not all AI is ML. Only ML improves its own performance over time.
- **Symbolic vs neural AI:**
    - Symbolic is transparent, explainable, deterministic and gives guaranteed deductions. It is brittle with edge cases and ambiguity.
    - Neural handles ambiguity but hallucinates.
    - Use rigid rules where a step must never be skipped.
- **How AI reasons:** symbolic/knowledge-graph logic, probabilistic (Bayesian) inference, and **chain-of-thought**.
- **How AI problem-solves:** search (A*, MCTS), agentic planning (plan, execute, check, re-plan), and constraint satisfaction.
- **Evolution of AI:** symbolic systems, then traditional ML (1990s–2010s), then deep learning and foundation LLMs (2017–23), then **reasoning models** (2024 onward).
- **Language models:**
    - A language model is a statistical model of the next token.
    - "Large" means a large number of parameters.
    - The key enabler is **self-supervision**, which removes the need for labelled data.
    - **Masked LMs** (e.g. BERT) fill in a blank using context on both sides. Good for classification, sentiment and debugging.
    - **Autoregressive LMs** predict the next token. Good for generation.
- **Foundation model:** a general-purpose, multimodal model trained with self-supervision. LLMs are text-only.
- **Transformer (2017):** the architecture behind LLMs, built on **self-attention**.
- **Reasoning models** produce hidden reasoning traces and spend extra compute at inference time.
    - **System 1** thinking is fast and intuitive. **System 2** is slow and deliberate.
    - **S2A (System 2 Attention)** rewrites the prompt to remove irrelevant information before answering.
- **Bug-fix use case (three approaches compared):**
    - Traditional ML only locates the likely buggy file.
    - A standard LLM writes a plausible one-pass patch that may break something.
    - A reasoning model traces the call stack, forms hypotheses, rules them out, then checks dependencies.

#### CS5 · Tokenization, context window, cost

- **Rule of thumb:** 1 token ≈ 4 characters ≈ 0.75 words, so 100 tokens ≈ 75 words.
- **Why tokens instead of words or characters:**
    - They split words into meaningful parts (cook + ing).
    - The vocabulary is smaller, so the model is more efficient.
    - They handle unknown words like "Googling".
- **Tokenization techniques:**
    - **Word:** out-of-vocabulary problems and huge lookup tables.
    - **Character:** good for Chinese and Japanese, but long words explode into many tokens.
    - **Subword (BPE, SentencePiece):** iteratively merges the most frequent adjacent pairs. Used by most modern LLMs.
    - **Morphological:** suited to highly inflected languages such as Hindi and German.
- **How models see code:**
    - Custom identifiers split into many tokens (e.g. `getUserPaymentHistory`, `user_ENV`).
    - Cryptic names cost more tokens.
    - Whitespace and indentation bloat the token count.
    - Minified code is hard to read.
    - URLs get split, and brackets don't pair neatly with neighbouring text.
    - **Code-aware tokenizers** use character offsets and AST-guided pre-training. In the slide example, the same snippet took about 19 tokens on an old tokenizer and about 10 on a new one.
- **System-level interventions:**
    - **Code interpreter:** delegate deterministic work to code that runs in a sandbox.
    - **Constrained decoding:** set the probability of invalid-syntax tokens to 0.
    - The lesson: prefer well-tested deterministic methods over letting the model guess.
- **Context window vs token limit:**
    - The **context window** is the model's working memory. It holds the system prompt, conversation history, current prompt and files, and the response being generated.
    - The **token limit** is the hard cap per inference call.
    - Typical sizes: Gemini 1–2M tokens, Claude 200K–1M.
- **Why token limits matter:**
    - **Cost:** billing is per token.
    - **Latency.**
    - **Accuracy:** "lost in the middle". Models are most accurate at the start and end of a long context.
- **Four failure modes:**
    1. Silent degradation.
    2. Attention dilution ("lost in the middle").
    3. Inconsistent behaviour.
    4. **Cascading failures**, e.g. an agent skips validation or leaves out files to save context.

  Mitigation: break tasks into smaller pieces and work file by file. *"Don't build agents without tracking token consumption."*
- **Tokenomics:** opaque billing, hidden costs, ROI that is hard to calculate, inefficient model routing.

#### CS6 · Agents and harness engineering

- **AI agent:** perceives its environment and acts on it with tools. Example: SWE-agent, whose environment is the terminal and file system. A chatbot only returns text, while an agent acts with **autonomy inside set boundaries**.
- **Agent types:**

  | Type | How it decides | Example |
    | --- | --- | --- |
  | Simple reflex | If/then rules on the current input | Thermostat |
  | Model-based reflex | Current input plus an internal model of the world | Braking on a wet road |
  | Goal-based | Plans towards a target state | GPS navigation |
  | Utility-based | Scores trade-offs | Ride-share dispatcher |
  | Learning | Improves from feedback | Netflix recommendations |

- **Claude Code and Copilot** are primarily utility-based, and also goal-based.
- **Single vs multi-agent:** a single-task autonomous agent does one job. A **multi-agent network** can be linear, parallel-converging, or hierarchical with a controller agent. Example: AWS Kiro, with coder, reviewer and tester agents.
- **Agent = Model + Harness.** The model provides the intelligence. The harness provides tools, state, execution, context, permissions and validation. Vibe-coding incidents (e.g. a production database wiped) are why harnesses are needed.
- **A production-ready harness needs:**
    - Guardrails: HITL approval gates, budget ceilings, hard boundary limits.
    - Tool orchestration.
    - Context and memory.
    - Execution shells.
    - Audit logs and observability.
- **Harness layers:**
    - **Coding harness:** built by the agent or SDK maker (tools, system prompt, sub-agents).
    - **User harness:** built by your team (CLAUDE.md, MCP servers, eval loops, skills). FinTech example: a compliance linter runs on every payment PR, and agents are never allowed to touch database migrations.
    - **Team/org/SDLC harness:** built by the platform team (context lake, agent registry, permissions, governance, HITL, measurement).
- **Guides vs sensors:**
    - **Guides (feedforward)** steer the agent before it acts: system prompts, specs, AGENTS.md.
    - **Sensors (feedback)** let it self-correct after it acts: linters, tests.
- **Computational vs inferential controls:**
    - **Computational:** deterministic, CPU-based, fast (type checkers, linters, ArchUnit).
    - **Inferential:** semantic, probabilistic, GPU-based (LLM-as-judge, AI review).
    - Prefer the deterministic one when it exists.

  | Control | Direction | Engine | Example |
    | --- | --- | --- | --- |
  | Coding conventions | Feedforward | Inferential | AGENTS.md, skills |
  | Bootstrap instructions | Feedforward | **Both** | Skill plus a bootstrap script |
  | Codemods | Feedforward | Computational | OpenRewrite recipes |
  | Structural tests | Feedback | Computational | ArchUnit pre-commit hook |
  | Review instructions | Feedback | Inferential | Skills |

- **Harness rules to remember:**
    - **More autonomy plus more irreversible actions means more harness.**
    - When a problem repeats, improve the guides so it can't recur, don't just fix it.
    - Revisit the harness whenever the agent's scope grows.
- **Harness across the SDLC:** Plan uses context management. Build uses tools and guardrails. Review uses sensors. Deploy uses **approval gates**.

#### CS7 · Context engineering, prompting, RAG, layers

- **Context engineering** means filling the context window with just the right information at each step.
    - Karpathy's analogy: the LLM is the CPU and the context window is the RAM.
    - LLMs have **no long-term memory**, so a badly managed context leads to hallucination.
    - **Steps:** selection, structuring, prompt design, compression, **sequencing** (most relevant first), and tool and memory integration.
    - Knowing databases and data formats (SQL, NoSQL, vector, graph, JSON) is a core skill here.
- **Prompt engineering is a narrower subset of context engineering.**
    - **Zero-shot:** no examples. Fine for summarisation and translation.
    - **One-shot / few-shot:** give example input-output pairs.
    - **Chain-of-thought:** reason step by step.
    - **Zero-shot CoT:** combines the two.
    - *"Prompt engineering has a limitation. Go beyond it to context and harness."*
- **System prompt vs user prompt.** The developer's system prompt **overrides** the user prompt. Example: a user can't make a library assistant break its policy.
- **RAG (retrieval-augmented generation):**
    1. Ingestion: chunk documents, embed them, store them in a vector DB.
    2. Retrieval: find chunks by semantic or cosine similarity.
    3. Augmentation: add the top chunks to the prompt.
    4. Generation: the LLM writes the answer.

  Variants include agentic, conversational and graph RAG. **RAG sits outside the model. It is not training, fine-tuning or transfer learning.**
- **Prompting vs fine-tuning.** Prompting changes no weights. Fine-tuning updates the weights. This course treats the model as a **black box**.
- **Prompt vs context vs harness:**

  | | Prompt | Context | Harness |
    | --- | --- | --- | --- |
  | What it is | The task | Reference material | Testing machinery |
  | Audience | The LLM | The LLM | The AI engineer |
  | Where it lives | User input or app logic | System instructions or vector DB | CI/CD pipeline or test suite |
  | Goal | Get the right answer now | Prevent hallucination | Prove the system works at scale |

- **Maturity phases:**
    1. **Prompt engineering** (2022–23): the words you send.
    2. **Context engineering** (2024–25): everything the model sees.
    3. **Harness engineering** (2026): the code around the model that runs tools, tracks state and handles errors.
    4. **Loop engineering:** the agent runs act → test → fix until the goal is met.
    5. **Graph engineering:** coordinates many loops. Nodes (LLM, function, router, verifier, human approval) are joined by edges and share state.
- **Three-layer operating model:**
    - **Spec layer:** human-authored intent and constraints.
    - **Harness layer:** mechanised validation.
    - **Loop layer:** the agent runs until the result converges.
- **Three gates of autonomy:**
    - **Human-in-the-loop:** a human reviews every agent PR or action. Suits high-risk domains.
    - **Human-on-the-loop:** the agent runs and merges on its own. Humans watch dashboards and are alerted when a threshold is breached, e.g. accuracy drops below 99.99%.
    - **Autonomous:** the agent runs within bounded constraints. Suits routine, well-harnessed tasks.
    - Some systems may never reach the autonomous gate.
- **AI engineering vs ML engineering.** ML engineering starts with data and a model, and the product comes last. AI engineering starts with the product on an existing model, and invests in data and models only once the product shows promise.
- **AI stack:** three layers — application development, model development, infrastructure.
- **MCP (Model Context Protocol):** an open standard, "USB-C for AI". A host runs **MCP clients**, and each client connects to an **MCP server**. Messages use JSON-RPC 2.0 over **stdio** (local) or **SSE** (remote). The flow is: discover tools → invoke → server acts → results return → final response.
- **AI-enabled systems (CMU SEI).** They are data-centric and probabilistic. New quality attributes are **explainability, data centricity, verifiability and change propagation**. "Invest in systems, not just models."

---

## 4. Topics the faculty stressed

The two sample questions come straight from the CS1 and CS3 material. Expect the real questions to be built the same way.

| Priority | Topic | What the faculty said | Session |
| --- | --- | --- | --- |
| Very high | **Inversion of engineering value** | "Verification is the new bottleneck." "Elevation of the profession, not elimination." Basis of Sample Q1 | CS3 |
| Very high | **Capability vs productivity, 40/60 split, local optimisation** | The traffic-jam metaphor. AI is an amplifier that needs good foundations first. Basis of Sample Q2 | CS1, CS8 recap |
| Very high | **The five shifts**: disposable microservices, docs as machine specs | "Precision of intent is more valuable than speed of implementation." The hard-coded API URL anecdote | CS2 end, CS3 |
| Very high | **Risks**: code slop, architectural drift, context blindness, hallucinated packages, reviewer fatigue | Asked the class how to stop hallucinated packages. Answer: security constraints in the spec or context, plus automated security testing | CS3 |
| High | **Economics**: inference + verification vs human cost, task–model mismatch, CAPEX→OPEX, 80/20 inversion, per-seat → outcome pricing | "Cost is something we have to discuss in detail." Unlike normal software, AI has a running token cost | CS3, CS8 recap |
| High | **Accountability** | "We can never say AI wrote it." Compliance needs evidence. The airport-checkpoint metaphor | CS3 |
| High | **Probabilistic outcomes** | Engineers now engineer confidence, not certainty. "Prompts alone are not the architecture" | CS3 |
| High | **Symbolic vs neural AI; ML vs AI** | "Very important point: only ML optimises over time" | CS4 |
| High | **Reasoning models, CoT, System 1/2** | "Reasoning is very important, we will revisit." The bug-fix comparison | CS4, CS5 |
| High | **Tokenization and code** | Class exercise comparing tokenizers. Why tokens, BPE, identifier splitting | CS5 |
| High | **System interventions** (code interpreter, constrained decoding) | "Very important lesson: if deterministic ways exist, use them" | CS5 |
| High | **Context window failure modes** | Lost in the middle. Cascading failures when an agent skips validation. "Track token consumption" | CS5 |
| Very high | **Agent = Model + Harness**: harness layers, guides vs sensors, computational vs inferential | The Martin Fowler article is "very important". Quizzed the class on why bootstrapping is both computational and inferential. "More autonomy means more harness" | CS6 |
| High | **Context vs prompt engineering vs RAG** | "Prompt engineering has a limitation." RAG is outside the model. The model is a black box | CS7 |
| Very high | **Three gates of autonomy** | Worked examples of each. The level depends on risk | CS7 |
| Medium | **System vs user prompt; zero-shot, few-shot, CoT** | The library-assistant example | CS7 |
| Medium | **MCP, AI vs ML engineering, quality attributes of AI-enabled systems** | Covered at the end of CS7, so still in the syllabus | CS7 |
| Medium | **SDLC evolution, technical debt, deployment vs release** | Banking examples. Faculty stressed that technical debt is not refactoring | CS2 |

**Faculty's own syllabus recap (CS8):**
- Module 1: what is changing, which changes are accepted, and which are not. Coding is accepted; requirements, deployment and monitoring much less so.
- Adopting AI in only one phase creates risk, because review is still manual.
- Tokens mean a running cost.
- Module 2: what AI is — learning types, LLMs, tokenization, reasoning models, agent types, and the prompt → context → harness progression.
- Loop and graph engineering are "still in the open phase".
- Her advice: "The concept itself is less… I cannot say this is important or that is important."

---

## 5. Handout vs lectures

All 11 Module 1–2 sub-topics in the handout were taught. Two of them were covered only lightly.

| Handout sub-topic | Status | Where / note |
| --- | --- | --- |
| M1 · Evolution of SDLC models | Covered | CS2 |
| M1 · AI-augmented lifecycle phases | Covered | CS1, CS2 |
| M1 · AI-driven change velocity | Covered | CS1 |
| M1 · Risk amplification (tech debt, hallucination, drift, automated errors) | Covered | CS3, CS2 |
| M1 · Cost and economics | Covered lightly | CS3 (faculty said "minimal and superficial"), plus CS5 tokenomics |
| M2 · Foundation models and types | Covered | CS4 |
| M2 · Transformer architecture | Covered lightly | CS4, self-attention only |
| M2 · Tokenization and its impact | Covered in depth | CS5 |
| M2 · Context windows | Covered in depth | CS5, CS7 |
| M2 · Managing non-deterministic outputs | Covered | CS3, CS5, CS6 |
| M2 · Prompting strategies | Covered | CS7 |
| M2 · Introduction to agentic workflows | Covered | CS4, CS6, CS7 |
| M3 · Requirements, spec-driven development, ADRs, threat modelling | Not in EC2 | Moved to EC3 |
| M4 · Coding and refactoring | Not in EC2 | Moved to EC3 |

**Taught in class but not named in the handout.** These are still examinable because they were in CS1–CS7:
- harness engineering, guides and sensors, computational vs inferential controls
- context engineering and the RAG pipeline
- loop and graph engineering, the spec/harness/loop layers
- the three gates of autonomy
- MCP, AI vs ML engineering
- System 1/2 thinking and S2A
- agent types
- inversion of engineering value

**Syllabus conflict.** The handout says the mid-sem covers "Contact sessions 1 to 8". The faculty narrowed this over the term:
- In CS6 she said Modules 1–3.
- In CS7 and again in CS8 she said **CS1–CS7 only**, for both regular and make-up exams.

Follow the latest statement.

---

## 6. Study plan and practice

### Five-day plan

| Day | Focus | Output |
| --- | --- | --- |
| 1 | CS1–CS2: adoption realities, 40/60 split, capability vs productivity, SDLC evolution table, technical debt | Draw the evolution table from memory |
| 2 | CS3: the five shifts with their examples, inversion of value, economics, risk catalogue | For each shift, write one scenario and one risk |
| 3 | CS4–CS5: AI types, symbolic vs neural, LLM vs foundation vs reasoning models, tokenization, context window failures, interventions | Explain each concept in 3 bullets |
| 4 | CS6–CS7: agents, harness layers, guides/sensors, computational/inferential, context and prompts, RAG, autonomy gates, MCP | Classify 10 controls as feedforward/feedback and computational/inferential |
| 5 | Timed practice: 5 scenarios × 2 sub-parts in 2 hours | Crisp point-form answers |

### Answer frame (about 2.5 marks per sub-part)
1. Name the concept in one line.
2. Apply it to the scenario in 2–3 points.
3. Justify, or give a mitigation, in 1–2 points.
4. Answer only what the sub-part asks.

### Sample Q1 outline: "Disposable microservices" (regenerate the service instead of refactoring or writing unit tests)
- **(a) Evaluate against the inversion of engineering value.**
    - The strategy is right that authorship is cheap.
    - It is wrong about where value moved. Value moved to verification and orchestration, and dropping tests removes exactly that.
    - Accountability stays human: "we can never say AI wrote it".
    - The spec becomes the primary artefact, so it must be rigorous and precise.
- **(b) Downstream maintainability risks.**
    - Regeneration is non-deterministic, so each run can behave differently: regressions and broken API contracts.
    - Architectural drift and code slop. Context blindness means duplicated helpers and ORM mappings.
    - With no tests there is no sensor to catch changes.
    - Hallucinated dependencies (supply-chain risk).
    - Compliance evidence and audit trail are lost.
    - Reviewer fatigue on full regenerations.
    - **Mitigation:** spec-level contract tests written independently of the generated code, computational gates, HITL review for critical services.

### Sample Q2 outline: 40% more PR throughput, but lead time still 4 weeks
- **(a) Why speed didn't translate.**
    - The 40/60 split: AI sped up only the 40% coding slice.
    - The bottleneck moved to review, QA environments, deployment configuration and meetings, which all still run at human speed.
    - This is the capability vs productivity gap (the traffic-jam metaphor).
    - More PRs can even grow the review queue.
- **(b) From local optimisation to systemic enablers.**
    - Optimise the whole value stream, not coding alone.
    - Automate review, testing and deployment gates.
    - Measure lead time and outcomes, not PR count.
    - Set up governance and HITL checkpoints.
- **(c) Two technical foundations to prioritise.** Any two of:
    - Platform engineering: self-service environments and infrastructure as code.
    - An automated CI/CD pipeline with quality gates and test automation.
    - Harness and guardrails: linters, security scans, approval gates.
    - Also valid: clear specs and documentation as context.

### More scenario types to practise
- Choose the right **autonomy gate** for a banking payment agent vs a docs-formatting agent, and justify it.
- A coding agent drops files or skips validation on a large repo. **Diagnose** it (context limit, lost in the middle, cascading failure) and **fix** it (split the task, RAG, sequencing, token tracking).
- Design a **user harness** for a FinTech team: which guides and which sensors, and which are computational vs inferential.
- **Task–model mismatch:** pick a model tier for a simple UI vs a complex debugging task, and justify it on cost.
- Where does a **symbolic/rule engine** beat an LLM? (Compliance checks, a step that must never be skipped.)
- Why does the LLM miscount characters or split identifiers? Propose **code interpreter or constrained decoding** as the fix.
- Should a support bot use **RAG vs fine-tuning vs prompting**? Should its policy go in the **system prompt**?
- An AI-generated app hard-codes URLs and pulls an unknown npm package. Name the **risks** and the **guardrails**.
- Explain the **MCP** flow for "fetch this report and email it" (host, client, server; stdio vs SSE).

### Final checklist
- [ ] Five shifts, with one example each
- [ ] Inversion of engineering value (old vs new: artefact, role, bottleneck)
- [ ] 40/60 split and capability vs productivity
- [ ] Economics formula, task–model mismatch, 80/20 inversion
- [ ] Risk catalogue (4 groups)
- [ ] SDLC evolution table
- [ ] Symbolic vs neural; ML types; LLM vs foundation vs reasoning models; masked vs autoregressive
- [ ] Why tokens; the 4 techniques; code tokenization issues; interventions
- [ ] Context window vs token limit; 4 failure modes; cost
- [ ] 5 agent types; Agent = Model + Harness; 3 harness layers
- [ ] Guides/sensors × computational/inferential table
- [ ] Context engineering steps; prompt techniques; system vs user prompt; RAG's 4 steps
- [ ] Prompt vs context vs harness table; maturity phases; spec/harness/loop layers
- [ ] HITL / HOTL / autonomous gates
- [ ] MCP architecture; AI vs ML engineering; AI-enabled system quality attributes