# Versioning

## Code versioning

All active code should be kept under Git.

## Data versioning

Use one of the following depending on project scale:

- folder-based versioning for small projects
- release snapshots for milestone datasets
- DVC for large datasets and ML pipelines

## Minimum versioning requirements

- each paper result must trace to a code commit
- each trained model must trace to a data version and config
- renamed files should not erase provenance

