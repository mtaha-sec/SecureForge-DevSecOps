#  SecureForge - Enterprise DevSecOps Security Pipeline

> **Enterprise DevSecOps CI/CD Pipeline for Vulnerable Web Applications**
>
> A complete DevSecOps security pipeline integrating Static Application Security Testing (SAST), Software Composition Analysis (SCA), Secret Detection, Container Security, Dynamic Application Security Testing (DAST), Code Quality Analysis, Docker, and Kubernetes deployment.
>
> This project was designed following the security-by-design principles and recommendations promoted by the **OWASP DevSecOps Guideline**, integrating security controls throughout the Software Development Lifecycle (SDLC).

---

#  Project Overview

Modern software security should not rely on manual testing performed only before production.

This project demonstrates how security can be integrated into every phase of the CI/CD pipeline by automating vulnerability detection, code quality analysis, dependency scanning, container security, dynamic testing, and secure deployment.

The vulnerable application used throughout this project is **OWASP Juice Shop**, one of the most widely used intentionally vulnerable web applications for security training.

---

# Objectives

The main objectives of this project are to:

- Integrate security into the CI/CD pipeline
- Automate application security testing
- Detect vulnerabilities before deployment
- Improve code quality
- Secure Docker images
- Deploy securely to Kubernetes
- Demonstrate an enterprise DevSecOps workflow

---

#  Architecture

```text
Developer
     │
     ▼
Git Push / Pull Request
     │
     ▼
GitHub Repository
     │
     ▼
GitHub Actions CI/CD
     │
     ├──────────────┐
     │              │
     ▼              ▼
 Semgrep       Gitleaks
 (SAST)      (Secrets)
     │
     ▼
Trivy Filesystem
 (SCA)
     │
     ▼
Docker Build
     │
     ▼
Trivy Image Scan
(Container Security)
     │
     ▼
SonarQube Cloud
(Code Quality)
     │
     ▼
Deploy Juice Shop
     │
     ▼
OWASP ZAP
(DAST)
     │
     ▼
Kind Kubernetes Cluster
     │
     ▼
Juice Shop Deployment
```

---

#  Security Pipeline

The project integrates multiple security controls covering different attack surfaces.

| Security Layer | Tool |
|---------------|------|
| Source Control | GitHub |
| CI/CD | GitHub Actions |
| SAST | Semgrep |
| Secret Detection | Gitleaks |
| Software Composition Analysis | Trivy |
| Container Security | Trivy |
| Code Quality | SonarQube Cloud |
| DAST | OWASP ZAP |
| Containerization | Docker |
| Orchestration | Kubernetes (Kind) |

---

#  Technology Stack

## DevOps

- Git
- GitHub
- GitHub Actions
- Docker
- Docker Compose
- Kubernetes (Kind)

## Security

- Semgrep
- Gitleaks
- Trivy
- SonarQube Cloud
- OWASP ZAP

## Application

- OWASP Juice Shop

---

#  Repository Structure

```text
SecureForge-DevSecOps/

├── .github/
│   └── workflows/
│       └── security-pipeline.yml
│
├── application/
│   └── juice-shop/
│
├── docker/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── .env
│
├── kubernetes/
│   ├── namespace.yaml
│   ├── deployment.yaml
│   └── service.yaml
│
├── security-tools/
│   ├── semgrep/
│   ├── trivy/
│   ├── gitleaks/
│   └── zap/
│
├── pentest/
│
├── reports/
│
├── screenshots/
│
├── docs/
│
├── README.md
│
└── LICENSE
```

---

#  CI/CD Workflow

The pipeline automatically performs the following steps:

- Checkout repository
- Install security tools
- Static code analysis (Semgrep)
- Secret detection (Gitleaks)
- Dependency scanning (Trivy FS)
- Docker image build
- Container image scanning (Trivy Image)
- Code quality analysis (SonarQube Cloud)
- Deploy OWASP Juice Shop
- Dynamic security testing (OWASP ZAP)
- Kubernetes deployment (Kind)

---

# ☁️ Kubernetes Deployment

The application is automatically deployed to a local Kubernetes cluster using **Kind**.

Deployment includes:

- Namespace
- Deployment
- Service

This demonstrates the Continuous Deployment (CD) phase of the DevSecOps pipeline.

---

#  Security Controls

## Static Application Security Testing

- Semgrep

Detects:

- SQL Injection patterns
- Command Injection
- Hardcoded credentials
- Unsafe functions
- Security misconfigurations

---

## Secret Detection

- Gitleaks

Detects:

- API Keys
- Passwords
- Tokens
- Private Keys
- JWT Secrets

---

## Software Composition Analysis

- Trivy Filesystem

Scans:

- Third-party dependencies
- Vulnerable packages
- Known CVEs

---

## Container Security

- Trivy Image

Scans:

- Docker images
- Operating System packages
- Container libraries
- Known vulnerabilities

---

## Code Quality

- SonarQube Cloud

Provides:

- Bugs
- Vulnerabilities
- Code Smells
- Maintainability
- Security Hotspots

---

## Dynamic Application Security Testing

- OWASP ZAP

Detects:

- Missing HTTP Security Headers
- Security Misconfigurations
- Authentication Issues
- XSS Indicators
- Information Disclosure

---

#  Screenshots

Project screenshots are available in the **screenshots/** directory.

Examples include:

- GitHub Actions Pipeline
- Semgrep Results
- Trivy Reports
- SonarQube Dashboard
- OWASP ZAP Results
- Kubernetes Pods
- Kubernetes Services

---

# Results

The pipeline automatically performs security validation before deployment.

Implemented controls include:

- Static Analysis
- Dependency Analysis
- Secret Detection
- Container Security
- Code Quality Analysis
- Dynamic Security Testing
- Kubernetes Deployment

---

#  References

This project was inspired by industry DevSecOps practices and follows the principles described in:

- OWASP DevSecOps Guideline
- OWASP Top 10
- OWASP Juice Shop
- OWASP ZAP Documentation
- GitHub Actions Documentation
- Trivy Documentation
- Semgrep Documentation
- SonarQube Cloud Documentation
- Kubernetes Documentation

---

#  Learning Outcomes

Through this project, I gained practical experience in:

- DevSecOps methodology
- Secure SDLC
- CI/CD pipeline design
- Docker security
- Kubernetes deployment
- Application security testing
- Container security
- Secure software delivery

---

# Future Improvements

Potential future enhancements include:

- Falco Runtime Security
- Policy-as-Code (OPA Gatekeeper)
- Helm Charts
- Argo CD
- GitOps workflow
- Slack Notifications
- Automated Security Reports
- SBOM generation
- Dependency Track integration

---

#  Author

**Mohamed Taha Aboumehdi Hassani**

Cybersecurity Engineering Student

- DevSecOps
- Application Security
- Cloud Security
- Offensive Security

---

#  Acknowledgment

This project is intended for educational purposes and security research.

OWASP Juice Shop is an intentionally vulnerable application developed by the OWASP Foundation for security awareness, training, and testing.
