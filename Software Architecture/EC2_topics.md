# Software Architectures (SE ZG651 / SS ZG653): Topics Discussed in Lectures CS01–CS08

Taken from the 8 lecture transcripts (instructor: H S Jabbal). Off-topic talk (the instructor's personal background, nostalgia, mic and camera mishaps) is left out.

| Session | Transcript file |
|---|---|
| CS01 | `Software Architectures (…)(S1-26).vtt` |
| CS02 | `…(1).vtt` |
| CS03 | `…(2).vtt` (extra evening session) |
| CS04 | `…(3).vtt` |
| CS05 | `…(4).vtt` |
| CS06 | `…(5).vtt` |
| CS07 | `…(6).vtt` |
| CS08 | `…(7).vtt` |

---

## CS01: Introduction
- Course overview: 16 sessions of 2 hours; architecture = the macro model; system design and UML are out of scope
- Evaluation approach: relative grading; quizzes (best 8 of 14); 2 assignments; mid-sem closed book, comprehensive open book; no choice in the paper
- Why architecture matters:
    - Early design decisions (distributed or centralised storage, web or thick client, CDN, local vs remote data)
    - "Delay decisions, freeze only what must be frozen"
- Functional requirements vs NFRs (quality attributes) vs constraints
    - Constraint examples: Oracle-only, no public cloud, Indian data kept in India under the IT Act
- NFRs are where the money is; educating the customer; trade-offs (security vs performance)
- Architecture enables evolutionary prototyping (DevOps), cost and schedule estimates, reuse, make-or-buy, independently developed components
- Architecture gives vocabulary: strategy (patterns) vs tactics vs operations; architectural patterns vs design patterns
- Architecture as a basis for training and recruitment
- Architecture competence: individual (duties, skills, knowledge) + organisational (processes, governance, framework), mentioned in passing
- Contexts:
    - Technical
    - Project life-cycle (inception, elaboration, construction, deployment; conformance)
    - Business (ROI, risk, the CEO security example)
    - Professional
- Stakeholders: customer, developer, maintainer, finance, government
- Business goals and non-architectural solutions (advertising agency and "mind space"; the 6 Ms)
- Usability as today's #1 quality attribute
- Architecture Influence Cycle
- Structure vs view: DB table vs DB view; the human-body analogy (orthopaedist, cardiologist, endocrinologist)
- Definition of architecture: elements, relations, properties of both (the nuclear-family example)
    - Architecture is an abstraction; every system has one; behaviour is part of it
- Three structure types: module, component-and-connector, allocation
- Module structures:
    - Decomposition
    - Uses
    - Layered (kernel, VM, TCP/IP stack)
    - Class/generalisation (car → SUV/sedan)
    - Data model
- C&C structures:
    - Service
    - Concurrency (MapReduce, Hadoop, Spark: "send the program to the data")
- Allocation structures: implementation, work assignment
- Structures relate to one another (the body-systems analogy)
- Architectural patterns and rules of thumb (previewed only)

## CS02: Quality Attributes I
- Quiz rules (15 questions in 5 minutes; best 8 of at least 13–14); watermarked slides for the comprehensive
- Quality-attribute scenario: source, stimulus, artifact, environment, response, response measure
    - "Memorise it"; it must be measurable so you can get paid
- Management actions / the 7 design decisions:
    - Allocation of responsibilities (runtime vs non-runtime)
    - Coordination model (timeliness, currency, completeness, correctness, consistency; GPS update-frequency example)
    - Data model (metadata)
    - Management of resources
    - Mapping among architectural elements
    - Binding time (early/compile vs late/runtime; service discovery)
    - Choice of technology
- Exam warning: don't reproduce every tactic; pick the right one (the heart-medicine analogy); case-oriented questions
- Functional and non-functional requirements are orthogonal; overlapping QA concerns (a DoS attack)
- Radar-failure scenario worked with an armed-forces student (source, stimulus, artifact, response, measure)
- The environment matters (load levels in performance testing)
- Meaning of "artifact" (every noun) and "stimulus"; reaction vs response
- Tactics vs strategy (FIFA analogy); building vocabulary; half-life of knowledge
- IRCTC history (ORG Systems, Fortran IV)
- Maintainability ≠ maintenance resources (the ease of maintaining; worth investing in only for long-lived systems)
- Interoperability: Android apps, SAP working with third-party fleet/Shell card systems, APIs and headless systems
- Availability:
    - Definition; general scenario; heartbeat example; fault vs failure
    - Detect / recover / prevent tactics
- Availability design checklist by decision category: bank branch cache when the network is down, ATM limits, hot/warm/cold backup, late binding, event loggers
- Performance introduced

## CS03: Quality Attributes II (extra evening session)
- Quiz results (most scored 14–15; AI use accepted); relative grading
- Recap of the scenario and design decisions
- Coordination example: rescheduling a class (sync vs async)
- Enterprise SMS server:
    - Priority queues (OTP first, bulk messages last)
    - Ways to hand it data: API, Android intent, folder drop, DB table
- Binding time: the matrimonial-site (Shaadi.com) service-registry analogy
- Performance: control demand vs manage resources; load distribution; read replicas with one write DB
- Usability:
    - UI/UX research; configuration-time vs runtime
    - Cancel, undo, pause/resume (visa form), aggregate
    - Task, user and system models
- Security: CIA (the instructor said "A = authorisation"; the slides say A = **Availability**)
- Other quality attributes: pointed to a standard list of QAs; only the basic ones are covered in class
- **Modifiability vs modify**:
    - Tata chassis vs a Maruti converted into a limo
    - SAP and Oracle Financials
    - DB views for flexibility; RDBMS vs NoSQL
- Interoperability:
    - Android, ODBC, open standards, the Apple ecosystem
    - Vehicular-LAN car clusters at crossroads
    - Discovery service, indirection, orchestration (Kubernetes), tailoring interfaces (buffering, smoothing, translation)
- Interoperability checklist (accept/reject/log, trust); solution vs enterprise architect; DFDs and UML out of scope
- Late-binding load: Mappls vs Google Maps; CDNs (Netflix); interoperability, performance and availability interplay
- Testability:
    - Testing vs testability; logging (Log4j); NFR testing; path coverage
    - Automated regression; controllability and observability; sandbox
    - Executable assertions (pre-conditions, post-conditions, invariants); limiting complexity

## CS04: Architecture Requirements & Design
- Evaluation style (a single evaluator); risks of requesting a recheck; answer keys
- Mid-sem vs comprehensive scope; open-book tips (index the slides); printouts and watermarks
- AI-generated question papers; DevSecOps and AI-driven vulnerability scanning
- Interoperability needs standard interfaces (JSON schema, banking standards), not just protocols
- Recap of structures, views and QAs
- Eliciting requirements: limits of the SRS, interviewing stakeholders, the "late break"
- Linking requirements to business goals ("what will the business achieve?")
- ASRs; decisions taken early vs kept open
- Utility tree: QA → scenarios → (Business, Architecture) ranked H/M/L; strategies X/Y/Z each cover different scenarios
- Attribute-Driven Design (mentioned)
- EC-1 details (quizzes, experiential assignments 1 and 2, group discussion)
- Documentation: audience, notation with a legend, choosing and combining views, 4+1 preview, documenting behaviour
- Local vs architectural change
- Agile and architecture:
    - Freeze only what's needed (building-pillar analogy)
    - Agile Manifesto and 12 principles
- Boehm–Turner sweet spot:
    - 10 / 100 / 1,000 KSLOC; KSLOC and function points
    - Dinner for 2 vs a family of 10 vs a 1,000-guest wedding analogy
- Agility and documentation; agility and evaluation (ATAM and lightweight evaluation, previewed)
- WebArrow case: top-down and bottom-up design
- Spikes vs POC (language choice: Python vs Java vs C)
- Netflix CDN as an architectural change; MS Teams scaling to large classes; servers (meeting, DB, messaging)
- Syllabus confirmed: CS1–8 for the mid-sem, same for the make-up

## CS05: Architecturally Significant Requirements
- Exam-centre selection issues; quiz policy (best 8)
- Review of the 7 design decisions: email/SMS allocation, sync/async, stateful/stateless, data lifecycle, binding, choice of technology
- Sample question: "How does choice of technology affect testability?"
- Assignment 1 spec:
    - A workplace system; FRs and NFRs
    - Utility tree; top 5 ASRs with tactics
    - 4 diagrams; submit as PDF; the marking scheme
- ASRs:
    - Building-architecture analogy (hospital, stadium, airport)
    - Response-time criticality (aircraft takeoff, telephony)
    - Delaying some decisions
- ASR indicators:
    - Technical risk and technical debt (.NET upgrades, microservices migration)
    - Password vaults
    - Point-to-point → middleware
    - Bank integration audits (HDFC/HSBC)
    - Influence of key stakeholders
    - Unique requirements (payment-gateway reconciliation)
    - SLAs; past budget overruns
    - Scalability, security and availability as typical ASRs
- Drivers: business goals, stakeholders, regulation (HIPAA, insurance, SEBI), cost, time to market; the scope–time–cost triangle
- Challenging FRs and NFRs:
    - Fraud detection; Netflix/YouTube scale
    - EHR access flagging
    - Audit trail, notifications, data-entry mechanisms (Copilot quiz import)
- Sources of ASRs: MoSCoW, SWEBOK, BSRs, leads from design decisions
- Quality Attribute Workshop steps and voting (30% of scenarios)
- Business goals: "X to Y by when"; 11 categories; the BHIM example
- PALM steps and pedigree ("why 40 ms?")
- Utility tree: root, branches, leaves; Nightingale scenarios parsed; (H,M) ranking
- Agile vs traditional; Agile principles
- Assignment 2 group discussion (random groups); relative grading

## CS06: Structures & Views
- Assignment extension policy; no PPT template
- ASR review:
    - Indicators, drivers, simple vs complex requirements
    - Extracting ASRs from design decisions
    - QAW purpose (make silent people speak and commit)
    - Business-goal format; PALM
    - Utility tree H/M/L pairs; KSLOC and up-front planning
- Situational-learning assignments; peer discussion; relative grading (B/C/D)
- Structure vs view; relationships analogy (family, org chart, Shakespeare, the epics)
- Module structure:
    - UI / middleware / DB (Spring Boot, WCF, PL/SQL)
    - Generalisation (vehicle → car, truck)
- C&C structure:
    - Client-server, shared DB, replication, data flow
    - Parallel processes and IPC; pipe-and-filter with decision points
- UML awareness (uml-diagrams.org, OMG)
- Allocation structure; the 3 structures and 3 broad decision types; sub-structure tables
- Kruchten 4+1:
    - Logical (Booch notation, PABX classes)
    - Process (sync vs async, Garlan & Shaw notation)
    - Development (layers; ATC example; a student's ATC and airline implementations)
    - Physical (primary/backup exchanges, line cards, logical vs physical circuits)
    - Scenarios (communication and sequence diagrams)
- Correspondence between views (inside-out, outside-in); iterative documentation
- Views matrix and tools (Rational Rose); SEI ↔ 4+1 mapping
- Modernised views:
    - UML 2.5, bounded contexts, APIs
    - Make vs "use" (pay-per-use)
    - Containers, serverless, eventual consistency, CAP (preview)
    - DevOps and CI/CD

## CS07: Layered Architecture & ATAM
- MS Teams display tips
- Feature-enhancement question for the assignment (treat the feature as the product)
- Syllabus: CS1–8 mid-sem, CS1–16 comprehensive; submission rules; avoid "plastic" AI-written answers
- Layered architecture:
    - Presentation → business → data access / services; no SQL in the UI
    - Sideways use; patterns allow exceptions
- Judiciary-system example: Airtel/Vodafone SMS adaptors, workflow engine, DAOs, firewalls
- Benefits: separation of concerns, loose coupling, reusable lower layers, exchangeable parts (blue-green DAL swap)
- Presentation-layer techniques:
    - Client vs server caching (Amazon catalogue, Canada visa site, passport scanning, DigiYatra)
    - AJAX; responsive design
    - Memcached; .NET datasets; thick clients
- Business-layer techniques:
    - Facade (and caching in the facade)
    - Session management
    - Workflow engine
- Coupling vs cohesion (marriage analogy); JSON for low coupling
- Flight-booking facade; EJB stateful vs stateless; aspect-oriented design
- Log4j explained by students (levels and priorities); framework vs library
- Data-layer techniques: connection pooling (singleton), read copies, atomicity, ORM, stored procedures, parameterised SQL vs SQL injection
- Service layer; SSL, IPSec and Log4j as awareness-only topics
- Exam format: direct vs scenario questions, time per mark, 7–8 marks per pair of sessions
- ATAM:
    - Trade-offs; evaluation by designer, by peers (bias), by outsiders (Air Force example)
    - Evaluation factors
    - Participants and roles (the questioner as "stoker"); business goals → prioritised QAs
    - Risk (make-up exam analogy), sensitivity, trade-off
    - Phases and steps; utility tree; analysis; brainstorming; presenting results
    - Lightweight ATAM

## CS08: Conformance, Testing & Reconstruction
- Mid-sem pattern:
    - About 3–4 questions with parts; about 30 marks
    - Time management; read the question first
    - Typed answers plus scanned diagrams
- Draft submissions; best-8 quizzes; the 19 Sep exam date (a student said 26 Sep was cancelled for the make-up)
- Definitions of conformance, testing, reconstruction
    - **Reconstruction ≠ modification** (the most common exam mistake)
- Architectural drift: layer skipping, technical debt, home-grown logging instead of Log4j
- Publish-subscribe (push notification, pull data)
- Conformance techniques:
    - Architecturally evident coding style
    - Frameworks (WCF, Spring, Hibernate, AUTOSAR, .NET)
    - Code templates (AI-generated templates, a read-only cursor)
    - Spring MVC (model, view, controller; passive views)
    - Updating documentation; architecture reviews
- Scrum roles (the product owner's awareness of the architecture); educating new members; code reviews; folders per architectural aspect
- Architecture and testing:
    - ASR/utility-tree priorities → test priorities
    - Integration test plan
    - Switching data sources, rollback, hot-swapping payment gateways (adapter or factory)
- Reconstruction:
    - Purposes
    - Tools students have used (Claude Code, Kiro, SonarQube); open-source/community editions; GitHub
    - A student's reconstruction of message-queue brokers and service discovery
- Reconstruction phases:
    - Raw view extraction (source, executables, build scripts, caller-callee)
    - DB construction
    - View fusion (ER + OO views; Sonar layers and slices)
    - Architecture analysis (finding violations)
    - Iteration
- ARMIN and the Vanish case (not strictly layered); tools (Dali, Lattix, SonarJ, Structure101)
- Goals; processes (top-down, bottom-up, hybrid); inputs; techniques (quasi-manual, semi-automatic, quasi-automatic); outputs
- Vertical vs horizontal conformance
- Reverse engineering (the JZ/JNZ hack story)
- Advice: use AI to generate practice questions and answers; understand all the tactics in the slides