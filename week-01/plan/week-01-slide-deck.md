---
marp: true
theme: default
paginate: true
headingDivider: 2
title: Week 1 - Container Fundamentals and Docker
description: Remote-friendly, student-friendly presentation for week 1 of the Kubernetes course
---

# Week 1: Container Fundamentals and Docker
## Advanced Cloud Native Orchestration

### What you’ll learn today

> Remote class tip: keep the pace steady, pause often for questions, and use the demo screen as the main visual anchor.
- Why containers are useful
- What a Docker image and container are
- How Dockerfiles work
- How to write a simple Dockerfile
- How to build and run that container locally
- What the lab will ask you to do

<!-- Speaker notes:
Start with a simple question: have you ever had an app that worked on one computer but not another?
That is the problem containers solve.
For a remote class, pause after this slide and invite students to type a quick example in chat.
-->

---

# Why containers matter

## The “works on my machine” problem
- Different computers can have different setup files and versions
- Apps can break when dependencies change
- Containers package the app with what it needs

### Big idea
Containers help make software easier to move and run anywhere, and Dockerfiles are the recipe for creating that portable environment.

<!-- Speaker notes:
Keep this very practical and relatable.
The goal is to make students feel that containers solve a real problem.
In a remote setting, ask them to compare their own local setup with a teammate’s setup.
-->

---

# A simple way to think about it

## Three ways to run software
- Bare metal: direct on the computer, but less flexible
- Virtual machines: more isolated, but heavier
- Containers: lighter and faster, with less overhead

### Easy takeaway
Containers are a practical middle ground between local development and full virtual machines.

<!-- Speaker notes:
Use plain language here.
Students do not need deep detail yet; they need the big picture.
-->

---

# Image vs container

## A helpful analogy
- An image is a blueprint
- A container is a running version of that blueprint

### Think about it like this
You build the recipe once, then you can cook it many times.

<!-- Speaker notes:
This is one of the most important concepts of the week.
Pause here and let the class repeat the difference back to you.
-->

---

# What Docker does

## Main pieces
- Docker client: the command-line tool you use
- Docker engine: the part that builds and runs containers
- Images: stored packages of your app and dependencies
- Containers: running instances of those images
- Registries: places where images are stored and shared

### The usual flow
1. Build an image
2. Run a container
3. Share the image if needed

<!-- Speaker notes:
Keep this simple.
The point is to show the flow without overwhelming students with too much detail.
-->

---

# Dockerfiles: the recipe

## What goes in a Dockerfile
- A base image
- Files to copy into the container
- Commands to install dependencies
- A command to start the app

### Week 1 goal
By the end of this week, students should understand Dockerfiles well enough to write one, build it, and run the resulting container.

### Example
```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```

<!-- Speaker notes:
Explain that this file is like a recipe for making the container.
Point out that the commands are run in order.
-->

---

# Why layers matter

## Docker builds in layers
- Each step in the Dockerfile adds a layer
- Docker can reuse layers to build faster
- Good layering makes builds easier to manage

### Why students should care
Faster builds mean less waiting and fewer frustrations while learning.

<!-- Speaker notes:
This is a good place to mention that Docker is efficient because it reuses work.
-->

---

# Build, run, and inspect

## In today’s demo
- Build an image from a Dockerfile
- Run the container on your own machine
- Check the running container
- Look at logs and container details

### Commands you may see
- `docker build`
- `docker run`
- `docker ps`
- `docker logs`
- `docker inspect`

<!-- Speaker notes:
Show the commands as they are used, not just as a list.
Let students connect the words to the action.
For a remote class, keep the terminal visible and narrate each step slowly so everyone can follow along.
-->

---

# Registries: where images go

## What a registry is
- A place to store and share container images
- Docker Hub is one common example
- Teams often use private registries too

### Why it matters
This is how images move from your laptop to a server or cloud environment.

<!-- Speaker notes:
Use a simple example: you build it here, then others can pull it from a registry later.
-->

---

# Bonus idea: multi-stage Dockerfiles

## Why this is useful
- Build your app in one stage
- Copy only the final result into a smaller runtime image
- Keep the final image leaner and more secure

### Example idea
A build stage can compile code, while the final stage runs the app with only the needed files.

```dockerfile
FROM node:20-alpine AS build
WORKDIR /app
COPY . .
RUN npm ci && npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
```

<!-- Speaker notes:
This is optional enrichment for students who finish early or want a stretch goal.
It introduces a useful real-world pattern without making the main lesson too heavy.
-->

---

# Security tips for beginners

## Good habits to start with
- Use a small base image if possible
- Do not put secrets in your image
- Keep your image focused on what it needs
- Run the app in a safe way when possible

### Reminder
Good security habits are easier when you start early.

<!-- Speaker notes:
Keep this encouraging and practical.
You do not need to overwhelm students with advanced security topics yet.
-->

---

# Lab goals for this week

## What you will do
- Create a simple Dockerfile
- Build an image from it
- Run the container locally
- Tag the image with a version
- Write down what you learned

### Success means
You can explain what a Dockerfile is, write one yourself, and show that your container runs.

<!-- Speaker notes:
Frame this as a first win.
The purpose is to build confidence before the more advanced Kubernetes topics.
For remote delivery, encourage students to share their terminal output in chat or the class discussion channel if they get stuck.
-->

---

# Wrap-up

## Key takeaway
Containers are a foundational tool for modern software development and cloud computing.

### Looking ahead
Next week, we will build on this by working with more than one container at a time.
