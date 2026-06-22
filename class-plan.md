# Class Planning Draft for CPSC 5xxx: Advanced Cloud Native Orchestration

This is a first-pass teaching plan based on the syllabus. It assumes one primary class meeting per week with a lecture/lab format.

## Planning Principles

- Each week should start with a short recap of the previous lab and any common issues.
- Every session should include one conceptual goal, one live demo, and one student exercise.
- Keep the capstone aligned with the weekly deliverables so students build toward the final project incrementally.
- Use the example project as the running lab environment whenever possible.

## Week-by-Week Plan

### Week 1: GKE Foundations and Access Control

- Goal: Get every student authenticated, connected, and working in a baseline GKE cluster.
- In class: review control plane vs. data plane, then provision a standard cluster with `gcloud`.
- Lab: create the course namespace and map IAM roles to Kubernetes RBAC.
- Checkpoint: students can deploy to the cluster and explain the difference between cloud IAM and cluster RBAC.
- Homework: verify cluster access and submit the baseline RBAC manifest.
- Plan: [week-01/plan/week-01-plan.md](week-01/plan/week-01-plan.md)
- YAML: [week-01/yaml/baseline-rbac.yaml](week-01/yaml/baseline-rbac.yaml)

### Week 2: Deployments and Self-Healing

- Goal: Teach how Kubernetes maintains desired state during failure.
- In class: explain ReplicaSets, rollout history, and rollback behavior.
- Lab: deploy two application versions and simulate pod disruption.
- Checkpoint: students can trigger a rollout and recover from a bad release.
- Homework: zero-downtime lab write-up and deployment YAML review.
- Plan: [week-02/plan/week-02-plan.md](week-02/plan/week-02-plan.md)
- YAML: [week-02/yaml/deployment-rollout.yaml](week-02/yaml/deployment-rollout.yaml)

### Week 3: Health and Lifecycles

- Goal: Make students design pods that start, run, and shut down cleanly.
- In class: compare liveness, readiness, and startup probes.
- Lab: add probe configuration and graceful termination handling.
- Checkpoint: students can explain why readiness is not the same as liveness.
- Homework: resilient YAML suite submission.
- Plan: [week-03/plan/week-03-plan.md](week-03/plan/week-03-plan.md)
- YAML: [week-03/yaml/probes.yaml](week-03/yaml/probes.yaml)

### Week 4: Services and Networking

- Goal: Connect pods into stable, discoverable services.
- In class: walk through ClusterIP, NodePort, and LoadBalancer.
- Lab: route traffic between frontend and backend services.
- Checkpoint: students can trace service-to-service traffic inside the cluster.
- Homework: service connectivity map.
- Plan: [week-04/plan/week-04-plan.md](week-04/plan/week-04-plan.md)
- YAML: [week-04/yaml/service.yaml](week-04/yaml/service.yaml)

### Week 5: Ingress and Traffic Control

- Goal: Expose application traffic cleanly at the edge.
- In class: introduce ingress controllers, Google Cloud Load Balancing, and TLS.
- Lab: configure host-based and path-based routing.
- Checkpoint: students can explain how ingress differs from a service.
- Homework: exposed HTTPS endpoint.
- Plan: [week-05/plan/week-05-plan.md](week-05/plan/week-05-plan.md)
- YAML: [week-05/yaml/ingress.yaml](week-05/yaml/ingress.yaml)

### Week 6: Config and Secrets

- Goal: Separate application behavior from deployed code.
- In class: cover ConfigMaps, Secrets, and mounted volumes.
- Lab: externalize environment-specific settings and sensitive values.
- Checkpoint: students can update config without rebuilding the image.
- Homework: externalized config lab.
- Plan: [week-06/plan/week-06-plan.md](week-06/plan/week-06-plan.md)
- YAML: [week-06/yaml/config-and-secret.yaml](week-06/yaml/config-and-secret.yaml)

### Week 7: Persistent Volumes

- Goal: Add durable storage for application state.
- In class: explain PV, PVC, and StorageClass relationships.
- Lab: mount a GCE Persistent Disk into a workload.
- Checkpoint: students can describe what survives pod replacement and what does not.
- Homework: persistent storage mount exercise.
- Plan: [week-07/plan/week-07-plan.md](week-07/plan/week-07-plan.md)
- YAML: [week-07/yaml/pvc.yaml](week-07/yaml/pvc.yaml)

### Week 8: StatefulSets

- Goal: Move from stateless replicas to ordered, identity-aware workloads.
- In class: discuss stable IDs, ordered startup, and PVC templates.
- Lab: deploy a small PostgreSQL cluster or equivalent stateful service.
- Checkpoint: students can explain why StatefulSets exist instead of Deployments for this use case.
- Homework: distributed DB cluster submission.
- Plan: [week-08/plan/week-08-plan.md](week-08/plan/week-08-plan.md)
- YAML: [week-08/yaml/statefulset.yaml](week-08/yaml/statefulset.yaml)

### Week 9: Resource Scheduling

- Goal: Make students reason about performance, cost, and reliability together.
- In class: requests, limits, QoS classes, and OOMKill behavior.
- Lab: intentionally tune resources too low and too high, then correct them.
- Checkpoint: students can justify resource settings from observed behavior.
- Homework: resource profiling report.
- Plan: [week-09/plan/week-09-plan.md](week-09/plan/week-09-plan.md)
- YAML: [week-09/yaml/resources.yaml](week-09/yaml/resources.yaml)

### Week 10: Autoscaling

- Goal: Scale pods based on demand instead of manual intervention.
- In class: Metrics Server, HPA, and custom metrics concepts.
- Lab: generate load and watch horizontal scaling behavior.
- Checkpoint: students can connect load changes to replica count changes.
- Homework: scaling benchmark.
- Plan: [week-10/plan/week-10-plan.md](week-10/plan/week-10-plan.md)
- YAML: [week-10/yaml/hpa.yaml](week-10/yaml/hpa.yaml)

### Week 11: Cluster Scaling

- Goal: Show what happens when pod scaling also requires node scaling.
- In class: node pools and cluster autoscaler behavior.
- Lab: simulate scheduling exhaustion and trigger new node creation.
- Checkpoint: students can distinguish pod scaling from cluster scaling.
- Homework: node scaling demo notes.
- Plan: [week-11/plan/week-11-plan.md](week-11/plan/week-11-plan.md)
- YAML: [week-11/yaml/scheduling-pressure.yaml](week-11/yaml/scheduling-pressure.yaml)

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

### Week 14: Flex Week and Capstone Proposal Checkpoint

- Goal: Clear blockers and validate final project scope.
- In class: backlog triage, architecture review, and risk planning.
- Lab: apply fixes to the weakest part of each project plan.
- Checkpoint: proposal is realistic, testable, and aligned with the semester goals.
- Homework: final proposal plus risk register.
- Plan: [week-14/plan/week-14-plan.md](week-14/plan/week-14-plan.md)
- YAML: [week-14/yaml/proposal-checklist.yaml](week-14/yaml/proposal-checklist.yaml)

### Week 15: Final Capstone

- Goal: Demonstrate an integrated, production-oriented system.
- In class: student demos, troubleshooting, and postmortem discussion.
- Lab: performance tuning and last-mile debugging.
- Checkpoint: application is containerized, stateful, observable, and deployed to GKE.
- Homework: final submission and presentation materials.
- Plan: [week-15/plan/week-15-plan.md](week-15/plan/week-15-plan.md)
- YAML: [week-15/yaml/final-checks.yaml](week-15/yaml/final-checks.yaml)

## What To Build Next

- Add estimated time per segment for each week.
- Add pre-class readings or video links for each topic.
- Add a rubric for lab grading and capstone checkpoints.
- Convert this into a calendar-friendly version with dates once the semester start date is confirmed.