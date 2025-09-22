# Codex

A clean, batteries-included repository template for your next project.

## What's inside

- **Docs-first** project structure (`/docs`) with quickstart & architecture notes
- Standard **open-source** files: MIT License, Code of Conduct, Contributing, Security
- **GitHub templates** for Issues & PRs
- Sensible defaults: `.gitignore`, `.editorconfig`, `.gitattributes`
- Minimal, language-agnostic **CI** that auto-detects common stacks (Node, Python, .NET)
- Ready-to-expand `/src` and `/tests`

> Rename "Codex" to your project name and update badges as you go.

## Quick start

```bash
# 1) Create a new repo on GitHub named codex (or your project name)
# 2) Unzip this folder and push it
git init
git add .
git commit -m "chore: bootstrap Codex repository"
git branch -M main
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
```

## Local development

- Put your code in `src/` and tests in `tests/`.
- If you're using **Node**:
  ```bash
  npm init -y
  npm install --save-dev typescript vitest
  npx tsc --init
  npm test
  ```
- If you're using **Python**:
  ```bash
  python -m venv .venv && source .venv/bin/activate
  pip install -U pip pytest
  pytest
  ```
- If you're using **.NET (C#)**:
  ```bash
  dotnet new gitignore # optional, this repo already provides a global one
  dotnet new sln -n Codex
  dotnet new classlib -o src/Codex
  dotnet sln add src/Codex/Codex.csproj
  dotnet new xunit -o tests/Codex.Tests
  dotnet sln add tests/Codex.Tests/Codex.Tests.csproj
  dotnet test
  ```

## Repository layout

```
codex/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── architecture.md
│   └── getting-started.md
├── src/            # your application/library code
├── tests/          # your tests
├── .editorconfig
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
└── README.md
```

## CI overview

The default CI workflow tries to detect common stacks and run basic checks:
- If `package.json` exists: run `npm ci` then `npm test`
- If `pyproject.toml` or `requirements.txt` exists: setup Python and run `pytest` (if present)
- If a `.sln` or `*.csproj` exists: run `dotnet restore` + `dotnet test` (if tests are present)

If none of these files are present, CI will simply validate the repository structure.

## Releasing

- Keep a human-readable **CHANGELOG.md**.
- Use semantic versioning (MAJOR.MINOR.PATCH).
- Tag releases in Git (`git tag v1.0.0 && git push --tags`).

## Licensing

This template is MIT licensed. Replace the copyright with your details if needed.
