# DSE-230

---

# Introduction

Project in postgres for the DSE 230 course

Data description
smartphone and smartwatch sensor data for common household tasks. can be used for activity classification


## Local Enviroment Setup with Docker
___

To setup app local enviroment install [docker](https://docs.docker.com/get-docker/)
and run the following command on the root directory of the project, this will create
containers for mysql and phpmyadmin:

---

MAC

```bash
sh launch.sh
```

Windows

```bash
. launch.ps1
```

## Running the Project
___

In order to run the project there a specific order that is required for everything
to work locally


### Required First

The fisrt notebook to run is `z1_parquet_gen.ipynb`

This notebook will convert all from out notebook into parquet file


### Required Second

The fisrt notebook to run is `z2_data_merging.ipynb`

This notebook will create 2 csv files that will be used by the other notebooks
from this point on, there is no more requirements, any notebooj can be run in
any order. Also being in the docker enviroment in not strictly necessary since dask
will no longer be used in the project.

### Decision trees simple modeling results

The notebook to run is `z3_decision_trees.ipynb`

