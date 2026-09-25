If you have **only 1 hour**, do **not** try to study the whole handout equally. For a case-study paper, your goal is:

> **Recognise the concept → define it in 1–2 lines → apply it to the case → justify your answer.**

Here is your **60-minute emergency revision sheet for CS01–CS07**.

---

# 🚨 60-MINUTE SPM EXAM CRASH PLAN

```text
00–10 min → CS01 Product Management
10–18 min → CS02 Discovery
18–27 min → CS03 MVP / Stories / Development
27–36 min → CS04 Prioritisation / Roadmap
36–47 min → CS05 Agile / Scrum
47–55 min → CS06 Estimation / Metrics / Technical Debt
55–60 min → CS07 Story Mapping / Roadmap + final recall
```

---

# 🟢 CS01 — PRODUCT MANAGEMENT FUNDAMENTALS

## ⏱️ 10 minutes

### 1. Product Management

**Definition:**

> Product Management is the discipline of identifying customer problems, defining what should be built, delivering value, and continuously improving the product.

### Remember

```text
Problem → Solution → Build → Release → Measure → Improve
```

---

### 2. Product Manager

**Definition:**

> A Product Manager is responsible for maximising product value by understanding customers, defining product direction, prioritising work and coordinating stakeholders.

### PM mainly thinks about:

* **Why** are we building it?
* **What** should we build?
* **For whom?**
* **What should come first?**
* **How do we know it succeeded?**

---

### 3. Product vs Project

| Product             | Project                   |
| ------------------- | ------------------------- |
| Continuous          | Temporary                 |
| Ongoing evolution   | Defined start/end         |
| Customer outcomes   | Deliverable/scope         |
| Continuous feedback | Usually defined objective |

### Exam trick

If case says:

> "Build X within six months."

Think **project**.

If case says:

> "Continuously improve X for customers."

Think **product**.

---

### 4. Product Thinking

> Focus on **customer problems and outcomes**, rather than simply building features.

### Remember:

❌ "Competitor has AI, so let's build AI."

✅ "What customer problem would AI solve?"

---

### 5. Product Lifecycle

```text
Idea
 ↓
Development
 ↓
Launch
 ↓
Growth
 ↓
Maturity
 ↓
Decline / Renewal
```

### Exam

If given a scenario, identify the stage and explain the PM's focus.

---

### 6. Customer / User / Buyer

**User** → uses the product.

**Buyer** → pays for/purchases the product.

**Customer** → receives/purchases the product; may or may not be the user.

### Case-study trick

Always ask:

> **Who uses it? Who pays? Who receives value?**

---

### 7. Problem vs Feature

This is **VERY important**.

> **Problem = customer pain/need.**

> **Feature = proposed solution.**

Example:

```text
Problem:
"I forget my appointments."

       ↓

Possible features:
• Push notification
• SMS
• Calendar integration
```

### Exam answer

Never blindly accept a requested feature.

Say:

> "The PM should first validate the underlying customer problem before selecting the solution."

---

### 8. Product-Market Fit

> Product-market fit means there is strong evidence that a product satisfies a meaningful customer/market need.

### Don't say:

> "10,000 downloads = product-market fit."

Instead look at:

* Retention
* Repeat usage
* Engagement
* Customer satisfaction
* Willingness to pay
* Churn
* Referrals

---

### 9. Output vs Outcome

**Output** = what you built.

**Outcome** = what changed because you built it.

Example:

> Output → Added reminder feature.

> Outcome → More users complete tasks on time.

🔥 **Memorise this distinction.**

---

# 🟡 CS02 — PRODUCT DISCOVERY

## ⏱️ 8 minutes

### 1. Product Discovery

> Product discovery is the process of understanding customer problems, needs and possible solutions before committing significant resources to development.

### Remember:

```text
Don't build first.
Learn first.
```

---

### 2. Customer Problem

A problem is the **pain, difficulty or unmet need experienced by the customer**.

Example:

❌ "Users need an AI chatbot."

✅ "Users cannot easily find answers to their questions."

The first is a solution.

The second is a problem.

---

### 3. Customer Needs

> A customer need is the underlying requirement or desired outcome that the customer wants to satisfy.

Example:

Customer says:

> "Give me reminders."

Underlying need:

> "Help me avoid forgetting important tasks."

---

### 4. Discovery vs Delivery

🔥 **Very likely case-study concept.**

| Discovery             | Delivery            |
| --------------------- | ------------------- |
| What should we build? | How do we build it? |
| Understand problem    | Implement solution  |
| Research              | Design/develop      |
| Validate              | Test/release        |

### Case clue

If the team starts coding without understanding the problem:

> **They jumped into delivery without sufficient discovery.**

---

### 5. Market / Customer Research

Methods:

* Interviews
* Surveys
* Observation
* Competitor analysis
* Usage data
* Market analysis

### Purpose

> Reduce assumptions and understand real customer needs.

---

### 6. Early Adopters

> Early adopters are customers who have a strong problem, actively seek solutions, are willing to try new products and provide feedback.

### Case question

If given several customer segments, look for the segment with:

* Strongest problem
* Highest urgency
* Willingness to try
* Willingness to provide feedback

---

### 🧠 CS02 case formula

```text
Who?
 ↓
What problem?
 ↓
How important?
 ↓
Research
 ↓
Validate
 ↓
Possible solutions
```

---

# 🟢 CS03 — PRODUCT DEVELOPMENT / MVP

## ⏱️ 9 minutes

### 1. Product Development Process

Know this flow:

```text
Problem
 ↓
Discovery
 ↓
Requirements
 ↓
MVP
 ↓
Build
 ↓
Test
 ↓
Release
 ↓
Measure
 ↓
Improve
```

---

### 2. MVP

🔥 **EXTREMELY IMPORTANT**

> MVP (Minimum Viable Product) is the smallest useful version of a product that allows the team to deliver core value and learn from real users.

### MVP is NOT:

❌ Cheapest product

❌ Worst-quality product

❌ Product containing every feature

### MVP is:

> **Minimum functionality needed to test the core value proposition.**

---

### 3. Iterative vs Incremental

### Iterative

> Repeatedly improve/refine something through feedback.

```text
Build → Learn → Improve → Repeat
```

### Incremental

> Deliver the product in smaller functional pieces.

```text
Part 1 → Part 2 → Part 3 → Part 4
```

### Agile

> Combines iterative and incremental development.

---

### 4. User Story

🔥 Memorise this exact structure:

> **As a [user], I want [goal], so that [benefit].**

Example:

> As a customer, I want to track my order so that I know when it will arrive.

### Remember:

```text
WHO → WHAT → WHY
```

---

### 5. Acceptance Criteria

> Conditions that must be satisfied for a user story to be considered complete/acceptable.

Example:

**Story:** Reset password.

Acceptance criteria:

* User can request reset.
* Reset link is sent.
* Link expires.
* User can create a new password.
* Invalid link is rejected.

### Memorise:

> **User Story = what the user wants.**

> **Acceptance Criteria = how we know it works.**

---

### 🧠 CS03 case formula

When asked to create an MVP:

```text
Identify core problem
        ↓
Identify essential workflow
        ↓
Choose minimum features
        ↓
Remove nice-to-have features
        ↓
Explain WHY
```

---

# 🔥 CS04 — PRIORITISATION + ROADMAP

## ⏱️ 9 minutes

This is one of the **highest-value sections for case studies**.

---

## 1. Feature Prioritisation

> Prioritisation is deciding which product work should be done first based on value, effort, risk, urgency and strategic importance.

### Factors to remember:

```text
VALUE
EFFORT
RISK
URGENCY
BUSINESS VALUE
CUSTOMER VALUE
DEPENDENCIES
```

---

### 2. How to answer a prioritisation question

Suppose you get:

| Feature | Value     | Effort    |
| ------- | --------- | --------- |
| Search  | High      | Low       |
| AI      | Medium    | Very High |
| Payment | Very High | Medium    |

Don't simply say:

> Search first because it is easy.

Say:

> Search should receive high priority because it provides high customer value with relatively low development effort and supports the core user journey.

**Always give the reason.**

---

# 3. Product Roadmap

> A product roadmap is a high-level plan showing the product's direction, priorities and planned evolution over time.

### Easy format:

```text
NOW
 ↓
NEXT
 ↓
LATER
```

---

# 4. Roadmap vs Backlog

🔥 **Memorise**

| Roadmap                 | Backlog                     |
| ----------------------- | --------------------------- |
| Strategic               | Operational                 |
| High-level              | Detailed                    |
| Product direction       | Work items                  |
| Shows priorities/themes | Stories/features/bugs/tasks |

### Shortcut:

> **Roadmap = Where are we going?**

> **Backlog = What work could/should we do?**

---

# 5. Release

> A release is making a product or new functionality available to users.

Think:

```text
Prioritise
 ↓
Plan
 ↓
Build
 ↓
Test
 ↓
Release
 ↓
Measure
```

---

# 🟡 CS05 — AGILE + SCRUM

## ⏱️ 11 minutes

You don't need to memorise every Agile sentence.

Understand the structure.

---

# 1. Agile

> Agile is an approach to software/product development based on iterative and incremental delivery, customer feedback, collaboration and adaptability.

### Agile mindset

```text
Build small
 ↓
Get feedback
 ↓
Learn
 ↓
Adapt
```

---

# 2. Agile Manifesto — 4 Values

🔥 Know these.

### Individuals and interactions

**over** processes and tools

### Working software

**over** comprehensive documentation

### Customer collaboration

**over** contract negotiation

### Responding to change

**over** following a plan

Important:

> The items on the right still have value; the items on the left are emphasised more.

---

# 3. Scrum

Scrum is an Agile framework for delivering products iteratively.

### Roles

**Product Owner**

* Maximises product value
* Manages/prioritises Product Backlog

**Scrum Master**

* Facilitates Scrum
* Helps remove impediments
* Supports Scrum adoption

**Developers**

* Build the product increment
* Decide how to accomplish the technical work

---

# 4. Scrum Events

Memorise:

```text
Sprint Planning
      ↓
     SPRINT
      ↓
Daily Scrum
      ↓
Sprint Review
      ↓
Retrospective
      ↓
Next Sprint
```

### Sprint Planning

> Decide what work to take into the Sprint and how it will be approached.

### Daily Scrum

> Short event for Developers to inspect progress and adapt the plan.

### Sprint Review

> Inspect the increment with stakeholders and discuss what to do next.

### Retrospective

> Team reflects on how to improve its way of working.

---

# 5. Product Backlog

> Ordered list of work needed or desired for the product.

Examples:

* Features
* User stories
* Bugs
* Improvements
* Technical work

---

# 6. Sprint Backlog

> Selected Product Backlog items plus the plan for delivering them during the Sprint.

### Remember:

```text
Product Backlog
      ↓
Select items
      ↓
Sprint Backlog
```

---

# 7. Definition of Done

> Shared criteria that determine when work is considered complete.

Example:

* Developed
* Tested
* Reviewed
* Meets acceptance criteria
* Integrated
* Meets required quality standards

---

# 🔥 CS05 CASE QUESTION

If case says:

> Team keeps changing requirements during development.

Answer using:

* Agile adaptability
* Backlog reprioritisation
* Customer feedback
* Short iterations
* Sprint-based delivery

If case says:

> Team has conflict / blockers.

Think:

> Scrum Master → facilitate → remove impediments.

If case says:

> Business wants to decide what is most valuable.

Think:

> Product Owner → Product Backlog → prioritisation.

---

# 🟠 CS06 — ESTIMATION + METRICS + TECHNICAL DEBT

## ⏱️ 8 minutes

---

# 1. Story Points

> Story points are a relative measure of the effort/complexity/uncertainty of a user story.

🔥 Important:

> Story points are **not directly equal to hours**.

Example:

```text
Story A = 2 points
Story B = 5 points
Story C = 8 points
```

An 8-point story is relatively more complex/uncertain than a 2-point story.

---

# 2. Planning Poker

> A collaborative technique where team members independently estimate story-point values and discuss differences.

### Flow:

```text
Understand story
 ↓
Everyone estimates
 ↓
Reveal estimates
 ↓
Discuss differences
 ↓
Re-estimate
 ↓
Agree
```

---

# 3. Velocity

> Velocity is the amount of work, commonly measured in story points, that a team completes in a Sprint.

Example:

```text
Sprint 1 = 20 points
Sprint 2 = 22 points
Sprint 3 = 21 points
```

Approximate historical velocity ≈ **21 points/Sprint**.

### Important

Velocity is useful for **planning**, not for comparing teams.

---

# 4. Burndown Chart

> Shows remaining work over time during a Sprint/release.

### Think:

```text
Start → lots of work
           ↓
        decreasing
           ↓
End → little/no remaining work
```

---

# 5. Cycle Time

> The time taken for a work item to move through the workflow from start to completion.

Used to understand delivery efficiency.

---

# 6. Technical Debt

🔥 Very likely scenario topic.

> Technical debt is the future cost created when a team chooses a quick/easy technical solution instead of a more robust solution.

Example:

```text
Quick solution
      ↓
Release faster
      ↓
Future complexity
      ↓
Refactoring required
```

### Case question

If team says:

> "We'll use this temporary workaround now and fix it later."

Think:

> **Technical debt.**

---

# 7. Agile Metrics

Know these:

* Velocity
* Burndown
* Cycle time
* Lead time
* Defect rate
* Throughput
* Team stability

### Don't blindly say:

> "Higher velocity = better team."

Metrics need context.

---

# 🟣 CS07 — STORY MAPPING + ROADMAP + PRIORITISATION

## ⏱️ 5 minutes

CS07 overlaps heavily with the roadmap/prioritisation concepts.

---

# 1. Story Mapping

> Story Mapping is a visual way of organising user activities, tasks and stories according to the user's journey.

Example:

```text
USER JOURNEY
────────────────────────────

Search → Select → Pay → Track

   ↓        ↓       ↓      ↓

Story    Story    Story   Story
Story    Story    Story   Story
```

### Why use it?

* Understand user journey
* Identify missing functionality
* Organise stories
* Identify MVP
* Prioritise releases

---

# 2. Story Mapping + MVP

This is a useful case-study connection:

```text
User Journey
     ↓
Identify stories
     ↓
Prioritise
     ↓
Draw release boundary
     ↓
MVP
```

---

# 3. Roadmap + Prioritisation

Remember:

```text
Features
   ↓
Prioritisation
   ↓
What first?
   ↓
Roadmap
   ↓
Release
```

---

# 🚨 THE 20 DEFINITIONS TO MEMORISE

If you're running out of time, **memorise these exact ideas**:

| #  | Concept             | One-line definition                                                   |
| -- | ------------------- | --------------------------------------------------------------------- |
| 1  | Product Management  | Managing a product to solve customer problems and deliver value       |
| 2  | Product Manager     | Person responsible for product direction and maximising product value |
| 3  | Product             | Ongoing solution that evolves to deliver value                        |
| 4  | Project             | Temporary initiative with a defined objective                         |
| 5  | Product Thinking    | Focus on problems, customers and outcomes rather than features        |
| 6  | Product Discovery   | Learning what should be built before significant development          |
| 7  | Product Delivery    | Building, testing and releasing the chosen solution                   |
| 8  | MVP                 | Smallest useful product version for delivering value and learning     |
| 9  | User Story          | User-focused description of desired functionality                     |
| 10 | Acceptance Criteria | Conditions that determine whether a story is acceptable               |
| 11 | Prioritisation      | Deciding what work should be done first                               |
| 12 | Product Roadmap     | High-level view of product direction and priorities                   |
| 13 | Product Backlog     | Ordered list of product work                                          |
| 14 | Agile               | Iterative/incremental approach emphasising feedback and adaptability  |
| 15 | Scrum               | Agile framework using Sprints and defined accountabilities/events     |
| 16 | Story Points        | Relative measure of effort/complexity/uncertainty                     |
| 17 | Velocity            | Amount of work completed by a team in a Sprint                        |
| 18 | Technical Debt      | Future cost resulting from shortcuts in technical implementation      |
| 19 | Product-Market Fit  | Evidence that a product satisfies a meaningful market need            |
| 20 | Outcome             | Measurable change/value resulting from product activity               |

---

# 🧠 THE CASE-STUDY CHEAT CODE

Whatever case they throw at you, first identify which of these it is asking:

```text
                    CASE
                     │
       ┌─────────────┼─────────────┐
       ↓             ↓             ↓
    PROBLEM        PEOPLE       PRODUCT
       │             │             │
   Need?          User?          MVP?
   Pain?          Buyer?         Feature?
   Why?           Customer?      Release?
       │                           │
       └─────────────┬─────────────┘
                     ↓
                 PRIORITISE
                     ↓
                  ROADMAP
                     ↓
                   BUILD
                     ↓
                  MEASURE
                     ↓
                  IMPROVE
```

---

# ✍️ HOW TO ANSWER ANY CASE QUESTION

This is probably the **most important thing for your last hour**.

## If asked: "Which feature should be prioritised?"

Write:

> **Recommendation:** Feature X should be prioritised.
> **Reason:** It addresses the identified customer problem and provides high customer/business value. Its effort/risk is also manageable compared with the alternatives.
> **Case evidence:** The scenario states that ______.
> **Conclusion:** Therefore, it should be addressed before lower-value features such as ______.

---

## If asked: "What should the MVP contain?"

Write:

> The MVP should contain the **minimum functionality required to solve the core customer problem and validate the product's value proposition**.

Then:

```text
Include:
✓ Core problem-solving features
✓ Essential user workflow
✓ Minimum required functionality

Exclude:
✗ Nice-to-have features
✗ High-cost features without validation
✗ Features unrelated to the core problem
```

Then **justify each major choice**.

---

## If asked: "Write a user story"

Immediately write:

> **As a [user], I want [goal], so that [benefit].**

Don't overthink it.

---

## If asked: "Write acceptance criteria"

Give **3–5 bullet points** describing observable conditions.

```text
✓ User can...
✓ System displays...
✓ System rejects...
✓ User receives...
✓ Action completes when...
```

---

## If asked: "Create a roadmap"

Use:

```text
NOW
→ Core problem / essential functionality

NEXT
→ Important enhancements

LATER
→ Advanced / lower-priority functionality
```

Then explain **why**.

---

## If asked about Agile/Scrum

Identify the clue:

| Case clue                                  | Answer          |
| ------------------------------------------ | --------------- |
| Who decides product priority?              | Product Owner   |
| Who facilitates Scrum/removes impediments? | Scrum Master    |
| Who builds the increment?                  | Developers      |
| Short development cycle?                   | Sprint          |
| Daily coordination?                        | Daily Scrum     |
| Demonstrate product increment?             | Sprint Review   |
| Improve team process?                      | Retrospective   |
| Ordered work list?                         | Product Backlog |
| Selected Sprint work?                      | Sprint Backlog  |
| Relative estimation?                       | Story Points    |
| Collaborative estimation?                  | Planning Poker  |
| Work completed per Sprint?                 | Velocity        |
| Quick technical shortcut?                  | Technical Debt  |

---

# 🔥 FINAL 5-MINUTE MEMORY DUMP

Before entering the exam, remember this:

```text
PRODUCT MANAGEMENT
= Solve problems + deliver value

PM
= Why + What + Who + Priority + Outcome

PROBLEM ≠ FEATURE
Problem = pain
Feature = solution

DISCOVERY
= Understand before building

DELIVERY
= Build + test + release

MVP
= Minimum useful product to deliver value + learn

USER STORY
= As a ___, I want ___, so that ___

ACCEPTANCE CRITERIA
= Conditions proving story works

PRIORITISATION
= Value + Effort + Risk + Urgency + Dependencies

ROADMAP
= Where we're going

BACKLOG
= Work we may/do need to do

AGILE
= Iterate + Increment + Feedback + Adapt

SCRUM
= PO + SM + Developers
  Sprint → Review → Retrospective

STORY POINTS
= Relative complexity/effort/uncertainty

VELOCITY
= Work completed per Sprint

TECHNICAL DEBT
= Shortcut now → cost later

OUTPUT
= What we built

OUTCOME
= What changed

METRICS
= Evidence of performance/value

PRODUCT-MARKET FIT
= Product meaningfully satisfies market need
```

## ⚠️ One final exam rule

**Don't answer case-study questions with definitions alone.**

Use:

> **Definition → Case evidence → Application → Reason**

For example:

> **MVP is the minimum useful version of a product used to deliver core value and learn from users. In this case, the team should include login, course access and basic assessments because these support the core learning workflow. AI tutoring should be postponed because it has high effort and is not necessary to validate the initial value proposition.**

That **definition + case + reasoning** structure is what you should use throughout the paper.

Sharpen your exam answers

* Make a 1-page revision sheet
* Give me practice case questions
