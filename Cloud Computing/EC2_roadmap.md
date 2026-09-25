Yes. Since you have **only 1 hour**, don't try to study everything equally. Based on the **EC-2 portion (Sessions 1–16)**, focus on definitions, comparisons, architecture concepts, and Docker/container concepts. The handout explicitly places Dockerfiles, images, containers, registries, and volumes in Sessions 9–10.

# 🚨 EC-2 — 1-HOUR CRASH PREP

## ⏱️ Your 60-minute plan

| Time          | Study                                          |
| ------------- | ---------------------------------------------- |
| **0–10 min**  | Cloud fundamentals + service/deployment models |
| **10–25 min** | Virtualization                                 |
| **25–40 min** | **Docker + containers + Dockerfile** ⭐         |
| **40–50 min** | Kubernetes + cloud-native                      |
| **50–60 min** | AWS/IaaS + rapid revision                      |

---

# 1️⃣ Cloud Computing — 10 min

### Definition

Cloud computing = providing computing resources/services **over a network on demand**, with resource pooling, elasticity and measured usage.

### Characteristics — MEMORIZE

Think:

**O-R-P-R-M**

* **On-demand self-service**
* **Resource pooling**
* **Rapid elasticity**
* **Broad network access**
* **Measured service**

### Service Models

| Model    | You manage                 | Provider manages            |
| -------- | -------------------------- | --------------------------- |
| **IaaS** | OS, apps, data             | Hardware, virtualization    |
| **PaaS** | Application + data         | Runtime, OS, infrastructure |
| **SaaS** | Mainly usage/configuration | Almost everything           |

### Easy memory

**IaaS → rent infrastructure**

**PaaS → rent platform**

**SaaS → use software**

---

# 2️⃣ Deployment Models

### Public Cloud

Infrastructure shared among customers and operated by a cloud provider.

### Private Cloud

Cloud infrastructure dedicated to one organization.

### Hybrid Cloud

Combination of private + public cloud.

### Community Cloud

Shared by organizations with common requirements.

### Multi-cloud

Using services from **multiple cloud providers**.

⚠️ **Hybrid ≠ Multi-cloud**

Example:

> AWS + on-premise = hybrid

> AWS + Azure = multi-cloud

---

# 3️⃣ Virtualization — 15 min

### What is virtualization?

Creating a **virtual version of a computing resource**, such as CPU, memory, storage, network or a complete machine.

### Hypervisor

Software/firmware layer that creates and manages VMs.

### Two common types

**Type 1 — Bare metal**

```text
Hardware
   ↓
Hypervisor
   ↓
VMs
```

**Type 2 — Hosted**

```text
Hardware
   ↓
Host OS
   ↓
Hypervisor
   ↓
VMs
```

### Virtualization types

Know these four:

* **Full virtualization**
* **Para-virtualization**
* **Hardware-assisted virtualization**
* **OS-level virtualization**

---

## Full vs Para

### Full virtualization

Guest OS doesn't need to be modified.

```text
Guest OS
   ↓
Virtual Hardware
   ↓
Hypervisor
   ↓
Hardware
```

### Para-virtualization

Guest OS is **aware of virtualization** and may be modified to interact with the hypervisor.

---

## Hardware-assisted virtualization

CPU provides hardware support for virtualization.

Examples of concepts you may encounter:

* Intel VT-x
* AMD-V

Main idea:

> Hardware helps the hypervisor efficiently run VMs.

---

# 4️⃣ VM vs Container ⭐⭐⭐

This is extremely important.

| VM                           | Container                                |
| ---------------------------- | ---------------------------------------- |
| Virtualizes hardware         | Virtualizes/isolate OS-level environment |
| Has guest OS                 | Shares host kernel                       |
| Heavier                      | Lightweight                              |
| Slower startup               | Fast startup                             |
| More resource overhead       | Less overhead                            |
| Stronger isolation generally | Process-level isolation                  |
| Hypervisor                   | Container runtime                        |

### Remember:

```text
VM

Hardware
 ↓
Hypervisor
 ↓
Guest OS
 ↓
Application
```

vs

```text
Container

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

---

# 5️⃣ 🔥 DOCKER — 15 MINUTES

The handout specifically includes:

* Docker images
* Dockerfiles
* Containers
* Registries
* Volumes
* Namespaces
* cgroups

## Docker Image

An **immutable/template-like package** containing everything required to create a container.

Think:

> **Image = blueprint**

## Container

A **running instance of an image**.

> Image → create/run → Container

### Easy analogy

```text
Dockerfile
    ↓ build
Docker Image
    ↓ run
Container
```

---

# ⭐ Dockerfile Creation — KNOW THIS

A Dockerfile is a text file containing instructions used to build a Docker image.

### Basic Dockerfile

```dockerfile
FROM python:3.12

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["python", "app.py"]
```

### What each line does

```dockerfile
FROM python:3.12
```

Base image.

```dockerfile
WORKDIR /app
```

Sets working directory inside container.

```dockerfile
COPY requirements.txt .
```

Copies file from host → image.

```dockerfile
RUN pip install -r requirements.txt
```

Executes command **while building the image**.

```dockerfile
COPY . .
```

Copies application files.

```dockerfile
EXPOSE 8000
```

Documents the port the application listens on.

```dockerfile
CMD ["python", "app.py"]
```

Default command executed when the container starts.

---

# 🔥 RUN vs CMD

Very likely MCQ territory.

### RUN

Executed **during image build**.

```dockerfile
RUN pip install flask
```

### CMD

Default command when **container starts**.

```dockerfile
CMD ["python", "app.py"]
```

Remember:

> **RUN → BUILD**

> **CMD → RUN**

---

# Dockerfile vs Image vs Container

Memorize this diagram:

```text
              docker build
Dockerfile ───────────────→ Image
                              │
                              │ docker run
                              ↓
                          Container
```

---

# Docker Commands

Know these basic commands:

### Build

```bash
docker build -t myapp .
```

### Run

```bash
docker run myapp
```

### Run with port mapping

```bash
docker run -p 8000:8000 myapp
```

Meaning:

```text
HOST : CONTAINER
8000 : 8000
```

### List containers

```bash
docker ps
```

### List all containers

```bash
docker ps -a
```

### Stop

```bash
docker stop <container>
```

### Remove

```bash
docker rm <container>
```

### List images

```bash
docker images
```

---

# Docker Registry

Registry = location where Docker images are **stored and distributed**.

Example:

```text
Dockerfile
    ↓
docker build
    ↓
Image
    ↓
docker push
    ↓
Registry
    ↓
docker pull
    ↓
Another machine
```

Examples include Docker Hub and private registries.

---

# Docker Volumes

Containers are generally treated as ephemeral.

If you need persistent data:

```text
Container
    ↓
Volume
    ↓
Persistent storage
```

Example:

```bash
docker run -v mydata:/data myapp
```

### Remember

**Container = application environment**

**Volume = persistent data**

---

# 6️⃣ Namespaces & cgroups

Very important conceptual distinction.

### Namespaces

Provide **isolation**.

They isolate things such as:

* Processes
* Network
* Mounts
* Users
* Hostname

Think:

> **Namespaces = "What can I see?"**

### cgroups

Control/limit **resource usage**.

Examples:

* CPU
* Memory
* I/O

Think:

> **cgroups = "How much can I use?"**

🔥 Memorize:

> **Namespace = isolation**

> **cgroup = resource control**

---

# 7️⃣ Kubernetes — 5 min

You only need the basic concept for this portion.

Kubernetes = **container orchestration platform**.

It helps manage:

* Container deployment
* Scaling
* Scheduling
* Networking
* Recovery/self-healing

Basic structure:

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

### Pod

Smallest deployable unit in Kubernetes.

Usually contains one or more closely related containers.

---

# 8️⃣ Cloud-Native Principles

Know these keywords:

* **Microservices**
* **Containers**
* **Declarative deployment**
* **Portability**
* **Automation**
* **Scalability**

### Declarative vs imperative

**Imperative:**

> "Do these steps."

**Declarative:**

> "This is the desired state."

Kubernetes is heavily based on **declarative configuration**.

---

# 9️⃣ IaaS / AWS — Last 10 min

## IaaS

Provides fundamental infrastructure resources such as:

* Compute
* Storage
* Networking

You manage more of the stack compared with PaaS/SaaS.

---

# AWS Regions vs AZ vs Edge

🔥 VERY IMPORTANT

### Region

Geographic area containing AWS infrastructure.

Example concept:

```text
Region
│
├── Availability Zone
├── Availability Zone
└── Availability Zone
```

### Availability Zone

An isolated infrastructure location within a Region.

Used to improve availability/fault tolerance.

### Edge Location

Used primarily for delivering content/services closer to users.

### Memory trick

> **Region = geographic area**

> **AZ = isolated location inside region**

> **Edge = closer to users**

---

# 🔐 IAM

Identity and Access Management.

Controls:

> **Who can do what?**

### Authentication

**Who are you?**

Example:

> Login with username/password.

### Authorization

**What are you allowed to do?**

Example:

> User can read S3 but cannot delete it.

### Role

An identity with permissions that can be assumed/used by users or services.

### Policy

Defines permissions.

Think:

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
Allowed / Denied
```

---

# VPC + Security Groups

### VPC

Virtual Private Cloud = logically isolated network environment in the cloud.

### Security Group

Acts as a virtual firewall controlling network traffic to/from resources such as instances.

Don't confuse:

> **VPC = network environment**

> **Security Group = traffic rules**

---

# 💾 Storage — MUST KNOW

Three types:

| Type               | Think             |
| ------------------ | ----------------- |
| **Object storage** | Files/objects     |
| **Block storage**  | Disk/volume       |
| **File storage**   | Shared filesystem |

### Easy example

```text
Object → S3-like storage
Block  → VM disk
File   → Shared filesystem
```

---

# 🧠 FINAL 5-MINUTE MEMORY SHEET

If you have literally **5 minutes left**, memorize this:

```text
CLOUD
├── Characteristics
│   ├── On-demand
│   ├── Broad network access
│   ├── Resource pooling
│   ├── Rapid elasticity
│   └── Measured service
│
├── Service Models
│   ├── IaaS
│   ├── PaaS
│   └── SaaS
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
│   ├── Namespace → isolation
│   └── cgroup → resource control
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

## ⭐ 10 things I would NOT walk into EC-2 without knowing

1. **IaaS vs PaaS vs SaaS**
2. **Public vs private vs hybrid vs multi-cloud**
3. **Full vs para vs hardware-assisted virtualization**
4. **VM vs container**
5. **Dockerfile**
6. **Image vs container**
7. **RUN vs CMD**
8. **Namespace vs cgroup**
9. **Region vs AZ vs Edge Location**
10. **Authentication vs authorization**

And **practice writing this Dockerfile from memory**:

```dockerfile
FROM python:3.12
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 8000
CMD ["python", "app.py"]
```

The official handout confirms that EC-2 ends at **Contact Session 16**, while Docker/Dockerfile content is specifically in Sessions 9–10 and IaaS begins at Sessions 13–16.

Keep your EC-2 revision focused

* Practice Dockerfile questions
* Review the hardest comparisons
* Take a rapid EC-2 quiz
