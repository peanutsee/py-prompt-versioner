# 🤝 Contributing to py-prompt-versioner

First off, thank you for considering contributing! It's people like you who make the AI engineering ecosystem better.

---

## 🛠 Development Setup

This project uses `uv` for dependency management. To set up your local environment:

1. **Fork and Clone** the repository.
2. **Install dependencies:**
```bash
uv sync
```
3. **Activate the virtual environment:**
```bash
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

---

## 🌿 Branching Strategy

We follow a structured naming convention for all branches. Please use the following prefixes:

| Category       | Branch Prefix | Example                        |
| -------------- | ------------- | ------------------------------ |
| New Features   | `feature/`    | `feature/jinja-filter-support` |
| Bug Fixes      | `fix/`        | `fix/yaml-parsing-error`       |
| Documentation  | `docs/`       | `docs/update-readme-badges`    |
| Refactoring    | `refactor/`   | `refactor/pydantic-v2-models`  |
| Chores/Tools   | `chore/`      | `chore/add-github-actions`     |

---

## ✅ Quality Standards

To keep the codebase clean, please ensure:

- **Linting:** Run `ruff check .` to ensure your code follows our style guide.
- **Formatting:** Run `ruff format .` before committing.
- **Typing:** Ensure all new functions have type hints and pass `mypy .`.
- **Testing:** Add tests for new features and run `pytest` to ensure no regressions.

---

## 🚀 Pull Request Process

1. Create a new branch from `main`.
2. Make your changes and commit using [Conventional Commits](https://www.conventionalcommits.org/).
3. Push your branch and open a Pull Request (PR).
4. Ensure all CI checks pass.
5. A maintainer will review your PR and provide feedback.
