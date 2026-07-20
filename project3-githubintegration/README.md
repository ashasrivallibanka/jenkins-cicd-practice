# Project 3 – GitHub Integration

## Objective

Integrate Jenkins with GitHub to automatically clone a repository.

## What is Source Code Management (SCM)?

Source Code Management is the process of storing and tracking application source code using version control systems like Git.

## Why integrate GitHub with Jenkins?

Instead of manually downloading code, Jenkins automatically clones the latest source code before every build.

## Jenkins Workflow

Developer

↓

Push Code to GitHub

↓

Jenkins clones repository

↓

Executes build

↓

Displays build result

## Commands Used

```bash
pwd
ls -la
git status
git branch
git log --oneline -1
```

## Workspace

Every Jenkins job has its own workspace.

Example:

```
/var/jenkins_home/workspace/github-integration-job
```

## Outcome

Successfully integrated Jenkins with GitHub and verified that Jenkins downloads the latest code from the repository before executing the build.
