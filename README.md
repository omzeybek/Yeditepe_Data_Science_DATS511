# DATS 511 — Applied Statistics and Data Analysis

Course notebooks for Fall 2026.

## Week 2: Exploratory Data Analysis and Data Preprocessing

[Open Week2_EDA.ipynb in Google Colab](https://colab.research.google.com/github/omzeybek/Yeditepe_Data_Science_DATS511/blob/main/Week2_EDA.ipynb)

The notebook is an in-class exercise using 554 fictional individuals localized for Türkiye. It creates the dataset directly in Python and keeps the raw data, cleaned data, and reports in memory. It includes raw summaries, frequency tables, annotated boxplots, histograms, grouped comparisons, stem-and-leaf output, mirrored population-style charts, a wage/wealth scatterplot, missingness and variation checks, targeted imputation, contextual outlier handling, and a wealth transformation discussion.

Every notebook cell contains at most eight lines except the explicitly marked dataset-generation cell. Analysis steps are split into short, explained operations, including separate stages for selecting data, calculating summaries, building plots, and checking results.

### Run in Colab

1. Open the notebook using the link above and run cells from top to bottom.
2. Run the data-preparation cell, then call the generator to create `df`.
3. Follow the short analysis cells. The original data remain in `df_raw`, and preprocessing creates `df_clean`.

No Drive mounting, CSV upload, or file loading is needed. The notebook does not automatically write files.

### Run locally

Use Python 3.12, install the tested packages with `python -m pip install -r requirements.txt`, and launch `jupyter lab`. Open `Week2_EDA.ipynb` and run all cells. The notebook works from any working directory because it generates its own data.

### Dataset design

All names, identifiers, and measurements are synthetic. `person_id` values such as `SYN0001` are classroom identifiers. This is neither a population estimate nor current official economic data.

The brief's literal percentages are retained: approximately **0.05% missing fields** (5 of 9,418 cells) and **0.02% deliberately injected numeric outliers** (1 of 4,432 numeric cells). Missingness is placed in the five fields used for imputation demonstrations. One record has the impossible value of **1,000 education years**; the cleaned dataset excludes that record, while retaining a legitimate doctoral example with 25 education years. Naturally generated observations outside IQR fences are reported separately and are not automatically discarded.

The generator uses seed `5112026`. Wealth has a dispersed, positive distribution suitable for comparing raw values with a log transformation. Wages are monthly TRY, wealth is TRY, home area is m², height is cm, and weight is kg. YKS scores are fictional values on a 150–500 scale, not historical results for the individuals.

| File | Purpose |
|---|---|
| `Week2_EDA.ipynb` | Runnable lesson and embedded dataset generator |
| `data/week2_personal_data.csv` | Optional reference snapshot; the notebook does not read it |
| `data/week2_dataset_metadata.json` | Reference units, seed, missingness, and injection provenance |
| `requirements.txt` | Package versions used for local validation |

The notebook's full execution is validated in a fresh Python kernel from an empty working directory, together with the eight-line cell limit.
