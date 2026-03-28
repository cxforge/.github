# Contributing to CXForge Solutions

Thank you for your interest in contributing to CXForge Solutions! We're building tools that prioritize creative experiences, and we'd love your help.

---

## Getting Started

### Prerequisites
- See individual project READMEs for specific requirements
- Docker (for containerized development)
- Git

### Development Setup
1. Fork the repository you want to contribute to
2. Clone your fork: `git clone https://github.com/YOUR_USERNAME/REPO_NAME.git`
3. Create a branch: `git checkout -b feature/your-feature-name`
4. Follow the project-specific setup in its README

---

## Development Workflow

### Branch Naming
- `feature/description` — New features
- `bugfix/description` — Bug fixes
- `docs/description` — Documentation updates
- `refactor/description` — Code refactoring

### Commit Messages
We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add user authentication
fix: resolve data sync issue
docs: update API documentation
refactor: simplify configuration handling
test: add endpoint tests
```

### Code Style
- Follow each project's specific linting and formatting configuration
- Use language-specific best practices (see project READMEs)

---

## Submitting Changes

### Pull Request Process
1. Ensure your code follows our style guidelines
2. Add/update tests for new functionality
3. Update documentation as needed
4. Fill out the PR template completely
5. Request review from maintainers
6. Address feedback promptly

### PR Template
All PRs should include:
- **Description:** What changed and why
- **Type of Change:** Bug fix, feature, docs, etc.
- **Testing:** How you tested the changes
- **Checklist:** All items completed
- **Screenshots:** If UI changes

---

## Development Guidelines

### Security
- Never commit secrets, API keys, or credentials
- Use environment variables for configuration
- Follow the [AGENTS.md](./AGENTS.md) guidelines for AI assistants

### Infrastructure
- All services must include health checks
- Changes should work in both staging and production
- Document any new environment variables

### Documentation
- Update README.md if adding new features
- Add inline comments for complex logic
- Update CHANGELOG.md for user-facing changes

---

## Questions?

- **General:** Open an issue with the `question` label
- **Security:** See [SECURITY.md](./SECURITY.md)
- **Brand:** See [brand/README.md](./brand/README.md)

---

## Code of Conduct

### Our Standards
- Be respectful and inclusive
- Welcome newcomers and help them learn
- Focus on constructive feedback
- Respect different viewpoints and experiences

### Unacceptable Behavior
- Harassment or discrimination of any kind
- Trolling, insulting/derogatory comments
- Public or private harassment
- Publishing others' private information

### Enforcement
Violations may result in temporary or permanent ban from project spaces.

---

Thank you for helping us forge creative experiences! 🚀
