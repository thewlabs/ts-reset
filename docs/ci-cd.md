# CI/CD Workflow Documentation

This document describes the enhanced CI/CD workflows for the `@thewlabs/ts-reset` project.

## 🚀 Workflows Overview

### 1. **CI Workflow** (`.github/workflows/main.yml`)

Runs on every push and pull request to ensure code quality and compatibility.

#### Features:
- **Multi-platform testing**: Tests on Ubuntu, Windows, and macOS
- **Multi-Node.js version support**: Tests Node.js 18, 20, and 22
- **Comprehensive checks**:
  - TypeScript compilation
  - Linting and formatting
  - Package export validation
  - Build artifact generation
- **Security scanning**: Automated vulnerability detection
- **Package validation**: Ensures the package can be properly distributed

#### Jobs:
1. **lint-and-typecheck**: Fast linting and type checking
2. **build-and-test**: Build and test across multiple environments
3. **security-audit**: Security vulnerability scanning
4. **validate-package**: Package integrity validation

### 2. **Release & Publish Workflow** (`.github/workflows/publish.yml`)

Automatically releases and publishes packages when changes are merged to main.

#### Features:
- **Automated releases**: Uses Changesets for version management
- **Pre-release validation**: Runs full CI before publishing
- **Provenance attestation**: Cryptographic proof of build integrity
- **GitHub releases**: Automatically creates GitHub releases
- **Slack notifications**: Optional team notifications

#### Jobs:
1. **pre-release-checks**: Validates changes before release
2. **release**: Publishes packages and creates releases

### 3. **Security Workflow** (`.github/workflows/security.yml`)

Continuous security monitoring and vulnerability detection.

#### Features:
- **CodeQL analysis**: Advanced code scanning
- **Dependency review**: Checks for vulnerable dependencies
- **Supply chain security**: Trivy vulnerability scanner
- **License compliance**: Ensures only approved licenses are used

### 4. **Dependency Updates** (`.github/workflows/dependency-updates.yml`)

Automated dependency maintenance.

#### Features:
- **Weekly updates**: Automatically updates dependencies
- **CI validation**: Ensures updates don't break functionality
- **Auto PR creation**: Creates PRs for dependency updates

### 5. **Manual Release** (`.github/workflows/manual-release.yml`)

Allows manual releases with custom version bumps.

#### Features:
- **Version control**: Choose patch, minor, major, or prerelease
- **Prerelease tags**: Support for alpha, beta, rc releases
- **CI skip option**: Option to skip CI for emergency releases

### 6. **Auto Label** (`.github/workflows/auto-label.yml`)

Automatic issue and PR labeling for better organization.

#### Features:
- **File-based labeling**: Labels based on changed files
- **Size labeling**: Labels PRs by size (XS, S, M, L, XL, XXL)
- **Auto-assignment**: Assigns reviewers automatically

## 🔧 Configuration Files

### GitHub Templates

#### Issue Templates
- **Bug Report** (`.github/ISSUE_TEMPLATE/bug_report.yml`): Structured bug reporting
- **Feature Request** (`.github/ISSUE_TEMPLATE/feature_request.yml`): Feature proposal template

#### Pull Request Template
- **PR Template** (`.github/PULL_REQUEST_TEMPLATE.md`): Comprehensive PR checklist

### Automation Config
- **Labeler** (`.github/labeler.yml`): Automatic labeling rules
- **Auto-assign** (`.github/auto-assign.yml`): Reviewer assignment rules

## 🎯 Key Improvements

### Security Enhancements
1. **Multi-layer security scanning**
2. **Dependency vulnerability monitoring**
3. **Supply chain security validation**
4. **License compliance checking**

### Quality Assurance
1. **Cross-platform testing**
2. **Multiple Node.js version support**
3. **Comprehensive linting and formatting**
4. **Package export validation**

### Developer Experience
1. **Structured issue and PR templates**
2. **Automatic labeling and assignment**
3. **Clear workflow status indicators**
4. **Comprehensive documentation**

### Release Management
1. **Automated version management with Changesets**
2. **Provenance attestation for security**
3. **Flexible release options (auto and manual)**
4. **GitHub releases with changelogs**

## 🚨 Required Secrets

Add these secrets to your GitHub repository:

### Required
- `NPM_TOKEN`: NPM authentication token for publishing
- `GITHUB_TOKEN`: Automatically provided by GitHub

### Optional
- `SLACK_WEBHOOK_URL`: For Slack notifications on releases

## 🎮 Usage

### For Contributors
1. **Creating Issues**: Use the provided templates for consistent reporting
2. **Submitting PRs**: Follow the PR template checklist
3. **Reviewing**: PRs are automatically labeled and assigned

### For Maintainers
1. **Releases**: Merge to main triggers automatic releases (if changesets present)
2. **Manual Releases**: Use the manual release workflow for custom versions
3. **Security**: Monitor security workflow results regularly

### For CI/CD
1. **All checks**: Must pass before merge
2. **Cross-platform**: Tested on multiple OS and Node.js versions
3. **Security**: Continuous monitoring and alerts

## 🔍 Monitoring

### Workflow Status
- Check the Actions tab for workflow status
- Failed workflows block releases automatically
- Security alerts appear in the Security tab

### Dependencies
- Weekly automated updates
- Vulnerability scanning on every change
- License compliance monitoring

### Releases
- Automatic GitHub releases
- NPM package publishing
- Slack notifications (if configured)

This enhanced CI/CD setup provides comprehensive automation, security, and quality assurance for the `@thewlabs/ts-reset` project.
