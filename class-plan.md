# Class Planning: CPSC 5xxx Advanced Cloud Native Orchestration

A 15-week course covering containerization (Docker, Docker Compose) and Kubernetes orchestration on Google Cloud Platform.

## Planning Principles

- Each week starts with a short recap of the previous lab and any common issues.
- Every session includes one conceptual goal, one live demo, and one student exercise.
- Keep the capstone aligned with weekly deliverables so students build toward the final project incrementally.
- Use the example project as the running lab environment whenever possible.

## Quick Overview

**Weeks 1–2**: Container fundamentals (Docker, Docker Compose)  
**Weeks 3–15**: Kubernetes on GKE (provisioning, workloads, networking, storage, security, monitoring, capstone)

## Week-by-Week Plan

### Week 1: Container Fundamentals and Docker

- Goal: Understand cloud computing, deployment models, and containerization; build Docker images from scratch.
- In class: compare bare metal, VMs, and containers; explain why containers solve the "works on my machine" problem; walk through images, layers, registries, and security best practices.
- Lab: write a Dockerfile, build an image, and run it locally.
- Checkpoint: students understand the cloud context and can build and run a containerized application.
- Homework: working Dockerfile with documentation.
- Plan: [week-01/plan/week-01-plan.md](week-01/plan/week-01-plan.md)
- YAML: [week-01/yaml/Dockerfile](week-01/yaml/Dockerfile)

### Week 2: Multi-Container Applications with Docker Compose

- Goal: Orchestrate multiple containers and understand service discovery.
- In class: explain Docker Compose, networking, volumes, and environment configuration.
- Lab: write a multi-container application with Compose.
- Checkpoint: students can define and run a multi-container app declaratively.
- Homework: working docker-compose.yml with multiple services.
- Plan: [week-02/plan/week-02-plan.md](week-02/plan/week-02-plan.md)
- YAML: [week-02/yaml/docker-compose.yml](week-02/yaml/docker-compose.yml)

### Week 3: GKE Foundations and Access Control

- Goal: Get every student authenticated, connected, and working in a baseline GKE cluster.
- In class: review control plane vs. data plane, then provision a standard cluster with `gcloud`.
- Lab: create the course namespace and map IAM roles to Kubernetes RBAC.
- Checkpoint: students can deploy to the cluster and explain the difference between cloud IAM and cluster RBAC.
- Homework: verify cluster access and submit the baseline RBAC manifest.
- Plan: [week-03/plan/week-03-plan.md](week-03/plan/week-03-plan.md)
- YAML: [week-03/yaml/baseline-rbac.yaml](week-03/yaml/baseline-rbac.yaml)

### Week 4: Deployments and Self-Healing

- Goal: Teach how Kubernetes maintains desired state during failure.
- In class: explain ReplicaSets, rollout history, and rollback behavior.
- Lab: deploy two application versions and simulate pod disruption.
- Checkpoint: students can trigger a rollout and recover from a bad release.
- Homework: zero-downtime lab write-up and deployment YAML review.
- Plan: [week-04/plan/week-04-plan.md](week-04/plan/week-04-plan.md)
- YAML: [week-04/yaml/deployment-rollout.yaml](week-04/yaml/deployment-rollout.yaml)

### Week 5: Health and Lifecycles

- Goal: Make students design pods that start, run, and shut down cleanly.
- In class: compare liveness, readiness, and startup probes.
- Lab: add probe configuration and graceful termination handling.
- Checkpoint: students can explain why readiness is not the same as liveness.
- Homework: resilient YAML suite submission.
- Plan: [week-05/plan/week-05-plan.md](week-05/plan/week-05-plan.md)
- YAML: [week-05/yaml/probes.yaml](week-05/yaml/probes.yaml)

### Week 6: Services and Networking

- Goal: Connect pods into stable, discoverable services.
- In class: walk through ClusterIP, NodePort, and LoadBalancer.
- Lab: route traffic between frontend and backend services.
- Checkpoint: students can trace service-to-service traffic inside the cluster.
- Homework: service connectivity map.
- Plan: [week-06/plan/week-06-plan.md](week-06/plan/week-06-plan.md)
- YAML: [week-06/yaml/service.yaml](week-06/yaml/service.yaml)

### Week 7: Ingress and Traffic Control

- Goal: Expose application traffic cleanly at the edge.
- In class: introduce ingress controllers, Google Cloud Load Balancing, and TLS.
- Lab: configure host-based and path-based routing.
- Checkpoint: students can explain how ingress differs from a service.
- Homework: exposed HTTPS endpoint.
- Plan: [week-07/plan/week-07-plan.md](week-07/plan/week-07-plan.md)
- YAML: [week-07/yaml/ingress.yaml](week-07/yaml/ingress.yaml)

### Week 8: Config and Secrets

- Goal: Separate application behavior from deployed code.
- In class: cover ConfigMaps, Secrets, and mounted volumes.
- Lab: externalize environment-specific settings and sensitive values.
- Checkpoint: students can update config without rebuilding the image.
- Homework: externalized config lab.
- Plan: [week-08/plan/week-08-plan.md](week-08/plan/week-08-plan.md)
- YAML: [week-08/yaml/config-and-secret.yaml](week-08/yaml/config-and-secret.yaml)

### Week 9: Persistent Volumes

- Goal: Add durable storage for application state.
- In class: explain PV, PVC, and StorageClass relationships.
- Lab: mount a GCE Persistent Disk into a workload.
- Checkpoint: students can describe what survives pod replacement and what does not.
- Homework: persistent storage mount exercise.
- Plan: [week-09/plan/week-09-plan.md](week-09/plan/week-09-plan.md)
- YAML: [week-09/yaml/pvc.yaml](week-09/yaml/pvc.yaml)

### Week 10: StatefulSets

- Goal: Move from stateless replicas to ordered, identity-aware workloads.
- In class: discuss stable IDs, ordered startup, and PVC templates.
- Lab: deploy a small PostgreSQL cluster or equivalent stateful service.
- Checkpoint: students can explain why StatefulSets exist instead of Deployments for this use case.
- Homework: distributed DB cluster submission.
- Plan: [week-10/plan/week-10-plan.md](week-10/plan/week-10-plan.md)
- YAML: [week-10/yaml/statefulset.yaml](week-10/yaml/statefulset.yaml)

### Week 11: Scaling: Pods and Nodes

- Goal: Scale applications automatically based on demand and understand resource constraints.
- In class: requests, limits, QoS classes, Horizontal Pod Autoscaler, and cluster node scaling.
- Lab: tune resources, generate load, and observe pod and node scaling behavior.
- Checkpoint: students can justify resource settings and explain the difference between pod and node scaling.
- Homework: scaling behavior report combining resource tuning and HPA.
- Plan: [week-11/plan/week-11-plan.md](week-11/plan/week-11-plan.md)
- YAML: [week-11/yaml/scaling.yaml](week-11/yaml/scaling.yaml)

### Week 12: Kubernetes Security Hardening

- Goal: Reduce blast radius and apply least privilege.
- In class: pod security standards, network policies, and service accounts.
- Lab: restrict workload communication and remove unnecessary permissions.
- Checkpoint: students can identify at least one security control at each layer.
- Homework: hardened security baseline.
- Plan: [week-12/plan/week-12-plan.md](week-12/plan/week-12-plan.md)
- YAML: [week-12/yaml/security-baseline.yaml](week-12/yaml/security-baseline.yaml)

### Week 13: Self-Hosted Monitoring

- Goal: Deploy the observability stack students will use for capstone validation.
- In class: Prometheus Operator, CRDs, and basic Grafana usage.
- Lab: install Prometheus and Grafana with Helm and confirm metrics flow.
- Checkpoint: students can query a metric and interpret a dashboard panel.
- Homework: running monitoring stack screenshot or export.
- Plan: [week-13/plan/week-13-plan.md](week-13/plan/week-13-plan.md)
- YAML: [week-13/yaml/monitoring-stack.yaml](week-13/yaml/monitoring-stack.yaml)

### Week 14: Capstone Proposal and Preparation

- Goal: Lock down final project scope and architecture; validate feasibility.
- In class: proposal reviews, architecture critique, and risk planning.
- Lab: prototype the core component and resolve blocking issues.
- Checkpoint: proposal is realistic, testable, and aligned with course learning outcomes.
- Homework: final proposal with system diagram and deployment checklist.
- Plan: [week-14/plan/week-14-plan.md](week-14/plan/week-14-plan.md)
- YAML: [week-14/yaml/capstone-checklist.yaml](week-14/yaml/capstone-checklist.yaml)

### Week 15: Final Capstone Delivery and Presentation

- Goal: Demonstrate an integrated, production-oriented system.
- In class: student demos, live troubleshooting, and postmortem discussion.
- Lab: final performance tuning and last-mile debugging.
- Checkpoint: application is containerized, stateful, observable, and deployed to GKE.
- Homework: final submission with presentation materials and lessons learned.
- Plan: [week-15/plan/week-15-plan.md](week-15/plan/week-15-plan.md)
- YAML: [week-15/yaml/final-checks.yaml](week-15/yaml/final-checks.yaml)

## What To Build Next

- Add estimated time per segment for each week.
- Add pre-class readings or video links for each topic.
- Add a rubric for lab grading and capstone checkpoints.
- Convert this into a calendar-friendly version with dates once the semester start date is confirmed.