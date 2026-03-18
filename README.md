# 📝 py-prompt-versioner

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python: 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Built with: uv](https://img.shields.io/badge/built%20with-uv-60a5fa.svg)](https://github.com/astral-sh/uv)

**Stop copy-pasting 500-line f-strings.** `py-prompt-versioner` is a lightweight utility designed for AI engineers who want to treat their prompts like code. Store prompts in Markdown, version them properly, and inject variables with ease.

---

## ✨ Features

- **Frontmatter Metadata:** Store model settings (temperature, model name) directly within the prompt file.
- **Jinja2 Templating:** Support for complex variable injection, loops, and logic.
- **Strict Validation:** Powered by **Pydantic** to ensure your metadata is always correct.
- **CLI First:** Bootstrap your prompt directory structure in one command.
- **Path-Agnostic:** Works seamlessly across Windows, Mac, and Linux.

---

## 🚀 Installation

Install via pip:

```bash
pip install py-prompt-versioner
```

or using **uv** for lightning-fast-setup:

```bash
uv add py-prompt-versioner
```

---

## 🛠 Quick Start

1. Initialize your project
   Use the CLI to create your prompt directory structure.

```bash
# Creates a default /prompts folder
prompt-versioner init

# Or specify a custom path
prompt-versioner init --path ./my_ai_assets
```

2. Create a prompt file
   Your prompts live in .md files with YAML frontmatter.
   Example: prompts/sample_task/v1.md

```
---
version: "v1"
model: "gpt-4o"
temperature: 0.7
---

Act as a professional editor. Summarize the following text: {{ text }}
```

---

## 📖 Usage Guide

Integrate **py-prompt-versioner** into your Python workflow to load and render prompts dynamically.

```python
from prompt_versioner import PromptManager

# 1. Initialize the manager with your prompts directory
pm = PromptManager(path="./prompts")

# 2. Load and render a specific version with variables
result = pm.get_prompt(
    task_name="sample_task",
    version="v1",
    variables={"text": "The quick brown fox jumps over the lazy dog."}
)

# 3. Use the result
print(f"Using model: {result['metadata'].model}")
print(f"Prompt: {result['content']}")
```

---

## 📂 Project Structure

A typical setup using py-prompt-versioner looks like this:

```
.
├── prompts/
│   ├── classification/
│   │   ├── v1.md
│   │   └── v2.md
│   └── summarization/
│       └── base.md
├── main.py
└── pyproject.toml
```

---

## ⚙️ How it Works

| Component   | Responsibility                              |
| ----------- | ------------------------------------------- |
| CLI         | Scaffolding and directory management        |
| Frontmatter | Parsing metadata (YAML) from Markdown files |
| Pydantic    | Validating metadata structure and types     |
| Jinja2      | Handling variable injection and logic       |

---

## 🤝 Contributing

Contributions are welcome! If you have a feature request or found a bug, please open an issue or submit a pull request on GitHub.

1. Fork the repo.
2. Clone it locally.
3. Submit a PR with your changes. Pssss, don't forget to **ruff** your codes!

---

## 🛠 Recommended Naming Convention

| Category       | Branch Prefix       | Example                        |
| -------------- | ------------------- | ------------------------------ |
| New Features   | `feature/`          | `feature/jinja-filter-support` |
| Bug Fixes      | `fix/` or `bugfix/` | `fix/yaml-parsing-error`       |
| Documentation  | `docs/`             | `docs/update-readme-badges`    |
| Refactoring    | `refactor/`         | `refactor/pydantic-v2-models`  |
| Performance    | `perf/`             | `perf/optimize-glob-search`    |
| Chores / Tools | `chore/`            | `chore/add-github-actions`     |

---

## 📄 License

Distributed under the MIT License. See LICENSE for more information.# py-prompt-versioner
