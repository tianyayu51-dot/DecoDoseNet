# DecoDoseNet

Code and data for dose-specific drug combination response prediction with DecoDoseNet, a dual-branch model combining an Interpretable Decoupling Branch (IDB) and a High-Performance Prediction Branch (HPB).

## Notebooks

| File | Description |
| --- | --- |
| `01_Graphlet_ABG_5seeds.ipynb` | Trains and evaluates DecoDoseNet across five random seeds (42, 52, 62, 72, and 82). Each run independently splits the data into training, validation, and test sets using disjoint drug-pair–cell-line groups. Saves model checkpoints, test predictions, split assignments, and evaluation metrics, with a summary of the mean and sample standard deviation across runs. |
| `02_Graphlet_ABG_drug_pair_cold_start.ipynb` | Evaluates generalization to unseen drug pairs using seed 42. Splits the data by unordered drug pair so that training, validation, and test sets contain mutually exclusive pairs. Saves split checks, model checkpoints, test predictions, and evaluation metrics. |
| `03_Graphlet_ABG_cell_line_cold_start.ipynb` | Evaluates generalization to unseen cell lines using seed 42. Splits the data by cell line so that training, validation, and test sets contain mutually exclusive cell lines. Saves split checks, model checkpoints, test predictions, and evaluation metrics. |
| `04_Graphlet_ABG_IDB_component_ablation.ipynb` | Evaluates the contributions of the IDB components using a fixed group-disjoint split and seed 42. Compares the full model with three variants: removing the learned residual term epsilon, fixing both single-agent weights to 0.5, and applying both changes together. Saves model checkpoints, predictions, and comparative metrics. |

## Data files

The following files are included in `DecoDoseNet_data/`.

| File | Description |
| --- | --- |
| `cell_features_977d.csv` | Cell-line gene expression features. Contains a `Cell_Line` identifier column and 977 gene feature columns. |
| `Graphlet_features_6_standardized.csv` | Drug graphlet features. Contains 6,890 numeric feature columns and the metadata columns `name`, `smile`, and `mol`. |
| `processed_combination_response_r070_clean_with_qc.csv` | Processed drug combination response data with quality-control fields. Includes drug and cell-line identifiers, paired concentrations, combination response targets, fitted single-agent responses, four-parameter logistic fit parameters, and fit-quality metrics. |

## Data path

The notebooks currently use `DATA_DIR = Path("data")`. To use the included folder, change this setting to `DATA_DIR = Path("DecoDoseNet_data")` and run the notebooks from the `DecoDoseNet_Code/` directory, or rename `DecoDoseNet_data/` to `data/`.
