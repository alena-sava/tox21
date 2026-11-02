
# Tox21 – Chemical Toxicity Prediction

Machine learning project for predicting chemical toxicity using the Tox21 dataset. The project focuses on the SR-ARE endpoint and compares Logistic Regression and Random Forest classifiers using molecular fingerprints.

## Project Structure

```text
tox21/
│
├── data/
│   └── tox21.csv
│
├── output/
│   └── tox21_clean.csv
│
├── report/
│   └── Tox21_Toxicity_Prediction_Report.pdf
│
├── src/
│   └── SR-ARE_Analysis.ipynb
│
├── README.md
└── requirements.txt
```

## Folder Description

| Folder / File | Description |
|---|---|
| `data/` | Original Tox21 dataset. |
| `output/` | Cleaned dataset generated during preprocessing. |
| `report/` | Final research report in PDF format. |
| `src/` | Jupyter Notebook containing data preprocessing, molecular standardization, feature extraction, model training and evaluation. |
| `requirements.txt` | Required Python libraries. |

## Requirements

The project uses Python 3.11 and the following libraries:

- Pandas – data manipulation.
- NumPy – numerical operations.
- RDKit – molecular structure validation and Morgan fingerprint generation.
- Scikit-learn – machine learning models and evaluation.
- Jupyter Notebook – interactive analysis.

## Installation

### 1. Create a Python environment

```bash
conda create -n tox21 python=3.11
conda activate tox21
```

### 2. Install dependencies

Install RDKit:

```bash
conda install -c conda-forge rdkit
```

Install other libraries:

```bash
pip install pandas numpy scikit-learn jupyter
```

### 3. Run the notebook

```bash
jupyter notebook
```

Open `src/SR-ARE_Analysis.ipynb` and run the cells sequentially.

## Dataset

The project uses the Tox21 toxicological screening dataset.

The analysis focuses on the SR-ARE (Stress Response – Antioxidant Response Element) endpoint.

Missing experimental measurements are excluded rather than treated as negative observations.

## Methodology

The analysis consists of the following steps:

1. Data loading and preprocessing.
2. SMILES validation using RDKit.
3. Molecular standardization and duplicate removal.
4. SR-ARE endpoint selection.
5. Morgan fingerprint generation (2048 bits).
6. Train-test split (80/20) with stratification.
7. Model training and evaluation.

## Machine Learning Models

Two classification models are compared:

- **Logistic Regression** – baseline linear model.
- **Random Forest** – non-linear ensemble model.

## Evaluation Metrics

Model performance is evaluated using:

- ROC-AUC
- Precision
- Recall
- F1-score
- Accuracy

## Research Question

Can the non-linear Random Forest model achieve superior performance compared to a Logistic Regression baseline in predicting SR-ARE activity from molecular fingerprints?

## Results

| Model | ROC-AUC | Precision | Recall | F1-score | Accuracy |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.764 | 0.398 | 0.536 | 0.456 | 0.795 |
| Random Forest | 0.795 | 0.617 | 0.160 | 0.254 | 0.849 |

Random Forest achieved a higher ROC-AUC, while Logistic Regression showed better Recall and F1-score.

## Conclusion

The results indicate that Random Forest provides better overall discrimination between positive and negative SR-ARE compounds. However, Logistic Regression performs better in identifying positive compounds at the default classification threshold.

## Course Information

- Programme: MSc Artificial Intelligence
- Specialisation: Variant Technieken
- Course: IM1012 – Machine Learning
- Academic Year: 2026–2027
- Quarter: 2

## References

- Wu et al. (2018). MoleculeNet: A benchmark for molecular machine learning.
- Chen et al. (2021). Chemical toxicity prediction based on semi-supervised learning and graph convolutional neural network.
