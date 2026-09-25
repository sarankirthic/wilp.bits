# Software Architectures (SE ZG651 / SS ZG653): EC-2 Mid-Sem Prep Guide

**Sources used:**
- **[H]** Course Handout v1.1 (First Sem 2026-27)
- **[S-CSxx]** Lecture slides: 8 decks, CS01–CS08 (instructor: H S Jabbal)
- **[L-CSxx]** Lecture transcripts: 8 sessions
- **[T1]** Bass, Clements & Kazman, *Software Architecture in Practice*, 3rd ed. (the main textbook)

Stars show how much the instructor stressed a topic: ★★★ = stressed again and again in lectures and tied to the exam or the assignment; ★★ = explained in detail; ★ = mentioned only in passing.

---

## 0. The exam: facts and the instructor's own advice

### Format

| Item | Value | Source |
|---|---|---|
| Component | EC-2 Mid-Semester Test, **Closed Book**, weight 30% | [H] |
| Duration | 2 hours according to the handout. In the lecture the instructor used "1½ hours, 30 marks" as his example, so **check the exam portal** | [H], [L-CS08] |
| Syllabus | **Contact sessions 1 to 8**. The make-up exam has the **same syllabus** | [H], [L-CS04], [L-CS07] |
| Date | Regular: 19 Sep 2026 (FN) according to the handout. A make-up follows (a student in CS08 said 26 Sep was the make-up weekend; confirm on eLearn) | [H], [L-CS08] |
| Paper shape | About **3–4 questions, each with parts (a, b, c)**. The parts can come from unrelated topics. **No choice**: every question is compulsory | [L-CS01], [L-CS08] |
| Coverage | Spread evenly over CS1–8, about **7–8 marks for every pair of sessions**. If you skip 2 sessions you lose roughly ¼ of the paper | [L-CS07] |
| Answer mode | You may type text and scan hand-drawn diagrams (this worked in past exams; confirm with the exam department) | [L-CS08] |
| Question setting | BITS uses an AI tool that takes the slides and textbook and generates the questions, answer key and rubric | [L-CS01], [L-CS04], [L-CS08] |

### What the instructor said about answering (quoted or closely paraphrased)
1. **"Don't list all the tactics."** Students who copy out every tactic for a quality attribute get **zero**. Questions are small cases, and you must **pick the right tactic(s) and justify them**. His analogy: a patient with a heart problem needs the right medicine and dose, not every heart medicine in the pharmacy. [L-CS02]
2. **Read the question for the first 5 minutes.** "Don't be in a hurry to dump your brain onto the paper." Understand exactly what is being asked. [L-CS08]
3. **Budget about 3 minutes per mark.** For a 5-mark part: think for 5 minutes, write for 10. [L-CS07]
4. **Be pointed.** Long background paragraphs make the examiner conclude you don't understand. Say which part of the question you are answering. [L-CS04], [L-CS05]
5. The mid-sem **can have direct questions** (e.g. "What is architecture?", "What are the steps of ATAM?") because it is closed book. Examiners usually wrap them in a small scenario. [L-CS07]
6. **Know the meaning of every tactic** in the slides. "Understand all the tactics that have been mentioned in the slides." These were his last words before the mid-sem. [L-CS08]
7. **Reconstruction trap:** "50% of the people write a long lecture on the wrong stuff." Reconstruction is **not** designing a new or modified architecture (see §8). [L-CS08]
8. Be able to **write a quality-attribute scenario from a case**: "Given a case study… how would you present an availability scenario from there? You should be able to draw the availability scenario out." [L-CS04]
9. His suggested practice method: give the slides to an AI tool and ask it for sample questions, answers and an evaluation guide. Past papers only show you what *won't* be asked again. [L-CS07], [L-CS08]

---

## 1. Topic map: handout ↔ slides ↔ lecture ↔ textbook

| CS | Handout topic [H] | Slide deck | Lecture focus | T1 chapters | Weight |
|---|---|---|---|---|---|
| 1 | Introduction to software architecture: definitions, structures and patterns, good architecture, importance, contexts, competence | `M1-CS01_Introduction` | Why architecture matters; FR vs NFR vs constraints; structure vs view (the body/X-ray analogy); 3 structure types; contexts | Ch 1, 2, 3, 24 | ★★★ |
| 2 | Quality attributes I: availability, performance, usability, security, modifiability | `M2-CS02-Quality` | **6-part QA scenario**; **7 design-decision categories**; tactics as vocabulary; availability tactics; maintainability vs maintenance; interoperability intro | Ch 4, 5, 7, 8, 9, 11 | ★★★ |
| 3 | Quality attributes II: interoperability, testability, scalability, integration, other QAs, trade-offs | `M2-CS03-Quality` (Interoperability, Testability) | Recap of the scenario and decisions; **modifiability vs modify**; interoperability (Android, ODBC, open standards, vehicular LAN); testability (assertions, Log4j) | Ch 6, 10, 12 | ★★★ |
| 4 | Capturing ASRs: QAW, business goals, drivers, scenarios, prioritising, utility tree | `M3-CS04-ArchReqDz` (overview + Agile) | Eliciting requirements; the "late break"; utility tree (H/M/L); Agile manifesto; **up-front vs rework sweet spot**; spikes | Ch 15, 16 | ★★★ |
| 5 | Architecture design: design strategy, ADD steps, architecting in Agile | `M3-CS05-ASRs` | Review of design decisions; ASR indicators; QAW steps; business goals and PALM; **utility tree (Nightingale)**; assignment 1 | Ch 16, 17, 15 | ★★★ |
| 6 | Documenting architecture: views, QA views, combining views, **Kruchten 4+1**, documentation package, **Hatley-Pirbhai** | `M4-CS06-StrViews` | Structure vs view; the 3 structure types and their sub-structures; **4+1 views** (PABX example); mapping SEI structures to 4+1 | Ch 1, 18 | ★★★ |
| 7 | Layered architecture (presentation, business, data, service layers) + **ATAM** | `M5-CS07-Layer_ATAM` | Layers and a technique for each layer; facade; coupling vs cohesion; SQL injection; ATAM (risk, sensitivity, trade-off, roles) | Ch 21 (ATAM); R2 | ★★★ |
| 8 | Conformance, testing, **reconstruction**, raw view extraction, view fusion, finding violations, real-time architectures | `M5-CS08-Conformance_Reconstruction` | Architectural drift and technical debt; 4 conformance techniques; how architecture helps testing; **reconstruction ≠ modification**; tools | Ch 19, 20 | ★★★ |

> **Gaps: topics in the handout that are thin or missing in the slides and lectures.** The AI question tool is fed the handout and textbook as well as the slides, so these could still appear. Short notes are in §9.
> - CS3: **Scalability** (only one line in the slides), **Integration**, **Design trade-offs**
> - CS5: **Design strategy and ADD steps** (the slide outline only names them)
> - CS6: **QA views** (security, communication, reliability), **Combining views**, **Documentation package**, **Hatley-Pirbhai template**
> - CS8: **Real-time architectures**

---

## 2. CS01: Introduction to software architecture

### Definition ★★★ (learn it word for word)
> *"The software architecture of a system is the **set of structures** needed to **reason about the system**, which comprise **software elements, relations among them, and properties of both**."* [S-CS01], [T1 ch1]

- This definition deliberately avoids "early" or "major" decisions. Not every early decision is architectural, and it's hard to judge what counts as "major". Structures, on the other hand, are easy to identify.
- **Architecture is an abstraction.** It leaves out private details that have no effect outside a single element.
- **Every system has an architecture**, even if it is undocumented, bad, or known to nobody. [L-CS01] and again in [L-CS08]
- **Architecture includes behaviour**, to the extent that behaviour affects reasoning about the system. A plain box-and-line drawing is *not* an architecture.

### Structure vs view ★★★
| | Structure | View |
|---|---|---|
| What it is | The set of elements as they actually exist in software or hardware | A *representation* of a structure, written by and read by stakeholders |
| Instructor's analogy | A **database table** (what exists) | A **database view** (what you show) [L-CS01] |
| | The human body | The orthopaedist's X-ray, the cardiologist's angiogram, and so on |
- "**Architects design structures. They document views** of those structures."

### The 3 categories of structure ★★★
| Category | Elements | Questions it answers | Useful sub-structures |
|---|---|---|---|
| **Module** (static, code units) | Modules: classes, layers, divisions of functionality | What is each module responsible for? What may it use, and what does it actually use? Which modules are related by inheritance? | **Decomposition** (is-a-submodule-of → modifiability, work breakdown), **Uses** (correctness requires another module to be present → building subsets, incremental development), **Layer** (virtual machine → portability), **Class/generalisation** (inherits-from → reuse), **Data model** |
| **Component-and-Connector (C&C)** (runtime) | Components (runtime entities) + connectors (call-return, pipes, sync operators) | What executes and how does it interact? Shared data stores? What is replicated? How does data flow? What runs in parallel? | **Service**, **Concurrency** (logical threads, resource contention), **Process**, **Shared data/repository**, **Client-server** |
| **Allocation** (software ↔ environment) | Software elements + the environment (hardware, file system, teams) | Which processor runs each element? Which files hold it? Which team builds it? | **Deployment** (allocated-to, migrates-to → performance, availability, security), **Implementation** (stored-in → configuration management and builds), **Work assignment** (assigned-to → teams) |
- A structure counts as *architectural* if it supports reasoning about a property that matters to some stakeholder.
- Modules and components map **many-to-many**. Don't expect a one-to-one match.
- Which structure supports which quality: the uses structure → extensibility or contraction; concurrency → freedom from deadlock and bottlenecks; deployment → performance, availability, security.

### Why architecture is important (Bass's 13 reasons) ★★
1. It **inhibits or enables the system's quality attributes**. The instructor called this "the most important message of this course".
2. It lets you reason about and **manage change**. About 80% of cost comes after deployment. Changes are **local** (one element), **non-local** (several elements, same approach) or **architectural** (changes how elements interact). A good architecture makes the most common changes local.
3. It enables **early prediction of qualities**.
4. It improves **communication among stakeholders**.
5. It carries the **earliest, hardest-to-change design decisions**: single vs distributed processors, layering, sync vs async, OS or hardware dependence, encryption, protocols.
6. It **constrains the implementation**, for example through performance budgets per element.
7. It **shapes the organisation** (work-breakdown structure), and the organisation shapes it back.
8. It enables **evolutionary prototyping** (a skeletal system).
9. It improves **cost and schedule estimates** (top-down combined with bottom-up).
10. It is a **transferable, reusable model** that can underpin a product line.
11. It supports **independently developed components** (COTS, open source).
12. It **restricts the design vocabulary** through patterns.
13. It is a **basis for training** new team members.

### Requirements triad ★★★ [L-CS01], [L-CS02]
- **Functional**: what the system does.
- **Quality attribute (NFR)**: *how well* it does it. "What you're paid for is more of the non-functional than the functional."
- **Constraint**: a design decision with **zero degrees of freedom**, e.g. "must use Oracle", "no public cloud", "Indian user data must stay in India under the IT Act".
- Functionality and quality attributes are **orthogonal**. Functionality does *not* determine the architecture.

### Contexts of architecture ★★
- **Technical**: which quality attributes it achieves, plus the current technology environment.
- **Project life-cycle**: waterfall, iterative, Agile, MDD. Seven architecture activities apply under any process: make the business case → understand the ASRs → create or select the architecture → document and communicate it → analyse and evaluate it → implement and test against it → ensure conformance.
- **Business**: business goals, ROI. Some goals have **non-architectural solutions** (instructor's example: hiring an advertising agency to win "mind space").
- **Professional**: the architect's skills (diplomacy, negotiation, communication, current knowledge).
- **Architecture competence** (handout CS1, T1 ch24; the instructor only mentioned it): for architecture to work you need **individual competence** (the architect's *duties, skills, knowledge*) *and* **organisational competence** (standard processes, architecture governance, and a framework that defines those duties, skills and knowledge).
- **Stakeholders**: anyone with a stake in the system. Engage them early. Ignoring one can sink the project.
- **Architecture Influence Cycle**: the business, technical, project and professional contexts influence the architect → the architecture → the system → which feeds back to influence future contexts.

### Patterns (a preview; covered in depth after the mid-sem)
- Module type: **Layered**. C&C types: **Shared-data/repository**, **Client-server**. Allocation types: **Multi-tier**, **Competence centre**, **Platform**.
- A **pattern is a strategy**; a **tactic** fine-tunes one quality attribute. The instructor's football analogy: the team strategy is the pattern, in-game moves are tactics, and playing is operations.

### What makes a "good" architecture ★★
There is no inherently good or bad architecture, only one that is **more or less fit for a purpose**.
- **Process rules of thumb**: a single architect or small team with a clear leader (conceptual integrity); a prioritised list of QA requirements; documentation in views; early evaluation; incremental implementation (a skeletal system).
- **Product rules of thumb**: information hiding and separation of concerns; well-known patterns and tactics; no dependence on a particular product version; separate data producers from consumers; don't expect module = component; make process-to-processor assignment easy to change; few interaction mechanisms ("do the same thing the same way"); a small, explicit set of resource-contention areas.

---

## 3. CS02 & CS03: Quality attributes

### 3.1 The six-part quality-attribute scenario ★★★ (instructor: "this has got to be memorised")
```
Source of stimulus ──► Stimulus ──► [ Artifact  within  Environment ] ──► Response ──► Response measure
```
| Part | Meaning | Instructor's radar example [L-CS02] |
|---|---|---|
| **Source** | The entity (human or system) that generates the stimulus | Built-in test equipment or the duty engineer |
| **Stimulus** | A condition that requires a response | The radar stops giving updates (communication failure) |
| **Artifact** | What is stimulated. "Everything is an artifact": any noun, such as a processor, channel, storage, the whole system, a document | The radar system |
| **Environment** | The conditions at the time: normal, peak load, overload, degraded, startup, war-time… | Operational, war-time |
| **Response** | The activity carried out as a result | Detect, diagnose, replace the faulty unit, restore |
| **Response measure** | Must be **measurable** so it can be tested and you can get paid | Restored within 30 min (5 min for critical categories) |

- **General scenario** = system-independent. **Concrete scenario** = specific to one system.
- "Reaction" is not the same as "response". A response is effortful, designed behaviour. [L-CS02]
- Scenarios fix two problems with plain QA definitions: definitions that can't be tested, and overlapping categories (is a DoS attack about availability, performance, security or usability? Just write the scenario).

### 3.2 The seven categories of design decisions ★★★ (the instructor revised these again in CS05)
1. **Allocation of responsibilities**: identify responsibilities and assign them to modules, components and connectors (runtime or non-runtime).
2. **Coordination model**: who may or may not coordinate; the properties (timeliness, currency, completeness, correctness, consistency); the mechanism (stateful/stateless, sync/async, guaranteed or not, throughput and latency). His example: an enterprise SMS server with priority queues (OTPs first, bulk messages last).
3. **Data model**: data abstractions and their operations; the lifecycle (create, init, access, persist, manipulate, translate, destroy); **metadata** ("data about data"); organisation (RDBMS, NoSQL, objects).
4. **Management of resources**: which resources, their limits, who manages them, how they are shared and arbitrated, what happens at saturation.
5. **Mapping among architectural elements**: modules ↔ runtime elements, runtime ↔ processors, data ↔ stores, modules ↔ units of delivery.
6. **Binding time**: **early** (compile or build time) is predictable but inflexible. **Late** (runtime, e.g. a service registry, "like Shaadi.com") is flexible but more complex. Every other decision has an associated binding time.
7. **Choice of technology**: availability, tool support, in-house familiarity, side effects, compatibility with the existing stack, whether the technology will survive ("don't die alone").

**Likely question shape:** "How does *<decision category>* affect *<quality attribute>*?" For example, the instructor asked in class how **choice of technology affects testability**. Answer: tools and frameworks for regression testing, fault injection and record/playback; the ability to inject state; the team's familiarity with the stack. [L-CS05]
Each QA has a **design checklist** organised by these 7 categories in the slides.

### 3.3 Tactics ★★★ (learn what each one means, then pick and justify for the case)
A tactic is a design decision that affects **one** quality-attribute response. A pattern is a *package of tactics*.

#### Availability [S-CS02], [T1 ch5]
- Definition: the system is **there and ready when needed**. It includes reliability and adds recovery (repair). The goal is to **stop faults from becoming failures**.
- Stimuli: omission, crash, incorrect timing, incorrect response. Measures: % uptime (e.g. 99.999%), time to detect, time to repair, time in degraded mode.
- Concrete example: *"Heartbeat monitor detects server non-responsive during normal operation → system informs operator and continues with no downtime."*

| Detect faults | Recover: preparation & repair | Recover: reintroduction | Prevent faults |
|---|---|---|---|
| **Ping/echo** (async request/response for reachability) | **Active redundancy** (hot spare, processes the same inputs in parallel) | **Shadow** (run the repaired component in shadow mode first) | **Removal from service** |
| **Monitor** (component watches health) | **Passive redundancy** (warm spare, periodic state updates) | **State resynchronisation** | **Transactions** (ACID) |
| **Heartbeat** (periodic message exchange) | **Spare** (cold spare, power-on reset on failover) | **Escalating restart** (vary the restart granularity) | **Predictive model** |
| **Timestamp** (detect wrong event order) | **Exception handling** | **Non-stop forwarding** (split supervisory and data plane) | **Exception prevention** (smart pointers, wrappers) |
| **Sanity checking** | **Rollback** (to the "rollback line") | | **Increase competence set** |
| **Condition monitoring** | **Software upgrade** (in service) | | |
| **Voting** (replication, functional or analytic redundancy) | **Retry** (transient faults) | | |
| **Exception detection** (timeouts, parameter fence) | **Ignore faulty behaviour** | | |
| **Self-test** | **Degradation** (keep critical functions, drop others) | | |
| | **Reconfiguration** | | |

The instructor's worked responses: log the fault, notify, disable the source, mask the fault, run degraded ("please log your request, the report will be emailed"), be temporarily unavailable ("service not available, try later"). Banking example: a **branch-level cache** lets customers view statements when the core network is down (remapping elements).

#### Performance [S-CS02], [T1 ch8]
- About **time**: responding to events (interrupts, messages, requests, clock ticks) within timing constraints.
- Stimulus: periodic, sporadic or stochastic arrivals. Measures: **latency, deadline, throughput, jitter, miss rate**. Example: *"Users initiate transactions under normal ops; average latency 2 s."*

| Control resource demand | Manage resources |
|---|---|
| Manage sampling rate | **Increase resources** (CPU, memory, network) |
| Limit event response (process up to a maximum rate) | **Increase concurrency** (threads) |
| **Prioritise events** | **Maintain multiple copies of computations** (replicas, load balancer) |
| Reduce overhead (remove intermediaries; this trades off against modifiability) | **Maintain multiple copies of data** (caching; many read replicas, one write DB [L-CS03]) |
| Bound execution times | **Bound queue sizes** |
| Increase resource efficiency (better algorithms) | **Schedule resources** |

#### Usability [S-CS02], [T1 ch11]
- How easily users accomplish tasks. It covers learning, efficient use, minimising the impact of errors, adapting, and confidence. The instructor called it the **"#1 QA of the last 10–15 years"** because users judge an app in 5 seconds. [L-CS01], [L-CS03]
- Example: *"User downloads a new app and is productive after 2 min of experimentation."*
- **Support user initiative**: **Cancel**, **Pause/Resume** (his example: a visa form that times out after 10 pages), **Undo**, **Aggregate**.
- **Support system initiative**: maintain a **task model** (where the user is in the task), a **user model** (agent vs applicant vs approver), and a **system model**.

#### Security [S-CS02], [T1 ch9]
- Protect data from unauthorised access while still serving authorised users. The core is **CIA: Confidentiality, Integrity, Availability**, supported by **Authentication, Authorisation and Non-repudiation**.
- Example: *"Disgruntled remote employee tries to modify the pay-rate table during normal ops → system keeps an audit trail; correct data restored within a day."*
- The tactic categories follow physical security: **Detect, Resist, React, Recover**.

| Detect attacks | Resist attacks | React to attacks | Recover |
|---|---|---|---|
| Detect intrusion (signatures) | Identify actors | **Revoke access** | Availability recovery tactics + **Audit** |
| Detect service denial | **Authenticate actors** | **Lock computer** (repeated failed attempts) | |
| Verify message integrity (checksum, hash) | **Authorise actors** | **Inform actors** | |
| Detect message delay | Limit access | | |
| | **Limit exposure** (smaller attack surface) | | |
| | **Encrypt data** | | |
| | **Separate entities** (VMs, air gap) | | |
| | Change default settings | | |

#### Modifiability [S-CS02], [T1 ch7] ★★★ (a favourite concept question)
- About the **cost and risk of change**. Ask three questions: *What can change? How likely is the change? When is it made and who makes it?*
- Example: *"Developer changes the UI at design time; done with no side effects in 3 hours."*

| Reduce module size | Increase cohesion | Reduce coupling | Defer binding |
|---|---|---|---|
| **Split module** | **Increase semantic coherence** | **Encapsulate**, **Use an intermediary**, **Restrict dependencies**, **Refactor**, **Abstract common services** | Bind as late as practical (parameters, config, plug-ins, pub-sub, registries) |

**Modifiability vs modify** [L-CS03]. The instructor explained this at length:
- **Modifiability** is designed in up front. It costs *more to build* and *less to change* later. Examples: SAP or Oracle Financials, a car chassis built to become anything from a truck to a sedan. *"Charge him the earth."*
- **Modify** means changing, after delivery, a system that wasn't designed for change. It is cheap to build and expensive to change. Example: cutting a Maruti into a limousine.
- Neither is always right. It depends on how long the system will live and how much change is expected.

**Maintainability ≠ maintenance resources** [L-CS02]. Maintainability is *the ease* with which a system can be maintained. Invest in it only if the system will live long and must keep changing. "If you don't spend on maintainability, you spend a lot on maintenance."

#### Interoperability [S-CS03], [T1 ch6]
- The degree to which two or more systems can **usefully exchange meaningful information**. It is a matter of degree, not yes or no. It needs **standard interfaces as well as protocols** (e.g. a JSON schema agreed industry-wide, not just JSON itself). [L-CS04]
- Example: *vehicle info system sends location to a traffic-monitoring system that overlays it on Google Maps; location correctly included 99.9% of the time.* The instructor also used the vehicular-LAN "car cluster" crossroads idea, Android intents, and SAP working with third-party fleet systems.
- **Locate**: **Discover service** (a directory, possibly with several levels of indirection).
- **Manage interfaces**: **Orchestrate** (e.g. Kubernetes-like coordination of service invocations), **Tailor interface** (add or remove capabilities: translation, buffering, smoothing, adapters).
- Checklist point: log requests, which is essential for non-repudiation in untrusted environments. Make sure a flood of requests can't exhaust critical resources.

#### Testability [S-CS03], [T1 ch10]
- The ease with which software **reveals its faults** through testing: the probability it fails on the next test if a fault exists. It needs **controllability and observability**.
- Example: *"Unit tester completes a code unit, runs a test sequence, results captured, 85% path coverage within 3 hours."*
- **Control & observe system state**: **Specialised interfaces**, **Record/playback**, **Localise state storage**, **Abstract data sources**, **Sandbox**, **Executable assertions** (pre-, post- and invariant conditions [L-CS03]).
- **Limit complexity**: **Limit structural complexity** (no cycles, isolate external dependencies), **Limit non-determinism**.

#### Other quality attributes (CS03 handout, [S-CS02] "Other QAs") ★
- **Variability** and **Portability** are special cases of modifiability. Also: **Development distributability**, **Deployability**, **Mobility**, **Monitorability**, **Safety** (same concerns as availability: prevent, detect, recover).
- **Scalability**: **horizontal** (scale out, e.g. add a server to a cluster) vs **vertical** (scale up, e.g. add memory).
- Other categories: **Conceptual integrity**, **Marketability**, **Quality in use** (effectiveness, efficiency, freedom from risk).
- **ISO/IEC 25010** standard list. Pros: a useful checklist. Cons: never complete, causes controversy, forces attention to irrelevant attributes.
- For a brand-new "X-ability" (e.g. green computing): **model it → assemble its tactics → build design checklists**.

#### Trade-offs ★★ (a recurring point)
You can't have everything: more security usually means lower performance; an intermediary helps modifiability but hurts performance; high availability costs money. The architect has to **balance**, explain the consequences to stakeholders, and get them to sign off. [L-CS01], [L-CS07]

---

## 4. CS04 & CS05: Architecturally Significant Requirements (ASRs) and design

### 4.1 What an ASR is ★★★
> A requirement that has a **profound, measurable effect on the architecture**. Without it, the architecture would likely be dramatically different. [S-CS05]

**Indicators** (lecture version [L-CS06 review]): **high business value**, **technical risk**, a **key stakeholder** with clout cares about it, **unique** functionality not handled by existing components, **non-standard QoS/SLA** needs, and **previously caused budget overruns** or client dissatisfaction.
**Drivers**: business goals and constraints · stakeholder concerns · quality attributes · regulatory compliance (GDPR, HIPAA) · technology constraints · cost and budget · **time to market**.
Plain functional requirements ("create an order") are not ASRs, but **hard** functional ones can be: real-time fraud detection, audit trail (file or DB?), notifications (SMS, email or queue? with acknowledgement?), third-party integration, workflow, a user-maintained rules engine.
Classify requirements as **Critical / Important / Useful** (only about 40% of features are actually used).
The instructor's project-management triangle: **scope, time, cost**. Fix any two and the third follows; fix all three and the project may be impossible. [L-CS05]

### 4.2 Four ways to find ASRs ★★★
1. **Requirements documents**: MoSCoW lists or user stories. QAs are often missing from them, so look for leads using the **7 design-decision categories** (e.g. the coordination model → look for named protocols and devices; binding time → look for regional or language variation).
2. **Interviewing stakeholders: the Quality Attribute Workshop (QAW)**. Its output is a list of architectural drivers and prioritised scenarios.
    1. QAW presentation and introductions
    2. **Business/mission presentation** (by a management representative, about 1 hour)
    3. **Architectural plan presentation** (by the architect)
    4. **Identify architectural drivers** (reach consensus on a distilled list)
    5. **Scenario brainstorming** (each scenario needs an explicit stimulus and response; at least one scenario per driver)
    6. **Scenario consolidation** (merge similar scenarios with the proposers' agreement)
    7. **Scenario prioritisation**: each stakeholder gets **votes = 30% of the number of consolidated scenarios** (e.g. 20 scenarios → 6 votes each)
    8. *(T1 adds)* Scenario refinement of the top scenarios into full six-part form
    - Why the instructor values it: silent stakeholders are made to speak up and **commit publicly**. [L-CS06]
3. **Understanding business goals: PALM (Pedigreed Attribute eLicitation Method)**. "Pedigree" means every QA requirement is traced back to the business goal it serves.
    1. PALM overview
    2. Business drivers presentation
    3. Architecture drivers presentation
    4. **Business goal elicitation** (using the standard categories, captured as scenarios)
    5. **Identify potential QAs from the business goals**
    6. **Assign pedigree** to the existing QA drivers ("why 40 ms and not 60 ms?")
    7. Conclusion
    - **Business goal format**: **"from X (current state) to Y (future state) by when"**, e.g. market share from 10% to 15% within a stated time.
    - **11 business-goal categories**: growth and continuity; financial objectives; personal objectives; responsibility to employees; to society (green computing); to the state (compliance); to shareholders; market position (IPR); business processes; product quality and reputation; environmental change (e.g. USD volatility).
    - A business goal can: (a) lead to a QA requirement, (b) affect the architecture directly without any QA, or (c) have no architectural influence at all (a non-architectural solution).
    - Example: government wants more cashless transactions → **BHIM** app → QAs of **usability** (easy enough for a tea-stall owner) and **security** (3-factor).
    - Rule: **the business owns the goal-to-QA link; the architect owns delivering measurable QAs.** [L-CS06]
4. **The utility tree** (below).

### 4.3 The utility tree ★★★ (in assignment 1 and highly likely in the exam)
```
Utility (root) ─┬─ Performance ─┬─ Transaction response time ── scenario ... (H,M)
                │               └─ Throughput ── scenario ... (M,M)
                ├─ Usability ── Proficiency training ── scenario ... (M,L)
                ├─ Security ── Confidentiality / Integrity ── scenarios ...
                └─ Availability ── No downtime ── scenario ... (H,L)
```
- **Root** = overall "utility" (how well the system satisfies stakeholders; you need not draw it). **Branches** = quality attributes. **Sub-branches** = attribute refinements (a short heading). **Leaves** = **concrete six-part scenarios**.
- Each leaf gets a **pair of ranks: (importance to business, impact on architecture)**, each H, M or L. **(H,H)** leaves get top priority for design *and* for testing.
- Nightingale hospital example [S-CS05]. Parse it as a scenario: *"A user (source) updates a patient's account (artifact) in response to a change-of-address notification (stimulus) while the system is under peak load (environment), and the transaction completes (response) in < 0.75 s (measure). (H,M)"*
- Other Nightingale leaves: 150 transactions/s at peak (M,M); a new hire proficient in < 1 week (M,L); a fee change made by configuration in 1 day with no code change (H,L); a DB vendor upgrade hot-swapped with no downtime (H,L); a physiotherapist sees only orthopaedic records (H,M); intrusion reported within 90 s (H,M).
- "What's the best approach?" The instructor's view: the architect is accountable for ASRs **even when no one wrote them down**. Plan stakeholder interviews early. The utility tree works like a repository. Choose the method that fits the time available.

### 4.4 Architecture design: strategy and ADD (handout CS5; slides only name them) ★★
See §9.1 for the steps (from the textbook). From the lectures: the architect **freezes only what must be frozen** and delays the rest ("always delay decision making" beyond the necessary). [L-CS01], [L-CS04]

### 4.5 Architecture in Agile projects ★★★ (in both the CS04 and CS05 decks)
- **Agile Manifesto**: individuals and interactions > processes and tools; working software > comprehensive documentation; customer collaboration > contract negotiation; responding to change > following a plan. There are also **12 principles** (e.g. early and continuous delivery, welcome late changes, simplicity, self-organising teams produce the best architectures).
- **"How much architecture?" (Boehm & Turner)**: more up-front architecture and risk resolution adds schedule time but reduces **rework**. Adding the two curves gives a **sweet spot**:
    - **10 KSLOC** → sweet spot at the far left (little or no up-front work)
    - **100 KSLOC** → about **20%** of the schedule
    - **1,000 KSLOC** → about **40%** of the schedule
    - The instructor's analogy: dinner for 2 (no planning) vs a family of 10 (some) vs a 1,000-guest wedding (an event planner). [L-CS04]
- A **"late break"** is a failure discovered late (at installation) that forces heavy rework. Agile and frequent demos reduce it. [L-CS04]
- **Agility and documentation**: *"Write for the reader. If no one needs it, don't write it"*, but remember future maintainers.
- **Agility and evaluation**: ATAM fits Agile. It focuses only on the top scenarios and can be made lightweight.
- **WebArrow case**: the team worked top-down (structures for QAs) and bottom-up (implementation constraints) at the same time, and ran **experiments ("spikes")**: distributed DB vs flat files → latency? mod_perl vs Perl → scalability? how many participants per meeting server? what ratio of DB to meeting servers?
    - **Spike vs POC** [L-CS04]: a spike is an architecture/Agile term for a *practical* experiment at the **subsystem** level. A POC is the programmer's equivalent at the code level.
- **Incremental Commitment Model (Boehm)**: stakeholder commitment and accountability; "satisficing"; incremental growth of the definition; iterative development; definition and development interleaved; risk-driven anchor-point milestones.
- **The authors' advice**: large system + stable requirements (or distributed development) → do a lot up front. Large + unstable → a quick candidate architecture, then evolve it through spikes. Small + uncertain → just agree on the major patterns.
- Agile architects propose an initial architecture and **refactor when the technical debt grows too large**. Agile works **inside an architectural framework**; the two are not opposites. [L-CS04]

---

## 5. CS06: Documenting architecture, structures and views, 4+1

### 5.1 Elements and relations of each structure ★★★ (table from [S-CS06])
| Structure | Relations | Useful for |
|---|---|---|
| Decomposition | is a submodule of; shares secret with | Resource allocation, project structuring, information hiding, configuration control |
| Uses | requires the correct presence of | Engineering subsets and extensions |
| Layered | requires presence of; uses services of; provides abstraction to | Incremental development, "virtual machines", **portability** |
| Class | is an instance of; shares access methods of | Rapid near-identical implementations from a template (OO) |
| Client-server | communicates with; depends on | Distributed operation, separation of concerns, performance analysis, **load balancing** |
| Process | runs concurrently with; excludes; precedes | Scheduling and performance analysis |
| Concurrency | runs on the same logical thread | Finding resource contention and fork/join points |
| Shared data | produces data; consumes data | Performance, data integrity, modifiability |
| Deployment | allocated to; migrates to | Performance, availability, security analysis |
| Implementation | stored in | Configuration control, integration, test |
| Work assignment | assigned to | Project management, best use of expertise, managing commonality |

- In a **strictly layered** structure, layer *n* may only use layer *n−1*.
- The relation in every C&C structure is **attachment**.

### 5.2 Kruchten's 4+1 view model ★★★
| View | Concerns | Main viewers | Maps to (SEI) | Notation and example |
|---|---|---|---|---|
| **Logical** | Functional requirements, key abstractions (objects and classes) | **End users** | **Module** | Booch notation / UML class and package diagrams; PABX: Conversation, Terminal, Controller, Numbering plan… |
| **Process** | Concurrency, synchronisation, distribution, **performance, scalability** | **Integrators** | **C&C** | Garlan & Shaw styles; major tasks vs minor/helper tasks; sync vs async, RPC, event broadcast |
| **Development** | Static organisation of modules and libraries, layers, reuse, tool constraints | **Programmers, software managers** | **Allocation** (to the development environment) | Layered style (e.g. the ATC system in 5 layers: domain-independent bottom two, domain-specific top) |
| **Physical** | Mapping software to hardware; **reliability, availability, performance** | **System engineers** | **Allocation** (deployment) | Nodes and links (dotted = non-permanent, arrow = one-way, thick = high bandwidth); a test/dev configuration and a deployment configuration |
| **+1 Scenarios** | Consistency and validity; ties the 4 views together | **All users, evaluators** | — | Like the logical view / communication diagram (e.g. PABX "local call": off-hook → dial tone → digits → connection) |

- **Careful:** in 4+1, "scenario" means a **use-case story**, *not* the six-part QA scenario. [L-CS06]
- **Correspondence between views**: logical → process has two strategies, **inside-out** (start from the logical view) and **outside-in** (start from the physical view). Logical → development: grouping into subsystems depends on team organisation, class categories/packages and lines of code.
- The process is iterative and scenario-driven, and **not every system needs every view**. Two artifacts result: a Software Architecture Document (following 4+1) and **Software Design Guidelines**. A weakness: no tooling to integrate the views, which leads to inconsistency during maintenance.
- **"Use SEI definitions for *what* to document and 4+1 for *who* you are documenting for."** [S-CS06]
- **Choosing views** [S-CS06]: complex UI → Logical; high performance or traffic → Process; large distributed team → Development; cloud-native or security-heavy → Physical. *Document only what is needed to communicate and to reduce risk.*
- Modern updates: Logical = UML 2.5 / bounded contexts / API contracts; Process = containers, serverless, sequence and activity diagrams, eventual consistency; Development = CI/CD, monorepo vs multi-repo, dependencies; Physical = VMs, Kubernetes, IaC, elasticity, gateways and load balancers.
- **Architectural drift**: code changes faster than the documents. Fixes: **architecture as code** (Mermaid, PlantUML stored in Git) and **fitness functions** (automated checks that dependencies don't break the layering). The goal is a living document.
- Documentation must suit its **audience**, and notation can be informal **if you provide a key/legend** (acceptable in this course). [L-CS04], [L-CS06]

---

## 6. CS07: Layered architecture and ATAM

### 6.1 Layers and techniques for each layer ★★★
Rule: **each layer uses only the layer directly below it.** Never put SQL in the presentation layer ("disastrous"). The presentation layer is "powder and lipstick" and does no thinking, not even adding two numbers. [L-CS07]
**Benefits**: separation of concerns, **loose coupling**, reusable lower-layer components (push common services downwards), **exchangeable parts** (swap a UI layer or data layer; blue-green deployment of a new DAL). Patterns in practice allow **exceptions**; they are models, not scripture.

| Layer | Role | Techniques |
|---|---|---|
| **Presentation** | UI and UX (React, Angular, mobile) | **Caching**: client-side (browser: user preferences, payment method, address) vs server-side (product codes, promotions), usually a combination; **Memcached** (distributed in-memory cache that takes load off the DB); **AJAX** (async partial page refresh: category → product list, loan-limit validation, chat panel, captcha reload; Google Maps and Suggest); **responsive design** (flexible grids, HTML5/CSS3) |
| **Business** | The heart: validation, rules, processing | **Application facade** (a unified interface that hides subsystems; e.g. flight booking fronting Schedule, Seat inventory and Pricing); **session management** (client-side cookies vs server-side; EJB **stateful** = same bean instance per client vs **stateless** = the client holds the state); **workflow and rules engines** (for modifiability; e.g. insurance policy processing, BizTalk, BPEL, Drools); **aspect-oriented design** for cross-cutting concerns (logging and instrumentation, auditing, caching, security) |
| **Data access (DAL)** | Persistence | **Connection pool** (singleton), **multiple copies of data** for reads, **transactions** (atomicity), **ORM** (Hibernate), **stored procedures** (performance), **parameterised SQL** (stops SQL injection: `WHERE name = ?` instead of concatenating `'x' OR 'x'='x'`) |
| **Service** | APIs for external consumers (e.g. a bank's Get Balance or Request Chequebook) | Must handle **duplicate requests** (idempotency), **out-of-sequence messages**, and **communication failure** (retry, or queue and send once the link is back) |

**Coupling vs cohesion** (the instructor's marriage analogy): **low coupling + high cohesion = good.** A module should handle its own job independently, without duplicating shared services. [L-CS07]
**Logging vs instrumentation**: log actionable errors ("DB unavailable"), and log sparingly because it is expensive. Instrumentation measures request rate, error rate, duration and queue length. Log4j supports priority levels.

**Exercises from the slides (likely exam style), with answers**
- **Aadhaar registration screen is slow** because of the State/District/Town drop-downs → **cache** the lists in the back end + **AJAX** to load districts and towns dynamically.
- **A hotel system must let MakeMyTrip query and book** → a **service layer** with `GetRoomAvailability(from, to) → rooms by type` and `ReserveRoom(n, type, from, to) → success/failure`.
- **A shipping/container logistics system must hide container, transporter and ship-finder modules from clients** → a **facade in the business layer** (a unified "place shipping request" API).
- **Airline DCS**: identify its components in each layer.
- Appendix topics: SSL handshake (certificate → verify against CA → symmetric session key encrypted with the server's public key → encrypted session), IPSec (IP-packet-level security), Log4j.

### 6.2 ATAM (Architecture Tradeoff Analysis Method) ★★★ (slides are mostly images; content from T1 ch21 + lecture)
**Why evaluate**: to "fail early". Fixing a problem costs less the earlier you find it. ATAM finds **risks and trade-offs**.
**Three forms of evaluation**:
1. **By the designer**: continuous, during design (generate and test).
2. **Peer review**: reviewers determine the QA scenarios (lightweight) → the architect presents → walk through each scenario → capture problems. Peers can be biased (halo effect, shared blind spots). [L-CS07]
3. **By outsiders**: neutral, "paid to break the design", more expensive (e.g. the Air Force hiring another company to review).

**Contextual factors**: which artifacts exist, who sees the results, who performs the evaluation, which stakeholders take part, the business goals.

**Key definitions** (very likely asked):
- **Risk**: an architectural decision that may lead to undesirable consequences for a QA. The instructor's analogy: choosing the make-up exam lets you study for 2 exams, but if you fall ill there's no "make-up for the make-up".
- **Non-risk**: a sound decision, judged safe.
- **Sensitivity point**: a property where a **small change in input causes a large change in a QA response**.
- **Trade-off point**: a property that affects **more than one QA** in opposite directions (e.g. encryption level: security up, performance down).
- **Risk themes**: groups of related risks that point to systemic weaknesses and are tied back to business goals.

**Participants**: the **evaluation team**, **project decision-makers**, and **architecture stakeholders**.
**Evaluation team roles** [S-CS07]:
- **Team leader**: sets up the evaluation, handles the client and the contract, and ensures the final report is delivered.
- **Evaluation leader**: runs the evaluation, facilitates scenario elicitation, prioritisation and analysis.
- **Scenario scribe**: writes scenarios on the board and captures the agreed wording.
- **Proceedings scribe**: keeps the electronic record of raw scenarios, the issue behind each one, and each resolution.
- **Questioner**: raises issues of architectural interest from their QA expertise. The instructor calls this person the "stoker" who gets discussion going.

**Outputs**: a concise presentation of the architecture · articulated business goals · **prioritised QA requirements as scenarios (utility tree)** · **risks and non-risks** · **risk themes** · a mapping of architectural decisions to QA requirements · **sensitivity and trade-off points**. **Intangibles**: a sense of community among stakeholders, open communication channels, better understanding of the architecture's strengths and weaknesses.

**Phases**
| Phase | Activity | Duration |
|---|---|---|
| 0 | Partnership and preparation | Informal, a few weeks |
| 1 | Evaluation, **steps 1–6** (evaluation team + decision-makers) | 1–2 days, then a 2–3 week break |
| 2 | Evaluation, **steps 7–9** (+ stakeholders) | 2 days |
| 3 | Follow-up: report and process improvement | 1 week |

**The 9 steps** ★★★ (a possible direct question)
1. **Present the ATAM**
2. **Present the business drivers** (by the project manager)
3. **Present the architecture** (by the architect)
4. **Identify architectural approaches** (patterns and tactics)
5. **Generate the QA utility tree**
6. **Analyse architectural approaches** (map the high-priority scenarios onto the architecture → risks, non-risks, sensitivities, trade-offs)
7. **Brainstorm and prioritise scenarios** (all stakeholders vote)
8. **Analyse architectural approaches** (again, with the new scenarios)
9. **Present results**

**Lightweight ATAM** (for internal or Agile teams, **4–6 hours**): step 1 takes 0 h; step 2 about 0.25 h; step 3 about 0.5 h; step 4 about 0.25 h; step 5 takes 0.5–1.5 h (reuse existing trees); **step 6 takes 2–3 h (most of the time)**; steps 7 and 8 take **0 h (omitted)**; step 9 about 0.5 h.

---

## 7. CS08: Conformance, testing and reconstruction

### 7.1 Conformance and architectural drift ★★★
**Drift examples**: skipping a layer (layer 1 calls layer 3 directly); accessing the DB without going through the DAL; notifying modules one by one instead of using **publish-subscribe**; home-grown logging instead of the common Log4j. These are usually "fix it later" shortcuts, which is **technical debt** (and 80–90% of it is never repaid, as one student observed).
**Four techniques to keep code and architecture consistent** [S-CS08]:
1. **Embed the design in the code (architecturally evident coding style)**: state in the code which layer it belongs to, publisher or subscriber, MQ producer or consumer.
2. **Use frameworks**: Spring (MVC: Model = data, View = rendering, Controller = handles requests and coordinates), Hibernate, AUTOSAR, JMS pub-sub, Salesforce workflow, Drools, Log4j, .NET/WCF.
3. **Use code templates**: e.g. the fault-tolerant primary/backup template (Normal → process and send state to backup; Update state; Switch-over → notify clients).
4. **Update the architecture documentation**: at least mark outdated parts "no longer applicable" (this keeps the rest trustworthy), and sync the documents with the code at every release.

**Extra techniques** (slide exercise): **educate new team members**, **code reviews** and periodic architecture reviews, **folders per architectural aspect** (layer, service, UI, interfaces). In Scrum, the architect (or a representative) attends the ceremonies, and the **product owner** must know the architecture. [L-CS08]

**Publish-subscribe as the instructor explained it**: the publisher keeps the data and a list of subscribers. It **pushes only a notification**; each subscriber **pulls** the data it wants. MVC is similar, with a controller acting as coordinator.

### 7.2 How architecture helps testing ★★
1. **Prioritise test cases using the ASRs**: the **utility tree's (H,H) scenarios become the high-priority test cases**. "Whatever is the priority in development is the priority in testing."
2. **Build the integration test plan**: the architecture shows which modules interact and depend on each other.
3. **Design for testability**: switch between test and production data sources; **roll back** test changes; **replace components with simulators** (payment gateway, sensors, Aadhaar). The instructor's example: an **adapter** or factory pattern that makes payment gateways hot-swappable.

### 7.3 Architecture reconstruction ★★★ (a known trap)
> **Reconstruction = determining, documenting and presenting views of the architecture of a system that ALREADY EXISTS** (from code, binaries, traces, build scripts, people). It is **NOT** designing a new architecture and **NOT** modifying an old one. That would be modification. [L-CS08]
> You often reconstruct *so that* you can modify safely ("don't put your hand in the oven without knowing whether it's on").

**Purposes**: understand an undocumented system; migrate old technology to new (mainframe → web); identify reusable components (logging, security). The fuller list of goals [L-CS08]: documentation, reuse, **conformance**, co-evolution, analysis, evolution.
**Phases** ★★★
1. **Raw view extraction**: pull information from **source code, execution traces and build scripts**: classes, files and data used, **caller–callee** relations, global data access (e.g. `#include`, DLLs).
2. **Database construction**: store the extracted data in a common format.
3. **View fusion**: combine views, e.g. **static** (source analysis) + **dynamic** (execution traces, which reveal runtime binding) + **expert grouping** into layers → one consolidated view (Sonar: layers and vertical slices).
4. **Architecture analysis (finding violations)**: check conformance to the rules, e.g. "a layer calls only the adjacent layer", "all DB access goes through entity beans", "no application code depends on JUnit".
5. **Iterate.**

The simpler 3-phase version in the slides: identify components and relations (with a tool) → aggregate them into abstract components → analyse.
**Approaches**: top-down, bottom-up or hybrid. **Inputs**: non-architectural (source, docs, traces, operation guides, physical and human organisation, history, human expertise) and architectural (styles, viewpoints, frameworks). **Techniques**: quasi-manual (construction, exploration), semi-automatic (abstraction, investigation), quasi-automatic (concepts, clustering, dominance, metrics). **Outputs**: visual views, full documentation, analysis. **Conformance** is **vertical** (consistent from top level to bottom) or **horizontal** (within one level, e.g. the DAL follows its specification).
**Tools**: **Dali, ARMIN, Lattix, SonarJ/SonarQube, Structure101**, DiscoTect, and today LLM tools (students reported using Claude Code to reconstruct views from source code). **The "Vanish" case**: ARMIN produced a "white-noise" view of everything → aggregation → analysis showed the system was **not strictly layered**.
*You won't be asked to use the tools, only to know that they exist and what they are for.* [L-CS08]

---

## 8. Common confusions the instructor warned about ★★★

| Confusion | Correct understanding |
|---|---|
| Reconstruction = redesign | **Reconstruction** recovers and documents an *existing* architecture. Changing it is **modification**. |
| Maintainability = resources for maintenance | Maintainability is the **ease** of maintaining, which is designed in and costs up front. |
| Modifiability = modifying | **Modifiability** is planned flexibility (expensive to build, cheap to change). **Modify** means changing a system not built for change (cheap to build, expensive to change). |
| Structure = view | **Structure** is what exists (the table). **View** is its representation for stakeholders (the DB view). |
| CIA's "A" = authorisation | In CS03 the instructor said "A is authorisation". The **slides and textbook say A = Availability**; authorisation is a *supporting* property alongside authentication and non-repudiation. Use the slide version in the exam. |
| Source = artifact | **Source** generates the stimulus (e.g. the heartbeat monitor). **Artifact** is what is stimulated (e.g. the server). |
| Scenario (QA) = scenario (4+1) | A QA scenario has 6 parts. The 4+1 "+1 scenario" is a use-case story. |
| Listing all tactics = a good answer | **Choose** the relevant tactic(s) for the case and **justify** them, or you may score zero. |
| Pattern = tactic | A pattern is a strategic package of tactics. A tactic fine-tunes one QA. |
| Architectural pattern = design pattern | Architectural patterns are about subsystems interacting. Design patterns are about classes interacting. |
| Architecture = system design | Architecture is the macro model (subsystem interaction). Design is classes, sequence diagrams, UML (not in this course). |
| Agile vs architecture | They complement each other. Freeze only what must be frozen; stay Agile inside the framework. |
| Spike = POC | Similar. A spike is at the architecture or subsystem level; a POC is at the code level. |
| Comprehensive covers only CS9–16 | The comprehensive covers **CS1–16**, and CS9–16 builds on CS1–8. |

---

## 9. Handout topics with little or no lecture coverage (from T1 / standard material)
*The lectures didn't cover these in depth. They are summarised here so you aren't caught out, since the AI question tool is also fed the handout and textbook.*

### 9.1 Design strategy and Attribute-Driven Design (ADD) [H CS5], [T1 ch17]
- **Design strategy**: **decomposition** (from the whole system down); **design to the ASRs**; **generate and test** (form a design hypothesis from existing systems, frameworks, patterns and tactics, domain decomposition or design checklists, test it against the ASRs, then refine).
- **ADD steps** (recursive):
    1. **Choose an element** of the system to design (start with the whole system)
    2. **Identify the ASRs** for that element
    3. **Generate a design solution** for it (patterns and tactics, allocated responsibilities)
    4. **Inventory the remaining requirements** and choose the input for the next iteration
    5. **Repeat** until all ASRs are satisfied

### 9.2 Documentation package, combining views, QA views [H CS6], [T1 ch18]
- **Uses of documentation**: education (onboarding), the main vehicle for stakeholder communication, and the basis for analysis and construction.
- **Documenting one view**: primary presentation · element catalogue (elements, relations, interfaces, behaviour) · context diagram · variability guide · rationale.
- **Documentation beyond views**: roadmap · how a view is documented · system overview · **mapping between views** · rationale · directory (index, glossary, acronyms).
- **Combining views**: good candidates are views with a strong association, e.g. deployment + C&C, decomposition + work assignment. Correspondences can be one-to-one, one-to-many or many-to-many.
- **Documenting behaviour**: **trace-oriented** (use cases, sequence, communication and activity diagrams) vs **comprehensive** (state machines).
- **Quality-attribute views** extract the parts relevant to one QA: **security view** (security components and flows), **communication view** (channels, protocols, retries), **exception/error-handling view**, **reliability view** (redundancy, failover), **performance view**.

### 9.3 Hatley-Pirbhai architecture template [H CS6]
A systems-engineering template that places functions in **5 regions**:

| | Top: **User-interface processing** | |
|---|---|---|
| **Input processing** (left) | **Main functions / process & control** (centre) | **Output processing** (right) |
| | Bottom: **Maintenance & self-test processing** | |

- It comes with an **Architecture Context Diagram (ACD)**, **Architecture Flow Diagrams (AFD)** and **Architecture Interconnect Diagrams (AID)**, which trace from the requirements model (data and control flow) to the architecture modules.

### 9.4 Scalability, integration, design trade-offs [H CS3]
- **Scalability**: horizontal (scale out) vs vertical (scale up). Tactics overlap with performance (replicas, load balancing, caching, partitioning or sharding, stateless services, async queues). Avoid **hard-coded resource limits** [S-CS01].
- **Integration**: bringing separately built parts or systems together. See interoperability tactics (discover, orchestrate, tailor interface) and the service layer (idempotency, retries, queues).
- **Trade-offs**: security ↔ performance, modifiability (intermediaries) ↔ performance, availability (redundancy) ↔ cost, usability ↔ security, testability (logging) ↔ performance.

### 9.5 Real-time architectures [H CS8]
- Hard vs soft deadlines. The core tactics are the performance ones: **prioritise events, bound execution times, schedule resources** (rate-monotonic or EDF), predictable technology (RTOS, C/embedded C rather than garbage-collected runtimes, which the instructor mentioned in CS04 when discussing language choice).
- Often combined with availability tactics (non-stop forwarding, hot spares) in avionics, radar and ATC systems.

---

## 10. Practice questions (in the style the instructor described: small cases, pointed answers)
1. A hospital's patient-record service must stay available 99.99% of the time. Write a **concrete availability scenario** (all 6 parts), then pick **two** tactics and justify them.
2. An e-commerce site slows down during sales. Which **performance** tactics apply, and what is the **trade-off** with modifiability?
3. For a **payroll system** (the disgruntled-employee case), write a security scenario and name the tactics for *detect*, *resist* and *recover*.
4. Build a **utility tree** with 5 leaves for an online exam portal, ranked (Business, Architecture).
5. Explain **modifiability vs modify** with an example. When should a client pay for modifiability?
6. How does **choice of technology** affect **testability**? (Or: how does the **coordination model** affect **availability**?)
7. List the **QAW steps**. How are the votes allocated?
8. Write a business goal in the "from X to Y by when" format for a food-delivery app and trace a QA to it (PALM "pedigree").
9. Map **Kruchten's 4+1 views** to the SEI structure types. Which view for integrators, and which for system engineers?
10. Which **structure** answers "which team builds this?" and "what runs in parallel?"
11. For the Aadhaar drop-down problem, which techniques in which layer?
12. Define **risk, non-risk, sensitivity point, trade-off point**. List the **9 ATAM steps** and what gets skipped in lightweight ATAM.
13. Give 4 examples of **architectural drift** and 4 **conformance techniques**.
14. A 20-year-old undocumented banking system must be migrated. Describe **architecture reconstruction**: its phases, inputs and tools. (Don't describe the new design!)
15. How does **architecture help testing**? Link the utility tree to test priority.
16. Using the Boehm–Turner curves, how much up-front architecture suits a 10, 100 and 1,000 KSLOC project, and why?