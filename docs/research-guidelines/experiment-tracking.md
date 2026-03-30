# Experiment Tracking

Every experiment must be recoverable.

## Minimum information to record

- project name
- experiment ID
- date and owner
- code commit hash
- dataset version
- configuration file
- hardware used
- training duration
- output checkpoint path
- main metrics
- short conclusion

## Recommended experiment ID format

```text
EXP-YYYYMMDD-short-description-v01
```

## Acceptable tools

- Markdown logs in the repository
- CSV experiment table
- Weights & Biases or MLflow
- structured YAML or JSON summaries

