# Monorepo Polyglot CI/CD Pipeline

This folder contains a complete CI/CD pipeline demonstration for monorepo projects with multiple languages and services.

## Overview

This Jenkins pipeline showcases advanced patterns:
- **Change Detection**: Detect which services changed
- **Parallel Builds**: Build multiple services simultaneously
- **Multi-Language**: Java, Python, Go, and Frontend
- **Integration Testing**: Test services together
- **Security Scanning**: Scan all images for vulnerabilities
- **Load Testing**: Performance testing with k6
- **Phased Deployment**: Staging then production
- **Smoke Tests**: Verify all services on staging
- **Manual Approval**: Gate production deployment
- **Orchestration**: Kubernetes deployment of all services

## Repository Structure

```
monorepo/
├── services/
│   ├── java/          # Java/Maven service
│   ├── python/        # Python/Flask service
│   ├── go/            # Go application
│   └── shared/        # Shared code
├── frontend/          # React/Node.js frontend
├── docker-compose.test.yml
├── docker-compose.load-test.yml
├── load-test.js       # k6 load testing script
└── Jenkinsfile
```

## Pipeline Stages

1. **Checkout** - Clone monorepo
2. **Detect Changes** - Identify modified services
3. **Parallel Build** - Build all services in parallel
4. **Test All Services** - Integration, security, load tests
5. **Push Images** - Push all images to registry
6. **Deploy to Staging** - Deploy all services
7. **Smoke Tests** - Verify staging health
8. **Approval** - Manual approval gate
9. **Deploy to Production** - Production deployment

## Key Features

### Change Detection
Identifies which services changed to optimize builds.

### Parallel Execution
Builds Java, Python, Go, and Frontend simultaneously:
- Tests run in parallel
- Security scanning runs in parallel
- Load testing runs separately

### Multiple Testing Strategies
- Unit tests in each service
- Integration tests with docker-compose
- Security scanning with Trivy
- Load testing with k6

### Deployment Strategy
- Staging first for validation
- Smoke tests on staging
- Manual approval gate
- Blue-green deployment to production

## Requirements

- Docker & Docker Compose
- Kubernetes cluster
- Maven (for Java service)
- Python 3.9+ (for Python service)
- Go 1.19+ (for Go service)
- Node.js 18+ (for frontend)
- k6 (for load testing)

## Usage

1. Copy files to monorepo root
2. Update Git URLs and Docker registry
3. Create services following the structure
4. Set up Kubernetes namespaces (staging, production)
5. Configure Jenkins pipeline job

## Environment Setup

Create necessary Kubernetes namespaces:

```bash
kubectl create namespace staging
kubectl create namespace production
```

## Testing Patterns

- **Unit Tests**: Run in each service build stage
- **Integration Tests**: Run with all services via docker-compose
- **Security**: Trivy scans all Docker images
- **Load**: k6 load testing for performance validation
- **Smoke**: Health checks post-deployment

## Approval Gate

Production deployment requires manual approval. Jenkins will pause and wait for user confirmation.
