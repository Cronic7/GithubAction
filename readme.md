# GithubActions


GitHub Actions is a powerful and flexible continuous integration/continuous deployment (CI/CD) and automation platform provided by GitHub. It allows you to automate workflows for your projects, making it easier to build, test, and deploy your code directly from your GitHub repository.

Here's a basic guide to get you started with GitHub Actions:

1. Understanding Workflow Files:
GitHub Actions are defined in YAML files within a .github/workflows directory in your repository. These files define one or more workflows, each consisting of jobs and steps.

Workflow: A set of rules defining when the workflow should run and what actions to take.
Job: A set of steps that run in parallel on the same runner.
Step: An individual task within a job.
2. Creating a Workflow File:
Create a new file in your repository under .github/workflows. The file should have a .yml extension. For example, .github/workflows/main.yml.

3. Writing a Simple Workflow:
Here's a basic example that runs on every push to the repository:

```
name: Simple Workflow

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Repository
      uses: actions/checkout@v2

    - name: Run a simple command
      run: echo "Hello, GitHub Actions!"

```

Explanation:
Workflow Name:

name: Simple Workflow
This is the name of your GitHub Actions workflow.
Trigger:

 ```
on:
  push:
    branches:
      - main

```
This workflow is triggered on every push to the main branch.
Job:
```
jobs:
  build:
    runs-on: ubuntu-latest
```
The workflow defines a job named build that runs on the latest version of the Ubuntu operating system.
Steps:
```
steps:
  - name: Checkout Repository
    uses: actions/checkout@v2
```
The first step (Checkout Repository) uses the actions/checkout action to fetch the contents of the repository, enabling subsequent steps to access the code.

 ```
- name: Run a simple command
  run: echo "Hello, GitHub Actions!"
```
The second step (Run a simple command) executes a simple command, which is to echo the message "Hello, GitHub Actions!".

Workflow Execution:
When a push event occurs on the main branch, GitHub Actions will initiate this workflow.
The build job runs on a virtual machine with the latest version of Ubuntu.
The first step checks out the repository code.
The second step echoes "Hello, GitHub Actions!" to the workflow log.
