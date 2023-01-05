# Java Maven CI/CD Pipeline

This folder contains a complete CI/CD pipeline demonstration for Java Maven projects.

## Overview

This Jenkins pipeline showcases:
- **Source Code Management**: Git checkout with branch specification
- **Build**: Maven clean build and package
- **Testing**: Unit tests with Maven
- **Code Quality**: SonarQube analysis and metrics
- **Artifacts**: JAR artifact archival
- **Containerization**: Docker image creation and tagging
- **Registry**: Push to Docker registry
- **Deployment**: Kubernetes deployment to dev environment
- **Testing**: Health check smoke tests
- **Cleanup**: Post-build workspace cleanup

## Pipeline Stages

1. **Checkout** - Clone the repository
2. **Build** - Compile and package the application
3. **Unit Tests** - Run Maven test suites
4. **SonarQube Analysis** - Code quality analysis
5. **Build Artifact** - Create JAR file
6. **Docker Build** - Build container image
7. **Push to Docker Registry** - Upload to registry
8. **Deploy to Dev** - Deploy to Kubernetes
9. **Smoke Tests** - Verify application health

## Requirements

- Java 11+
- Maven 3.6+
- Docker
- Kubernetes cluster
- SonarQube instance

## Usage

1. Copy `Jenkinsfile` to your Java project root
2. Update the Git URL and Docker registry details
3. Configure SonarQube credentials in Jenkins
4. Create a Jenkins pipeline job pointing to this Jenkinsfile
