# Dataset Management

## Principles

- datasets must be traceable to their source
- annotation versions must be documented
- derived datasets must be reproducible from raw data whenever possible

## Minimum dataset documentation

- acquisition source
- ownership and usage restrictions
- date of acquisition
- preprocessing steps
- annotation protocol
- train/validation/test split rationale

## Recommended files

```text
data/
├── raw/
├── processed/
├── annotations/
└── dataset_card.md
```

## Dataset card should include

- task definition
- class definitions
- known limitations
- imbalance issues
- labeling quality notes

