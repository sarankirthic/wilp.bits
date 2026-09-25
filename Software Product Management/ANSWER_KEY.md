Yes. Below are **model answers for all six case studies**, written in an **EC-2 exam style**: concise, structured, and with enough justification to score well.

# CASE STUDY 1 — FitTrack

## Q1. Product vs Project

### a) Difference

| Product                            | Project                                              |
| ---------------------------------- | ---------------------------------------------------- |
| Continuous and evolves over time   | Temporary initiative                                 |
| Focuses on customer/business value | Focuses on delivering a defined scope                |
| Has ongoing users and feedback     | Has a defined start and end                          |
| Continuously improved              | Usually considered complete after objectives are met |

### b) Why FitTrack is a product

FitTrack should be treated as a **product** because:

* It has identifiable customers and users.
* It solves ongoing wellness problems.
* It will require continuous improvements.
* New features can be added based on user feedback.
* Its success depends on customer adoption and business outcomes, not simply completing development.
* It will have multiple releases over its lifetime.

**Exam line:**

> FitTrack is a product because the objective is to continuously deliver customer and business value rather than merely complete a predefined project scope.

---

# Q2. Customer, User and Buyer

### a) Identification

| Role          | Likely stakeholder                                    |
| ------------- | ----------------------------------------------------- |
| **Users**     | Employees                                             |
| **Customers** | Organisations using FitTrack                          |
| **Buyers**    | HR/management responsible for purchasing the solution |

IT administrators may also be important users/administrators.

### b) Different needs

**Employees**

* Simple tracking
* Reminders
* Easy-to-use interface
* Useful wellness functionality

**HR**

* Employee participation
* Aggregate wellness information
* Reporting
* Easy administration

**Management**

* Business value
* Employee engagement
* Cost effectiveness
* Measurable results

**IT**

* Security
* Integration
* Reliability
* Administration

### c) Why distinguish them?

Different stakeholders have different goals.

If the PM focuses only on employees, they may miss organisational purchasing requirements. If they focus only on management, the product may fail to provide a good user experience.

> **User adoption + customer value + buyer requirements must all be considered.**

---

# Q3. Problem vs Feature

### a) Actual customer problem

The case indicates:

> Employees struggle to consistently remember and perform health tracking activities.

### b) Why AI recommendations may not be the correct first solution

The AI recommendation feature is based primarily on:

> “Competitors have it.”

rather than validated customer need.

It may:

* Require significant development effort.
* Increase product complexity.
* Not solve the immediate tracking problem.
* Consume resources that could be used for higher-value functionality.

### c) Alternative solutions

Two possible solutions are:

1. **Push reminders** for regular tracking.
2. **Simple goal/progress reminders** that encourage consistent usage.

Other possible solutions could include email reminders or personalised schedules.

**Core principle:**

> Identify the problem first; select the feature/solution afterward.

---

# Q4. MVP

### a) Suitable MVP

A suitable FitTrack MVP could contain:

* User registration/login
* Basic daily health/activity tracking
* Goal setting
* Reminders
* Basic employee progress view
* Basic HR aggregate dashboard

### b) Criteria

Features should be selected based on:

* Ability to solve the core customer problem
* Customer value
* Business value
* Minimum functionality required
* Development effort
* Risk
* Ability to obtain user feedback quickly

### c) Postpone

**AI recommendations**

* High complexity
* Not clearly validated
* Not necessary for testing the core tracking proposition

**Community/social features**

* Not central to the identified problem
* Can be tested later after core adoption is established

**Exam conclusion:**

> The MVP should contain enough functionality to deliver the core value and learn from real users, rather than attempting to build the complete product.

---

# CASE STUDY 2 — QuickCart

# Q1. Feature Prioritisation

### a) Factors

The PM should consider:

* Customer value
* Business value
* Development effort
* Risk
* Urgency
* Dependencies
* Strategic importance
* Revenue impact

### b) Possible prioritisation

A reasonable next-release focus would be:

1. **Search**
2. **Online payment**
3. **Order tracking**

### c) Reasoning

**Search**

* Very high customer demand
* Low development effort
* Fundamental to finding products

**Online payment**

* Very high customer and business value
* Essential for completing purchases

**Order tracking**

* High customer value
* Improves post-purchase experience
* Supports customer trust

AI recommendations could provide future value but has **very high effort and low current demand**.

Social sharing has relatively low value and can be postponed.

---

# Q2. Product Roadmap

### NOW

* Search
* Online payment
* Order tracking

### NEXT

* Multiple delivery slots
* Loyalty points

### LATER

* AI recommendations
* Social sharing

### Explanation

The roadmap starts with features that are:

* Core to the purchasing experience
* Highly demanded
* Valuable to the business
* Relatively practical to implement

Lower-value or high-effort functionality is deferred.

---

# Q3. Product Backlog vs Roadmap

| Roadmap                             | Backlog                                 |
| ----------------------------------- | --------------------------------------- |
| High-level product direction        | Detailed list of potential work         |
| Strategic                           | Operational                             |
| Shows priorities/themes/releases    | Contains stories, features, bugs, tasks |
| Helps communicate product direction | Helps manage development work           |

The CEO should not simply present the backlog because the backlog contains too much implementation detail.

> **Roadmap = where the product is going.**
> **Backlog = work that may need to be done.**

---

# Q4. Release Planning

The payment dependency should be identified as a **dependency/risk**.

The PM should:

1. Confirm the payment provider's availability.
2. Assess whether another payment solution exists.
3. Evaluate the impact on the release.
4. Reorder dependent work if necessary.
5. Adjust the roadmap/release plan.
6. Communicate the change to stakeholders.

If payment is essential for the release, the team may need to:

* Delay that release,
* Use an alternative provider, or
* Release other functionality first.

**Key idea:**

> Roadmaps and releases should adapt when dependencies and constraints change.

---

# CASE STUDY 3 — LearnPro

# Q1. Product Discovery

### a) Why discovery first?

Discovery reduces the risk of building the **wrong solution**.

It helps determine:

* Who has the problem?
* What is the problem?
* How important is it?
* What solutions are possible?
* What do customers actually value?

### b) Key problem

Students have difficulty **selecting appropriate courses because course information and relationships to their goals are unclear**.

### c) How research changed understanding

Initially the team assumed:

> “Students need AI recommendations.”

Research showed that the underlying problems include:

* Unclear descriptions
* Difficult prerequisites
* Unclear career relevance
* Too many similar choices

Therefore, AI is only **one possible solution**, not necessarily the actual requirement.

---

# Q2. Product Thinking

The product-thinking approach is:

```text
Problem
  ↓
Understand customer
  ↓
Identify need
  ↓
Explore solutions
  ↓
Select appropriate solution
  ↓
Build
  ↓
Measure
```

### Application

**Problem:** Students struggle to select courses.

**Need:** Students need clear guidance to choose appropriate courses.

**Solution:** Provide better course-selection assistance.

**Feature:** AI recommendation engine is one possible implementation.

The PM should therefore avoid assuming that the proposed AI feature is automatically the right solution.

---

# Q3. User Story & Acceptance Criteria

### a) User story

> **As a student, I want to understand which courses match my career goals so that I can choose appropriate courses.**

### b) Acceptance criteria

* Student can select a career goal.
* System displays relevant courses.
* Course prerequisites are clearly displayed.
* Course difficulty is shown.
* Student can view why a course is relevant to the selected goal.

---

# Q4. MVP

**Option B** is more suitable for an MVP.

### Why?

* Lower development effort
* Directly addresses the validated problem
* Uses information students actually need
* Allows the team to test whether students find the guidance useful
* Avoids premature investment in complex AI

Option A introduces significant complexity before the core value has been validated.

> **MVP should test the core value proposition with minimum necessary functionality.**

---

# CASE STUDY 4 — TravelMate

# Q1. Customer & Market Understanding

### a) Groups

* **Individual travellers**
* **Corporate travellers**
* **Travel agencies**

### b) Different needs

| Segment               | Main need                    |
| --------------------- | ---------------------------- |
| Individual travellers | Simple itinerary planning    |
| Corporate travellers  | Expenses + policy compliance |
| Travel agencies       | White-label capabilities     |

### c) Additional research

The PM should investigate:

* Problem severity
* Market size
* Willingness to pay
* Frequency of use
* Competition
* Acquisition cost
* Expected revenue
* Customer accessibility
* Development requirements
* Business strategic fit

The PM should validate assumptions rather than selecting a segment purely based on intuition.

---

# Q2. Early Adopter

An early adopter is a customer who:

* Has a significant problem
* Actively seeks a solution
* Is willing to try a new product
* Is willing to provide feedback
* Can tolerate an imperfect early product

A segment with a **strong, urgent problem** is generally more suitable for early validation.

For TravelMate, corporate travellers could potentially be considered if research confirms that expense/policy management is a significant problem and organisations are willing to adopt a new solution.

However, the case alone does **not prove** that they are the best segment; this requires validation.

---

# Q3. Product-Market Fit

### a)

No.

**50,000 downloads alone do not establish product-market fit.**

Downloads measure acquisition/interest, but do not show sustained customer value.

### b) Evidence to examine

The PM should examine:

* Retention
* Repeat usage
* Customer satisfaction
* Engagement
* Conversion to paying users
* Churn
* Willingness to pay
* Referrals
* Qualitative customer feedback

### c) Useful metrics

For example:

```text
Downloads
   ↓
Registrations
   ↓
Active users
   ↓
Retained users
   ↓
Paying users
```

The large drop from downloads to active users is something the PM should investigate.

---

# Q4. Product Success

### Output

> The itinerary feature was developed and released on time.

### Outcome

> Users successfully create and use itineraries, resulting in improved travel-planning behaviour/value.

### Suitable measures

* Number of itineraries created
* Feature adoption
* Repeat usage
* Customer satisfaction
* Task completion rate
* Retention among users using the feature

**Key principle:**

> Delivering a feature is an output; creating measurable customer/business value is an outcome.

---

# CASE STUDY 5 — FoodNow

# Q1. Identify the Problem

### Customer problems

* Checkout abandonment
* Inaccurate delivery estimates

### Restaurant problem

* Delayed order updates

### Business/product problem

* Poor customer retention

The loyalty programme should not automatically be prioritised simply because management requested it.

Why?

Because the case already provides evidence of more fundamental problems:

> Customers are abandoning orders and experiencing inaccurate delivery information.

Fixing these issues may address the underlying customer experience before introducing another engagement mechanism.

---

# Q2. Prioritisation

A reasonable prioritisation based on the case would be:

### Immediate focus

**1. Faster/better checkout**

High impact because customers are abandoning orders.

**2. Accurate delivery estimates**

Directly affects customer experience and trust.

**3. Restaurant order updates**

Addresses an operational/customer-experience problem.

### Later

**4. Loyalty programme**

Potentially useful for retention once core experience is working.

**5. AI recommendations**

Potential value, but no strong evidence in the case that this is the immediate problem.

**6. Social sharing**

Low evidence of customer/business need.

### Factors

The PM should evaluate:

* Customer value
* Business value
* Effort
* Risk
* Urgency
* Dependencies
* Strategic alignment

---

# Q3. Roadmap

### NOW

```text
Faster checkout
Accurate delivery estimates
Restaurant order updates
```

### NEXT

```text
Loyalty programme
```

### LATER

```text
AI recommendations
Social sharing
```

### Reasoning

The roadmap first addresses **known customer and operational problems** before investing in less-validated enhancements.

---

# Q4. Metrics

Useful metrics include:

### Checkout

* Checkout conversion rate
* Cart abandonment rate
* Checkout completion time

### Delivery

* Delivery estimate accuracy
* Late-delivery rate
* Customer complaints

### Restaurant updates

* Order update delay
* Order-status accuracy

### Retention

* Repeat order rate
* Customer retention
* Churn

The PM should compare metrics **before and after changes** to determine whether the initiatives produced meaningful outcomes.

---

# CASE STUDY 6 — EduMax

This is the **big integrated case**, so this is particularly good practice.

# Q1. Product Strategy

### a) Personas

**Students**

* Primary users

**Faculty**

* Users

**University management**

* Customer/stakeholder

**Finance**

* Buyer/business stakeholder

**IT administrators**

* Operational users/stakeholders

### b) Different needs

| Stakeholder | Need                                              |
| ----------- | ------------------------------------------------- |
| Students    | Course access, mobile access, reminders           |
| Faculty     | Course management, attendance, assessments        |
| Management  | Analytics, integration, organisational visibility |
| Finance     | Cost-effective implementation                     |
| IT          | Integration, security, administration             |

### c) Why distinguish them?

Because a successful product must satisfy **different stakeholder requirements simultaneously**.

The user experience alone does not determine purchasing or organisational success.

---

# Q2. MVP & Product Discovery

### a) Key initial problems

The initial problems supported by the case include:

* Students need easy access to courses.
* Students need reminders.
* Faculty need easier course management.
* Faculty need assessment/attendance functionality.

These should be validated further through discovery.

### b) Four-month MVP

A reasonable MVP:

* Student registration/login
* Course access
* Basic course management
* Online assessments
* Attendance
* Basic reminders
* Basic faculty dashboard

### c) Exclude initially

**AI tutor**

* High complexity
* Not necessary to validate the core learning platform

**Gamification**

* Useful enhancement but not core to initial course delivery

**Parent dashboard**

* Not identified as a primary initial problem

**Advanced analytics**

* Can follow after basic usage data is available

**White-label/mobile/advanced integrations** can also be phased depending on validated requirements and dependencies.

The exact MVP should ultimately be validated with the target universities.

---

# Q3. Prioritisation

The PM should evaluate each feature using:

### 1. Customer value

Does it solve an important user problem?

### 2. Business value

Does it help the company acquire, retain or monetise customers?

### 3. Effort

How much engineering/design work is required?

### 4. Risk

What technical, operational or business risks exist?

### 5. Urgency

Does the product need it immediately?

### 6. Dependencies

Does another feature/system need to exist first?

### Example

**Course access**

* High customer value
* Core product functionality
* High priority

**AI tutor**

* Potentially high value
* Very high effort
* Not required for core MVP
* Lower initial priority

**Basic assessment**

* High student/faculty value
* Supports core learning workflow
* High priority

---

# Q4. Roadmap & Release

## NOW — Initial release

```text
Student registration
Course access
Basic course management
Attendance
Basic assessments
Basic reminders
```

## NEXT — Product expansion

```text
Faculty dashboard improvements
Analytics
Mobile improvements
System integrations
```

## LATER — Advanced capabilities

```text
AI tutor
Gamification
Parent dashboard
Advanced analytics
Additional integrations
```

### Explanation

The roadmap begins with functionality required to establish the **core learning workflow**.

Later releases add capabilities based on:

* Customer feedback
* Product usage
* Business priorities
* Technical feasibility
* Validated demand

---

# 🧠 THE BIG EXAM PATTERN

After doing all these cases, you should notice something.

Most case-study questions can be solved using this mental model:

```text
                 CUSTOMER
                    ↓
              What do they need?
                    ↓
                PROBLEM
                    ↓
             Validate the problem
                    ↓
               SOLUTIONS
                    ↓
              Choose MVP
                    ↓
             PRIORITISE
                    ↓
                ROADMAP
                    ↓
                RELEASE
                    ↓
                 MEASURE
                    ↓
              LEARN & IMPROVE
```

And when the question asks **“Why?”**, use this:

```text
CASE FACT
   ↓
CONCEPT
   ↓
APPLICATION
   ↓
JUSTIFICATION
```

### Example

Don't write:

> “Reminders should be prioritised.”

Write:

> **Reminders should be prioritised because employees struggle to consistently track their activities. The feature directly addresses the identified problem, requires less effort than AI recommendations, and allows the team to test whether reminders improve tracking behaviour.**

That's the difference between a **definition answer** and a **case-study answer**.

## 🔥 Topics I would be able to apply without hesitation

For your CS01–CS07 preparation, make sure you can take **any random company/product scenario** and answer:

* **Who is the customer/user/buyer?**
* **What is the actual problem?**
* **What is the underlying need?**
* **Is this discovery or delivery?**
* **What should the MVP contain?**
* **Which features should be prioritised and why?**
* **Write a user story**
* **Write acceptance criteria**
* **Build a roadmap**
* **Roadmap vs backlog**
* **Plan releases**
* **Identify outputs vs outcomes**
* **Select appropriate metrics**
* **Assess evidence related to product-market fit**
* **Apply Agile/Scrum concepts to the product scenario**
* **Apply estimation/story points/velocity where given**
* **Use Story Mapping for feature organisation and prioritisation**

Those are the kinds of things I'd practice rather than memorising 20 separate textbook definitions.
