---
title: "Setting Up GitLab CI/CD for Your Project"
author: mdomocos
date: 2024-11-26 09:00:00 +0200
categories: [DevOps, Tutorials, CI/CD]
tags: [gitlab, cicd, devops, pipelines, automation]
math: false
mermaid: false
pin: false
---

Automating your workflow with GitLab CI/CD might sound intimidating, but it’s easier than it seems! With a simple `.gitlab-ci.yml` file and a bit of tinkering, you can automate testing, building, and deploying your code. Let me show you how I got started.

## Prerequisites
Before diving in, here’s what you need:
- A GitLab repository for your project.
- Basic knowledge of Git and command-line usage.
- A machine to act as a runner (optional but recommended).

## Step 1: Create a `.gitlab-ci.yml` File
The `.gitlab-ci.yml` file is the heart of your CI/CD pipeline. Here’s an example to get started:

```yaml
stages:
  - test
  - build
  - deploy

test:
  stage: test
  script:
    - echo "Running tests..."
    - pytest || echo "Tests failed!"

build:
  stage: build
  script:
    - echo "Building the project..."
    - python setup.py build || echo "Build failed!"

deploy:
  stage: deploy
  script:
    - echo "Deploying to production..."
    - scp -r ./build user@yourserver:/var/www/ || echo "Deployment failed!"
```

This pipeline has three stages: **test**, **build**, and **deploy**. Each stage runs in the order defined in the `stages` section.

## Step 2: Set Up a Runner
GitLab needs a runner to execute the jobs in your pipeline. You can either use GitLab’s shared runners or set up your own.

### Using Shared Runners
If you’re just starting out, GitLab’s shared runners are fine. They’re enabled by default, so you don’t need to do anything extra.

### Setting Up Your Own Runner
For more control:
1. Go to **Settings > CI/CD > Runners** in your project.
2. Follow the instructions to register a runner on your machine.  
   (It’s mostly copy-pasting commands, so don’t worry.)

## Step 3: Push Your Code
Commit your `.gitlab-ci.yml` file and push it to your GitLab repository:
```bash
git add .gitlab-ci.yml
git commit -m "Add CI/CD pipeline"
git push origin main
```

Go to **CI/CD > Pipelines** in your GitLab project, and you should see your pipeline running. 🎉

## Step 4: Fine-Tune Your Pipeline
Once you have a basic pipeline working, you can start improving it:

### Environment Variables
Store sensitive data like passwords or API keys securely:
1. Go to **Settings > CI/CD > Variables**.
2. Add your variables (e.g., `API_KEY`).
3. Use them in your pipeline:
   ```yaml
   script:
     - echo $API_KEY
   ```

### Docker Images
Use Docker to simplify dependencies:
```yaml
test:
  image: python:3.9
  script:
    - pip install -r requirements.txt
    - pytest
```

### Caching
Speed up builds by caching dependencies:
```yaml
cache:
  paths:
    - .venv/
```

### Artifacts
Save files for later stages or debugging:
```yaml
build:
  stage: build
  script:
    - mkdir build
    - echo "Build complete" > build/output.txt
  artifacts:
    paths:
      - build/
```

## Step 5: Expand Your Pipeline
Want to do more? Here are some ideas:
- Add code quality checks with tools like `flake8` or `eslint`.
- Deploy to a staging environment before production.
- Notify your team on Slack or Teams when a pipeline fails.

## Conclusion
GitLab CI/CD makes automation accessible, even for beginners. With a little experimentation, you can set up a pipeline that saves time and improves the quality of your code. Start small, keep tweaking, and soon you’ll wonder how you ever managed without it!
