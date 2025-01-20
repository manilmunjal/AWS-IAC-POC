Sure, here is the content in complete markdown code:

```markdown
# Terraformer (AWS-IAC-POC)

This repository contains Terraform code for automating the deployment of AWS infrastructure as part of a Proof of Concept (POC). The goal is to showcase Infrastructure as Code (IaC) principles and demonstrate how to efficiently manage and provision AWS resources using Terraform.

## Table of Contents

* [Overview](#overview)
* [Prerequisites](#prerequisites)
* [Usage](#usage)
    * [Manual Terraform Usage](#manual-terraform-usage)
    * [Automated GitHub Actions CI/CD Pipeline](#automated-github-actions-cicd-pipeline)
* [Resources Provisioned](#resources-provisioned)
* [Directory Structure](#directory-structure)
* [Contributing](#contributing)

## Overview

This Proof of Concept (POC) aims to:

* Demonstrate the power of **Terraform** as an effective tool for **Infrastructure as Code (IaC)**.
* Automate the provisioning of AWS resources, showcasing the potential for scaling and managing infrastructure.
* Promote the use of **reusable**, **scalable**, and **modular** Terraform code that can be adapted for various cloud architectures.

## Prerequisites

Before using this repository, ensure you have the following installed and configured:

1. **Terraform CLI:**
   Install Terraform by following the official [Terraform Installation Guide](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli).
2. **AWS CLI:**
   Install and configure AWS CLI using the instructions provided in the official [AWS CLI User Guide](https://aws.amazon.com/cli/).
   Configure your AWS credentials:

   ```bash
   aws configure
   ```

* AWS Account:
  Ensure you have an AWS account with the necessary permissions to create and manage resources.
* Terraform Backend (Optional but recommended):
  Configure a remote backend (e.g., AWS S3) for storing the Terraform state. Modify the backend block in Terraform-vpc/provider.tf to match your S3 bucket name.

## Usage

### Manual Terraform Usage

Follow these steps for manual provisioning of AWS resources using Terraform:

1. Clone the repository:

   ```bash
   git clone [invalid URL removed]
   cd AWS-IAC-POC
   cd Terraform-vpc
   ```

2. Initialize the Terraform environment:

   ```bash
   terraform init
   ```

3. Validate the Terraform configuration files:

   ```bash
   terraform validate
   ```

4. Create an execution plan for Terraform:

   ```bash
   terraform plan
   ```

5. Apply the configuration to provision resources:

   ```bash
   terraform apply
   ```

   Confirm the action when prompted.

6. If necessary, destroy the provisioned infrastructure:

   ```bash
   terraform destroy
   ```

### Automated GitHub Actions CI/CD Pipeline

This repository is integrated with GitHub Actions for automated deployment and management of AWS resources.

#### Triggering the Terraform CI/CD Pipeline

This section explains how to manually trigger the Terraform CI/CD pipeline via GitHub Actions for deploying AWS resources.

**Steps to Trigger the Workflow**

1. Navigate to GitHub Actions:
   * Open your GitHub repository.
   * Click on the Actions tab.
2. Locate the Terraform Workflow:
   * Find the Terraform CI/CD pipeline for Deploy AWS resources workflow on the left side.
   * Click on it to open the details.
3. Trigger the Workflow:
   * Click on Run workflow on the right side.
   * Select the following options:
       * Workspace: Choose from dev, test, or prod.
       * Deployment Type: Choose deploy or destroy.
   * Click Start workflow.
4. Monitor the Workflow:
   * Refresh the page to view the workflow progress. The workflow will execute the following steps:
       * Terraform Init: Initializes Terraform.
       * Terraform Validate: Validates the configuration.
       * Workspace Selection: Selects the workspace.
       * Terraform Plan: Previews the deployment or destruction.
       * Terraform Apply/Destroy: Applies the changes or destroys resources.

**Input Details**

* Workspace: Choose the environment (dev, test, or prod).
* Deployment Type: Choose deploy to deploy or destroy to remove resources.

**Conclusion**

By following the above steps, you can easily trigger and monitor the Terraform CI/CD pipeline for deploying or destroying resources in your selected workspace.

## Resources Provisioned

This POC provisions the following AWS resources:

* Virtual Private Cloud
