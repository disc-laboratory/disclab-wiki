# Coding Standards

## General principles

- Code must be readable before it is clever.
- Prefer modular functions over long scripts.
- Every reusable project should include a clear entry point.

## Python standards

- follow PEP 8 where reasonable
- use descriptive variable and function names
- include docstrings for non-trivial functions
- avoid hard-coded file paths
- store configurable values in config files

## Recommended tooling

- formatter: `black`
- linter: `ruff`
- type hints when useful
- environment management with `venv`, `conda`, or `poetry`

## ML-specific guidance

- separate training, evaluation, and inference code
- record random seeds
- save configuration used for each run
- never overwrite model checkpoints silently

