# DecoDoseNet Code

This archive contains notebooks for DecoDoseNet experiments and the corresponding input data.

## Notebooks

| File | Description |
| --- | --- |
| `01_Graphlet_ABG_5seeds_.ipynb` | Repeated group-disjoint training and evaluation across five seeds (42, 52, 62, 72, 82); summarizes test metrics. The notebook reads an existing seed-42 prediction file and trains the remaining seeds by default. |
| `02_2Graphlet_ABG_seed_42.ipynb` | Trains and evaluates the full model with a group-disjoint train/validation/test split at seed 42; saves predictions and the trained model. |
| `03_3Graphlet_ABG_ablation.ipynb` | Compares separately trained IDB-only and HPB-only variants at seed 42. |
| `04_Graphlet_ABG_IDB_component_ablation.ipynb` | Evaluates IDB component variants without ε, with fixed drug weights, and with both changes. |
| `05_DecoDoseNet_cold_start_cell_line.ipynb` | Leave-one-cell-line-out evaluation: each cell line is held out for testing in its own fold. |
| `05_DecoDoseNet_cold_start_drug_pair.ipynb` | Leave-one-unordered-drug-pair-out evaluation: each drug pair is held out for testing in its own fold. |

## Data (`DecoDoseNet_data/`)

| File | Description |
| --- | --- |
| `processed_combination_response_r070_clean_with_qc.csv` | Processed dose-specific combination responses after monotherapy fit quality control at the R² ≥ 0.70 threshold. |
| `Graphlet_features_6_standardized.csv` | Standardized graphlet-based drug features. |
| `cell_features_977d.csv` | Cell-line feature table with 977 expression features. |

**Data paths:** The two cold-start notebooks expect these three CSV files in `data/` relative to the notebook working directory. The other notebooks use an absolute `DATA_DIR` path. Set `DATA_DIR` to the extracted `DecoDoseNet_data/` directory (or copy the data to the expected location) before running them. The five-seed notebook additionally expects an existing seed-42 prediction CSV at `EXISTING_SEED42_PREDICTIONS` unless its configuration is changed.
