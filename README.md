# DATS 511 — Applied Statistics and Data Analysis

Course notebooks for Fall 2026.

## Week 2: Exploratory Data Analysis and Data Preprocessing

[Open Week2_EDA.ipynb in Google Colab](https://colab.research.google.com/github/omzeybek/Yeditepe_Data_Science_DATS511/blob/main/Week2_EDA.ipynb)

The notebook is an in-class exercise using 554 fictional individuals localized for Türkiye. It includes raw summaries, frequency tables, annotated boxplots, histograms, grouped comparisons, stem-and-leaf output, mirrored population-style charts, a wage/wealth scatterplot, missingness and variation checks, targeted imputation, contextual outlier handling, and a wealth transformation discussion.

### Run in Colab

1. Open the notebook using the link above and run cells from top to bottom.
2. Authorize your own Google Drive when the mounting cell prompts you.
3. The notebook creates `MyDrive/DATS511/Week2/week2_personal_data.csv` from its fixed-seed generator if the file is absent. You can instead put the supplied CSV in that folder before running it. Existing data files are preserved.
4. Cleaned data and quality reports are exported to the separate `outputs/` folder in that Drive directory.

Opening the notebook does not itself upload anything to Drive; the mounting and dataset-writing cell does so when you run it with your Google session.

### Run locally

Use Python 3.12, install the tested packages with `python -m pip install -r requirements.txt`, and launch `jupyter lab` from the repository root. Open `Week2_EDA.ipynb` and run all cells. It loads the included CSV from `data/` and writes analysis exports to `outputs/`.

The optional `DATS511_DATA_PATH` and `DATS511_OUTPUT_DIR` environment variables override local input and output paths.

### Dataset design

All names, identifiers, and measurements are synthetic. `person_id` values such as `SYN0001` are classroom identifiers. This is neither a population estimate nor current official economic data.

The brief's literal percentages are retained: approximately **0.05% missing fields** (5 of 9,418 cells) and **0.02% deliberately injected numeric outliers** (1 of 4,432 numeric cells). Missingness is placed in the five fields used for imputation demonstrations. One record has the impossible value of **1,000 education years**; the cleaned dataset excludes that record, while retaining a legitimate doctoral example with 25 education years. Naturally generated observations outside IQR fences are reported separately and are not automatically discarded.

The generator uses seed `5112026`. Wealth has a dispersed, positive distribution suitable for comparing raw values with a log transformation. Wages are monthly TRY, wealth is TRY, home area is m², height is cm, and weight is kg. YKS scores are fictional values on a 150–500 scale, not historical results for the individuals.

| File | Purpose |
|---|---|
| `Week2_EDA.ipynb` | Runnable lesson and embedded dataset generator |
| `data/week2_personal_data.csv` | Raw 554 × 17 teaching dataset |
| `data/week2_dataset_metadata.json` | Units, seed, missingness, and injection provenance |
| `requirements.txt` | Package versions used for local validation |

The notebook's full execution is validated in a fresh Python kernel. Colab's interactive Drive authorization must be completed in your own Google session.
