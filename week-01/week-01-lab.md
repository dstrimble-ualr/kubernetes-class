# Week 1 Lab: Write and Run a Dockerfile

## Objective
By the end of this lab, students should be able to:
- understand the purpose of a Dockerfile
- write a simple Dockerfile
- build a Docker image locally
- run the container locally
- explain what happened during the build and run process

## Prerequisites
- Docker installed and running locally
- A terminal with access to Docker
- A small sample application or a simple text file to containerize

## Suggested App
Use a very simple Python or Node.js app. For example, a Python script that prints a message.

Example app:

```python
# app.py
print("Hello from the container!")
```

## Lab Steps

### 1. Create a project folder
Create a folder for the lab:

```bash
mkdir week1-lab
cd week1-lab
```

### 2. Create the application file
Create a file named `app.py` with the simple script above.

### 3. Create a Dockerfile
Create a file named `Dockerfile` with the following content:

```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY app.py /app/app.py
CMD ["python", "app.py"]
```

### 4. Build the image
Run:

```bash
docker build -t week1-lab:1.0 .
```

### 5. Run the container
Run:

```bash
docker run --rm week1-lab:1.0
```

### 6. Inspect the container
Try these commands:

```bash
docker ps -a
docker images
docker inspect week1-lab:1.0
```

### 7. Optional extension
Try changing the output message in `app.py` and rebuilding the image.

## Lab Reflection Questions
- What does the `FROM` instruction do?
- What is the role of `COPY` in the Dockerfile?
- Why is `CMD` important?
- What did you learn from building and running the container?

## Success Criteria
Students can show:
- a working Dockerfile
- a successfully built image
- a container that runs and prints output
