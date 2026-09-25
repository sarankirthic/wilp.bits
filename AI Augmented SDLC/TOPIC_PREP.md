# AI-Augmented SDLC — Complete Topic List

> Based on the CS1–CS8 material provided. Each topic has a one-line explanation.

## 1. SDLC Fundamentals and AI Adoption

- **Software Development Life Cycle (SDLC)** — A structured process for planning, building, testing, deploying, and maintaining software.
- **SDLC Phases** — The major stages of software development and the roles responsible for activities within those stages.
- **Traditional SDLC** — Conventional development approaches where work progresses through defined processes and handoffs.
- **AI-Driven SDLC** — An SDLC in which AI tools and agents participate across development activities.
- **AI Adoption in Software Engineering** — The increasing use of AI tools across coding, testing, review, operations, and other SDLC activities.
- **AI Capability vs Productivity Gap** — The difference between what AI tools can technically do and the value actually realised in engineering workflows.
- **AI as an Engineering Amplifier** — AI can amplify strong engineering practices but does not replace sound engineering foundations.
- **40/60 Split** — The observation that feature implementation represents only part of engineering work, with substantial effort spent on other activities.
- **AI in High-Risk SDLC Activities** — Teams may be more cautious about AI use in deployment, monitoring, planning, and other high-risk activities.
- **AI-Augmented Development** — Using AI to assist engineers rather than treating AI as a complete replacement for engineering work.
- **AI Slop** — Low-quality or excessive AI-generated output that creates additional review, maintenance, or quality problems.

## 2. Evolution of SDLC Models

- **Waterfall Model** — A sequential SDLC model associated with defined stages and limited iteration between them.
- **V-Model** — A development model that explicitly pairs development stages with corresponding testing activities.
- **Iterative Development** — Develops software through repeated cycles that refine the system over time.
- **Incremental Development** — Builds the system through successive increments that add functionality.
- **Agile/Scrum** — An iterative development approach based on short cycles, feedback, and adaptive planning.
- **DevOps** — Integrates development and operations practices to enable faster and more continuous software delivery.
- **CI/CD** — Automates integration, testing, and delivery or deployment of software changes.
- **AI-Native / Agentic SDLC** — An emerging SDLC model in which AI agents participate more autonomously across engineering workflows.
- **SDLC Model Selection** — Choosing an SDLC approach according to the characteristics and needs of a project.
- **SDLC Evolution Drivers** — Changes in technology, delivery expectations, team structures, and engineering bottlenecks that drive SDLC evolution.

## 3. AI Across the SDLC

- **AI-Assisted Coding** — AI copilots and agents assist with generating, modifying, and understanding code.
- **AI-Assisted Testing** — AI can generate edge cases, maintain tests, and support automated testing workflows.
- **AI-Assisted Code Review** — AI can perform static and semantic analysis to identify potential code issues.
- **AIOps** — Uses AI techniques to assist with monitoring, operations, incident response, and remediation.
- **Autonomous Remediation** — AI-driven systems can automatically respond to certain operational problems.
- **Self-Healing Test Suites** — Tests can be automatically adapted or repaired when changes cause test failures.
- **Autonomous Edge-Case Generation** — AI can generate additional test scenarios to explore unusual or failure-prone cases.

## 4. Technical Debt and Engineering Practices

- **Technical Debt** — Future cost or difficulty created by shortcuts, incomplete work, or suboptimal technical decisions.
- **Technical Debt vs Refactoring** — Technical debt describes accumulated technical cost, while refactoring changes internal structure without changing intended behaviour.
- **Hard-Coding as Technical Debt** — Fixed values or assumptions embedded in code can make future changes more difficult.
- **Skipped Tests as Technical Debt** — Omitting tests can reduce confidence and increase future maintenance risk.
- **Infrastructure as Code (IaC)** — Defines infrastructure through version-controlled code rather than manual configuration.
- **Environment Parity** — Keeps development, testing, staging, and production environments sufficiently consistent to reduce environment-specific failures.
- **Deployment vs Release** — Deployment puts software into an environment, while release makes functionality available to users.
- **Blue-Green Deployment** — Uses separate environments so traffic can be switched between old and new versions.
- **A/B Deployment** — Exposes different versions to different user groups or traffic segments to compare behaviour.

## 5. Paradigm Shifts in Software Engineering

- **Dev Effort Is No Longer the Bottleneck** — AI can reduce the effort required for some implementation tasks, shifting attention to other engineering constraints.
- **Parallel Prototyping** — AI can make it practical to explore multiple prototypes instead of heavily restricting early implementation scope.
- **Design Documents as Machine Specifications** — Structured specifications can increasingly serve as direct inputs to AI-assisted implementation.
- **Role Blurring** — AI-enabled workflows reduce some boundaries between PM, development, QA, and SRE responsibilities.
- **Disposable Microservices** — AI-assisted development can make some implementation decisions cheaper or easier to replace.
- **AI Accountability** — AI-generated artefacts introduce questions about responsibility, traceability, compliance, and software supply chains.
- **Probabilistic Outcomes** — AI-generated outputs are not guaranteed to be correct and therefore require verification.
- **Inversion of Engineering Value** — Engineering value shifts from manually producing every artefact toward orchestration, verification, and system-level judgement.
- **Orchestration** — Engineers coordinate AI models, tools, workflows, and constraints to achieve engineering outcomes.
- **Verification** — Engineers validate AI-generated artefacts for correctness, security, quality, and compliance.
- **AI Engineering Competencies** — New skills combine traditional software engineering with AI tooling, context management, evaluation, and orchestration.
- **Education Shift** — Engineering education must adapt to workflows where AI participates in software development.
- **Tooling Shift** — Engineering tools increasingly incorporate AI models and autonomous capabilities.
- **Process Shift** — SDLC processes evolve to account for AI-generated artefacts and probabilistic output.
- **Professional Practice Shift** — Software engineering roles and responsibilities change as AI becomes integrated into development.

## 6. Software Economics in AI-Native Development

- **Zero Marginal Cost of Software Work** — AI can reduce the incremental human effort required for some software tasks.
- **CAPEX to OPEX Shift** — AI-based development can move some costs from traditional capital investment toward ongoing service or usage costs.
- **Build vs Buy in AI** — Build-or-buy decisions increasingly involve comparing AI/token costs with human engineering effort.
- **Task–Model Mismatch** — Different tasks require different AI capabilities, making model selection important.
- **Usage-Based Pricing** — AI services may be priced according to usage or outcomes rather than fixed user seats.
- **80/20 Cost Inversion** — AI can alter where software-development costs are concentrated, shifting effort away from some implementation work toward verification and other activities.
- **Token Cost** — The computational usage represented by model tokens can become a direct engineering cost.
- **Token Explosion** — Poorly designed AI workflows can consume excessive tokens and increase cost and latency.

## 7. AI Risks Across the SDLC

- **AI-Generated Code Quality Risk** — Generated code can contain correctness, maintainability, or architectural problems.
- **Insecure Generated Code** — AI-generated implementations can introduce security vulnerabilities.
- **Hallucinated Packages** — AI may recommend packages, APIs, or dependencies that do not exist or are inappropriate.
- **Missing Edge Cases** — AI-generated implementations may fail to account for unusual inputs or conditions.
- **Architectural Drift** — AI-generated changes can gradually move implementation away from the intended architecture.
- **Code Slop** — Excessive or low-quality generated code can increase maintenance and review burden.
- **Code Bloat** — AI can generate more code than necessary, increasing complexity and maintenance cost.
- **Context Blindness** — AI output can be incorrect when the model lacks relevant project or system context.
- **Reviewer Fatigue** — Large volumes of AI-generated output can make human review difficult or less effective.
- **Skill Atrophy** — Excessive dependence on AI can reduce opportunities to practise and retain engineering skills.
- **Legal and IP Risk** — AI-generated artefacts can introduce intellectual-property and legal concerns.
- **Compliance Risk** — AI use can create additional regulatory, governance, and audit requirements.
- **Vendor Lock-In** — Dependence on a particular AI provider can make future migration difficult.
- **Operational Risk** — AI systems introduce additional costs, dependencies, and failure modes into engineering workflows.

## 8. AI Fundamentals

- **Artificial Intelligence** — The broader field of systems capable of performing capabilities associated with intelligent behaviour.
- **Learning** — The ability of an AI system to derive patterns or behaviour from data or experience.
- **Reasoning** — The ability to derive conclusions or make decisions from information.
- **Problem-Solving** — The ability to search, plan, or otherwise determine solutions to problems.
- **Perception** — The ability to interpret inputs such as images, speech, or multimodal information.
- **Machine Learning** — AI approaches that learn patterns from data rather than relying solely on explicitly programmed rules.
- **Supervised Learning** — Learns from labelled examples.
- **Unsupervised Learning** — Finds patterns or structures in data without explicit labels.
- **Reinforcement Learning** — Learns behaviour through interaction and reward signals.
- **Deep Learning** — Uses multi-layer neural networks to learn complex representations.
- **Rule-Based AI** — Uses explicitly defined rules rather than learned statistical models.
- **Narrow/Weak AI** — AI designed for specific tasks or domains.
- **General/Strong AI (AGI)** — The concept of AI capable of general-purpose intellectual abilities across many tasks.
- **Symbolic AI** — Represents knowledge and reasoning through explicit symbols, rules, and structures.
- **Neural AI** — Uses neural networks to learn representations and behaviours from data.

## 9. AI Reasoning, Problem-Solving and Perception

- **Knowledge Graphs** — Represent entities and relationships explicitly to support structured reasoning.
- **Probabilistic Inference** — Uses probabilities to reason under uncertainty.
- **Chain-of-Thought** — A reasoning approach involving intermediate reasoning steps.
- **Search** — Explores possible states or solutions to find an answer.
- **A\*** — A search algorithm that combines path cost with a heuristic estimate.
- **Monte Carlo Tree Search (MCTS)** — Explores possible actions using repeated simulations to guide search.
- **Agentic Planning** — Uses an agent to determine and execute a sequence of actions toward a goal.
- **Constraint Satisfaction** — Finds solutions that satisfy a defined set of constraints.
- **Computer Vision** — Enables AI systems to interpret visual information.
- **Speech Processing** — Enables systems to process and understand spoken language or audio.
- **Multimodal Fusion** — Combines information from multiple modalities such as text, images, and audio.

## 10. Evolution of AI and Language Models

- **Symbolic AI Era** — Early AI focused heavily on explicit rules, symbols, and knowledge representation.
- **Traditional ML Era** — AI increasingly used statistical learning from data.
- **Deep Learning Era** — Neural networks enabled major advances in perception and representation learning.
- **LLM Era** — Large language models enabled broad language and code-generation capabilities.
- **Reasoning Model Era** — Newer models are designed to improve performance on complex reasoning tasks.
- **Statistical Language Models** — Models that estimate probabilities of language sequences.
- **Self-Supervised Learning** — Learns from data by creating training signals from the data itself.
- **Model Parameters** — Learned numerical values that determine model behaviour.
- **Masked Language Models** — Models such as BERT learn by predicting masked portions of input.
- **Autoregressive Language Models** — Generate sequences by predicting the next token based on previous tokens.
- **Foundation Models** — Broadly capable models that can support many downstream tasks and modalities.
- **Multimodal Foundation Models** — Foundation models that operate across multiple types of input or output.
- **Reasoning Models** — Models designed or trained to improve performance on tasks requiring extended reasoning.
- **Reasoning Traces** — Intermediate reasoning representations or traces associated with reasoning processes.
- **System 1 Thinking** — Fast, intuitive, pattern-based reasoning.
- **System 2 Thinking** — Slower, deliberate, analytical reasoning.
- **System 2 Attention (S2A)** — A technique discussed in the material for focusing reasoning on relevant information.

## 11. Transformer Architecture

- **Transformer Architecture** — A neural architecture based heavily on attention mechanisms and widely used for modern language models.
- **Self-Attention** — Allows each token representation to incorporate information from other relevant tokens in the sequence.
- **Attention Mechanism** — Determines how strongly different input elements should influence a representation.
- **Tokenization** — Converts text or code into model-readable token units.

## 12. Tokenization

- **Tokens** — Basic units processed by language models, which may represent words, subwords, characters, or other fragments.
- **Tokenization** — The process of converting raw text or code into tokens.
- **Token Rule of Thumb** — The material gives approximately 1 token ≈ 4 characters ≈ 0.75 words as a rough estimate.
- **Word Tokenization** — Splits text primarily into whole-word units.
- **Character Tokenization** — Represents text using individual characters.
- **Subword Tokenization** — Splits text into reusable word fragments.
- **Byte Pair Encoding (BPE)** — A subword tokenization approach that builds tokens from frequently occurring character sequences.
- **SentencePiece** — A tokenization framework commonly used for subword-based tokenization.
- **Morphological Tokenization** — Uses linguistic word structure to split words into meaningful components.
- **Highly Inflected Languages** — Languages where words change form extensively, affecting tokenization requirements.
- **Weakly Inflected Languages** — Languages with comparatively fewer morphological variations.
- **Identifier Splitting** — Code identifiers may be divided into multiple tokens.
- **Indentation Bloat** — Formatting and indentation can consume additional context tokens.
- **Minified Code** — Removing formatting can change how code is represented and tokenised.
- **URL Splitting** — URLs can be divided into multiple tokens due to their special-character structure.
- **Special Characters** — Punctuation and programming symbols can affect tokenisation efficiency.

## 13. Code-Aware AI Processing

- **Code-Aware Tokenizers** — Tokenizers specifically designed to represent programming code more effectively.
- **Positional Metadata** — Additional information about where elements occur in code can improve representation.
- **Syntax-Guided Pretraining** — Uses programming-language syntax such as AST structure during model training.
- **Code Interpreters** — Tools that allow AI systems to execute or analyse code rather than relying solely on generated text.
- **Tool Delegation** — AI systems delegate tasks to external tools when direct model reasoning is insufficient.
- **Structured Output** — Constrains model output into a predefined structure.
- **Constrained Decoding** — Restricts possible model outputs during generation.
- **Logits Masking** — Prevents invalid token choices by masking their generation probabilities.

## 14. Context Windows and Token Limits

- **Context Window** — The amount of information a model can consider within a single interaction or processing context.
- **Token Limit** — A model-specific restriction on the number of tokens that can be processed or generated.
- **Context Window vs Token Limit** — Context window concerns the usable input context, while token limits can apply to processing or generation constraints.
- **Context Size** — Larger context windows allow more information to be provided but do not guarantee equal attention to all information.
- **Context Cost** — Larger contexts can increase AI usage cost.
- **Context Latency** — Processing larger contexts can increase response time.
- **Lost in the Middle** — Important information placed within a large context can receive less effective attention.
- **Silent Degradation** — Model output quality can degrade without an obvious failure signal as context becomes problematic.
- **Attention Dilution** — Relevant information can receive less effective attention when surrounded by excessive context.
- **Inconsistent Behaviour** — Large or poorly structured contexts can cause inconsistent model responses.
- **Cascading Context Failures** — Context problems can propagate through multi-step AI workflows.

## 15. Tokenomics

- **Tokenomics** — The study of token usage, cost, efficiency, and economic impact in AI systems.
- **AI Billing** — AI services may charge based on token or compute usage.
- **Hidden AI Costs** — AI workflows can incur costs through excessive context, retries, tool calls, and model usage.
- **AI ROI** — Evaluating whether the value generated by AI justifies its cost.
- **Model Routing** — Selecting different models for tasks based on capability, cost, or latency.
- **Tokenomics Foundation** — A concept mentioned in the material concerning the economics and management of token usage.

## 16. AI Agents

- **AI Agent** — A system that uses a model, tools, context, and control logic to pursue goals through actions.
- **Agent vs Chat Tool** — An agent can act through tools and workflows, whereas a basic chat tool primarily responds to user input.
- **SWE-agent** — An example of a coding agent that interacts with a terminal and file system.
- **Simple Reflex Agent** — Acts directly according to current input and predefined rules.
- **Model-Based Reflex Agent** — Maintains an internal representation of the environment when selecting actions.
- **Goal-Based Agent** — Chooses actions according to a defined goal.
- **Utility-Based Agent** — Selects actions using a utility or preference function.
- **Learning Agent** — Improves its behaviour through learning from experience or feedback.
- **Single-Task Agent** — Focuses on completing a specific autonomous task.
- **Multi-Agent System** — Uses multiple agents that cooperate or coordinate to complete larger workflows.
- **Linear Multi-Agent Pattern** — Agents execute sequentially, with one stage passing results to the next.
- **Parallel Multi-Agent Pattern** — Multiple agents perform tasks simultaneously.
- **Hierarchical/Controller Pattern** — A controller coordinates specialised agents or subtasks.
- **Agent Classification** — Analyses AI coding tools according to their degree of autonomy and agent behaviour.

## 17. Harness Engineering

- **Harness Engineering** — Designing the environment, tools, controls, context, and feedback mechanisms around an AI model.
- **Agent = Model + Harness** — Agent capability depends on both the underlying model and the surrounding execution and control system.
- **Vibe Coding** — Informal AI-assisted coding where generated output is accepted without sufficient engineering controls or verification.
- **Production-Ready Harness** — A harness designed with controls and infrastructure suitable for reliable engineering workflows.
- **Guardrails** — Constraints that limit unsafe, invalid, expensive, or unintended AI actions.
- **Human-in-the-Loop Gates** — Require human approval at selected points before an agent proceeds.
- **Budget Ceilings** — Limit the resources, tokens, or cost an AI workflow can consume.
- **Tool Orchestration** — Coordinates the tools an agent can invoke and the order in which they are used.
- **Context and Memory** — Provides agents with relevant project information and persistent state.
- **Observability** — Makes agent actions, decisions, outputs, and failures visible for monitoring and debugging.
- **Coding Harness** — Controls and supports AI during software implementation tasks.
- **User Harness** — Controls how users interact with AI systems and their outputs.
- **Team/Organisation/SDLC Harness** — Extends AI controls and practices across broader engineering workflows.
- **Feedforward Control** — Provides instructions or constraints before an AI action occurs.
- **Feedback Control** — Uses observed results to adjust or constrain subsequent AI actions.
- **Computational Controls** — Enforce rules through deterministic computation or tooling.
- **Inferential Controls** — Use model-based reasoning or judgement to evaluate actions or outputs.
- **Coding Conventions** — Provide explicit rules that guide AI-generated implementation.
- **Project Bootstrap** — Establishes project structure and conventions before autonomous implementation.
- **Codemods** — Automated code transformations used to apply consistent structural changes.
- **AST-Based Transformations** — Modify code using its parsed syntax structure rather than raw text manipulation.
- **Structural Tests** — Tests that enforce architectural or code-structure constraints.
- **ArchUnit** — A tool/example for testing architectural rules in code.
- **Review Instructions** — Explicit guidance given to AI systems for evaluating generated work.
- **Autonomy-Harness Relationship** — Greater agent autonomy requires stronger controls and more comprehensive harness engineering.
- **Harness Scope Changes** — Harness design should be revisited when the agent's responsibilities or scope changes.
- **Plan/Build/Review/Deploy Harness** — Harness controls can be applied across planning, implementation, review, and deployment stages.

## 18. Context Engineering

- **Context Engineering** — Systematically selecting, structuring, compressing, sequencing, and managing information supplied to AI systems.
- **Context as CPU/RAM Analogy** — Context engineering treats information supplied to a model as a resource that must be managed efficiently.
- **Context Selection** — Chooses which information should be provided to the model.
- **Context Structuring** — Organises information so the model can use it effectively.
- **Prompt Design** — Designs instructions that guide model behaviour within the supplied context.
- **Context Compression** — Reduces context size while retaining useful information.
- **Context Sequencing** — Determines the order in which information is presented.
- **Tool Integration** — Connects AI systems with external tools to obtain information or perform actions.
- **Memory Integration** — Provides persistent or reusable information to AI systems.
- **Context Retrieval** — Finds relevant information to include in the model's context.
- **Context Generation** — Produces useful contextual information for downstream model operations.
- **Context Processing** — Transforms information into a form useful to the model.
- **Context Management** — Controls context lifecycle, size, relevance, and persistence.
- **Databases for Context Engineering** — Databases can provide structured and retrievable project information for AI.
- **Data Formats for Context Engineering** — Appropriate data representation makes information easier for AI systems to retrieve and consume.

## 19. Prompt Engineering

- **Prompt Engineering** — Designing instructions and examples to guide an AI model toward desired outputs.
- **Zero-Shot Prompting** — Asking the model to perform a task without providing examples.
- **One-Shot Prompting** — Providing one example to guide the model.
- **Few-Shot Prompting** — Providing multiple examples to demonstrate the desired task or output.
- **Chain-of-Thought Prompting** — Prompting for structured intermediate reasoning steps.
- **Zero-Shot Chain-of-Thought** — Encouraging reasoning without providing worked examples.
- **CRISP Framework** — A prompting framework discussed in class for structuring AI instructions.
- **System Prompt** — Higher-level instructions that define model behaviour and constraints.
- **User Prompt** — Instructions or requests supplied by the user.
- **Prompt Priority** — Different instruction levels have different precedence when determining model behaviour.
- **Prompt Caching** — Reuses previously processed prompt/context representations to reduce repeated processing cost or latency.
- **KV Cache** — Stores attention-related intermediate values so repeated context does not need to be recomputed from scratch.

## 20. Retrieval-Augmented Generation

- **RAG** — Combines external information retrieval with language-model generation.
- **RAG Ingestion** — Collects and prepares source information for later retrieval.
- **RAG Retrieval** — Finds relevant source information for a particular query.
- **RAG Augmentation** — Adds retrieved information to the model's context.
- **RAG Generation** — Uses the augmented context to generate an answer or output.
- **Types of RAG** — Different RAG architectures and retrieval approaches can be used depending on the application.
- **RAG vs Transfer Learning** — RAG supplies external information at inference time, whereas transfer learning adapts a model using knowledge learned from another task or dataset.
- **RAG vs Fine-Tuning** — RAG changes the supplied context, while fine-tuning changes model parameters through additional training.
- **Model as a Black Box** — RAG can add external knowledge without modifying the underlying model parameters.

## 21. AI Engineering Maturity

- **Prompt Phase** — Early AI engineering focuses primarily on improving instructions given to models.
- **Context Phase** — More mature systems systematically provide relevant information and external knowledge.
- **Harness Phase** — Mature systems surround models with tools, controls, memory, observability, and execution infrastructure.
- **Loop Engineering** — Designs iterative AI workflows where outputs are evaluated and fed into subsequent steps.
- **Graph Engineering** — Represents AI workflows as connected states or tasks with controlled transitions.
- **AI Layers in the SDLC** — AI capabilities can be applied across planning, development, review, testing, deployment, and operations.
- **Spec-Harness-Loop Operating Model** — AI-native engineering can be organised around specifications, controlled execution environments, and iterative loops.
- **Human-in-the-Loop** — A human directly approves or participates in an AI decision or action.
- **Human-on-the-Loop** — A human supervises the system and can intervene without approving every individual action.
- **Autonomous Operation** — The AI system acts without routine human approval within defined controls.

## 22. Model Context Protocol (MCP)

- **Model Context Protocol (MCP)** — A protocol for connecting AI applications to external tools, data, and services.
- **MCP Host** — The AI application that manages MCP connections and interaction.
- **MCP Client** — The component within the host that communicates with an MCP server.
- **MCP Server** — Provides tools, resources, or capabilities that an MCP client can access.
- **JSON-RPC 2.0** — The message protocol used by MCP for structured request and response communication.
- **MCP over stdio** — A transport where client and server communicate through standard input/output.
- **MCP over SSE** — A server-sent-events transport mechanism discussed for MCP communication.
- **MCP Tool Flow** — The sequence in which an AI application discovers and invokes capabilities exposed through MCP.

## 23. AI Stack and AI-Enabled Systems

- **AI Application Layer** — Contains the application-specific logic and user-facing AI functionality.
- **AI Model Layer** — Contains the underlying foundation or specialised models providing AI capabilities.
- **AI Infrastructure Layer** — Provides compute, storage, networking, serving, and other infrastructure required by AI systems.
- **AI Complexity Matrix** — A framework discussed for understanding the increasing complexity of AI adoption.
- **AI Adoption Maturity** — Describes increasing organisational and engineering maturity in adopting AI capabilities.
- **Data Centricity** — Treats data quality, structure, availability, and management as central engineering concerns.
- **Explainability** — The ability to provide understandable information about AI system outputs or decisions.
- **Verifiability** — The ability to verify that AI system outputs satisfy required correctness or quality conditions.
- **Change Propagation** — The ability to understand and manage how changes in data, models, prompts, or components affect the overall system.
- **AI Engineering vs ML Engineering** — AI engineering focuses on building systems around models, while ML engineering focuses more directly on developing and operating machine-learning models.

## 24. Traditional to AI-Native SDLC

- **Traditional Six-Phase SDLC** — A process-oriented development lifecycle with distinct stages and handoffs.
- **Build-to-Review Bottleneck** — AI-assisted implementation can reduce coding effort and shift bottlenecks toward review, testing, and governance.
- **Translation Loss** — Information can be lost when requirements are repeatedly translated between stakeholders, specifications, design, implementation, and validation.
- **Spec-Driven Development (SDD)** — Uses explicit specifications as a central source for guiding implementation and validation.
- **SDD Workflow** — The material presents a workflow involving constitution, specification, clarification, and planning.
- **Constitution** — Defines foundational rules, principles, or constraints for an SDD project.
- **Specify** — Defines the desired behaviour and requirements before implementation.
- **Clarify** — Resolves ambiguity in the specification before implementation proceeds.
- **Plan** — Determines how the specified system should be implemented.
- **SDD Toolkits and Frameworks** — Tools and conventions support the specification-driven workflow.
- **PRD and Technical Decisions** — The material distinguishes product requirements from technical implementation decisions, with the PRD excluding technical decisions.
- **intent.md** — A project-level document used in the material to capture intent and guide AI-assisted development.
- **Skills** — Advisory instructions or capabilities that guide AI behaviour.
- **Hooks** — Deterministic mechanisms that enforce actions or constraints automatically.
- **SDD vs Model-Driven Development** — SDD centres implementation around explicit specifications, while model-driven development centres around formal models.
- **SDD vs Test-Driven Development** — SDD starts from specifications, while TDD starts from tests that guide implementation.
- **SDD vs Behaviour-Driven Development** — SDD focuses on system specifications, while BDD expresses expected behaviour through scenarios and examples.
- **Spec-Derived Test Cases** — Test cases can be generated from specifications rather than inferred only from implementation code.
- **End-to-End AI-Augmented SDLC** — Integrates AI capabilities across the lifecycle from specification and planning through implementation, validation, and delivery.
