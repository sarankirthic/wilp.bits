# Software Architecture — Complete Topic List

> Based on the CS01–CS08 lecture material provided. Each topic has a one-line explanation.

## 1. Software Architecture Fundamentals

- **Software Architecture** — The macro-level structure of a software system, including its elements, relationships, properties, and behaviour.
- **Architecture as an Abstraction** — Architecture represents a system at a higher level while hiding unnecessary implementation detail.
- **Architecture vs System Design** — Architecture focuses on major structural decisions, while detailed system design is outside the stated course scope.
- **Architecture vs UML** — UML is a notation used to document aspects of a system; architecture defines the structures and decisions being documented.
- **Architecture Influence Cycle** — Architecture influences development and business outcomes, while business and technical changes influence the architecture.
- **Architectural Patterns** — Reusable high-level approaches for structuring systems and solving recurring architectural problems.
- **Design Patterns vs Architectural Patterns** — Architectural patterns operate at system structure level, while design patterns address smaller design-level problems.
- **Architectural Strategies** — High-level approaches used to satisfy important architectural requirements.
- **Architectural Tactics** — Specific design decisions used to achieve quality-attribute goals.
- **Architectural Operations** — Runtime or operational mechanisms that support architectural behaviour.
- **Architectural Trade-offs** — Choosing between competing quality attributes or architectural concerns.
- **Architectural Stakeholders** — People or groups affected by architectural decisions, such as customers, developers, maintainers, finance, and government.
- **Technical Context** — Architectural decisions are influenced by the available technologies and technical environment.
- **Business Context** — Architecture must support business goals, ROI, risk, and organisational needs.
- **Project Life-cycle Context** — Architecture evolves through inception, elaboration, construction, deployment, and conformance activities.
- **Professional Context** — Architecture is also influenced by professional practices, skills, governance, and organisational processes.

## 2. Architectural Structures

- **Module Structure** — Describes how software is divided into implementation-oriented modules.
- **Decomposition** — Breaks a system into smaller modules with defined responsibilities.
- **Uses Structure** — Shows which modules depend on or use other modules.
- **Layered Structure** — Organises modules into layers where higher layers use services of lower layers.
- **Generalisation Structure** — Organises elements through inheritance or generalisation relationships.
- **Data Model Structure** — Represents how data-related elements are organised within the architecture.
- **Component-and-Connector (C&C) Structure** — Describes runtime components and the connectors through which they interact.
- **Service Structure** — Represents functionality exposed through services and their interactions.
- **Concurrency Structure** — Describes parallel execution and coordination among concurrent components.
- **Client-Server Structure** — Separates clients that request functionality from servers that provide it.
- **Shared Database Structure** — Allows multiple components or applications to interact through a common database.
- **Replication Structure** — Uses multiple copies of data or components to improve availability or performance.
- **Data Flow Structure** — Represents how data moves between processing components.
- **Pipe-and-Filter Structure** — Processes data through a sequence of independent filters connected by pipes.
- **Inter-Process Communication (IPC)** — Mechanisms that allow concurrent processes to communicate.
- **Allocation Structure** — Maps software elements to implementation environments, teams, or work responsibilities.
- **Implementation Allocation** — Maps architectural elements to hardware, software, deployment, or implementation locations.
- **Work Assignment** — Maps architectural responsibilities to people, teams, or organisational units.

## 3. Quality Attributes

- **Quality Attribute** — A measurable non-functional characteristic describing how well a system performs a particular property.
- **Quality Attribute Scenario** — A measurable scenario defined using source, stimulus, artifact, environment, response, and response measure.
- **Availability** — The ability of a system to remain operational and accessible when required.
- **Performance** — The system's ability to respond within required time and resource limits.
- **Usability** — The ease with which users can understand and effectively operate the system.
- **Security** — Protection of system assets through mechanisms such as confidentiality, integrity, and availability.
- **Modifiability** — The ease with which the system can be changed without causing excessive impact elsewhere.
- **Maintainability** — The ease of performing maintenance activities on a system.
- **Interoperability** — The ability of different systems or components to work together through suitable interfaces and standards.
- **Testability** — The ease with which system behaviour can be controlled, observed, and verified through testing.
- **Scalability** — The ability of a system to handle increasing workload or size while meeting required qualities.

## 4. Quality Attribute Tactics

- **Allocation of Responsibilities** — Decides which component or part of the system is responsible for a particular function.
- **Coordination Model** — Determines how components coordinate, including timing, consistency, completeness, and correctness.
- **Data Model** — Defines how data and its metadata are represented and managed.
- **Resource Management** — Controls and allocates computational, storage, network, and other resources.
- **Mapping Among Architectural Elements** — Defines how elements in one architectural structure correspond to elements in another.
- **Binding Time** — Determines when an architectural decision or dependency is fixed, from compile time to runtime.
- **Choice of Technology** — Selects technologies that support the required architecture and quality attributes.
- **Availability Detection Tactics** — Detect failures or abnormal conditions so the system can respond.
- **Availability Recovery Tactics** — Restore service after faults or failures.
- **Availability Prevention Tactics** — Reduce the likelihood or impact of failures.
- **Performance Demand Control** — Controls incoming workload to keep system demand manageable.
- **Performance Resource Management** — Improves performance by managing available resources efficiently.
- **Load Distribution** — Spreads workload across multiple resources to avoid bottlenecks.
- **Read Replicas** — Uses additional database copies to distribute read workload.
- **Usability Tactics** — Features such as cancel, undo, pause/resume, and aggregation that improve user interaction.
- **Modifiability Tactics** — Architectural techniques that reduce the impact and cost of future changes.
- **Interoperability Tactics** — Discovery, indirection, orchestration, buffering, translation, and interface tailoring used to connect systems.
- **Testability Tactics** — Techniques such as logging, controllability, observability, sandboxing, and assertions that make testing easier.

## 5. Architectural Requirements

- **Functional Requirements** — Describe what the system must do.
- **Non-Functional Requirements** — Describe qualities or constraints governing how the system must operate.
- **Architecturally Significant Requirements (ASRs)** — Requirements that strongly influence architectural decisions because of their technical or business impact.
- **Architectural Drivers** — Business, stakeholder, regulatory, technical, cost, and time factors that drive architecture.
- **Business Goals** — Desired measurable business outcomes that architecture must support.
- **Stakeholder Requirements** — Needs or constraints originating from people or organisations affected by the system.
- **Technical Risk** — Architectural uncertainty or difficulty that can threaten system success.
- **Technical Debt** — Future cost or difficulty created by architectural or technical shortcuts.
- **Regulatory Constraints** — Legal or regulatory requirements that restrict architectural choices.
- **SLA Requirements** — Service-level commitments that can become important architectural drivers.
- **Scope-Time-Cost Triangle** — The relationship between project scope, delivery time, and cost constraints.

## 6. Quality Attribute Workshop and Utility Tree

- **Quality Attribute Workshop (QAW)** — A structured method for eliciting and prioritising quality-attribute scenarios with stakeholders.
- **Utility Tree** — Organises quality attributes and scenarios into a hierarchy for prioritisation.
- **Quality Attribute Scenario Ranking** — Prioritises scenarios according to business and architectural importance.
- **H/M/L Prioritisation** — Classifies scenarios by high, medium, or low importance.
- **PALM** — A technique used to identify and justify measurable performance or quality targets.
- **Scenario Voting** — Stakeholders vote to identify the most important quality-attribute scenarios.
- **Business Goal Traceability** — Connects architectural requirements and scenarios back to measurable business goals.

## 7. Attribute-Driven Design

- **Attribute-Driven Design (ADD)** — Designs architecture by using architecturally significant quality attributes and requirements as primary drivers.
- **Top-Down Design** — Starts with high-level architectural concerns and progressively decomposes them.
- **Bottom-Up Design** — Builds architectural understanding from existing components, technologies, or implementation constraints.
- **Architectural Strategy Selection** — Selects architectural approaches that address the important scenarios and requirements.

## 8. Architecture Documentation and Views

- **Architecture Documentation** — Records architectural decisions, structures, behaviour, and relationships for different audiences.
- **Architectural Views** — Present selected aspects of an architecture to address particular stakeholder concerns.
- **Viewpoint** — Defines how a particular architectural concern should be represented and documented.
- **View Correspondence** — Describes relationships between elements represented in different architectural views.
- **Views Matrix** — Organises the relationship between architectural structures, views, and documentation.
- **Behaviour Documentation** — Documents how architectural elements interact and behave over time.
- **4+1 Documentation** — Uses multiple architectural views plus scenarios to document different aspects of a system.

## 9. Kruchten 4+1 View Model

- **Logical View** — Describes important functional and structural elements of the system.
- **Process View** — Describes runtime processes, communication, synchronisation, and concurrency.
- **Development View** — Describes the organisation of software modules and development structures.
- **Physical View** — Describes how software is mapped onto hardware and deployment environments.
- **Scenario View** — Uses scenarios to illustrate and validate interactions across the other views.

## 10. Layered Architecture

- **Layered Architecture** — Organises a system into layers with defined responsibilities and controlled dependencies.
- **Presentation Layer** — Handles user interaction and presentation-related responsibilities.
- **Business Layer** — Contains business rules, workflows, and application-level logic.
- **Data Access Layer** — Handles interaction with databases and other persistent data sources.
- **Service Layer** — Exposes reusable application or business functionality through defined services.
- **Separation of Concerns** — Keeps different responsibilities separated so each architectural part has a focused purpose.
- **Loose Coupling** — Minimises dependencies between components so changes have less impact.
- **Cohesion** — Measures how closely related the responsibilities within a component or module are.
- **Layer Reusability** — Allows lower-level functionality to be reused by multiple higher-level components.
- **Layer Exchangeability** — Allows one implementation of a layer to be replaced by another with limited impact.
- **Layer Skipping** — Occurs when components bypass intended architectural layers and directly access lower-level functionality.

## 11. Layered Architecture Techniques

- **Client-Side Caching** — Stores frequently used data near the client to reduce repeated requests.
- **Server-Side Caching** — Stores reusable data on the server to reduce processing or database load.
- **AJAX** — Allows web clients to exchange data asynchronously without requiring full-page reloads.
- **Responsive Design** — Adapts presentation to different screen sizes and device environments.
- **Facade** — Provides a simplified interface over a more complex subsystem.
- **Session Management** — Maintains user or interaction state across multiple requests.
- **Workflow Engine** — Coordinates a sequence of business activities or processing steps.
- **Connection Pooling** — Reuses database connections instead of repeatedly creating and destroying them.
- **Read Copies** — Uses replicated data sources to distribute read operations.
- **Object-Relational Mapping (ORM)** — Maps application objects to relational database structures.
- **Stored Procedures** — Encapsulate database-side operations for execution within the database.
- **Parameterized SQL** — Separates SQL structure from input values to reduce injection risk.
- **Framework vs Library** — A framework controls application structure and execution flow, while a library is called by application code.

## 12. Architectural Patterns and Mechanisms

- **Client-Server Pattern** — Separates requesters of services from providers of those services.
- **Layered Pattern** — Structures software into layers with defined responsibilities and dependencies.
- **Pipe-and-Filter Pattern** — Processes data through a chain of independent processing stages.
- **Publish-Subscribe Pattern** — Allows publishers to send events or messages without directly knowing subscribers.
- **Facade Pattern** — Provides a unified interface to a subsystem.
- **Service Discovery** — Allows clients to locate available services dynamically.
- **Service Registry** — Maintains information about available services and their locations.
- **Middleware** — Provides common communication or integration functionality between distributed components.
- **Replication** — Maintains multiple copies of data or services to support architectural goals.
- **Caching** — Stores frequently accessed information closer to consumers to reduce latency or load.
- **Stateful vs Stateless Architecture** — Distinguishes components that retain interaction state from those that do not.
- **Event-Driven Architecture** — Uses events to communicate state changes or trigger processing between components.

## 13. Architecture Evaluation and ATAM

- **Architecture Evaluation** — Examines an architecture to determine how well it satisfies important requirements and quality attributes.
- **ATAM** — Architecture Tradeoff Analysis Method used to identify risks, sensitivity points, and trade-offs.
- **Architectural Risk** — A decision or uncertainty that may negatively affect important quality attributes or business goals.
- **Sensitivity Point** — An architectural decision that significantly affects a particular quality attribute.
- **Trade-off Point** — An architectural decision that affects multiple quality attributes, potentially improving one while harming another.
- **ATAM Participants** — Includes stakeholders, evaluators, architects, and other relevant participants.
- **ATAM Utility Tree** — Uses prioritised quality-attribute scenarios as input to architecture evaluation.
- **ATAM Analysis** — Evaluates architectural strategies against important scenarios and identifies risks and trade-offs.
- **Lightweight ATAM** — A reduced form of ATAM used when a full evaluation process is unnecessary.

## 14. Architecture Conformance

- **Architectural Conformance** — Ensures implementation remains consistent with the intended architecture.
- **Architectural Drift** — Gradual divergence of the implementation from the intended architecture.
- **Architectural Erosion** — Accumulation of implementation changes that weaken or violate architectural structure.
- **Vertical Conformance** — Checks implementation against the intended architectural structures or layers.
- **Horizontal Conformance** — Checks consistency across related architectural structures or views.
- **Architecturally Evident Coding Style** — Coding practices that make architectural boundaries and responsibilities visible in the implementation.
- **Framework Enforcement** — Uses frameworks to enforce or encourage architectural structures.
- **Code Templates** — Standard implementation templates that help developers follow architectural conventions.
- **Architecture Reviews** — Periodic reviews used to detect architectural violations and maintain conformance.
- **Code Reviews** — Reviews implementation changes to identify violations and maintain architectural consistency.
- **Documentation Updates** — Keeps architectural documentation aligned with actual implementation.

## 15. Architecture and Testing

- **Architecture-Driven Testing** — Uses architectural requirements and priorities to determine testing priorities.
- **ASR-Based Test Prioritisation** — Gives higher testing attention to scenarios associated with important ASRs.
- **Integration Testing** — Verifies interactions between architectural components and external systems.
- **Data Source Switching** — Tests whether components can switch between alternative data sources as architecturally intended.
- **Rollback Testing** — Verifies that the system can safely return to a previous state after a failure or problematic change.
- **Hot-Swapping** — Tests replacing components or services while minimising system disruption.
- **Adapter for Replaceable Components** — Provides a compatible interface when substituting one implementation for another.
- **Factory for Replaceable Components** — Centralises creation of interchangeable implementations.

## 16. Architecture Reconstruction

- **Architecture Reconstruction** — Recovers the architecture of an existing system from its implementation and other available evidence.
- **Reconstruction vs Modification** — Reconstruction seeks to understand or recover architecture rather than change the system.
- **Reverse Engineering** — Analyses existing software to recover higher-level information about its structure and behaviour.
- **Raw View Extraction** — Extracts initial architectural information from source code, executables, build scripts, and dependencies.
- **Caller-Callee Analysis** — Identifies which components or functions call other components or functions.
- **Database Reconstruction** — Recovers architectural information from database structures and relationships.
- **View Fusion** — Combines information from different recovered views to build a more complete architectural picture.
- **Architecture Analysis** — Examines the reconstructed architecture to identify structures, relationships, and violations.
- **Architecture Violation Detection** — Identifies differences between intended architectural rules and the actual implementation.
- **Iterative Reconstruction** — Repeats extraction and analysis to progressively improve architectural understanding.
- **Top-Down Reconstruction** — Starts with known architectural concepts and maps implementation details to them.
- **Bottom-Up Reconstruction** — Starts from implementation evidence and derives higher-level architectural structures.
- **Hybrid Reconstruction** — Combines top-down and bottom-up reconstruction approaches.
- **Reconstruction Tools** — Tools such as SonarQube, Lattix, Dali, SonarJ, and Structure101 can assist architectural analysis.

## 17. Architectural Evolution

- **Architectural Change** — Modification of significant architectural decisions or structures as system needs evolve.
- **Local vs Architectural Change** — Distinguishes changes confined to implementation details from changes that affect system architecture.
- **Evolutionary Prototyping** — Uses incremental development to validate architectural decisions and evolve the system.
- **Delayed Architectural Decisions** — Keeps decisions open until enough information exists to make them confidently.
- **Binding Time** — Determines when architectural choices become fixed, allowing some decisions to remain flexible until runtime.
- **Architectural Migration** — Moves an existing system toward a different architectural structure or technology.
- **Technical Debt and Architecture** — Architectural shortcuts can create future maintenance and migration costs.
- **Scaling Architecture** — Architectural structures may need to change as workload, users, or system scope increases.

## 18. Architecture, Agile and DevOps

- **Agile Architecture** — Balances architectural planning with iterative development and changing requirements.
- **Freeze Only Necessary Decisions** — Fix important architectural decisions early while keeping unnecessary decisions flexible.
- **Architecture in Agile Development** — Architecture evolves incrementally while supporting continuous delivery of functionality.
- **Spikes** — Short technical investigations used to reduce uncertainty before committing to an implementation.
- **Proof of Concept (POC)** — A small implementation used to demonstrate whether a technical approach is feasible.
- **DevOps and Architecture** — Architecture must support automated build, deployment, operation, and continuous change.
- **CI/CD** — Continuous integration and continuous delivery/deployment practices that support frequent architectural and implementation changes.
- **Architecture Conformance in Continuous Development** — Architectural rules must remain enforceable as the codebase evolves continuously.

## 19. Modern Architectural Concepts Mentioned

- **APIs** — Defined interfaces that allow software components or systems to communicate.
- **Containers** — Package applications with their dependencies into isolated, portable execution units.
- **Serverless Architecture** — Runs application functionality through managed execution environments without directly managing servers.
- **Bounded Contexts** — Defines clear boundaries within which particular models and terminology apply.
- **Eventual Consistency** — Allows distributed replicas to become consistent over time rather than immediately.
- **CAP** — Describes trade-offs among consistency, availability, and partition tolerance in distributed systems.
- **Microservices** — Structures an application as independently deployable services around focused responsibilities.
- **Service Discovery** — Enables distributed components to locate services dynamically.
- **Orchestration** — Coordinates deployment and operation of distributed components or services.
- **Kubernetes** — A container orchestration platform mentioned as an example of orchestration.
- **CDN** — Distributes content closer to users to reduce latency and improve scalability.
- **Distributed Systems** — Systems whose components operate across multiple computing environments and communicate over networks.

## 20. Architecture Governance and Competence

- **Individual Architecture Competence** — The skills, knowledge, and responsibilities required for an individual to perform architectural work.
- **Organisational Architecture Competence** — Processes, governance, and frameworks that allow an organisation to perform architecture effectively.
- **Architecture Governance** — Organisational mechanisms for controlling, reviewing, and aligning architectural decisions.
- **Architecture Processes** — Repeatable activities used to create, evaluate, document, and evolve architecture.
- **Architecture Frameworks** — Structured approaches for organising architectural practices and documentation.
- **Architecture Training** — Developing architectural knowledge and skills within an organisation.
- **Architecture Recruitment** — Using architectural competencies as a consideration when selecting technical personnel.
