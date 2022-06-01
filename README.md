# DSE-230

---

# Introduction

Project for UCSD DSE 230 - Scalable Data Analysis

Data description: smartphone and smartwatch sensor data for common household tasks. Can be used for classification of physical activity.


Contributors:
- [Alejandro Hohmann](https://github.com/gojandrooo)
- [Garrett Michael](https://github.com/garrett391/)
- [Leo Clo](https://github.com/leoclo)

## Local Enviroment Setup with Docker
___

To setup app local enviroment install [docker](https://docs.docker.com/get-docker/)

---

MAC

```bash
sh launch.sh
```

Windows

```bash
.\launch.ps1
```

## Running the Project
___

Run the notebook files in the following order:
- `dse230_01_parquet_generation.ipynb`
- `dse230_02_data_merging.ipynb`
- `dse230-03_eda.ipynb`
- `dse230_04_decision_tree_classification.ipynb`

In order to run the project there is a specific order that is required for everything
to work locally.


### Data Generation

The first notebook to run is `dse230_01_parquet_generation.ipynb`. It must be run in within docker container.

Given the size of the dataset (16M+ records), explicitly managing memory is necessary to run the workflow. This notebook will convert all the raw data files into lighter parquet files with the smallest data types possible without losing precision of the data. This may take a few minutes. Do not run the subsequent files until this is complete.


### Grouping and Merging Data

The second notebook to run is `dse230_02_data_merging.ipynb`. It must be run within docker container.

This notebook will create two `csv` files of the prepared data that will be used by the next two notebooks. The raw data is changed from one record every millisecond to three second aggregations.

### Exploratory Data Analysis

The third notebook to run is `dse230_03_eda.ipynb`. This file does not use `dask` therefore `docker` is not strictly necessary but still recommended.

It includes visualizations of the aggregated data.

### Decision trees simple modeling results

The fourth notebook to run is `dse230_04_decision_tree_classification.ipynb`. This file does not use `dask` therefore `docker` is not strictly necessary but still recommended.

During our exploration, we ran multiple types of classification models and selected the model that returned the best performance (`Decision Tree Classifier`). For the sake of brevity, only the best model is retained. However, if you wish to check performance of alternate models, uncomment the import statements and switch out the model.
