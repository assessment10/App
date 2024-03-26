# App

This guide explains how to use the App pipeline set up in GitHub include the process of build and deploy.

## Prerequisites

- AWS and credential
- Dockerhub and credential
- Configure secrets as below (I removed secrets but you can verify in GitHub action history)

## Setup GitHub Secrets

1. Add 4 secrets
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `DOCKER_USERNAME`
   - `DOCKER_PASSWORD`

## Understanding the Workflow

The `.github/workflows/build-app.yml` file defines following key steps:

- **Terraform Init:** Prepares the Terraform working directory.
- **Terraform Validate:**  Verify Terraform scripts.
- **Terraform Plan:** Shows the changes that will be applied.
- **Terraform Apply:** Applies the changes.

## Items can be improve

- Terraform code shall include ECR for continues deployment.
- Terraform apply can be manual action.
- Terraform code can be categorize as modules for big project.
- Pipeline shall conduct scanning stage for Terraform source code.
- Terraform state file shall consider S3 + Dynamo DB in real case.
- GitHub need setup branch protection rules and conduct PR.
- etc...

## Screenshot
- ![access via lb](https://github.com/assessment10/IaC/assets/73170256/51ea168b-7a06-490d-9afa-8127a4462717)

- ![pipeline details](https://github.com/assessment10/IaC/assets/73170256/74f66130-1bc9-4c72-85d5-f0d1ab2bc16c)

- ![ecs details](https://github.com/assessment10/IaC/assets/73170256/ddfd595e-323b-4358-b080-c2179a5f9a72)
