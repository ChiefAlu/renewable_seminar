# Seminar: Machine Learning for Renewable Energy Systems
---

This repository contains a first draft of the code to predict the energy consumption for buildings based on the [The Building Data Genome 2 (BDG2) Data-Set](https://github.com/buds-lab/building-data-genome-project-2).
A probabilistic approach (based on this [tutorial](https://huggingface.co/blog/time-series-transformers)) with transformer was used.

---

Download:
---
- [Repository](https://github.com/buds-lab/building-data-genome-project-2) using Git LFS (I recommend using [GitHub Desktop](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/platform/documentation/how-to-use-git-lfs-with-github-desktop-app.md))
- `git clone https://github.com/ChiefAlu/renewable_seminar.git`

Files:
---
Files that are necessary to run the code:
```
.
+-- building-data-genome-project-2
|    +-- data
|         +-- metadata
|             +-- metadata.csv
|         +-- meters
|             +-- raw
|                 +-- electricity.csv
|         +-- weather
|             +-- weather.csv
+-- renewable_seminar
    +-- data
    +-- sanitize_data.ipynb
    +-- create_small_dataset.ipynb
    +-- transformer.ipynb
```

Installation:
---
```
conda create --name <env-name> python=3.10
conda activate <env-name>
pip install -r renewable_seminar/requirements.txt
```

Run:
---
- First sanitize the data and by running the notebook `sanitize_data.ipynb`.
- Merge the meter data with the weather data. For faster computation and testing cases we use only a small sample of the data that gets created by running `create_small_dataset.ipynb`.
- Finally create the dataloaders, train the transformer, do inference and plot the results with the notebook `transformer.ipynb`.

---

### TODOs
- Improve performance by testing other architectures and hyperparameters.
- Check correlation between features and delete unnecessary features.
- Train with more data.
- Improve visualization.
- Compare results with benchmark.
