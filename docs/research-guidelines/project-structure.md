# Project Structure

Each research project should have a predictable structure.

## Recommended top-level layout

```text
project-name/
├── README.md
├── docs/
├── data/
│   ├── raw/
│   ├── interim/
│   ├── processed/
│   └── external/
├── src/
├── configs/
├── experiments/
├── models/
├── results/
├── notebooks/
├── reports/
└── references/
```

## Rules

- `raw/` data must remain immutable.
- `src/` contains reusable code, not one-off scripts.
- `configs/` stores all experiment settings.
- `experiments/` contains logs and run-level metadata.
- `results/` stores generated outputs and figures.
- `reports/` stores project memos, internal summaries, and deliverables.

## Minimum required files

- `README.md`
- one environment file (`requirements.txt`, `environment.yml`, or similar)
- one configuration example
- one usage example

