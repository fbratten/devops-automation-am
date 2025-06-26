# DevOps Automation - AlgoMingle

CI/CD pipelines and automation scripts for the AlgoMingle messaging platform.

## Overview

This repository contains:
- GitHub Actions workflows for all repositories
- Deployment scripts and configurations
- Infrastructure as Code (Terraform/CloudFormation)
- Monitoring and alerting setup
- Security scanning automation

## Structure

```
devops-automation-am/
├── .github/
│   └── workflows/     # Reusable GitHub Actions workflows
├── scripts/           # Automation scripts
│   ├── deploy/       # Deployment scripts
│   ├── setup/        # Environment setup
│   └── monitoring/   # Monitoring configuration
├── terraform/        # Infrastructure as Code
├── k8s/             # Kubernetes manifests
├── docker/          # Docker configurations
└── docs/            # DevOps documentation
```

## Automated Workflows

### Contract Deployment
- Automated testing on PR
- Deployment to testnet on merge
- Mainnet deployment with approval gates

### Application CI/CD
- Build and test on every push
- Security scanning (SAST/DAST)
- Automated dependency updates
- Preview deployments for PRs

### Cross-Repository Orchestration
- Coordinated releases across all repos
- Automated version bumping
- Changelog generation
- Integration testing

## Getting Started

### Prerequisites

- GitHub CLI (`gh`)
- Docker and Docker Compose
- Kubernetes CLI (`kubectl`) - optional
- Terraform - for infrastructure management

### Setup

```bash
# Clone the repository
git clone https://github.com/fbratten/devops-automation-am.git
cd devops-automation-am

# Install GitHub CLI extensions
gh extension install github/gh-actions-cache

# Set up secrets (requires repo admin access)
./scripts/setup/configure-secrets.sh
```

### Usage

#### Deploy Contracts
```bash
./scripts/deploy/deploy-contracts.sh --network testnet
```

#### Run Integration Tests
```bash
./scripts/test/integration-test.sh
```

#### Monitor System Health
```bash
./scripts/monitoring/health-check.sh
```

## GitHub Actions Secrets Required

- `ALGORAND_MNEMONIC` - Deployment account mnemonic
- `ANTHROPIC_API_KEY` - For AI services
- `CROSS_REPO_TOKEN` - PAT for cross-repo triggers
- `DOCKER_REGISTRY_TOKEN` - For container registry
- `MONITORING_WEBHOOK` - Alerts webhook URL

## Related Repositories

This is part of the AlgoMingle multi-repository project:
- [algorand-contracts-am](https://github.com/fbratten/algorand-contracts-am) - Smart contracts
- [algomingle](https://github.com/fbratten/algomingle) - Frontend application
- [ai-orchestrator-am](https://github.com/fbratten/ai-orchestrator-am) - AI services
- [development-playbook-am](https://github.com/fbratten/development-playbook-am) - Documentation

---

## 🚧 Project Status

This repository is part of an active development project and is **not currently accepting external contributions**.

- ✅ Feel free to **explore, fork, and learn** from the code
- 💬 **Questions?** Please use the [Discussions](../../discussions) tab
- ⭐ **Like the project?** Give it a star!
- 📧 **Private inquiries:** jack.bratten@adaptivearts.ai

For more information, see [CONTRIBUTING.md](CONTRIBUTING.md).
