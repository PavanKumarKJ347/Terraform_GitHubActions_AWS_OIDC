
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

**1. Developer Pushes Code to GitHub.**<br>
**2. GitHub Actions Runs Terraform `init`, `validate`, and `plan`.**<br>
**3. GitHub Actions Authenticates to AWS Using OIDC.**<br>
**4. Terraform Applies Infrastructure Changes After Approval.**<br>

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

## GitHub Actions Should be able to Authenticate With AWS Cloud Using OpenID Connect.
