# FLU DAY PREDICTION - Code Supplement

## Purpose 
This repository contains the analysis notebooks used to train, validate, and visualize machine-learning models for estimating time since influenza infection and viral shedding status from CyTOF immune profiling data.

## Input files
The following input files are required to run the notebooks:
- `WCCT_data.csv` – Study A dataset
- `VXA_data.csv`  – Study B dataset
- `matched_populations.xlsx`    – Mapping of matched immune cell populations between studies
- `Consolidated_A_B_minimal.csv`- Used for pooled analyses
- `univariate_importance_classifier_WCCT.csv` - Used for network plots based on Study A classifier 
- `univariate_importance_classifier_VXA.csv`  - Used for network plots based on Study B classifier 
- `univariate_importance_regressor_WCCT.csv`  - Used for network plots based on Study A regressor 
- `univariate_importance_regressor_VXA.csv`   - Used for network plots based on Study B regressor 

All files should be placed in the root directory of the repository.

Each row corresponds to a single measurement taken by a volunteer for specific tasks on that day; therefore, there are no repeated measurements by the same volunteer within a specific assessment for that day.

Volunteers 101, 109 and 304 were excluded from the shedders category because they were not positive for PCR detection of viral shedding for more than one day, representing a marginal viral shedding. 

## Notebooks
- `Training.ipynb` – Model training and cross-validation on Study A
- `Validation.ipynb` – External validation on independent Study B cohort
- `uMAP_StudyA.ipynb` – UMAP visualization for Study A
- `uMAP_StudyB.ipynb` – UMAP visualization for Study B
- `Network_Plots_Classifier.ipynb` – Network analysis (classifier, Study A and Study B)
- `Network_Plots_Regressor.ipynb`  – Network analysis (regressor, Study A and Study B)
- `Population_Feature_Importance.ipynb` – Cross-study feature importance comparison

## Outputs
Notebooks generate figures used in the manuscript and supplementary materials (ROC curves, UMAP embeddings, network plots, heatmaps), which are saved locally as image files.

## Environment
The analysis was run using Python 3.11.
Main addictions include:
- numpy
- pandas
- scipy
- matplotlib
- seaborn
- scikit-learn
- umap-learn
- networkx

A `requirements.txt` file is provided for reproducibility.
