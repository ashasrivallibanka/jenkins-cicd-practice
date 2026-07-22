# Project 4 – Jenkins Pipeline Job

## Objective

Learn how to create a Jenkins Pipeline using a Jenkinsfile.

## What is a Pipeline?

A Pipeline is a sequence of automated stages executed by Jenkins.

## Why Pipelines?

- Pipeline as Code
- Version Controlled
- Easier to Maintain
- Supports CI/CD

## Jenkinsfile

A Jenkinsfile contains all pipeline instructions written in Groovy.

## Pipeline Components

### agent

Defines where the pipeline runs.

Example:

agent any

### stages

Logical phases of the pipeline.

### stage

A named phase such as Build, Test, or Deploy.

### steps

Commands executed within a stage.

### sh

Executes Linux shell commands.

Example:

sh 'pwd'

## Outcome

Successfully created and executed a Jenkins Pipeline Job using a Jenkinsfile.
