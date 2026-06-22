# Week 0: Cloud Fundamentals and Why Kubernetes

## Session Goals

- Understand why cloud computing matters and the problems it solves.
- Compare bare metal, VMs, containerization, and their tradeoffs.
- Explore the cloud service model (IaaS, PaaS, SaaS).
- Introduce Kubernetes as the container orchestration platform for this course.

## Why Cloud?

### The Problem: "It Works on My Machine"

Before cloud computing, deployment meant:
- Manual provisioning of physical hardware.
- Long lead times for capacity.
- Difficulty scaling up or down.
- High cost and inflexibility.

Cloud computing solves this with on-demand, elastic, pay-as-you-go infrastructure.

## Comparing Deployment Models

### Bare Metal

**Pros:**
- Full control over hardware.
- Maximum performance (no hypervisor overhead).
- Predictable costs at scale.

**Cons:**
- High upfront capital cost.
- Long provisioning time.
- Difficult to scale rapidly.
- Operator must manage everything (OS patches, networking, security).

### Virtual Machines (VMs)

**Pros:**
- Share hardware across multiple OS instances.
- Fast provisioning (minutes).
- Isolation per OS kernel.
- Easy to migrate and back up.

**Cons:**
- Each VM includes a full OS (gigabytes).
- Hypervisor overhead.
- Slower boot time (minutes).
- Management complexity increases with VM count.

### Containers (Docker)

**Pros:**
- Lightweight (share the host OS kernel).
- Fast startup (seconds).
- Minimal overhead.
- Portable: "Build once, run anywhere."

**Cons:**
- All containers on a host share the same OS kernel.
- Less isolation than VMs.
- Requires container orchestration for production.

## The Cloud Service Model

### Infrastructure as a Service (IaaS)

**Examples:** AWS EC2, Google Compute Engine, Azure VMs

- You manage: applications, data, runtime, middleware.
- Cloud manages: OS, virtualization, servers, storage, networking.

**Use case:** You want flexibility and control but not hardware management.

### Platform as a Service (PaaS)

**Examples:** Heroku, Google App Engine, AWS Elastic Beanstalk

- You manage: applications, data.
- Cloud manages: everything else (runtime, OS, servers, etc.).

**Use case:** You want to focus on code, not infrastructure.

### Software as a Service (SaaS)

**Examples:** Salesforce, Google Workspace, Microsoft 365

- You manage: your data and usage.
- Cloud manages: everything (app, servers, patches, etc.).

**Use case:** Use an application without deploying or managing anything.

## Kubernetes: Orchestration at Scale

### The Container Problem

You can run one container with `docker run`. But what about:
- Running 100 containers across 10 servers?
- Handling a failed container automatically?
- Rolling out a new version with zero downtime?
- Scaling up when demand spikes?
- Managing networking between containers?
- Updating storage and configuration without downtime?

**Answer:** Kubernetes (container orchestration).

### What is Kubernetes?

Kubernetes is a **container orchestration platform** that:
- Automates deployment and scaling of containerized applications.
- Manages networking, storage, and configuration.
- Provides self-healing (automatic restart of failed containers).
- Enables declarative configuration (you describe desired state; K8s ensures it).
- Works across cloud providers (AWS, Google Cloud, Azure, on-premises, hybrid).

### Why Kubernetes in This Course

Kubernetes represents the modern cloud-native standard for container management. Learning Kubernetes teaches you:
- How to design resilient, scalable systems.
- Production operations patterns (health checks, security, monitoring).
- Infrastructure-agnostic application design.
- How platform teams deliver infrastructure to developers.

## Key Concepts to Understand

- **Declarative vs. Imperative:** Kubernetes is declarative—you describe *what* you want, not *how* to achieve it.
- **Desired State:** Kubernetes constantly works to keep the system in the state you declare.
- **Abstraction:** Kubernetes abstracts away the underlying infrastructure (cloud provider, data center, etc.).
- **Scalability:** Kubernetes scales from a single node to thousands of nodes and clusters.

## Lab Checkpoint

- Understand the differences between bare metal, VMs, and containers.
- Explain why Kubernetes is needed for container orchestration at scale.
- Describe how Kubernetes fits into the broader cloud ecosystem.

## Deliverable

Conceptual understanding and readiness to provision a GKE cluster in Week 1.
