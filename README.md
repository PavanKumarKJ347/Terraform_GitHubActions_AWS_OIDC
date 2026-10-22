# AWS Infrastructure Using Terraform and GitHub Actions

## This Repository Provisions AWS Infrastructure Using Terraform and Automates Deployments Through GitHub Actions.
## GitHub Actions Authenticates With AWS Using **OIDC [OpenID Connect]**, Eliminating the Need for Long Lived AWS Access Keys.

## Architecture

- **Terraform**
- **AWS**
- **GitHub Actions**
- **OIDC**
- **IAM Role**

## Workflow

**Developer Pushes Code to GitHub.**<br>
**GitHub Actions Runs Terraform `init`, `fmt`, `validate`, and `plan`.**<br>
**GitHub Actions Authenticates to AWS Using OIDC.**<br>
**Terraform Applies Infrastructure Changes After Approval.**<br>

## Prerequisites

**AWS Account**<br>
**GitHub Repository**<br>
**AWS IAM OIDC Provider and IAM Role**<br>
**Terraform Configuration for the Required AWS Resources**<br>

## Setup

**Create an OIDC Identity Provider in AWS for `token.actions.githubusercontent.com`.**<br>
**Create an IAM Role With a Trust Policy Restricted to GitHub Repository and Branch.**<br>
**Add the IAM Role ARN as a GitHub Repository Secret Named `AWS_ROLE_ARN`.**<br>
**Configure Terraform Files for AWS Infrastructure.**<br>
**Push Changes to Trigger the GitHub Actions Workflow.**<br>

## GitHub Actions Should be able to Authenticate With AWS Cloud Using OpenID Connect.