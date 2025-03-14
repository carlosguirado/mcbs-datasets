# Contributing to MCBS Datasets

Thank you for your interest in contributing to the MCBS Datasets repository! This document provides guidelines for adding new datasets.

## Adding a New Dataset

1. **Prepare your dataset**:
   - Clean and format your data
   - Use a standard format (CSV is preferred)
   - Compress the file using gzip to reduce size (`.csv.gz`)

2. **Add your dataset**:
   - Create a new subdirectory in the `datasets` directory with the name of your dataset
   - Add your compressed dataset file(s) to this subdirectory
   - Follow the naming pattern: `datasets/your_dataset_name/your_dataset_name.csv.gz`

3. **Submit a pull request**:
   - Fork this repository
   - Add your dataset and commit changes
   - Submit a pull request with a description of your dataset

## Dataset Metadata

When adding a new dataset, you'll need to provide metadata that will be used by the MCBS package. The metadata should be updated in the main MCBS package repository, in the `metadata.json` file.

Here's the format to use:

```json
"your_dataset_name_dataset": {
  "filename": "your_dataset_name/your_dataset_name.csv.gz",
  "description": "Brief description of your dataset",
  "target": "target_column_name",
  "features": ["feature1", "feature2", "feature3", ...],
  "n_samples": number_of_samples,
  "n_features": number_of_features,
  "task": "prediction"
}
```

## Dataset Guidelines

- Datasets should be relevant to transportation mode choice modeling
- Personal identifiers should be removed or anonymized
- Include a reference to the original source if applicable
- Document any preprocessing or modifications made to the original data

Thank you for contributing to MCBS Datasets!