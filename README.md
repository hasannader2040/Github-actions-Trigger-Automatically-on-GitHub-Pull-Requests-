# simple-java-app
## This is simple Java App to Test Continous Integration and Deployment

# GitHub Actions: Trigger Automatically on Pull Requests

## Overview

This project demonstrates how to set up **Continuous Integration (CI)** and **Continuous Deployment (CD)** pipelines using **GitHub Actions**. It focuses on automatically triggering workflows on **GitHub Pull Requests** to ensure code quality, run tests, and deploy applications seamlessly. The primary objective is to automate the testing and deployment processes to improve development efficiency and maintain code quality.

## Purpose

The main purpose of this project is to:

- Automate testing and deployment workflows using GitHub Actions.
- Trigger CI/CD pipelines automatically whenever a pull request is opened or updated.
- Ensure that all code changes are tested and validated before merging into the main branch.
- Deploy the application automatically upon successful merge, if configured.

By setting up these workflows, the project aims to provide a robust CI/CD pipeline that helps developers maintain high-quality code and streamline the development process.

## Features

- **Automatic CI/CD Pipeline**: Workflows are triggered automatically on pull requests.
- **Code Quality Checks**: Linting and unit tests run automatically to ensure code quality.
- **Automated Deployment**: Optionally deploy the application automatically if all checks pass.
- **Customizable Workflows**: Easily modify workflows to fit different project requirements.

## Getting Started

### Prerequisites

Before setting up GitHub Actions for your repository, ensure you have:

- A **GitHub account** with access to the repository you want to set up the workflows for.
- Basic knowledge of **Git** and **GitHub**.
- Familiarity with **YAML** syntax used for GitHub Actions workflows.

### Installation

Follow these steps to set up GitHub Actions workflows for your repository:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/hasannader2040/Github-actions-Trigger-Automatically-on-GitHub-Pull-Requests-.git
   ```

2- **Navigate to the project directory:**


 ```bash
cd Github-actions-Trigger-Automatically-on-GitHub-Pull-Requests-
 ```
3- **Create GitHub Actions Workflow Directory:**

GitHub Actions workflows are stored in the .github/workflows directory. If this directory does not exist, create it:


 ```bash
mkdir -p .github/workflows
 ```

4- **Create a Workflow File:**

Create a YAML file inside the **.github/workflows** directory to define your workflow. For example, **ci.yml:**

 ```bash
name: CI Pipeline

on:
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

      - name: Lint code
        run: npm run lint
 ```

This workflow will trigger on every pull request made to the main branch, check out the code, set up Node.js, install dependencies, run tests, and lint the code.

## Usage
Here are some examples of how to use GitHub Actions for CI/CD with pull requests:

1 - **Creating a Pull Request:**

When you create a new pull request against the **main** branch, the GitHub Actions workflow will be triggered automatically. It will perform the steps defined in the workflow YAML file, such as running tests and linting the code.

2- **Viewing Workflow Runs:**

You can view the status and results of workflow runs in the "Actions" tab of your GitHub repository. Each run will show detailed logs of each step, making it easy to identify and fix issues.

3 - **Modifying the Workflow:**

To modify the workflow, edit the corresponding YAML file in the **.github/workflows** directory. For example, to add deployment steps, you might add:

 ```bash
deploy:
  runs-on: ubuntu-latest
  needs: build
  steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Deploy to Server
      run: |
        echo "Deploying to production server..."
        # Add your deployment script here
 ```

        
This example shows a deployment job that runs after the build job completes successfully.

4- **Re-running Workflows:**

If a workflow fails, you can re-run it from the "Actions" tab on GitHub. Simply click on the failed workflow run and select "Re-run jobs."

## Tools and Technologies
This project utilizes the following tools and technologies:

1- **GitHub Actions**: GitHub's built-in CI/CD tool used to automate workflows directly in the GitHub environment.
**Node.js:** JavaScript runtime used for running scripts and tests in this example.
**YAML:** A human-readable data serialization standard that is used to define workflows for GitHub Actions.


## Contributing
Contributions are welcome! Please follow these steps to contribute:

1- Fork the repository.
2- Create a new branch (git checkout -b feature/your-feature-name).
3- Make your changes and commit them (git commit -m 'Add some feature').
4- Push to the branch (git push origin feature/your-feature-name).
5- Open a pull request.


## License
This project is licensed under the MIT License. See the LICENSE file for more details.

## Acknowledgements
Thanks to the GitHub Actions team for creating an excellent CI/CD tool.
Special thanks to the developers who contribute to the open-source community.







# Github-actions-Trigger-Automatically-on-GitHub-Pull-Requests-


![1](https://github.com/user-attachments/assets/19f8df9e-787b-47fa-9e38-c77ed89da18d)
