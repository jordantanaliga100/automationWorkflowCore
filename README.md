# automationWorkflowCore

Core resources and workflows for learning and testing **GitHub Actions** and **Git workflows**.

This repository is meant for developers who want to experiment, learn, and automate GitHub tasks, including CI/CD, workflow automation, and Git best practices.

---

## 🛠 Features

- Ready-to-use GitHub Actions workflow templates
- Automation scripts for Git tasks
- Sample project setups for learning and testing
- Workspace configurations for VS Code

---

Author:
jordantanaliga100

Collaborator:
tanaliga100


# Key Building Blocks 
* Workflows 
  - are attached to that github repo, can be one or more
  - triggered upon events (ex. new commits are push)
* Jobs 
  - lives inside the workflow, can be one or more
  - define a so called runners
  - can be conditional
  - run in parallel
* Steps
  - lives inside the Jobs
  - a command, can be subsequent
  - execute a shell script or an action
  - executed in order


##### First Workflow | Simple Workflow Github 

  

  This is a basic workflow to help you get started with Actions

name: CI

###### Controls when the workflow will run
on:
  ###### Triggers the workflow on push or pull request events but only for the "main" branch
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

  ###### Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

###### A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  ###### This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v4

      # Runs a single command using the runners shell
      - name: Run a one-line script
        run: echo Hello, world!

      # Runs a set of commands using the runners shell
      - name: Run a multi-line script
        run: |
          echo Add other actions to build,
          echo test, and deploy your project.
          