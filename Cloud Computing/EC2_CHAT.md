# Cloud Computing — EC-2 Study Chat Export

## Purpose

This document preserves the key points from the Cloud Computing EC-2 preparation discussion, with the **official course handout** as the verified source available in the conversation.

> **Important source limitation:** The uploaded `cloud-computing.zip` was said to contain lecture transcripts, but its transcript contents were not exposed to the file-search index during this chat. Therefore, this export does **not** claim that any point below was specifically emphasized by the lecturer unless the available source supports it.

---

# 1. EC-2 Portion

According to the official **Cloud Computing Digital Learning Handout**:

> **EC-2 = Mid-Semester Test — Closed Book — 30% — 2 hours**

The handout explicitly states:

> **Syllabus for Mid-Semester Test (Closed Book): Topics in Contact Sessions 1 to 16.**

Therefore, EC-2 covers **Contact Sessions 1–16**.

## Session mapping

### Sessions 1–4 — Introduction to Cloud Computing

- Cloud computing: definition, characteristics, motivation
- Evolution and origins of cloud computing
- Cloud service models:
  - IaaS
  - PaaS
  - SaaS
- Cloud deployment models:
  - Public
  - Private
  - Hybrid
  - Community
  - Multi-cloud
- Cloud infrastructure:
  - Compute
  - Storage
  - Network
  - Data-centre regions
- Benefits, limitations and adoption drivers

### Sessions 5–12 — Virtualization and Containers

- Introduction to virtualization
- Benefits and limitations of virtualization
- Types of virtualization:
  - Full virtualization
  - Para-virtualization
  - Hardware-assisted virtualization
  - OS-level virtualization
- x86 hardware virtualization
- Resource management for SaaS, PaaS and IaaS
- Containers and containerization
- Docker:
  - Images
  - Dockerfiles
  - Containers
  - Registries
  - Volumes
- Namespaces and cgroups
- System containers vs application containers
- Virtual machines vs containers
- Kubernetes overview
- Cloud-native design principles:
  - Microservices
  - Declarative deployment
  - Portability

### Sessions 13–16 — Infrastructure as a Service

- Introduction to IaaS
- IaaS architecture and reference model
- AWS as an IaaS reference platform
- Regions
- Availability Zones
- Edge Locations
- Identity and Access Management (IAM):
  - Authentication
  - Authorization
  - Roles
  - Policies
- Compute services:
  - Instances
  - Clusters
  - VPC
  - Security groups
- Storage:
  - File
  - Block
  - Object
- Cloud data services:
  - RDS
  - NoSQL
  - Data storage
  - Analytics overview
- Big-data services:
  - HDFS
  - EMR
  - Data warehousing overview

---

# 2. Topics NOT in EC-2

Because EC-2 ends at Contact Session 16, the following later topics are outside the official EC-2 syllabus:

- VM provisioning and provisioning workflows
- Image-based provisioning
- VM migration
- Cold/live/storage migration
- Infrastructure as Code
- Resource tagging, quotas and governance
- VM → container/managed-service migration
- Capacity management
- Resource scheduling
- Reservation-based provisioning
- SLA-aware provisioning
- Elasticity and autoscaling
- Horizontal/vertical scaling
- Kubernetes scheduling in detail
- Cost-aware scheduling/right-sizing
- Availability and fault tolerance
- Multi-tenancy
- Cloud security/threat models
- Shared responsibility
- SLA/SLO lifecycle
- Data residency/compliance
- Sovereign cloud
- APIs/API gateways
- CI/CD
- Observability
- Hybrid/multi-cloud deployment details
- Edge computing
- AI/ML cloud workloads
- Quantum/neuromorphic/photonic/accelerator/green cloud

These are part of the later course sessions and/or comprehensive exam scope, not the official EC-2 boundary.

---

# 3. One-Hour EC-2 Preparation Plan

If only **60 minutes** are available, prioritize concepts rather than trying to read every topic equally.

| Time | Focus |
|---|---|
| 0–10 min | Cloud fundamentals + service/deployment models |
| 10–25 min | Virtualization |
| 25–40 min | **Docker + containers + Dockerfile** |
| 40–50 min | Kubernetes + cloud-native concepts |
| 50–60 min | IaaS + AWS + IAM + networking + storage |

---

# 4. Cloud Fundamentals — Key Points

## Cloud characteristics

Remember the five standard characteristics:

1. On-demand self-service
2. Broad network access
3. Resource pooling
4. Rapid elasticity
5. Measured service

## Service models

### IaaS

Infrastructure as a Service.

The provider supplies infrastructure such as:

- Compute
- Storage
- Networking

The customer manages more of the software stack.

### PaaS

Platform as a Service.

The provider manages the infrastructure and platform/runtime while the customer focuses primarily on the application and data.

### SaaS

Software as a Service.

The provider manages almost the entire underlying stack and the user primarily consumes/configures the application.

### Memory

```text
IaaS → infrastructure
PaaS → platform
SaaS → software
```

---

# 5. Deployment Models

## Public cloud

Cloud infrastructure operated for use by multiple customers.

## Private cloud

Cloud infrastructure dedicated to one organization.

## Hybrid cloud

Combination/integration of private/on-premise and public-cloud environments.

## Community cloud

Cloud infrastructure shared by organizations with common requirements.

## Multi-cloud

Use of services from multiple cloud providers.

### Important distinction

```text
Hybrid cloud
= combination of different environments

Multi-cloud
= multiple cloud providers
```

They can overlap.

---

# 6. Virtualization

## Definition

Virtualization creates a virtual representation of computing resources, allowing multiple virtual environments to share underlying physical resources.

## Hypervisor

A hypervisor is the software/firmware layer responsible for creating and managing virtual machines.

### Type 1

```text
Hardware
   ↓
Hypervisor
   ↓
VMs
```

Bare-metal hypervisor.

### Type 2

```text
Hardware
   ↓
Host OS
   ↓
Hypervisor
   ↓
VMs
```

Hosted hypervisor.

---

# 7. Virtualization Types

Know the four listed in the handout:

- Full virtualization
- Para-virtualization
- Hardware-assisted virtualization
- OS-level virtualization

## Full virtualization

Guest OS can run without being specifically modified for the virtualized environment.

## Para-virtualization

Guest OS is aware of virtualization and can cooperate with the hypervisor.

## Hardware-assisted virtualization

Processor hardware provides virtualization support.

Examples commonly associated with the concept include Intel VT-x and AMD-V.

## OS-level virtualization

Isolation occurs at the operating-system level rather than providing each environment with a complete guest OS.

This is the basic model behind containers.

---

# 8. VM vs Container

## Virtual Machine

```text
Hardware
   ↓
Hypervisor
   ↓
Guest OS
   ↓
Application
```

## Container

```text
Hardware
   ↓
Host OS
   ↓
Container Runtime
   ↓
Containers
   ↓
Applications
```

## Core comparison

| VM | Container |
|---|---|
| Includes guest OS | Shares host kernel |
| Generally heavier | Generally lightweight |
| Higher overhead | Lower overhead |
| Slower startup | Fast startup |
| Hardware virtualization | OS-level isolation |
| Managed through hypervisor | Managed through container runtime |

---

# 9. Docker — HIGH PRIORITY

The handout explicitly includes:

- Docker images
- Dockerfiles
- Containers
- Registries
- Volumes
- Namespaces
- cgroups

## Core relationship

```text
Dockerfile
    ↓ docker build
Docker Image
    ↓ docker run
Container
```

### Dockerfile

A Dockerfile is a text file containing instructions used to build a Docker image.

### Image

A packaged, immutable image/template from which containers are created.

### Container

A running instance of an image.

### Registry

A location for storing and distributing container images.

### Volume

Persistent storage associated with containers.

---

# 10. Dockerfile Creation — MUST PRACTICE

A basic Python application Dockerfile:

```dockerfile
FROM python:3.12

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["python", "app.py"]
```

## What each instruction means

### FROM

```dockerfile
FROM python:3.12
```

Selects the base image.

### WORKDIR

```dockerfile
WORKDIR /app
```

Sets the working directory inside the image/container.

### COPY

```dockerfile
COPY requirements.txt .
```

Copies files from the build context into the image.

### RUN

```dockerfile
RUN pip install -r requirements.txt
```

Executes a command while building the image.

### COPY .

```dockerfile
COPY . .
```

Copies the application source into the image.

### EXPOSE

```dockerfile
EXPOSE 8000
```

Documents the port the application is expected to listen on.

### CMD

```dockerfile
CMD ["python", "app.py"]
```

Specifies the default command executed when the container starts.

---

# 11. RUN vs CMD

Very important distinction.

## RUN

Executed during **image build**.

```dockerfile
RUN pip install flask
```

## CMD

Default command when the **container starts**.

```dockerfile
CMD ["python", "app.py"]
```

### Memory trick

```text
RUN → BUILD
CMD → CONTAINER START
```

---

# 12. Basic Docker Commands

## Build image

```bash
docker build -t myapp .
```

## Run container

```bash
docker run myapp
```

## Run with port mapping

```bash
docker run -p 8000:8000 myapp
```

Meaning:

```text
HOST PORT : CONTAINER PORT
8000      : 8000
```

## List running containers

```bash
docker ps
```

## List all containers

```bash
docker ps -a
```

## List images

```bash
docker images
```

## Stop container

```bash
docker stop <container>
```

## Remove container

```bash
docker rm <container>
```

---

# 13. Docker Registry

Conceptual flow:

```text
Dockerfile
    ↓
docker build
    ↓
Image
    ↓ docker push
Registry
    ↓ docker pull
Another machine
```

Registry = storage/distribution location for container images.

---

# 14. Docker Volumes

Containers are commonly treated as ephemeral.

Persistent application data can be stored using volumes.

```bash
docker run -v mydata:/data myapp
```

Memory:

```text
Container → application environment
Volume    → persistent data
```

---

# 15. Namespaces vs cgroups

This is an important distinction.

## Namespaces

Provide **isolation**.

They can isolate:

- Processes
- Network
- Mounts
- Users
- Hostname

Memory:

> **Namespaces = What can I see?**

## cgroups

Control/limit **resource usage**.

Examples:

- CPU
- Memory
- I/O

Memory:

> **cgroups = How much can I use?**

### One-line answer

```text
Namespaces → isolation
cgroups    → resource control
```

---

# 16. Kubernetes

Kubernetes is a **container orchestration platform**.

It helps with:

- Container deployment
- Scheduling
- Scaling
- Networking
- Recovery/self-healing

Basic conceptual structure:

```text
Kubernetes Cluster
│
├── Control Plane
│
└── Worker Nodes
      │
      ├── Pod
      │    └── Container
      │
      └── Pod
           └── Container
```

## Pod

A Pod is the smallest deployable unit in Kubernetes and can contain one or more closely related containers.

---

# 17. Cloud-Native Principles

Key terms from the handout:

- Microservices
- Declarative deployment
- Portability
- Containers
- Automation
- Scalability

## Imperative vs declarative

### Imperative

Tell the system **how** to perform steps.

> "Do these steps."

### Declarative

Specify **what state you want**.

> "Make the system look like this."

Kubernetes heavily uses declarative configuration.

---

# 18. IaaS / AWS

## IaaS

Provides fundamental cloud infrastructure resources such as:

- Compute
- Storage
- Networking

## AWS concepts

### Region

A geographic area containing cloud infrastructure.

### Availability Zone

An isolated infrastructure location within a Region.

Conceptually:

```text
Region
│
├── Availability Zone
├── Availability Zone
└── Availability Zone
```

### Edge Location

Infrastructure used to bring services/content closer to end users.

### Memory

```text
Region → geographic area
AZ     → isolated location within region
Edge   → closer to users
```

---

# 19. IAM

Identity and Access Management.

Core question:

> **Who can do what?**

## Authentication

**Who are you?**

Example:

> Logging in with credentials.

## Authorization

**What are you allowed to do?**

Example:

> User can read storage but cannot delete objects.

## Role

An identity with permissions that can be assumed/used by users or services.

## Policy

Defines what actions are allowed or denied.

Conceptually:

```text
Authentication
      ↓
Who are you?
      ↓
Authorization
      ↓
What can you do?
      ↓
Policy
      ↓
Allow / Deny
```

---

# 20. VPC and Security Groups

## VPC

Virtual Private Cloud.

A logically isolated network environment in the cloud.

## Security Group

A virtual firewall controlling network traffic associated with cloud resources such as instances.

### Memory

```text
VPC            → network environment
Security Group → traffic rules
```

---

# 21. Cloud Storage

Know the three major storage types:

| Type | Main idea |
|---|---|
| Object | Objects/files |
| Block | Disk/volume |
| File | Shared filesystem |

Memory:

```text
Object → files/objects
Block  → VM disk
File   → shared filesystem
```

---

# 22. Final EC-2 Priority List

If there is almost no time left, memorize these **10 areas**:

1. **IaaS vs PaaS vs SaaS**
2. **Public vs private vs hybrid vs multi-cloud**
3. **Full vs para vs hardware-assisted virtualization**
4. **VM vs container**
5. **Dockerfile creation**
6. **Image vs container**
7. **RUN vs CMD**
8. **Namespace vs cgroup**
9. **Region vs AZ vs Edge Location**
10. **Authentication vs authorization**

---

# 23. Ultra-Fast Memory Sheet

```text
CLOUD
├── Characteristics
│   ├── On-demand self-service
│   ├── Broad network access
│   ├── Resource pooling
│   ├── Rapid elasticity
│   └── Measured service
│
├── Service Models
│   ├── IaaS → Infrastructure
│   ├── PaaS → Platform
│   └── SaaS → Software
│
├── Virtualization
│   ├── Full
│   ├── Para
│   ├── Hardware-assisted
│   └── OS-level
│
├── CONTAINERS ⭐
│   ├── Dockerfile
│   ├── Image
│   ├── Container
│   ├── Registry
│   ├── Volume
│   ├── Namespace → Isolation
│   └── cgroup → Resource control
│
├── KUBERNETES
│   ├── Orchestration
│   ├── Cluster
│   ├── Node
│   └── Pod
│
└── AWS / IaaS
    ├── Region
    ├── Availability Zone
    ├── Edge Location
    ├── IAM
    │   ├── Authentication
    │   └── Authorization
    ├── VPC
    ├── Security Group
    └── Storage
        ├── Object
        ├── Block
        └── File
```

---

# 24. Source Status

### Verified from the course handout

- EC-2 = Contact Sessions 1–16
- Topics in Sessions 1–16
- Docker/Dockerfile/image/container/registry/volume coverage
- Virtualization and container topics
- Kubernetes overview
- IaaS/AWS/IAM/network/storage topics
- Practical Dockerfile/image/registry/volume exercise

### NOT yet verified from the lecturer transcripts

The following claims were discussed in the chat but **should not be treated as confirmed lecturer emphasis** until the actual transcript files are accessible:

- "The lecturer repeatedly emphasized Docker."
- "The lecturer said X is important for the exam."
- "The lecturer gave X as a likely exam question."
- Any ranking of topics based specifically on lecturer emphasis.

The uploaded ZIP was identified as containing lecture transcripts, but those transcript contents were not accessible through the file-search index during this conversation.
