# Docker Multi-Stage Build CI/CD Pipeline

This folder contains a complete CI/CD pipeline demonstration for Docker multi-stage builds.

## Overview

This Jenkins pipeline showcases Docker best practices:
- **Dockerfile Validation**: Hadolint linting
- **Multi-Stage Builds**: Separate test and production stages
- **Container Testing**: Running tests inside containers
- **Production Build**: Optimized final image
- **Vulnerability Scanning**: Trivy security scanning
- **Registry Push**: Push to Docker registry
- **Kubernetes Deployment**: Deploy to production
- **Health Verification**: Post-deployment verification
- **Cleanup**: Image pruning and cleanup
- **Metadata**: Image inspection and archiving

## Pipeline Stages

1. **Checkout** - Clone the repository
2. **Validate Dockerfile** - Hadolint validation
3. **Build Test Image** - Build test stage
4. **Run Tests in Container** - Execute tests inside image
5. **Build Final Image** - Build production stage
6. **Scan Image** - Trivy vulnerability scanning
7. **Push to Registry** - Upload to Docker registry
8. **Deploy to Production** - Kubernetes deployment
9. **Verify Deployment** - Health check verification
10. **Cleanup** - Clean up local images

## Multi-Stage Dockerfile Example

```dockerfile
# Test stage
FROM node:18 as test
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run lint && npm test

# Production stage
FROM node:18-alpine as production
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY --from=test /app/dist ./dist
EXPOSE 8080
CMD ["node", "dist/index.js"]
```

## Requirements

- Docker with BuildKit support
- Docker registry credentials
- Hadolint for Dockerfile validation
- Trivy for vulnerability scanning
- Kubernetes cluster

## Usage

1. Copy `Jenkinsfile` to your project root
2. Update Git URL and Docker registry
3. Create a multi-stage `Dockerfile`
4. Create a Jenkins pipeline job
5. Configure Docker registry credentials

## Build Arguments

The pipeline passes build arguments to Docker:
- `BUILD_DATE`: Build timestamp
- `VCS_REF`: Git commit SHA
- `VERSION`: Jenkins build number

## Vulnerability Scanning

Scans for HIGH and CRITICAL vulnerabilities using Trivy.
Fails on critical issues (can be made non-blocking with `|| true`).
