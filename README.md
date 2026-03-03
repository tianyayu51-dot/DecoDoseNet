# DecoDoseNet: Interpretable Decomposition Network for Dose-Specific Drug Combination Prediction

## Overview

**DecoDoseNet** is a deep learning framework designed for drug
combination synergy prediction, with a focus on **dose-specific
modeling** and **biological interpretability**.\
The system performs drug combination contribution decomposition and
synergy prediction based on parameterized dose-response modeling.

------------------------------------------------------------------------

## Repository Structure

### `01dose_response.ipynb`

Implements single-agent dose-response modeling to extract baseline
pharmacological features.

### `02Graphlet feature.ipynb`

Extracts structural drug features using graphlet-based fingerprints.\
This module requires the **`minervachem`** library.

### `03Dual-Branch.ipynb`

Contains the dual-branch neural network architecture for joint training
on chemical structures and dose-response data.

------------------------------------------------------------------------

## Installation

### 1. Requirements

Install the core dependencies (including PyTorch, RDKit, and
Scikit-learn) via the provided `requirements.txt`:

``` bash
pip install -r requirements.txt
```

### 2. Dependency: `minervachem`

The feature extraction in `02Graphlet feature.ipynb` relies on
**minervachem**, the implementation of graphlet models from the
following study:

> Tynes, M., et al. *Linear graphlet models for accurate and
> interpretable cheminformatics.*\
> Digital Discovery, 2024, 3, 1980.

Ensure the `minervachem` source code is available in your environment
path.

------------------------------------------------------------------------

## Usage

### 1. Preprocessing

Run `01dose_response.ipynb` for data cleaning and single-drug modeling.

### 2. Feature Extraction

Run `02Graphlet feature.ipynb` to generate graphlet structural features
using the MinervaChem framework.

### 3. Training

Run `03Dual-Branch.ipynb` for final model training and synergy
prediction.

------------------------------------------------------------------------

## Citation

If you use this work in your research, please cite:

> **DecoDoseNet: Interpretable Decomposition Network for Dose-Specific
> Drug Combination Prediction.**

