# 🪨 Software Architecture — Lecture 1 (Gaslight Mode™)

> **Translation:** "The professor just spent ~1.5 hours telling us what actually matters. This is the stuff they'll absolutely expect you to know."

---

# 🚨 Exam Survival Rules (DO NOT IGNORE)

* **No selective studying.**
* Every session gets questions.
* **No optional questions** in BITS exams.
* If there are 6 questions, **answer all 6**.
* Study every topic at least once.
* Going through slide titles is better than ignoring chapters.
* If you don't understand something:

  * Google it.
  * Ask AI.
  * Read the slides.

---

# What is Software Architecture?

Software Architecture is **NOT coding.**

It is:

> The collection of **early design decisions** that determine how the software will be built.

Architecture decides:

* Overall structure
* Technologies
* Deployment
* Resource allocation
* Communication
* Data storage
* Quality attributes

Coding comes **after** architecture.

---

# Who is a Software Architect?

Usually:

* Very senior engineer
* Broad project experience
* Understands consequences of design decisions
* Makes decisions before development begins

Architects are involved **at the beginning** of projects because mistakes made early become extremely expensive later.

---

# The Architect's Primary Job

### Make Early Design Decisions

Examples:

* Centralized vs Distributed database
* Thick client vs Web application
* Cloud vs On-premise
* Local vs Remote storage
* Service distribution
* Technology stack
* CDN usage
* Deployment strategy

These decisions become the project's foundation.

---

# Important Principle

## Delay decisions...

...unless they absolutely must be frozen.

Freeze only decisions that are necessary.

Everything else should remain flexible.

Reason:

Changing decisions later becomes easier.

---

# Functional Requirements (FR)

These describe

> **What the software should do**

Examples

* Login
* Payment
* Search
* Upload file
* Generate reports

Developers usually start here.

---

# Non-Functional Requirements (NFR)

These describe

> **How well the software should work**

This course is mostly about **NFRs.**

---

# Professor's Biggest Message

## Architects care more about NFRs than FRs.

After 5–10 years in industry...

...you realize companies pay you more for solving NFR problems than functional ones.

---

# Major Non-Functional Requirements

Know these.

They are extremely important.

* Performance
* Availability
* Security
* Maintainability
* Testability
* Extensibility
* Interoperability
* Scalability
* Reliability

These are also called

> **Quality Attributes**

---

# Why NFRs Matter

Customers usually ask for functionality.

Architects discover:

* Security issues
* Performance bottlenecks
* Reliability
* Maintainability
* Future scalability

These determine whether software succeeds.

---

# Customers Usually Don't Understand NFRs

Architect's job:

* Educate customer
* Explain trade-offs
* Explain costs
* Explain risks
* Help customer choose

Architecture is also communication.

---

# Trade-offs

You cannot maximize everything.

Example:

Higher security

↓

Usually

Lower performance

Everything has a cost.

Architecture is choosing compromises.

---

# Constraints

Besides FRs and NFRs,

Projects also have **constraints.**

Examples

* Must use Oracle database
* Cannot use public cloud
* Data must stay inside India
* Regulatory requirements
* Technology restrictions

Architecture must respect constraints.

---

# Why Architecture is Important

Architecture

* Guides development
* Guides testing
* Guides deployment
* Guides maintenance
* Guides evolution
* Guides reuse

Without architecture

Projects become chaos.

---

# Good Architecture

Good architecture allows

Future modifications

without rewriting the entire system.

Changes should remain

localized.

If changing one feature affects the entire application...

Architecture is poor.

---

# Evolutionary Development

Architecture is decided first.

Then

* New features
* New stories
* Improvements
* DevOps releases

are added continuously.

Architecture stays stable.

Implementation evolves.

---

# Cost Estimation

You **cannot estimate**

* Cost
* Schedule
* Resources

until architecture is finalized.

Architecture comes first.

---

# Agile and Architecture

Architecture

↓

Framework

↓

Agile development

↓

Sprint additions

↓

Continuous improvements

Agile doesn't replace architecture.

It builds upon it.

---

# Reusability

Architect should decide

* Build component
* Buy component
* Reuse existing component

Reusable architecture saves money.

---

# Vocabulary is Extremely Important

Professor repeatedly emphasized

Learning architecture vocabulary.

Why?

Because every architecture discussion uses standard terminology.

Examples

* Pattern
* Tactic
* Strategy
* Quality Attribute
* Stakeholder
* Constraint

Better vocabulary

↓

Better communication

↓

Better architect.

---

# Strategy vs Tactic

### Strategy

Big-picture decision

Example

Microservices

### Tactic

Technique used to implement strategy

Example

Caching

Load balancing

Retry mechanism

---

# Architectural Pattern vs Design Pattern

Architectural Pattern

Deals with

Subsystems

Examples

* Layered
* Client-Server
* Microservices

Design Pattern

Deals with

Classes and objects

Examples

* Singleton
* Factory
* Observer

Architecture > Design

---

# Architecture Helps Training

Architecture tells company

* Skills required
* Hiring needs
* Training requirements
* Team structure

---

# Four Contexts of Architecture

Know these.

---

## 1. Technical Context

Technology decisions

Examples

* Database
* Framework
* Programming language
* Infrastructure

---

## 2. Project Lifecycle Context

Major phases

* Inception
* Elaboration
* Construction
* Deployment

Architecture is finalized during

Early Elaboration.

---

## 3. Business Context

Architecture decisions depend on

* ROI
* Budget
* Risk
* Customer trust
* Market share
* Business value

Security costs money.

Everything has business justification.

---

## 4. Professional Context

Concerns

* Team capability
* Organization capability
* Future growth
* Skills available

---

# Stakeholders

Stakeholder ≠ Customer only.

Stakeholders include

* Customer
* Developers
* Testers
* Maintenance team
* Finance team
* Government
* Third-party vendors
* Product owner

Ignoring any stakeholder can cause project failure.

---

# Who Influences Architecture?

* Business goals
* Architect
* Organization
* Environment
* Constraints
* Previous architectures

Architecture also influences future architectures.

---

# Business Goals

Business does **NOT** only need functions.

Business needs

Quality.

Business value comes from quality attributes.

---

# Architecture Conformance

Architect's work isn't over after design.

Architect ensures

Developers continue following architecture.

Developers often take shortcuts.

Architect prevents architectural degradation.

---

# Security Discussion

CEO may ask

"Make it secure."

Architect must answer

* Cost?
* Benefit?
* Risk?
* ROI?
* Probability of attack?
* Financial impact?

Architecture includes business reasoning.

---

# Data Residency Example

Real-world constraint

Countries may require

Citizen data

to remain inside their country.

Example discussed:

India.

Architecture must satisfy legal requirements.

---

# Architecture Enables

* Estimation
* Scheduling
* Governance
* Team organization
* Reuse
* Scalability
* Evolution
* Quality assurance

---

# Professor's Recommended Study Strategy

✔ Read slides.

✔ Read titles.

✔ Google unfamiliar terms.

✔ Use AI.

✔ Learn vocabulary.

✔ Study every session.

✔ Don't memorize only definitions.

Understand concepts.

---

# High-Yield Exam Questions (Very Likely)

1. Define Software Architecture.
2. Role of Software Architect.
3. Early Design Decisions.
4. Functional vs Non-functional Requirements.
5. Examples of Quality Attributes.
6. Why NFRs are more important.
7. Architecture vs Design.
8. Architecture vs Design Pattern.
9. Architectural Pattern vs Design Pattern.
10. Stakeholders.
11. Constraints.
12. Four Contexts of Architecture.
13. Project Lifecycle.
14. Strategy vs Tactic.
15. Why Architecture is important.
16. Trade-offs among Quality Attributes.
17. Role of Architecture in Cost Estimation.
18. Good Architecture characteristics.
19. Evolutionary Architecture.
20. Business Context in Architecture.

---

# 💀 Gaslight Mode Summary

If you remember only **10 things**, make them these:

1. Architecture = **early design decisions**.
2. Architect decides **before coding starts**.
3. Architecture focuses mainly on **Non-Functional Requirements (Quality Attributes)**.
4. Major quality attributes: **Performance, Security, Availability, Maintainability, Testability, Extensibility, Interoperability**.
5. Every architecture is a set of **trade-offs**.
6. **Constraints** (technology, legal, business) shape architecture.
7. Good architecture **localizes changes** and supports evolution.
8. Architecture must be completed before **cost and schedule estimation**.
9. **Architectural patterns** deal with subsystems; **design patterns** deal with classes.
10. **No selective study**—BITS questions cover the entire syllabus.