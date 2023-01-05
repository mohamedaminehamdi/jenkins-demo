# Python Flask CI/CD Pipeline

This folder contains a complete CI/CD pipeline demonstration for Python Flask web applications.

## Overview

This Jenkins pipeline showcases:
- **Environment Setup**: Python virtual environment creation
- **Dependency Management**: PIP package installation
- **Code Linting**: Flake8 and PyLint code quality checks
- **Testing**: Pytest unit tests with code coverage
- **Artifacts**: Python wheel distribution package
- **Containerization**: Docker image building
- **Registry**: Push to Docker registry
- **Deployment**: Kubernetes deployment
- **Integration**: Integration testing post-deployment
- **Reports**: JUnit and HTML coverage reports

## Pipeline Stages

1. **Checkout** - Clone the Flask repository
2. **Setup Environment** - Create Python virtual environment
3. **Install Dependencies** - Install requirements.txt packages
4. **Code Quality - Linting** - Flake8 analysis
5. **Code Quality - PyLint** - PyLint analysis
6. **Unit Tests** - Pytest with coverage
7. **Build Artifact** - Create Python wheel
8. **Build Docker Image** - Containerize Flask app
9. **Push to Docker Registry** - Upload image
10. **Deploy to Dev** - Deploy to Kubernetes
11. **Integration Tests** - End-to-end testing

## Requirements

- Python 3.9+
- PIP package manager
- Docker
- Kubernetes cluster

## Usage

1. Copy `Jenkinsfile` to your Flask project root
2. Update the Git URL and Docker registry
3. Ensure `requirements.txt` is present
4. Create a Jenkins pipeline job pointing to this Jenkinsfile
5. Configure any needed credentials in Jenkins

## Test Coverage

The pipeline generates:
- JUnit XML test reports
- HTML coverage reports in `htmlcov/index.html`
- PyTest detailed output
