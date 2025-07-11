# Contributing to QCS Event Management System

First off, thank you for considering contributing to QCS Event Management System! It's people like you that make this project a great tool for event management professionals.

## 🤝 How to Contribute

### Reporting Bugs

Before creating bug reports, please check the issue list as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

* **Use a clear and descriptive title**
* **Describe the exact steps to reproduce the problem**
* **Provide specific examples to demonstrate the steps**
* **Describe the behavior you observed and what behavior you expected**
* **Include screenshots if possible**
* **Provide your environment details** (OS, Python version, browser, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

* **Use a clear and descriptive title**
* **Provide a step-by-step description of the suggested enhancement**
* **Provide specific examples to demonstrate the steps**
* **Describe the current behavior and explain the behavior you expected**
* **Explain why this enhancement would be useful**

### Pull Requests

1. **Fork the repository**
2. **Create a feature branch** from `develop`:
   ```bash
   git checkout -b feature/your-feature-name develop
   ```
3. **Make your changes**
4. **Add tests** for your changes
5. **Ensure tests pass**
6. **Update documentation** if needed
7. **Commit your changes** using conventional commits:
   ```bash
   git commit -m "feat: add new event completion feature"
   ```
8. **Push to your fork**
9. **Create a Pull Request**

## 🌿 Branching Strategy

We follow **Git Flow** branching strategy:

### Main Branches
- **`main`** - Production-ready code
- **`develop`** - Latest development changes

### Supporting Branches
- **`feature/*`** - New features (branch from `develop`)
- **`release/*`** - Release preparation (branch from `develop`)
- **`hotfix/*`** - Critical fixes (branch from `main`)

### Branch Naming Convention
```
feature/feature-name
bugfix/bug-description
hotfix/critical-fix
release/version-number
```

## 📝 Commit Message Guidelines

We use [Conventional Commits](https://www.conventionalcommits.org/) specification:

### Format
```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types
- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that do not affect code meaning
- **refactor**: Code change that neither fixes a bug nor adds a feature
- **perf**: Performance improvements
- **test**: Adding missing tests
- **chore**: Changes to build process or auxiliary tools

### Examples
```bash
feat(calendar): add one-click event completion
fix(auth): resolve login redirect issue
docs(readme): update installation instructions
style(ui): improve button spacing on dashboard
refactor(api): optimize event query performance
test(calendar): add unit tests for event creation
chore(deps): update Flask to version 2.3.3
```

## 🧪 Development Setup

### Prerequisites
- Python 3.9+
- Git
- Virtual environment tool

### Setup Steps
1. **Clone your fork**
   ```bash
   git clone https://github.com/your-username/qcs-event-management.git
   cd qcs-event-management
   ```

2. **Add upstream remote**
   ```bash
   git remote add upstream https://github.com/original-owner/qcs-event-management.git
   ```

3. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r qcs_enhanced_final/requirements.txt
   pip install -r requirements-dev.txt  # Development dependencies
   ```

5. **Initialize database**
   ```bash
   cd qcs_enhanced_final
   python init_db.py
   ```

6. **Run tests**
   ```bash
   python -m pytest scripts/test.py -v
   ```

## 🎨 Code Style Guidelines

### Python Code Style
- Follow **PEP 8** guidelines
- Use **Black** for code formatting
- Use **flake8** for linting
- Maximum line length: 88 characters (Black default)

### Frontend Code Style
- Use **Prettier** for JavaScript/CSS formatting
- Follow **BEM methodology** for CSS class naming
- Use semantic HTML5 elements
- Ensure accessibility compliance (WCAG 2.1)

### Code Organization
```python
# File structure within modules
# 1. Standard library imports
import os
import sys

# 2. Third-party imports
from flask import Flask, request
import requests

# 3. Local application imports
from helpers import get_db
from blueprints import calendar_bp
```

## 🧪 Testing Guidelines

### Writing Tests
- Write tests for all new features
- Maintain minimum 80% code coverage
- Use descriptive test names
- Follow AAA pattern (Arrange, Act, Assert)

### Test Categories
- **Unit Tests**: Test individual functions/methods
- **Integration Tests**: Test component interactions
- **End-to-End Tests**: Test complete user workflows

### Running Tests
```bash
# Run all tests
python -m pytest scripts/test.py -v

# Run with coverage
python -m pytest scripts/test.py --cov=. --cov-report=html

# Run specific test file
python -m pytest scripts/test.py::TestEventManagement -v
```

## 📚 Documentation

### Code Documentation
- Use docstrings for all functions, classes, and modules
- Follow Google-style docstrings
- Include examples in docstrings when helpful

### API Documentation
- Document all API endpoints
- Include request/response examples
- Specify required parameters and data types

### User Documentation
- Update README.md for user-facing changes
- Add screenshots for UI changes
- Update deployment guides if needed

## 🔒 Security Guidelines

### Security Best Practices
- Never commit sensitive information (passwords, API keys)
- Use environment variables for configuration
- Validate all user inputs
- Follow OWASP security guidelines
- Report security vulnerabilities privately

### Code Review Security Checklist
- [ ] No hardcoded secrets
- [ ] Input validation implemented
- [ ] SQL injection prevention
- [ ] XSS protection in place
- [ ] CSRF tokens used
- [ ] Authentication checks present

## 📋 Pull Request Checklist

Before submitting a pull request, ensure:

- [ ] Code follows style guidelines
- [ ] Tests are written and passing
- [ ] Documentation is updated
- [ ] Commit messages follow conventional format
- [ ] Branch is up-to-date with develop
- [ ] No merge conflicts
- [ ] Screenshots included for UI changes
- [ ] Security considerations addressed

## 🎯 Feature Development Process

### 1. Planning Phase
- Create GitHub issue describing the feature
- Discuss approach with maintainers
- Break down into smaller tasks if needed

### 2. Development Phase
- Create feature branch from `develop`
- Implement feature incrementally
- Write tests as you go
- Update documentation

### 3. Review Phase
- Self-review your code
- Ensure all tests pass
- Create pull request with detailed description
- Address review feedback

### 4. Integration Phase
- Maintainer reviews and approves
- Merge into `develop` branch
- Feature included in next release

## 🏷️ Release Process

### Version Numbering
We follow **Semantic Versioning** (SemVer):
- **MAJOR**: Breaking changes
- **MINOR**: New features (backward compatible)
- **PATCH**: Bug fixes (backward compatible)

### Release Steps
1. Create release branch from `develop`
2. Update version numbers
3. Update CHANGELOG.md
4. Test release candidate
5. Merge to `main` and tag
6. Deploy to production
7. Merge back to `develop`

## 💬 Community

### Communication Channels
- **GitHub Issues**: Bug reports and feature requests
- **GitHub Discussions**: General questions and ideas
- **Pull Requests**: Code contributions

### Code of Conduct
- Be respectful and inclusive
- Focus on constructive feedback
- Help others learn and grow
- Maintain professional communication

## 🙋‍♀️ Getting Help

If you need help:
1. Check existing documentation
2. Search through GitHub issues
3. Create a new issue with detailed description
4. Tag appropriate maintainers if urgent

## 🎉 Recognition

Contributors will be recognized in:
- CHANGELOG.md for their contributions
- README.md contributors section
- GitHub repository insights

Thank you for contributing to QCS Event Management System! 🚀