
# AWS Infrastructure Using Terraform and GitHub Actions

## Overview

This Repository Provisions AWS Infrastructure Using Terraform and Automates Deployments Through GitHub Actions.
GitHub Actions Authenticates With AWS Using **OIDC [OpenID Connect]**, Eliminating the Need for Long Lived AWS Access Keys.

## Architecture

- **Terraform** – Infrastructure as Code
- **AWS** – Cloud Infrastructure
- **GitHub Actions** – CICD Automation
- **OIDC** – Secure Authentication Between GitHub and AWS
- **IAM Role** – Grants GitHub Actions the Required AWS Permissions

## Workflow

1. Developer pushes code to GitHub.
2. GitHub Actions runs Terraform `init`, `validate`, and `plan`.
3. GitHub Actions authenticates to AWS using OIDC.
4. Terraform applies infrastructure changes after approval, if configured.

## Prerequisites

- AWS Account
- GitHub Repository
- AWS IAM OIDC Provider and IAM Role
- Terraform Configuration for the Required AWS Resources

## Setup

1. Create an OIDC Identity Provider in AWS for `token.actions.githubusercontent.com`.
2. Create an IAM Role With a Trust Policy Restricted to GitHub Repository and Branch.
3. Add the IAM Role ARN as a GitHub Repository Secret Named `AWS_ROLE_ARN`.
4. Configure Terraform Files for AWS Infrastructure.
5. Push Changes to Trigger the GitHub Actions Workflow.

## Security

- No Long Lived AWS Access Keys Stored in GitHub.
- Follow the Principle of Least Privilege for IAM Permissions.
- Restrict OIDC Trust to the Intended Repository and Branch.
- Use GitHub Environment Approvals for Production Deployments.

## GitHub Actions Should be able to Authenticate With AWS Cloud Using OIDC Strategy.