# pre-commit-devops

A `.pre-commit-config.yaml` template that bundles the checks I want on every infra repo: Terraform fmt/validate/tfsec, YAML lint, Dockerfile lint (hadolint), and secret scanning (gitleaks) — so mistakes get caught before the PR, not in CI five minutes later.

## Usage

Copy `.pre-commit-config.yaml` into a repo, then:

```bash
pip install pre-commit
pre-commit install
pre-commit run --all-files
```

Hooks that don't apply to a given repo (e.g. `hadolint-docker` in a repo with no Dockerfile) simply find nothing to run against and pass.
