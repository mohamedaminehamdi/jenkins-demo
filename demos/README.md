# Jenkins CI/CD Pipeline Demonstrations

A comprehensive collection of Jenkins pipeline examples demonstrating CI/CD best practices across multiple programming languages and deployment scenarios.

## 📁 Folder Structure

```
demos/
├── java-maven/              # Java/Maven application CI/CD
├── python-flask/            # Python Flask web app CI/CD
├── go-app/                  # Go application CI/CD
├── nodejs-npm/              # Node.js/NPM application CI/CD
├── docker-multistage/       # Docker multi-stage build CI/CD
└── monorepo-polyglot/       # Monorepo with multiple languages
```

## 🚀 Pipeline Examples

### 1. Java Maven (`java-maven/`)
Complete CI/CD pipeline for Java projects using Maven.

**Features:**
- Maven build and package
- Unit testing
- SonarQube code analysis
- Docker containerization
- Kubernetes deployment
- Health checks

**Key Stages:** Checkout → Build → Test → Analysis → Docker → Deploy

---

### 2. Python Flask (`python-flask/`)
End-to-end CI/CD for Python web applications.

**Features:**
- Virtual environment setup
- Dependency management
- Flake8 and PyLint linting
- Pytest with coverage
- Docker containerization
- Kubernetes deployment with rollout

**Key Stages:** Checkout → Setup → Lint → Test → Docker → Deploy

---

### 3. Go Application (`go-app/`)
Production-grade pipeline for Go projects.

**Features:**
- Go modules management
- golangci-lint analysis
- Unit tests with race detection
- Static binary compilation
- Gosec security scanning
- Docker multi-architecture builds

**Key Stages:** Checkout → Lint → Test → Build → Security → Docker → Deploy

---

### 4. Node.js NPM (`nodejs-npm/`)
Modern CI/CD pipeline for JavaScript/TypeScript projects.

**Features:**
- NPM dependency management
- ESLint code quality
- Jest unit testing
- application build
- Security audit
- E2E and performance testing

**Key Stages:** Checkout → Setup → Lint → Test → Build → Deploy → E2E

---

### 5. Docker Multi-Stage (`docker-multistage/`)
Best practices for containerized applications.

**Features:**
- Dockerfile validation (Hadolint)
- Multi-stage builds (test & production)
- Container-based testing
- Trivy vulnerability scanning
- Docker registry push
- Production deployment

**Key Stages:** Validate → Test → Build → Scan → Push → Deploy

---

### 6. Monorepo Polyglot (`monorepo-polyglot/`)
Advanced pipeline for large monorepos with multiple services.

**Features:**
- Change detection per service
- Parallel builds (Java, Python, Go, Frontend)
- Integration testing
- Security scanning all images
- Load testing
- Staged deployment (staging → production)
- Manual approval gates

**Key Stages:** Detect Changes → Parallel Build → Test → Deploy Staging → Approval → Deploy Production

---

## 🎯 Quick Start

Choose the pipeline that matches your project type:

```bash
# For Java projects
cp demos/java-maven/Jenkinsfile /path/to/your/java/project/

# For Python projects
cp demos/python-flask/Jenkinsfile /path/to/your/python/project/

# For Go projects
cp demos/go-app/Jenkinsfile /path/to/your/go/project/

# For Node.js projects
cp demos/nodejs-npm/Jenkinsfile /path/to/your/nodejs/project/

# For Docker projects with multi-stage
cp demos/docker-multistage/Jenkinsfile /path/to/your/docker/project/
```

## 📋 Common Pipeline Patterns

### Build Stages (All Pipelines)
1. **Checkout** - Clone source code
2. **Build** - Compile/package application
3. **Test** - Run unit and integration tests
4. **Artifact** - Create Docker image or package
5. **Push** - Push to registry
6. **Deploy** - Deploy to target environment

### Testing Strategies
- **Unit Tests** - Framework-specific (Maven, Pytest, Jest)
- **Code Quality** - SonarQube, ESLint, golangci-lint
- **Security** - Trivy (Docker images), Gosec (Go), npm audit (Node)
- **Integration** - docker-compose or API tests
- **E2E** - Application health checks
- **Load** - k6 for performance (monorepo)

### Deployment Targets
- **Local** - Workspace cleanup
- **Staging** - Pre-production testing
- **Production** - Final rollout
- **Kubernetes** - Container orchestration

## 🔧 Configuration

Each pipeline requires:
- **Git Repository** - Update SSH/HTTP URLs
- **Docker Registry** - Set REGISTRY and IMAGE_NAME
- **Kubernetes** - Configure namespaces and contexts
- **Infrastructure** - Jenkins agents with required tools

Tool Requirements by Pipeline:
- **Java**: Maven 3.6+, Java 11+, Docker, kubectl
- **Python**: Python 3.9+, Virtual env, Docker, kubectl
- **Go**: Go 1.19+, golangci-lint, Gosec, Docker, kubectl
- **Node.js**: Node.js 18+, NPM 8+, Docker, kubectl
- **Docker**: Docker 20.10+, Hadolint, Trivy, kubectl
- **Monorepo**: All of the above + k6

## 📊 CI/CD Best Practices Demonstrated

1. **Automated Testing** - Built-in testing at each stage
2. **Code Quality** - Static analysis tools integrated
3. **Security Scanning** - Vulnerability detection
4. **Containerization** - Docker for consistency
5. **Orchestration** - Kubernetes deployment
6. **Monitoring** - Health checks and monitoring hooks
7. **Parallelization** - Faster builds with parallel stages
8. **Approval Gates** - Manual review for production
9. **Artifact Management** - Archive and versioning
10. **Notifications** - Post-build status updates

## 📚 Learning Path

1. Start with **Java Maven** for basic CI/CD concepts
2. Explore **Python Flask** for alternative Language
3. Study **Go Application** for compiled languages
4. Learn **Docker Multi-Stage** for containerization
5. Advance to **Monorepo Polyglot** for complex architectures

## 🔍 Key Concepts

### Pipeline as Code
All pipelines are defined in `Jenkinsfile` (Declarative syntax).

### Stages
Sequential or parallel execution blocks with specific tasks.

### Agents
Jenkins nodes/workers that execute the pipeline.

### Environment Variables
Global and stage-specific configuration.

### Post Actions
Cleanup, reporting, and notifications after pipeline execution.

### Options
Pipeline configuration like timeouts, build discarder, timestamps.

## 🚨 Error Handling

All pipelines include:
- Timeout enforcement
- Build history management
- Error logging and reporting
- Cleanup in post-block
- Optional failure notifications

## 💡 Tips & Tricks

1. **Parallel Execution** - Use `parallel {}` blocks for speed
2. **Change Detection** - Use `git diff` for optimization
3. **Container Testing** - Run tests inside containers
4. **Environment Variables** - Centralize configuration
5. **Artifact Archival** - Keep important outputs
6. **Workspace Cleanup** - Use post-block for cleanup
7. **Approval Gates** - Use `input()` for manual gates

## 🔗 Related Resources

- [Jenkins Documentation](https://www.jenkins.io/doc/)
- [Declarative Pipeline Syntax](https://www.jenkins.io/doc/book/pipeline/syntax/)
- [Docker Best Practices](https://docs.docker.com/develop/dev-best-practices/)
- [Kubernetes Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

## 📝 License

These pipeline examples are provided as-is for educational purposes.

## 🤝 Contributing

Feel free to extend these examples with:
- Additional languages
- New deployment targets
- More testing strategies
- Enhanced security scanning
- Custom monitoring integration

---

**Last Updated:** January 5, 2023
**Version:** 1.0

For questions or improvements, refer to the individual README files in each demo folder.
