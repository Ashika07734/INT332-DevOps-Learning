# GitHub Actions Basics

## Introduction to GitHub Actions

GitHub Actions is a powerful automation tool provided by GitHub that enables developers to automate software development workflows directly inside a repository.

It is mainly used to implement **Continuous Integration (CI)** and **Continuous Deployment (CD)** processes. GitHub Actions allows developers to automatically build, test, package, and deploy applications whenever changes are made to the codebase.

GitHub Actions workflows are written using **YAML configuration files**, which define a sequence of steps executed automatically based on specific events.

These workflow files are stored inside:

.github/workflows/

This structure allows GitHub to detect and execute workflows automatically.

---

## Workflow Directory Structure

GitHub Actions workflows must be placed inside a specific directory structure.

Example:
```
project-folder/
│
├── src/
├── pom.xml
├── Dockerfile
│
└── .github/
└── workflows/
└── ci-cd.yml
```

The `.github/workflows` folder is mandatory. If workflow files are not stored in this location, GitHub will not detect or execute them.

---

## What is a Workflow?

A workflow is an automated process defined in a YAML file. It contains instructions that GitHub follows to perform tasks such as building code, running tests, or deploying applications.

A workflow consists of:

- Events  
- Jobs  
- Steps  
- Actions  
- Runners  

Workflows allow automation of repetitive tasks and ensure consistency across development environments.

---

## Workflow Events and Triggers

Workflows run automatically based on specific **events** or **triggers**.

Common triggers include:

### Push Trigger

This trigger runs the workflow whenever code is pushed to a repository.
Example:
```
on:
push:
branches:
- main
```

### Pull Request Trigger

This trigger runs when a pull request is created or updated.

Example:
```
on:
pull_request:
branches:
- main
```

This allows users to manually start workflows from GitHub.

---

## Jobs in GitHub Actions

A job is a collection of steps executed on the same runner.

Each workflow can contain multiple jobs. Jobs may run:

- Sequentially  
- In parallel  

Example:
```
jobs:
build:
runs-on: ubuntu-latest
```

Jobs help organize tasks and manage workflow execution.

---

## Steps in GitHub Actions

Steps are individual commands executed inside a job.

Each step performs a specific action, such as:

- Running shell commands  
- Installing dependencies  
- Building code  

Example:
```
steps:

name: Run command
run: echo "Hello GitHub Actions"
```

Steps execute sequentially within a job.

---

## Actions in GitHub Actions

Actions are reusable components that perform predefined tasks.

GitHub provides built-in actions such as:

- actions/checkout  
- actions/setup-java  
- actions/cache  

Example:
```
uses: actions/checkout@v4
```

GitHub Marketplace offers thousands of pre-built actions that simplify workflow creation.

---

## Runners in GitHub Actions

A runner is a server that executes workflow jobs.

There are two types of runners:

### GitHub-hosted Runners

These are virtual machines provided by GitHub.

Common options:

- ubuntu-latest  
- windows-latest  
- macos-latest  

GitHub-hosted runners are easy to use and require no setup.

---

### Self-hosted Runners

These runners are installed on personal servers or local machines.

Advantages:

- More control over environment  
- Custom configuration  
- Improved performance  

Self-hosted runners are useful for large-scale applications.

---


This runs the workflow using multiple Java versions.

Matrix builds help test applications across different environments.

---

## Multi-job Workflows

Workflows can include multiple jobs that depend on each other.

Example:
```
jobs:
build:
runs-on: ubuntu-latest

test:
needs: build
```
This ensures that the test job runs only after the build job completes.

Multi-job workflows improve workflow flexibility.

---
## Importance of GitHub Actions

GitHub Actions is an essential tool in modern DevOps practices because it enables workflow automation and continuous integration.

Its importance includes:

- Automates repetitive tasks  
- Reduces manual errors  
- Improves software quality  
- Supports CI/CD pipelines  
- Enhances collaboration  
- Speeds up development cycles  
- Enables reliable deployments  

GitHub Actions plays a major role in automating software delivery.

---

## Conclusion

GitHub Actions provides a flexible and powerful framework for automating software workflows. By using workflows, jobs, steps, and runners, developers can build efficient Continuous Integration pipelines.

Understanding GitHub Actions basics helps developers automate application builds, testing, and deployment processes effectively.

This knowledge forms the foundation for implementing advanced CI/CD pipelines and integrating tools such as Docker into automated workflows.
