# Jenkins CI/CD Pipeline for AWS ECS Deployment

This repository contains a Jenkins pipeline script designed to automate the build, push, and deployment of a Docker image to an AWS ECS cluster. The pipeline script is defined in the `Jenkinsfile`, automating the full CI/CD process.

## Pipeline Overview

The Jenkins pipeline includes the following stages:

1. **Build**: Compiles a minimal Docker image using a simple C program.
2. **Dockerize**: Creates a Docker image with a minimal `scratch` base image.
3. **Push**: Pushes the Docker image to the AWS Elastic Container Registry (ECR).
4. **Deploy**: Deploys the Docker image to an ECS service, triggering a new deployment.

## Requirements

To run this pipeline, the following are required:

- **Jenkins**: Ensure Jenkins is set up with:
  - AWS Credentials Plugin
  - Docker Pipeline Plugin
  - Pipeline Utility Steps (optional for notifications)
- **AWS Configuration**: AWS credentials should be set up in Jenkins with permissions for ECR and ECS actions.
- **Environment Variables and Parameters**: Configurations can be set within Jenkins or as parameters in the Jenkins job.

## Parameters and Environment Variables

This Jenkins pipeline utilizes both parameters and environment variables for flexibility:

- **AWS_account_number**: AWS Account ID for the ECR repository.
- **AWS_REGION**: AWS region (default: `us-east-1`).
- **ECR_REPO_NAME**: Name of the ECR repository.
- **ECS_CLUSTER**: Name of the ECS cluster.
- **ECS_SERVICE**: Name of the ECS service within the cluster.
