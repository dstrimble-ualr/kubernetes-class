# Week 1 Homework: Build and Run a Tiny Web Container

## Instructions
For this homework, you will create a very small Docker image that serves a simple web page. Use the base image `nginx:alpine`, which already includes a basic web server.

### Starter files
Create two files in your project folder:

1. `index.html`
2. `Dockerfile`

Example content for `index.html`:

```html
<!doctype html>
<html>
  <body>
    <h1>Hello from Week 1!</h1>
  </body>
</html>
```

## Part A: Write a Dockerfile

### 1. Write a Dockerfile that uses `nginx:alpine` to serve your `index.html` file.
Your Dockerfile should:
- use `nginx:alpine` as the base image
- copy your `index.html` into the correct folder for nginx
- expose port 80

Write your Dockerfile here:

```dockerfile
# Write your Dockerfile here
```

## Part B: Build and Run the Container

### 2. Write the command to build the image.
Write the command and the output you would expect:

```bash
# Your command here
```

```text
# Expected output here
```

### 3. Write the command to run the container in the background.
Use the container name `week1-web` and map port `8080` on your machine to port `80` in the container.

```bash
# Your command here
```

```text
# Expected output here
```

## Part C: Inspect and Interact with the Container

### 4. Write the command to list the running containers.
Include the output you would expect.

```bash
# Your command here
```

```text
# Expected output here
```

### 5. Write the command to view the web page from your computer.
Use `curl` to request the page.

```bash
# Your command here
```

```text
# Expected output here
```

### 6. Write the command to open a shell inside the running container.
Use `sh` as the command.

```bash
# Your command here
```

```text
# Expected output here
```

## Part D: Stop and Remove the Container

### 7. Write the command to stop the container.

```bash
# Your command here
```

```text
# Expected output here
```

### 8. Write the command to remove the container.

```bash
# Your command here
```

```text
# Expected output here
```

## Submission Guidelines
- Submit your Dockerfile and your answers to all questions.
- If you ran the commands locally, include the actual output you saw.
- Be ready to explain what each Docker command did.
