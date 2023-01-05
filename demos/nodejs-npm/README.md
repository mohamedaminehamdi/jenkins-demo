# Node.js NPM CI/CD Pipeline

This folder contains a complete CI/CD pipeline demonstration for Node.js/NPM applications.

## Overview

This Jenkins pipeline showcases:
- **Dependency Management**: NPM CI with offline preference
- **Code Linting**: ESLint for JavaScript/TypeScript
- **Testing**: Jest unit tests with coverage reports
- **Building**: Application compilation to dist/
- **Security**: NPM security audit
- **Containerization**: Docker image creation
- **Registry**: Docker registry push
- **Deployment**: Kubernetes staging deployment
- **E2E Testing**: End-to-end testing
- **Performance**: Performance testing stage
- **Reporting**: Coverage and linting reports

## Pipeline Stages

1. **Checkout** - Clone the Node.js repository
2. **Setup NodeJS** - Verify Node and NPM versions
3. **Install Dependencies** - NPM CI (clean install)
4. **Code Quality - ESLint** - Lint analysis
5. **Unit Tests** - Jest with coverage
6. **Build** - Build distribution files
7. **Security Audit** - NPM security check
8. **Build Docker Image** - Create container
9. **Push to Registry** - Upload to registry
10. **Deploy to Staging** - Deploy to Kubernetes
11. **E2E Tests** - End-to-end testing
12. **Performance Test** - Performance evaluation

## Requirements

- Node.js 18.x+
- NPM 8.x+
- Docker
- Kubernetes cluster
- Jest for testing

## Usage

1. Copy `Jenkinsfile` to your Node.js project root
2. Update Git URL and Docker registry
3. Ensure `package.json` has scripts: `test`, `build`, `test:e2e`
4. Create a Jenkins pipeline job
5. Configure optional credentials

## Build Output

The pipeline generates:
- Built files in `dist/` directory
- Test coverage report in `coverage/`
- ESLint report in JSON format
- Docker image with application

## NPM Scripts Expected

Your `package.json` should include:
```json
{
  "scripts": {
    "build": "...",
    "test": "jest --coverage",
    "test:e2e": "...",
    "performance-test": "..."
  }
}
```
