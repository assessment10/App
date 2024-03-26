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

- **Build the Docker image:** Build container image and make sure tag point to Dockerhub.
- **Update ECS task def:**  Reuse task definition from IaC and replace the image from Dockerhub.
- **Update ECS service:** Force ECS service update with latest version of task definition.

## Items can be improve

- Secret can be environment based.
- The actual register shall be ECR not Dockerhub.
- Pipeline shall include scanning stage for container image.
- Dockerfile can be optimize, like run as non-root user and so on...
- etc...

## Screenshot
- ![pipeline details](https://github.com/assessment10/App/assets/73170256/c55ada89-928a-4fab-9e07-46535fb39020)
- ![dockerhub images](https://github.com/assessment10/App/assets/73170256/88d64199-9b21-40e7-b276-70e05eecae16)
- ![ECS service details](https://github.com/assessment10/App/assets/73170256/f553d41d-71a0-42a7-b532-3023479342c1)
- ![Web site](https://github.com/assessment10/App/assets/73170256/548ce913-5992-474a-aa52-84927aef0b31)
