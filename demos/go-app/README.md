# Go Application CI/CD Pipeline

This folder contains a complete CI/CD pipeline demonstration for Go (Golang) applications.

## Overview

This Jenkins pipeline showcases:
- **Dependency Management**: Go modules verification
- **Code Linting**: golangci-lint code quality analysis
- **Testing**: Unit tests with code coverage and race detection
- **Build**: Static binary compilation for Linux
- **Security**: Gosec static security scanning
- **Containerization**: Docker image creation
- **Registry**: Push to Docker registry
- **Deployment**: Kubernetes deployment
- **Health Checks**: Application availability verification
- **Reporting**: Coverage and security reports

## Pipeline Stages

1. **Checkout** - Clone the Go repository
2. **Setup** - Verify Go environment
3. **Download Dependencies** - Go modules download and verify
4. **Lint** - golangci-lint analysis
5. **Unit Tests** - Testing with race detection
6. **Build** - Compile binary for Linux
7. **Security Scan** - Gosec vulnerability scanning
8. **Build Docker Image** - Create container image
9. **Push to Registry** - Upload to registry
10. **Deploy to Dev** - Deploy to Kubernetes
11. **Health Check** - Verify application health

## Requirements

- Go 1.19+
- golangci-lint
- Gosec
- Docker
- Kubernetes cluster

## Usage

1. Copy `Jenkinsfile` to your Go project root
2. Ensure `go.mod` and `go.sum` files are present
3. Update Git URL and Docker registry
4. Create a Jenkins pipeline job
5. Configure credentials if needed

## Build Output

The pipeline produces:
- Compiled Go binary: `bin/app`
- Coverage report: `coverage.html`
- Security report: `gosec-report.json`
- Docker image with multi-stage build
