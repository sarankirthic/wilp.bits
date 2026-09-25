# Cloud Computing: 1-Hour Revision Guide (Mid-Sem, Modules 1–3)

**Built from:** your 8 lecture transcripts + the course handout (v3.0).
**Mid-Sem:** closed book, 30%, 2 hours. Handout lists **20/09/2026 (afternoon)**; the lecturer said "19th" in Session 6, so confirm on eLearn.
**Syllabus:** contact sessions 1–16 = **Module 1** (Intro), **Module 2** (Virtualization & Containers), **Module 3** (IaaS/AWS).

⭐ = the lecturer explicitly stressed it or hinted it is exam-relevant.

## Study plan (60 min)

| Time | Section | What to do |
|---|---|---|
| 0:00–0:05 | 0. Exam intel | Read once; know the priority list |
| 0:05–0:15 | 1. Intro to Cloud | Learn the 3-4-5 framework cold |
| 0:15–0:30 | 2. Virtualization | Master the 3 techniques, hypervisor types, overcommitment maths |
| 0:30–0:42 | 3. Containers & Docker | VM vs container table, namespaces/cgroups, Dockerfile |
| 0:42–0:55 | 4. IaaS / AWS / EC2 / Storage | Regions, IAM, EC2, block/file/object |
| 0:55–1:00 | 5. Self-test + cheat sheet | Cover the answers and quiz yourself |

---

## 0. Exam intel (what the lecturer actually said)

- **Style:** scenario- and analysis-based. Answer to the point; length is not judged by marks.
- **No code or scripting.** Cloud concepts only: motivations, origins, NIST definitions, virtualization, Docker, containerization.
- **Dockerfile is examinable** (he calls it IaC, not code). You should know how to create and read one.
- **Kubernetes/orchestration:** terminology only. Do not study it deeply.
- **PaaS is not expected** in this mid-sem (he said the syllabus would run "till IaaS only").
- Sample question styles he showed (not the real questions):
  - a ticket-selling website scenario
  - "a cloud-native approach may not work for converting legacy systems; justify why"
  - questions based on a "convergence of technologies" figure

**Priority list (study these first):**

1. ⭐ NIST **3-4-5** (service models, deployment models, characteristics)
2. ⭐ **VM, host, guest, hypervisor** and hypervisor types
3. ⭐ **Three virtualization techniques:** binary translation (full), para, hardware-assisted, plus x86 rings
4. ⭐ **CPU and memory overcommitment** (ratio maths)
5. ⭐ **VM vs container** ("the most important differentiation")
6. ⭐ **Namespaces and cgroups** (what each does, not the file details)
7. ⭐ **Dockerfile** and image layers / copy-on-write
8. ⭐ **Local zone vs AZ**; Wavelength vs Outposts
9. ⭐ **IAM:** authentication vs authorization, roles, policies; shared responsibility model
10. ⭐ **EC2:** instance types, AMI, key pair, security group, tenancy
11. ⭐ **Block vs file vs object storage**; S3, EBS, EFS, Glacier

**Skip list (he said not needed):** cgroup parameter names, VPC/CIDR maths (unless doing an AWS cert), monolithic vs microkernel hypervisors, Docker syntax memorisation, Kubernetes internals.

---

## 1. Module 1: Introduction to Cloud Computing

### 1.1 Definition and motivation

- **NIST definition (paraphrase):** cloud computing is a model for convenient, on-demand network access to a **shared pool of configurable resources** (servers, storage, networks, apps) that can be provisioned and released quickly with minimal management effort.
- **Lecturer's version:** applications and services that run on a **distributed network**, use **virtualized resources**, and are accessed via standard internet protocols.
- Quick sound bite: "someone else's computer, rented by the slice."
- ⭐ **The Dilbert lesson:** moving to the cloud does not automatically solve your problems. The app must be **cloud-native** (able to scale out, restart from failure, run in parallel). A giant monolith that cannot break or resume is hard to move.
- **Cloud vs plain hosting:** hosting rents you a fixed machine. Cloud gives on-demand, elastic, metered, self-service resources.
- **Motivation (Session 6 recap):**
  - Old world: plan hardware procurement months ahead, pay big upfront capital, and face customs and vendor lead times.
  - Cloud: negligible lead time, pay-as-you-go, not tied to a location.

### 1.2 Evolution and origins

- **Computing journey:** dumb terminals and mainframes → Unix → distributed servers → server farms → **virtualized, software-defined data centres**.
- **Technologies that converged:** distributed computing (clusters, grids, parallel computing), virtualization, cheap broadband/internet, web services, and systems management.
- **Amazon story:** Amazon started as an online bookstore and bought lots of servers. When it had spare capacity, it started renting it out, like carpooling. Rackspace was an earlier hosting pioneer (physical servers on rent, not cloud).
- **Why "cloud"?** A cloud drawing was used for the external network in old architecture diagrams.

### 1.3 ⭐ The NIST 3-4-5 rule

| The "3" | The "4" | The "5" |
|---|---|---|
| Service models: IaaS, PaaS, SaaS | Deployment models: public, private, community, hybrid | Essential characteristics |

**The 5 essential characteristics:**

1. **On-demand self-service:** get resources yourself via portal/API with no human in the loop.
2. **Broad network access:** available over the network from any standard device.
3. **Resource pooling:** the provider's resources are shared across many customers (multi-tenant), and you don't know where they physically are.
4. **Rapid elasticity:** scale up or down quickly, for example 15 GB → 1 TB storage and back.
5. **Measured service:** usage is metered and billed per service consumed.

**Other common traits (lecturer's list):** massive scale, resilience (auto-swap failed instances), heterogeneity, virtualization, low-cost software, advanced security, service orientation, geographic distribution.

**Service models:**

| Model | You get | Example | Analogy (lecturer) |
|---|---|---|---|
| **IaaS** | Compute, storage, network, OS. You load your own software. | AWS EC2, Azure VMs, GCP | Company gives a new hire a bare machine on a network |
| **PaaS** | Ready platform: OS + dev tools/runtime. You bring code. | Azure platform services, Visual Studio/DevOps environments | Machine already loaded with OS and Eclipse |
| **SaaS** | Finished application via a link | Gmail, Office 365, SharePoint Online | Just open the app |

- All the "XaaS" variants (DBaaS, BaaS, etc.) fit under these three pillars.
- **Provisioning** = the act of requesting and getting a resource.
- **IaaS pricing analogies (lecturer):** an advance **reservation** is committed and cheaper; an **on-the-spot** request costs more (like a Tatkal ticket).

> Real AWS note: on-demand is the default pay-as-you-go rate, reserved/savings plans give discounts for commitment, and Spot is discounted spare capacity that can be interrupted.

### 1.4 ⭐ Deployment models

| Model | Meaning | Lecturer's analogy |
|---|---|---|
| **Public** | Owned and run by a provider; anyone can subscribe. Pay-as-you-go. | Indian Railways / metro |
| **Private** | Dedicated to a single organisation. Can be on-premise or carved from public infrastructure with restricted access. | Company-only shuttle buses |
| **Community** | Shared by several organisations with common interests | Metro Zip serving many Hinjewadi employers; CERN's scientific cloud. Rare today. |
| **Hybrid** | Private + public together | A cook who buys 150 extra dishes from another caterer at peak |
| **Multi-cloud** | Multiple providers at once, to avoid lock-in and a single point of failure | Multiple OTT subscriptions |

- ⭐ **Service model ≠ deployment model.** Service models describe what you get (IaaS/PaaS/SaaS). Deployment models describe how you consume it. Any deployment model applies to any service model.
- **Cloudbursting** = overflow from your own capacity to another (public) cloud when demand spikes suddenly.
- **Homogeneous vs heterogeneous:** one provider means a uniform infrastructure; multi-cloud means heterogeneous.
- **Shared vs dedicated:** "shared" refers to underlying hardware. Your VM is not shared, but the hardware beneath it is.

### 1.5 Infrastructure overview and multi-tenancy

- Cloud infrastructure = compute + storage + network, delivered from **data centre regions**.
- **Multi-tenancy** = many customers on the same physical hardware (like carpooling). This is what lowers cost.
- **Geographic distribution:** pick a region close to users or one that meets legal needs. Cost varies by region.

### 1.6 Benefits and limitations

| Benefits | Limitations / risks |
|---|---|
| No upfront capex, pay for use | **Cost surprises:** forgetting to switch things off; every customisation adds cost |
| Fast provisioning (minutes) | Provider outages cascade to you (JetBlue-type incidents) |
| Elasticity and auto-scaling | **Data residency and compliance** (GDPR, government rules) |
| Global reach and resilience | Latency for far-away regions |
| Lower cost through shared pools | Vendor lock-in (why multi-cloud exists) |
| Focus on business, not hardware | Applications must be cloud-ready |
| | Loss of control over underlying infrastructure |

---

## 2. Module 2: Virtualization

### 2.1 What and why

- **Virtualization** turns physical hardware into software-defined equivalents. It is the **key enabler of IaaS and cloud**. Without hypervisors, there is no cloud.
- **Vocabulary:**
  - **Host:** the physical machine plus its hypervisor.
  - **Guest / VM:** the virtual machine created by the hypervisor.
  - **Hypervisor / VMM (Virtual Machine Monitor):** software, firmware, or hardware that creates and runs VMs and manages host resources.
- ⭐ **Virtualization is not only about CPUs:** storage, network, memory and devices can all be virtualized.

**Levels of virtualization:**

| Level | Example |
|---|---|
| Application | JVM, .NET runtime (a translator between code and the host ISA) |
| Library | WINE (a library that lets Windows apps run on Linux; not an emulator) |
| **Operating system** | Containers/Docker (walled-off spaces sharing one kernel) |
| **Hardware abstraction** | Hypervisors (VMware, VirtualBox), which are what cloud VMs use |
| ISA | Cross-architecture emulation (e.g., x86 code on ARM); rarely practical now |

**Other resource types:**

- **Storage virtualization:** a pool of disks is presented as contiguous blocks. The provider chunks and **replicates** files (like OneDrive/Google Drive).
- **Network virtualization:** e.g., **VLAN** lets many logical networks share the same physical switch.
- **Memory virtualization:** memory cannot be shared naively (integrity issues), so you use the overcommitment techniques in 2.5.
- **Device virtualization:** USB, serial, printer ports and similar.

### 2.2 ⭐ Benefits and limitations

**Hypervisor design goals:**

- **Fidelity:** a VM must behave like a real machine.
- **Resource control:** the VMM stays in control of the host, and guests cannot bypass it.
- **Efficiency:** near-native performance.

**Benefits (business goals):**

- **Time sharing / resource multiplexing:** many VMs on one box, so lower cost per PC.
- **Isolation and fault containment:** one VM failing doesn't affect others (flat/apartment analogy).
- **Security boundary.**
- **Hardware abstraction and portability:** move a VM to another host or cluster.
- **Operational agility:** provision 12 VMs in minutes from a template, versus a week or more of lead time before.
- **Reliability and availability, legacy application support** (e.g., a COBOL VM), a choice of OS, and load balancing.

**Limitations:**

- Performance overhead, especially with weaker techniques.
- **Host or hypervisor failure takes down every guest** (the "fire in the building" case).
- **Overcommitment risks:** slowdowns, hung VMs.
- Needs capable hardware. Old hardware may not convert well to cloud.
- Guest and host must usually share the same ISA.

### 2.3 ⭐ Hypervisor types

| | **Type 1: bare-metal** | **Type 2: hosted** |
|---|---|---|
| Runs on | Directly on hardware | On top of a host OS |
| Example | VMware vSphere/ESXi, Xen, Hyper-V, KVM | Oracle VirtualBox (what you used in the lab) |
| Use | Data centres and cloud | Desktops, learning |
| Management | Central console (e.g., vCenter) sees every node in the rack | Managed per machine |

- Cloud providers use **hyperscale hypervisors**. AWS uses **Nitro**: virtualization offloaded to dedicated chips with remote control planes.
- The cloud SRE plans how many VMs a host can carry and monitors capacity.

### 2.4 ⭐ x86 hardware virtualization: rings and the three techniques

**x86 privilege rings:**

- **Ring 0** = most privileged (the OS kernel). **Ring 3** = least privileged (user applications). Rings 1 and 2 are barely used.
- **Ring model:** the kernel controls memory, network and devices. A user app that wants a sensitive operation makes a request, and the kernel **traps** it (like a secretary stopping you before you reach the CEO).
- ⭐ **The problem:** a guest OS expects to be in ring 0 to issue privileged instructions, but the host kernel already owns ring 0. If the VM runs as an ordinary app in ring 3, its privileged instructions fail. So how do we let guests behave like real machines?

**Three solutions, in order of history:**

| | **Binary translation (full virtualization)** | **Paravirtualization** | **Hardware-assisted** |
|---|---|---|---|
| Idea | Hypervisor traps and rewrites guest's privileged instructions on the fly | Guest kernel is modified to call the hypervisor directly via **hypercalls** | CPU itself supports virtualization; hardware handles privileged events |
| Guest OS modified? | No, and it doesn't know it's virtualized | **Yes** (recompiled kernel/PV drivers) | No |
| Guest ring | Moved to **ring 1** | Ring 1 | Runs normally under new CPU modes (Intel VT-x, AMD-V) |
| Analogy (lecturer) | Shadow agent following an amnesiac ex-owner | Guest told the truth and given a call button | Hotel room redesigned so every device calls the right desk |
| Pros | Works with any OS | Less overhead than translation | Best performance; no translator, no retraining |
| Cons | Translator per guest → latency, can be overwhelmed; guest and host must share ISA | Needs kernel changes: easy for open-source Linux/BSD, hard for Windows; less portable | Needs modern CPU |
| Era | First (VMware) | Second | **Modern cloud standard** |

- ⭐ **Full virtualization does not give cross-architecture flexibility.** Guest and host must share the same ISA (instruction set architecture, e.g., x86-64).

### 2.5 ⭐ Resource management and overcommitment

**IaaS reference architecture (bottom to top):**

1. Physical machines bought by the provider
2. Virtualization layer
3. **Resource pools** (vCPU, memory, storage, network)
4. Monitoring and management
5. **Self-service portal**

This stack delivers the five NIST characteristics (on-demand self-service, elasticity, pay-as-you-go). Everything is a chargeable service.

**Who manages what:**

| Layer | IaaS | PaaS | SaaS |
|---|---|---|---|
| Application and data | You | You (app/data) | Provider |
| Runtime / middleware / OS | You | Provider | Provider |
| Virtualization, servers, storage, network | Provider | Provider | Provider |

**CPU overcommitment** (assuming no CPU is busy 100% of the time):

- **Ratio = total vCPUs ÷ physical cores.**
- **1:1** for latency-sensitive workloads (databases, real-time transactions).
- **3:1 to 5:1** is a typical sweet spot for microservice-style apps.
- **Above about 8:1** you are in trouble.
- Warning sign: **CPU-ready time above about 5%**. Processes hang and the VM struggles.
- ⭐ **Worked example:** host has 4 physical cores, 6 VMs × 2 vCPU = 12 vCPU → 12 ÷ 4 = **3:1**, which is in the safe zone but must be monitored.

**Memory overcommitment:**

- **Example:** 128 GB RAM host, 20 VMs × 8 GB = 160 GB → 160 ÷ 128 = **1.25:1**.
- Techniques, from best to worst:
  1. **Transparent page sharing:** merge identical pages across VMs, with **copy-on-write** when a VM modifies a shared page.
  2. **Ballooning:** the hypervisor makes the guest OS give back unused memory.
  3. **Compression:** compress pages in RAM.
  4. **Host swapping:** spill to disk. This is the slowest.
- Overcommitment is trial and error: tune, watch, retune. It sits at the heart of cloud cost optimisation (FinOps).

**T-series CPU credits (AWS example of the same idea):** an idle instance banks credits, and a busy instance spends them. When credits run out it is throttled to a baseline.

---

## 3. Module 2 (contd.): Containers and Docker

### 3.1 Why containers

- **Problem:** apps on a shared machine have conflicting dependencies (like pouring roti, rice and dal into one plastic bag). A container **packages an app with its dependencies** and isolates it.
- **Containers = OS-level virtualization.** They share the **host kernel** and skip the guest OS and hypervisor. They are very light and start in ms to seconds.

### 3.2 ⭐ Namespaces and cgroups (both are Linux kernel primitives)

| | **Namespaces** | **cgroups (control groups)** |
|---|---|---|
| What | **Isolation:** each container gets its own view of processes, network, filesystem, etc. | **Resource limits and accounting:** CPU, memory, I/O per container |
| Analogy | Your own apartment or a secure team space in the building | The society's rules: pool timings, occupant limits |
| Purpose | Contain what a container can *see* | Stop a "greedy" container from hogging resources |

- He said you may be asked **what** namespaces and cgroups are, but **not** the detailed parameters.
- **History:** namespaces/cgroups existed in the kernel in the mid-2000s. **LXC** (Linux Containers) was the first usable tool wrapping them. Docker initially built on it. **LXD** is the improved successor.
- LXD improvements over LXC: one daemon managing all containers, better control, and **snapshots** (useful for migration).
- Older cgroups were "advisory". Newer setups enforce limits strictly.

**System (OS) containers vs application containers:**

| | System container | Application container |
|---|---|---|
| Runs | A full OS user-space (e.g., Rocky Linux) | One app plus its dependencies |
| Tool | LXC/LXD | Docker |
| Demo you saw | EC2 Ubuntu VM → LXD → Rocky Linux container. `uname -r` showed the **same kernel**, but `os-release` showed a different OS. | Docker containers on the same VM |

- ⭐ **Consequences of the shared kernel:** the container OS can differ but the **kernel is the host's**. It must share the same ISA, and a container cannot use a kernel feature the host lacks. Cross-ISA images do not work.

### 3.3 Docker architecture

- **Client (CLI):** where you type `docker build`, `docker run`, etc.
- **Daemon / engine (`dockerd`):** listens to the client, builds and runs containers. Can be centralised for many clients.
- **Registry:** stores images. **Docker Hub** is the public default. Private registries exist (Azure, AWS ECR) for compliance and security.
- **Objects:** images, containers, volumes, networks, plugins.
- **Pull flow:** check the **local image cache first**, then go to the registry. Pulled images are cached locally.
- Use **official/certified images**, because anyone can push malicious ones.

### 3.4 ⭐ Images, layers and copy-on-write

- An **image** = a read-only template (poha analogy: freeze a dish, thaw to get the same dish anywhere). A **container** = a running instance of an image.
- Each Dockerfile instruction adds a **layer** on top of the base image.
- ⭐ **Copy-on-write (COW):** the base layers are never modified. Your changes go into a new writable layer. This keeps the original image intact (integrity, security, reproducibility, no "it works on my machine").
- **Same idea** as page sharing in memory overcommitment: share until someone needs to change.
- Reproducibility is the payoff: the same image behaves identically in Pune, Chennai or Delhi.

### 3.5 ⭐ Dockerfile

- File name is exactly **`Dockerfile`**: capital D, **no extension**, case-sensitive.
- Illustrative example:

```dockerfile
FROM python:3.12-slim          # base image (pin the version!)
WORKDIR /app
COPY requirements.txt .        # dependencies first
RUN pip install -r requirements.txt
COPY . .                       # app code last
CMD ["python", "app.py"]       # what runs on start
```

**Best practices he stressed:**

- ⭐ **Pin image versions**, don't rely on `:latest`. Otherwise a newer base can break your libraries and bring back the same dependency conflict.
- ⭐ **Never hardcode secrets** (passwords, API keys) in a Dockerfile. Anyone with the image can run `docker history` and read them. Pass secrets at runtime with `-e`.
- **Order steps:** update → install dependencies → copy application code last, so layers are reused.
- The trailing **`.`** in `docker build -t name:tag .` tells Docker where to find the Dockerfile and build context.

### 3.6 Commands and container lifecycle

| Command | What it does |
|---|---|
| `docker build -t name:tag .` | Builds a **new image** from a Dockerfile |
| `docker pull name:tag` | Downloads an existing image |
| `docker commit` | Creates an image from a running container |
| `docker create` | Creates a container but **doesn't start** it |
| `docker start` | Starts an existing container |
| `docker run` | **Create + start** in one step (the only one that does both) |
| `docker run -it` | Interactive, attaches your terminal (it blocks your screen) |
| `docker run -d` | **Detached**, runs in the background |
| `docker exec -it <name> sh` | Get a shell inside a running container |
| `docker images` / `docker ps` / `docker ps -a` | List images / running containers / all containers |
| `docker volume create`, `docker network create` | Volumes and networks |

- Container **names must be unique**.
- A container that finishes its command **exits**. Only long-running processes stay up.
- `docker run -e VAR=... -v vol:/path -p 5433:5432` sets an env var, mounts a volume, and maps host port 5433 to container port 5432. Port mapping is how you run two Postgres containers on the same VM.

### 3.7 Volumes and networks

- **Volumes** give persistent storage that outlives a container. A local volume lives on the VM's disk, so if the VM dies the data is gone. For durability, back it with **EBS, EFS or S3**.
- **Networks:** to make an app container talk to a DB container, create a user-defined network (e.g., `pgnet`) and attach both. Keep the **persistence layer separate** from the app.
- **Demo you saw:** custom Postgres image built from a Dockerfile plus `init.sql`, run with a volume and port mapping, with a Python app container joined over a network.

### 3.7a Orchestration and cloud-native (terminology only)

- **Container orchestration** = managing many containers (scheduling, scaling, networking, healing). **Docker Swarm** is Docker's own. **Kubernetes** is now the industry choice. Not examined in depth.
- **Cloud-native principles** (handout 2.12): microservices, declarative deployment, portability.

### 3.8 ⭐ VM vs container

| | **Virtual machine** | **Container** |
|---|---|---|
| Virtualizes | **Hardware** (via hypervisor) | **The OS** (namespaces + cgroups) |
| Guest OS | Full guest OS with its own kernel | Shares the **host kernel** |
| Start time | Seconds to minutes | Milliseconds to seconds |
| Size | Large (GBs) | Small (MBs) |
| Density (workloads per host) | Low | **High** |
| Managed by | Hypervisor | Container engine |
| Isolation | Strong (separate kernels) | Weaker (shared kernel) |
| Guest OS can differ from host? | Yes | OS flavour can differ, **kernel must be the same** |

- **Nested:** you commonly run **containers inside a VM** (your EC2 VM hosted both LXD and Docker containers).

---

## 4. Module 3: IaaS and AWS

### 4.1 IaaS basics

- **IaaS** lets you provision processing, storage, networks and other fundamental resources, and run arbitrary software (OS and apps). You **don't manage or control** the underlying cloud infrastructure.
- **Characteristics:** dynamic scaling (1, 10, 100 units), variable cost, multi-tenancy, no hardware purchase. Delivered as public, private or hybrid.
- **Everything is a service** (compute, storage, network, OS) and is time-sliced and metered.
- **Motivation:** the same procurement lifecycle as on-premise, but with negligible lead time, and capex becomes pay-as-you-go (BH-series vehicle registration analogy).
- **Architecture:** the physical layer is invisible to you (served through regions, AZs, edge, Outposts, Wavelength zones). You build compute pools, network pools and storage pools that are all software-defined (VPC, subnets, gateways are software constructs).
- **AWS is the reference platform** for the course. Azure has the Azure Portal and GCP has its console; the concepts are the same.

### 4.2 ⭐ Regions, AZs and edge

| Term | Meaning |
|---|---|
| **Region** | A geographic location (e.g., US East N. Virginia, Mumbai). Chosen for latency, cost and **legal/data-residency** needs. |
| **Availability Zone (AZ)** | One or more data centres within a region, linked with redundant connectivity. AZs sit in different locations to avoid single-point risk (the Mumbai flooding story). Their physical addresses are confidential. |
| **Edge locations** | Points closer to users for content delivery/caching. |
| ⭐ **Local Zone** | An **extension of a region** closer to your users, offering a **subset of services** for lower latency (Pizza Hut Express at the airport vs the full restaurant). |
| ⭐ **Wavelength Zone** | AWS compute placed **inside telecom carriers' 4G/5G data centres** for ultra-low latency (e.g., driverless-car telemetry). Only in select places. |
| ⭐ **Outposts** | AWS infrastructure installed **in your own premises** (like a bank's ATM in your office). For data-residency rules (GDPR, US gov) and zero-latency local access. |

- **Wavelength vs Outposts:** Wavelength sits in the carrier's network. Outposts sits in your building.
- ⭐ **Local zone vs AZ** was flagged as a likely mid-sem question. Answer along these lines: an AZ is a full data-centre group within a region. A local zone extends the region toward the customer with a limited set of services for low latency.
- **AZs give you a failover option, not automatic failover.** If you put everything in one AZ and it fails, you lose it. You choose redundancy (multi-AZ deployments, Auto Scaling, replication).
- **Not all services exist in all regions.** Services get added and deprecated, so check the docs.
- **Region cost varies.** US East (N. Virginia) is the cheapest. Newer regions (Mumbai, Singapore, Abu Dhabi) cost more.
- About 80–90% of workloads use standard regions and AZs. Only 10–20% (ultra-low latency, intensive compute) need special locations.

### 4.3 ⭐ Shared responsibility model

- **AWS** is responsible for the **cloud itself**: hardware, software, regions, availability zones.
- **You** are responsible for what you put **in** the cloud: your **data, applications and identity/access management**. On IaaS this also covers your guest OS and instance firewall rules (security groups).
- Providers won't stop you from doing something unsafe in your own instance (the chartered-coach "havan" analogy).

### 4.4 ⭐ IAM (Identity and Access Management)

| Concept | Meaning | Analogy |
|---|---|---|
| **Authentication** | Proving **who you are** | ID card check at the gate |
| **Authorization** | What you're **allowed to do** once identified | Card only opens floors 1, 5 and 7 |
| **Roles** | Bundles of permissions/responsibilities assigned to identities | Access profile for a particular building/project |
| **Policies** | The **rulebook** stating what's allowed (read-only vs super-user) | Actual access rules |

- **Why it matters:** cloud has a large attack surface, and one mistake can mean a catastrophic data or reputation loss.
- **Least privilege:** give only the access needed.
- Authentication ≠ authorization.

### 4.5 ⭐ Compute: EC2 (Elastic Compute Cloud)

**Basics**

- **EC2** = AWS compute service. You launch **instances** (virtual machines). Name: "Elastic Compute Cloud", written as "EC2" like "A2B".
- **Billing:** each component (instance, storage, IP) is charged separately (burger with extras). ⭐ **Switch off what you're not using.** The onus is on you. Set a **billing alert**.
- The old free tier is gone. You get starter credits, and any instance costs money.

**Instance types and families**

- Families: **general purpose** (T3, M7), **compute-optimised**, **memory-optimised**, **storage-optimised**, **HPC**. "Right tool for the right job."
- **Graviton** = AWS's own **ARM-based** processors (not x86), usually cheaper than Intel.
- Within a family, size increases (nano → micro → small → medium → large → xlarge), giving more vCPU/RAM and higher price.
- **Lab restriction:** only **T3a** allowed. Others give a "not authorised" error.
- Instance type can be **changed after stopping** the instance.
- **Burstable (T-series):** earn CPU credits when idle and spend them under load. When credits are exhausted you are throttled to baseline (like a fair-usage broadband policy). *(T3 can also run in "unlimited" mode, where you pay for the surplus instead.)*
- The hypervisor exposes different virtual hardware depending on the underlying servers (Intel/AMD/Graviton). That's why Windows Server can run in a 1 GB instance: memory management plus time-slicing.

**⭐ AMI (Amazon Machine Image): 4 ways to get one**

1. **Published by AWS** (Amazon Linux, Ubuntu, Windows, macOS, Red Hat…)
2. **Created from your existing instance** (organisations harden a base OS and share it as a golden image)
3. **AWS Marketplace** (third-party bundles, e.g., SQL Server, Ubuntu Pro; extra cost)
4. **Uploaded virtual servers:** VMDK (VMware) or VHD (Azure) images imported for migration. Not everything migrates seamlessly.

**Launch flow:** name → AMI → instance type → **key pair** → network (VPC/subnet) → **security group** → storage → launch.

**⭐ Key pairs and security groups**

- **Key pair** = public/private key. AWS keeps the public key, you keep the private key. **Lose it and you lose access.**
  - **.pem** works with OpenSSH and is used to decrypt the Windows admin password.
  - **.ppk** is for PuTTY.
- **Security group** = the virtual firewall controlling **who can reach the instance and on which port**. He called this "the most important question."
  - SSH = port 22, RDP = 3389, HTTP = 80.
  - ⭐ `0.0.0.0/0` opens the rule to the entire internet, a **no-no** in real life. Restrict to **My IP**. If your IP changes, edit the inbound rule.
- **Session Manager** is an advanced alternative to SSH.
- In real organisations these settings are stored as code (Terraform, Ansible).

**Connecting**

- **Linux:** SSH (PuTTY/PowerShell). Default user `ec2-user` on Amazon Linux, `ubuntu` on Ubuntu. Key file permissions must be restricted or you get a "bad permissions" error.
- **Windows:** **RDP** file → decrypt password using your private key.
- **EC2 Instance Connect** = browser-based.

**Identifiers and IPs**

- **Public IP** (changes on stop/start), **private IP**, **instance ID**, and the **ARN** (Amazon Resource Name: `arn:aws:ec2:<region>:<account-id>:instance/<instance-id>`).
- ⭐ **Elastic IP** = static public IP you keep. **Billed if not attached** to a running instance.

**⭐ Lifecycle:** `pending → running → stopped → terminated`

- **Stopped:** you don't pay for compute, but **attached volumes still cost**. Software you installed is preserved.
- **Terminated:** instance is destroyed. This is the only way to be sure charges stop.

**⭐ Tenancy**

| | Meaning | Analogy | Cost |
|---|---|---|---|
| **Shared** | Instances from different customers on the same physical host (80–90% of workloads) | A train coach with strangers | Lowest |
| **Dedicated instance** | Your instances run on hardware not shared with other customers | Booked the whole coach | Higher |
| **Dedicated host** | The whole physical server is yours | Booked the whole bus | Highest |

**Other EC2 topics**

- **Placement groups:** place related instances (e.g., API layer + database) close together for **high-speed networking (10 Gbps+)**.
- **VPC (Virtual Private Cloud):** your private network in the cloud, including subnets, gateways, peering and NAT. Instances are launched into a subnet. He said the CIDR maths isn't needed here.
- **Auto Scaling** for capacity and DR: policies define how many instances, when and where.
- **Old note:** EC2-Classic had no VPC; EC2-VPC is today's model.

### 4.6 ⭐ Storage: block vs file vs object

| | **Block** | **File** | **Object** |
|---|---|---|---|
| Stores | Data as fixed-size **raw chunks** (block size depends on hardware). Only the changed chunk is rewritten. | Files and folders via a **file system** (NTFS, ext4) layered **on top of block** | Whole **objects + metadata** in a flat structure |
| Access | Low latency, random read/write | Shared paths / mounts | HTTP/API; **write once, read many (WORM)** |
| Update | Chunk-level | File-level | Replace the **entire object** |
| Best for | Databases, transaction processing | Shared files, web servers, dev/test | Large objects, backups, media, static websites, big data |
| AWS | **EBS**, instance store | **EFS** | **S3**, Glacier |

- **EBS (Elastic Block Store):** persistent block volumes for EC2. Types include SSD and **Provisioned IOPS SSD**. **IOPS** = input/output operations per second. Choose based on workload latency needs.
- **Instance store (ephemeral):** local, temporary disks. Data is lost when the instance stops or terminates.
- **EFS (Elastic File System):** managed shared file system for big data, web servers and dev/test.
- **S3 (Simple Storage Service):**
  - **Bucket** = container (created in a specific region). Each file inside is an **object**.
  - Flat "quasi file structure": you create buckets, not nested folders.
  - Large objects use **multipart upload** (split and upload in parts). Max object size is 5 TB. *(The transcript is garbled on this figure.)*
  - Access is via API calls (create bucket, list, put object, get object).
  - Pick the region carefully for **compliance** (GDPR etc.).
  - **No automatic failover or replication.** DR is up to you unless you configure replication.
  - You can't nest buckets. Think of Google Drive with a single folder level.
- **Glacier:** cold **archive** storage for infrequently accessed data kept for compliance (bank retention rules, like tape archives). It now lives inside S3 as an archive tier, and the limits are the same as S3.
- **Charges:** **data at rest** (storing it) and **data in motion** (reading/transferring out) are both billed.

### 4.7 Data services and big data (only touched briefly in class)

The lecturer said this was compressed and promised more, but it was never taught in depth. Orientation only:

- **RDS:** managed relational databases on AWS.
- **NoSQL** (e.g., DynamoDB): key-value/document stores for flexible, scalable access.
- **HDFS / EMR:** HDFS stores files as blocks across many nodes. EMR is AWS's managed Hadoop/Spark for big data processing. He linked HDFS to block storage.
- **Data warehouse** (e.g., Redshift): analytics on large structured data.
- Read the handout references (T1 Ch2, T2 Ch3, R8) if you have spare time.

---

## 5. Self-test (cover the answers)

1. **Name the NIST 5 essential characteristics.**
   On-demand self-service, broad network access, resource pooling, rapid elasticity, measured service.
2. **Service model vs deployment model?**
   Service = what you get (IaaS/PaaS/SaaS). Deployment = how you consume it (public/private/community/hybrid).
3. **What is cloudbursting?**
   Overflowing to a public cloud when your own capacity is exceeded.
4. **Hypervisor vs VMM?**
   Same thing (the layer that creates and manages VMs).
5. **Type 1 vs Type 2 hypervisor?**
   Type 1 runs on bare metal (vSphere, Xen). Type 2 runs on a host OS (VirtualBox).
6. **Why is virtualization on x86 hard?**
   The guest OS expects ring 0, which the host kernel already owns.
7. **Three techniques?**
   Binary translation (full), paravirtualization (hypercalls, modified kernel), hardware-assisted (VT-x/AMD-V, standard today).
8. **Which technique modifies the guest kernel?**
   Paravirtualization.
9. **6 VMs × 2 vCPU on a 4-core host. Ratio?**
   12 ÷ 4 = 3:1.
10. **When use 1:1 CPU allocation?**
    Latency-sensitive workloads like databases and real-time transactions.
11. **4 memory overcommit techniques?**
    Page sharing (with COW), ballooning, compression, host swapping.
12. **Namespaces vs cgroups?**
    Namespaces isolate what a container sees. Cgroups limit and track what it can use.
13. **Key VM vs container differences?**
    Hardware vs OS virtualization, own kernel vs shared kernel, slow vs fast start, large vs small, low vs high density.
14. **What must be true of a container's kernel?**
    It is the host's kernel (same ISA).
15. **What does copy-on-write protect?**
    The base image: changes go into a new layer.
16. **Filename rule for Dockerfile?**
    `Dockerfile`, capital D, no extension.
17. **Why not `:latest`?**
    Version drift can break dependencies.
18. **Why not put a password in a Dockerfile?**
    `docker history` reveals it.
19. **`docker run` vs `docker create`?**
    `run` = create + start. `create` only creates.
20. **`-it` vs `-d`?**
    Interactive/attached vs detached (background).
21. **Local zone vs AZ?**
    A local zone is a limited extension of a region near users for low latency. An AZ is a full set of data centres within a region.
22. **Wavelength vs Outposts?**
    Wavelength is inside telecom 5G networks. Outposts is AWS gear in your own premises.
23. **Authentication vs authorization?**
    Who you are vs what you may do.
24. **Who secures what?**
    AWS secures the cloud infrastructure. You secure your data, applications and identities.
25. **4 ways to get an AMI?**
    AWS-published, from your own instance, Marketplace, uploaded VM images.
26. **.pem vs .ppk?**
    .pem for OpenSSH and Windows password decryption. .ppk for PuTTY.
27. **Why is `0.0.0.0/0` bad?**
    Opens the port to the whole internet.
28. **What still costs money when an instance is stopped?**
    Attached volumes (and any unattached Elastic IP).
29. **Three tenancy options in order of cost?**
    Shared < dedicated instance < dedicated host.
30. **Block vs file vs object?**
    Raw chunks (databases) vs file-system abstraction (shared files) vs whole objects with metadata (write once, read many).

---

## 6. One-page cheat sheet

- **3-4-5:** 3 service models · 4 deployment models · 5 characteristics.
- **Virtualization in one line:** the guest thinks it owns the hardware; the hypervisor keeps control.
- **Order of virtualization techniques:** binary translation → paravirtualization → hardware-assisted (today's default).
- **Overcommit ratio** = virtual ÷ physical. CPU sweet spot 3:1–5:1; 1:1 for latency-sensitive; over ~8:1 = trouble; CPU-ready time over ~5% = trouble.
- **Container = app + dependencies + shared kernel.** Namespace = isolation. cgroup = limits.
- **VM:** hypervisor, own kernel, heavy. **Container:** engine, shared kernel, light, dense.
- **Docker flow:** Dockerfile → `build` → image → (registry push/pull) → `run` → container. Volumes persist data; networks connect containers.
- **Dockerfile rules:** capital D, no extension · pin versions · no secrets · dependencies before app code · trailing `.` on `build`.
- **AWS geography:** Region ⊃ AZs · Local Zone (limited, near you) · Wavelength (in telco network) · Outposts (in your building) · Edge (caching).
- **Shared responsibility:** AWS = *of* the cloud. You = data, apps, identity *in* the cloud.
- **IAM:** authN (who) · authZ (what) · roles · policies · least privilege.
- **EC2 checklist:** AMI + instance type + key pair + security group + storage → launch → connect (SSH 22 / RDP 3389) → **stop or terminate when done**.
- **Storage:** EBS (block, DB) · EFS (file, shared) · S3 (object, WORM) · Glacier (archive) · instance store (ephemeral).
- **Costs:** everything is metered. Stopped ≠ free (volumes, Elastic IPs). Billing alerts on.

## 7. After the mid-sem (comprehensive exam, open book, all topics)

Not yet taught in these transcripts: PaaS/SaaS/BaaS/FaaS comparison, provisioning and migration, IaC, capacity management and autoscaling, availability, multi-tenancy levels, security, SLAs, sovereign cloud, CI/CD, and future paradigms. Use the handout's Modules 4–9 and the prescribed books (open book: publisher copies only).