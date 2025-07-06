# Terraform AKS Lab - CI/CD Pipeline with GitHub Actions and Husky

## Overview

This project demonstrates a simple Infrastructure as Code (IaC) setup using Terraform to create Azure resources. It includes:

- A basic Terraform script to provision Azure resources (AKS cluster or others) inside the `infrastructure` folder.
- A Husky pre-commit hook that runs `terraform fmt`, `terraform validate`, and `tflint` to enforce code quality and formatting before commits.
- A GitHub Actions workflow (`.github/workflows/action-terraform-verify.yml`) to automate Terraform validation and formatting checks on Pull Requests.
- A multi-job workflow that includes:
  - Terraform formatting and validation checks.
  - Terraform plan validation to simulate infrastructure changes.

## Project Structure

- `infrastructure/` — Contains Terraform configuration files.
- `.husky/` — Contains Git hooks configured via Husky for pre-commit checks.
- `.github/workflows/` — Contains GitHub Actions workflow files.

## How It Works

- **Local development:** Husky runs pre-commit hooks to prevent bad Terraform code from being committed.
- **CI/CD pipeline:** GitHub Actions runs on every Pull Request to `main` or `master` branch:
  - Checks Terraform formatting.
  - Validates Terraform configuration.
  - Runs `terraform plan` to simulate infrastructure changes before applying.

## Usage

1. Clone the repository.
2. Run `terraform init` inside the `infrastructure` folder.
3. Develop your Terraform configuration.
4. Commit changes — Husky hooks will run locally.
5. Push branches and open Pull Requests — GitHub Actions will validate your code.

## Notes

- The `.terraform/` folder and provider binaries are excluded from version control.
- Ensure you have Terraform, Node.js, and npm installed to use Husky locally.
- The workflow uses Terraform version 1.2.4.

## Author

Keval Trivedi  
GitHub: [Keval0045](https://github.com/Keval0045)

---
