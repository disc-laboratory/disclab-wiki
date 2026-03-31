# Reproducibility and Reporting

## General principle

Research outputs must be **traceable, reproducible, and well-documented**.

A reader (or lab member) should be able to understand how results were obtained and, where possible, reproduce them.

## Key expectations

- experiments must be documented;
- datasets must be clearly described;
- results must be linked to specific configurations and methods.

## What should be reported

### Data

- dataset source and description;
- preprocessing steps;
- dataset splits (train/validation/test).

### Methods

- model architecture or methodology;
- key parameters and configurations;
- training or processing procedures.

### Experiments

- experiment setup;
- variations between experiments;
- evaluation metrics used.

### Results

- quantitative results (with clear metrics);
- qualitative results when relevant;
- comparison with baselines.

## Traceability

Each result should be traceable to:

- a dataset version;
- a code version;
- a configuration file;
- an experiment record.

## Link with lab structure

- experiments → `04_Experiments/`
- models → `03_Models/`
- results → `05_Results/`

All reported results should correspond to stored and documented artifacts.

## Common issues

- missing details about data or preprocessing;
- unclear experimental setup;
- results that cannot be linked to a specific experiment;
- inconsistent reporting across sections.

## Final note

Reproducibility is not optional. It is a core aspect of scientific quality.