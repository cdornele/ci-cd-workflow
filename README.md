# CI/CD Workflow Templates

This repository provides reusable CI/CD workflow templates for Terraform modules and general scripts. These templates are designed to help you automate testing, validation, and deployment processes in your projects.

## Contents

- **Terraform Workflows**: Templates for linting, validating, and applying Terraform modules.
- **General Script Workflows**: Templates for running and testing generic scripts (e.g., Bash, Python).

## Usage

1. **Copy the desired workflow template** from the `workflows/` directory into your project's `.github/workflows/` folder.
2. **Customize the workflow** as needed for your project (e.g., update environment variables, secrets, or script paths).
3. **Commit and push** the workflow to your repository to enable automated CI/CD.

## Example: Using a Terraform Workflow

```yaml
# .github/workflows/terraform.yml
name: Terraform CI

on:
  push:
    paths:
      - 'terraform/**'
  pull_request:

jobs:
  terraform:
    uses: ./workflows/terraform.yml# ci-cd-workflow
CI/CD Workflow templates
