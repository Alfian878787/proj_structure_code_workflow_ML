# proj_structure_code_workflow_ML
How to structure python code some some generic ML project. The idea is to have a generic template with an automatic workflow.


# Structure

```

├── LICENSE
│
├── Makefile                 <- Makefile with commands like `make data` or `make train`
│
├── README.md                <- The top-level README for developers using this project
│
├── environment.yml           <- The requirements file for reproducing the analysis environment, e.g.
│                                generated with `pip freeze > requirements.txt`
├── config-private.yml        <- config file in YAML, can be exported as env vars if need
│
├── data
│   ├── external             <- Data from third party sources.
│   ├── intermediate         <- Intermediate data that has been transformed.
│   ├── processed            <- The final, canonical data sets for modeling.
│   └── raw                  <- The original, immutable data dump.
│
├── results
│   ├── outputs
│   └── models               <- Trained and serialized models, model predictions, or model summaries
│
├── documents
│   ├── docs
│   ├── images
│   └── references           <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports                   <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures               <- Generated graphics and figures to be used in reporting
│
├── notebooks                <- Jupyter notebooks. Naming convention is a number (for ordering),
│                               the creator's initials, and a short `-` delimited description, e.g.
│                               `1.0-jqp-initial-data-exploration`.d
│
├── src                       <- Source code for use in this project.
│   ├── __init__.py           <- Makes src a Python module
│   │
│   ├── data                  <- Scripts to download or generate data
│   │   └── make_dataset.py
│   │
│   ├── features              <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   │
│   ├── models                <- Scripts to train models and then use trained models to make
│   │   │                        predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   │
│   └── visualization          <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py

```

# Instruction
## create a python env based on a list of packages from environment.yml
```conda env create -f environment.yml -n env_ds```

## update a python env based on a list of packages from environment.yml
```conda env update -f environment.yml -n env_ds```

## download the data manually
python src/data/download.py "https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data" data/raw/iris.csv


# References
https://towardsdatascience.com/structure-and-automated-workflow-for-a-machine-learning-project-2fa30d661c1e

https://towardsdatascience.com/structure-and-automated-workflow-for-a-machine-learning-project-part-2-b5b420625102  

https://github.com/artofai/overcome-the-chaos

https://github.com/ThomasRobertFr/ml-project-structure

# Makefile documentation

There are seven “core” automatic variables:

    $@: The filename representing the target.

    $%: The filename element of an archive member specification.

    $<: The filename of the first prerequisite.

    $?: The names of all prerequisites that are newer than the target, separated by spaces.

    $^: The filenames of all the prerequisites, separated by spaces. This list has duplicate filenames removed since for most uses, such as compiling, copying, etc., duplicates are not wanted.

    $+: Similar to $^, this is the names of all the prerequisites separated by spaces, except that $+ includes duplicates. This variable was created for specific situations such as arguments to linkers where duplicate values have meaning.

    $*: The stem of the target filename. A stem is typically a filename without its suffix. Its use outside of pattern rules is discouraged.

https://stackoverflow.com/questions/3220277/what-do-the-makefile-symbols-and-mean

