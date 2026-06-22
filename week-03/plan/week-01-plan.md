# Week 1: GKE Foundations and Access Control

## Session Goals

- Understand the GKE control plane and data plane.
- Provision a standard cluster with `gcloud`.
- Map cloud IAM access to Kubernetes RBAC.
- Create a baseline namespace for the course.

## Key Concepts

- Standard clusters give students direct control over node behavior.
- IAM controls who can reach the cluster; RBAC controls what they can do inside it.
- Namespaces are the first isolation boundary for class exercises.

## Live Demo

- Create or inspect the GKE cluster.
- Apply the namespace and baseline role binding.
- Confirm access with `kubectl get ns` and `kubectl auth can-i`.

## Lab Checkpoint

- Students can authenticate to the cluster.
- Students can explain the difference between IAM and RBAC.
- Students can identify the namespace used for course work.

## Deliverable

Functional GKE cluster plus baseline RBAC policy.