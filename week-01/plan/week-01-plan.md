# Week 1: Container Fundamentals and Docker

## Session Goals

- Understand what containers are and why they solve the "works on my machine" problem.
- Build and run Docker images locally.
- Work with Docker registries.
- Debug and inspect container internals.

## Key Concepts

- **Image vs. Container:** An image is a blueprint; a container is a running instance.
- **Dockerfile:** A recipe for building an image (layer-by-layer).
- **Layers:** Docker images are built in layers; understanding caching improves build speed.
- **Registries:** Where images are stored and pulled from (Docker Hub, GCR, ECR, etc.).
- **Security:** Image scanning, minimal base images, and avoiding secrets in images.

## Live Demo

- Write a simple Dockerfile (Node.js or Python app).
- Build and tag the image.
- Run the container locally and interact with it.
- Push to a registry (or prepare for it).
- Show `docker inspect` and `docker logs`.

## Lab Focus

- Create a Dockerfile for a simple application.
- Build the image and verify it runs locally.
- Tag the image with a version.
- Document the build process.

## Checkpoint

- Students can explain the purpose of a Dockerfile.
- Students can build an image and run a container from it.
- Students understand the relationship between images, layers, and registries.

## Deliverable

A working Dockerfile and a built image that runs locally without errors.
