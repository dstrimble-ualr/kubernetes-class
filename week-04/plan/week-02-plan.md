# Week 2: Deployments and Self-Healing

## Session Goals

- Explain ReplicaSets, rollouts, and rollbacks.
- Show how Kubernetes preserves desired state.
- Practice controlled failure with pod disruption.

## Key Concepts

- Deployments manage ReplicaSets for versioned application updates.
- Rollouts are safer when changes are observable and reversible.
- Self-healing means failed pods are replaced automatically.

## Live Demo

- Deploy two app revisions.
- Kill a pod and observe recovery.
- Roll back to a known good release.

## Deliverable

Zero-downtime lab with rollback evidence.