# Contributing to GENESIS

Thank you for your interest in contributing to GENESIS!

This guide explains our contribution workflow, conventions, and review process.

---

## Before You Start

### Understanding Our Workflow

We use a **fork-first workflow**. This means:
- You work on your own copy (fork) of the repository
- Changes are proposed via Pull Requests from your fork
- This keeps the main repository clean and secure

---

## Fork-First Workflow

### Step 1: Fork the Repository

1. Click the "Fork" button on the repository page
2. This creates your personal copy at `github.com/YOUR-USERNAME/genesis`

### Step 2: Clone Your Fork

```bash
git clone https://github.com/YOUR-USERNAME/genesis.git
cd genesis

git remote add upstream https://github.com/The-OASIS-Project/genesis.git
```

### Step 3: Create a Feature Branch

**Never work directly on `main`**. Always create a branch.

**First, verify the correct issue number:**

```bash
# List open issues to find the right issue number
gh issue list --repo malcolmhoward/genesis
```

**Then create your branch with that issue number:**

```bash
git checkout -b feat/genesis/<issue#>-description

# Example: Working on issue #2
git checkout -b feat/genesis/2-foundation-files
```

---

## Branch Naming Conventions

| Type | Purpose | Example |
|------|---------|---------|
| `feat/` | New feature | `feat/thermal-camera-support` |
| `fix/` | Bug fix | `fix/gpio-cleanup` |
| `docs/` | Documentation only | `docs/rtsp-examples` |
| `refactor/` | Code restructuring | `refactor/camera-abstraction` |
| `chore/` | Maintenance tasks | `chore/update-dependencies` |

---

## Conventional Commits

We follow [Conventional Commits](https://www.conventionalcommits.org/) for clear, consistent history.

### Format

```
type(scope): description

[optional body]

[optional footer]
```

### Examples

```bash
git commit -m "feat(rtsp): add ZED camera support"
git commit -m "fix(vision): handle API timeout gracefully"
git commit -m "docs(readme): add installation troubleshooting"
```

---

## Coding Standards

### Python Guidelines

- Python 3.7+ compatible
- Use type hints where practical
- Follow PEP 8 style guidelines
- Document functions with docstrings
- Keep scripts self-contained where possible

### Hardware Considerations

- **Test on target hardware** - Pi scripts need Pi, Jetson scripts need Jetson
- **Document hardware requirements** - Specify Pi model, Jetson variant, etc.
- **Handle missing hardware gracefully** - Provide mock modes where practical

### Security

- **Never hardcode credentials** - Use environment variables or config files
- **Keep API keys out of logs** - Redact sensitive information
- **Document credential handling** - Explain where keys should be stored

---

## Pull Request Process

### Before Submitting

- [ ] Code runs without errors on target hardware
- [ ] No credentials or API keys in code
- [ ] Branch is up-to-date with main
- [ ] Commit messages follow conventions
- [ ] README updated if adding new component

### PR Description Template

```markdown
## Summary
Brief description of changes.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation
- [ ] Refactoring

## Hardware Tested
- [ ] Raspberry Pi (specify model)
- [ ] NVIDIA Jetson (specify model)
- [ ] Desktop/laptop (no hardware required)

## Checklist
- [ ] Runs without errors
- [ ] No hardcoded credentials
- [ ] Documentation updated
- [ ] No breaking changes (or documented)
```

---

## Adding New Components

When adding a new utility:

1. Create a new directory or script file
2. Include a README.md with:
   - Purpose and features
   - Hardware requirements
   - Installation steps
   - Usage examples
3. Update the main README.md to list the component
4. Add any new dependencies to documentation

---

## Code of Conduct

We are committed to providing a welcoming and inclusive environment.
Please be respectful and constructive in all interactions.

---

## Getting Help

- **Questions**: Open a GitHub Discussion or Issue
- **Bugs**: Open an issue with the bug report template
- **Features**: Open an issue with the feature request template
- **O.A.S.I.S. Ecosystem**: See [S.C.O.P.E.](https://github.com/malcolmhoward/the-oasis-project-meta-repo) for cross-project coordination
