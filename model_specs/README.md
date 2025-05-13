# MCBS Model Specifications

This directory contains model specifications for the Mode Choice Benchmarking Sandbox (MCBS).

## Overview

Model specifications are JSON files that describe discrete choice models in a structured format. These specifications can be used to dynamically create model classes in MCBS without requiring package updates.

## File Structure

- `metadata.json`: Contains metadata about all available model specifications
- `*.json`: Individual model specification files (e.g., `mnl_swissmetro.json`)

## Model Specification Format

Each model specification is a JSON file with the following structure:

```json
{
  "name": "model_name",
  "description": "Model description",
  "model_type": "mnl|nl|mixed",
  "compatible_datasets": ["dataset1", "dataset2"],
  "base_class": "BaseModelClass",
  "parameters": [
    {"name": "PARAM1", "default": 0, "fixed": false},
    {"name": "PARAM2", "default": 0, "fixed": true, "value": 1}
  ],
  "utility_functions": {
    "1": "expression for alternative 1",
    "2": "expression for alternative 2"
  },
  "availability": {
    "1": "availability condition for alt 1",
    "2": "availability condition for alt 2"
  },
  "custom_methods": {
    "method_name": "method code"
  }
}
```

## Adding New Specifications

To add a new model specification:

1. Create a JSON file following the format above
2. Place it in this directory
3. Update metadata.json to include information about the new specification

## Usage in MCBS

```python
from mcbs.datasets import fetch_data
from mcbs.models import create_model_from_spec

# Fetch a dataset
data = fetch_data("swissmetro_dataset")

# Create a model from specification
model = create_model_from_spec("mnl_swissmetro", data)

# Estimate the model
results = model.estimate()

# Get metrics
metrics = model.get_metrics()
```

For more information, see the MCBS documentation and MODEL_FETCHING.md in the main repository.