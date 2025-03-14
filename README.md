# MCBS Datasets

This repository contains datasets for the Mode Choice Benchmarking Sandbox (MCBS) package.

## Structure

The repository is organized as follows:

```
datasets/
├── swissmetro/
│   └── swissmetro.csv.gz      # Swiss mode choice dataset
├── modecanada/
│   └── modecanada.csv.gz      # Canadian intercity mode choice dataset
└── ltds/
    └── ltds.csv.gz            # London Travel Demand Survey dataset
```

## Dataset Descriptions

### Swissmetro

This dataset contains stated preference data collected for the analysis of a high-speed train alternative in Switzerland. The choices are between car, regular train, and the Swissmetro.

### ModeCanada

This dataset contains intercity travel choices between Canadian cities. The modes include car, bus, train, and air travel. It includes variables for travel time, travel cost, and traveler characteristics.

### LTDS (London Travel Demand Survey)

This dataset comes from the London Travel Demand Survey and includes urban travel choices within London. It contains variables related to trip characteristics, demographics, and available transportation options.

## Adding a New Dataset

To add a new dataset to this repository:

1. Create a new subdirectory in the `datasets` directory with the name of your dataset
2. Add your dataset file(s) to this subdirectory (preferably as .csv.gz for consistency)
3. Update the `metadata.json` file in the main MCBS package to include information about your dataset

## Usage

These datasets are automatically downloaded by the MCBS package when needed. Users can access them using:

```python
from mcbs.datasets import fetch_data

# Download and load a dataset
data = fetch_data("swissmetro_dataset")
```

## License

These datasets are provided for research and educational purposes only. Please refer to the original sources for specific usage restrictions.