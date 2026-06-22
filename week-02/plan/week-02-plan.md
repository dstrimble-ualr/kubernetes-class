# Week 2: Multi-Container Applications with Docker Compose

## Session Goals

- Coordinate multiple containers that work together.
- Use Docker Compose to define and run multi-container applications.
- Understand networking, volumes, and environment configuration in Compose.
- Build toward production-like deployments.

## Key Concepts

- **Service Discovery:** Containers find each other by name on a Docker network.
- **Docker Compose:** A declarative YAML format for multi-container apps.
- **Volumes:** Persistent storage and data sharing between containers.
- **Networks:** Custom networks for container communication.
- **Environment Variables:** Configuration without rebuilding images.
- **Dependencies:** Startup order and readiness (depends_on, healthchecks).

## Live Demo

- Write a `docker-compose.yml` with a web service and a database.
- Demonstrate service discovery (containers calling each other by name).
- Show logs aggregation and container health checks.
- Update a service and redeploy without downtime.

## Lab Focus

- Create a multi-container application (web app + database + cache, etc.).
- Define services, networks, and volumes in `docker-compose.yml`.
- Use environment variables for configuration.
- Verify inter-service communication.
- Clean up and redeploy to show repeatability.

## Checkpoint

- Students can write a working `docker-compose.yml`.
- Students understand service discovery and networking.
- Students can manage persistent data with volumes.
- Students understand the relationship between Compose and what Kubernetes does (at a larger scale).

## Deliverable

A working multi-container application defined in `docker-compose.yml` that can be started and stopped with one command.
