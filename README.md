# CI/CD Workflow Templates

This repository provides reusable GitHub Actions workflow templates for Terraform modules and general scripts. These templates help automate validation, documentation, security analysis, and other CI/CD tasks.

## Contents

- **Terraform Module Workflows**: Templates for validating, generating documentation, and performing security analysis on Terraform modules.
- **General Script Workflows**: Templates for running and testing generic scripts (e.g., Bash, Python).

## Usage

1. **Reference the desired workflow template** in your repository using the `uses` keyword and the relative path to the workflow file.
2. **Customize the workflow** as needed (e.g., set environment variables, secrets, or adjust job dependencies).
3. **Commit and push** your workflow file to `.github/workflows/` in your repository.

## Example: Using the Terraform Modules CI Workflow

```yaml
# .github/workflows/ci-tf-modules.yml
name: Generic CI PR - Terraform Modules

on:
  workflow_call:

jobs:
  validate:
    uses: ./.github/workflows/validate-tf-modules.yml

  doc:
    needs: [validate]
    uses: ./.github/workflows/docs-tf-modules.yml

  security-check:
    needs: [doc]
    uses: ./.github/workflows/security-analysis-tf-modules.yml.github/workflows/
      ci-tf-modules.yml              # Main CI workflow for Terraform modules
      validate-tf-modules.yml        # Validation workflow for Terraform modules
      docs-tf-modules.yml            # Documentation generation workflow
      security-analysis-tf-modules.yml # Security analysis workflow
      # Add other script workflows as neededThis version uses real workflow names and structure from your repository.# CI/CD Workflow Templates

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
