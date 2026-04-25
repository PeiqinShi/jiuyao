# SysComs

`SysComs` is a research project for systems biology and interpretable machine learning. It combines genome-scale metabolic model (GEM) analysis for multiple microorganisms with notebook-based machine learning workflows for predicting and explaining fermentation-related traits.

The repository currently contains two main parts:

- `GEMs/`: metabolic model simulation, flux analysis, pathway summaries, and visualization
- `Interpretable ML/`: regression modeling, feature selection, SHAP analysis, and figure generation

## Project Structure

```text
syscoms/
├── GEMs/
│   ├── Bacillus subtilis.ipynb
│   ├── Saccharomyces cerevisiae.ipynb
│   ├── Rhizopus microsporus.ipynb
│   ├── Rhizopus_curated.xml
│   └── data/
├── Interpretable ML/
│   ├── data/
│   │   └── data.xlsx
│   ├── model/
│   │   ├── Fermentation power.ipynb
│   │   ├── Liquefaction power.ipynb
│   │   └── Saccharification power.ipynb
│   └── figures/
└── README.md
```

## Recommended Environment

The notebooks in this repository import the following Python packages:

- `jupyter`
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scipy`
- `scikit-learn`
- `statsmodels`
- `shap`
- `boruta`
- `deap`
- `matplotlib-venn`
- `lazypredict`
- `cobra`
- `openpyxl`

Because this repository does not yet include a locked environment file, the versions below are **recommended versions** chosen for compatibility with the current notebooks:

```text
python==3.11
jupyter==1.0.0
notebook==7.2.1
ipykernel==6.29.5
pandas==2.2.2
numpy==1.26.4
matplotlib==3.8.4
seaborn==0.13.2
scipy==1.13.1
scikit-learn==1.4.2
statsmodels==0.14.2
shap==0.45.1
boruta==0.4.3
deap==1.4.1
matplotlib-venn==0.11.10
lazypredict==0.2.12
cobra==0.29.0
openpyxl==3.1.5
```

## Installation

Create and activate a virtual environment:

```bash
cd "/Users/mac/Jupyter notebook/syscoms"
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

Install the required packages:

```bash
pip install \
  jupyter==1.0.0 \
  notebook==7.2.1 \
  ipykernel==6.29.5 \
  pandas==2.2.2 \
  numpy==1.26.4 \
  matplotlib==3.8.4 \
  seaborn==0.13.2 \
  scipy==1.13.1 \
  scikit-learn==1.4.2 \
  statsmodels==0.14.2 \
  shap==0.45.1 \
  boruta==0.4.3 \
  deap==1.4.1 \
  matplotlib-venn==0.11.10 \
  lazypredict==0.2.12 \
  cobra==0.29.0 \
  openpyxl==3.1.5
```

Register the environment as a Jupyter kernel if needed:

```bash
python -m ipykernel install --user --name syscoms --display-name "syscoms"
```

## How To Run The Code

### 1. Start Jupyter Notebook

From the project root:

```bash
cd "/Users/mac/Jupyter notebook/syscoms"
source .venv/bin/activate
jupyter notebook
```

Then open the notebook you want to run in your browser.

### 2. Run the GEMs workflows

Open one of these notebooks:

- `GEMs/Bacillus subtilis.ipynb`
- `GEMs/Saccharomyces cerevisiae.ipynb`
- `GEMs/Rhizopus microsporus.ipynb`

Before running:

- Make sure the SBML/XML model files are still in the expected locations
- Run all cells from top to bottom
- Check the `GEMs/data/` folder for generated CSV, XML, HTML, and figure outputs

These notebooks use `COBRApy` for model loading, optimization, pFBA analysis, and exchange/pathway summary generation.

### 3. Run the interpretable ML workflows

Open one of these notebooks:

- `Interpretable ML/model/Fermentation power.ipynb`
- `Interpretable ML/model/Liquefaction power.ipynb`
- `Interpretable ML/model/Saccharification power.ipynb`

Before running:

- Make sure `Interpretable ML/data/data.xlsx` is present
- Run all cells from top to bottom
- Check `Interpretable ML/figures/` for exported plots and model interpretation results

These notebooks include feature selection, model comparison, hyperparameter tuning, SHAP analysis, and regression performance evaluation.

## Notes

- The notebooks currently record a `syscoms` kernel in their metadata.
- A dedicated `requirements.txt` or `environment.yml` would be a good next step for full reproducibility.
- If package conflicts appear, use Python `3.11` first; it is the safest target for the current dependency set.
