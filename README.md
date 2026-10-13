# Smart-X Machine Learning

A machine-learning component for the Smart-X IoT telemetry platform, focused on predicting likely operator actions from historical sensor telemetry, device states, and command patterns.

## Objectives

* Generate realistic synthetic telemetry and command-history data.
* Explore and engineer features from time-ordered IoT events.
* Train and evaluate a Random Forest classifier.
* Export the fitted scikit-learn pipeline using joblib.
* Expose predictions through a Python inference API.
* Integrate predictive recommendations with the Smart-X ASP.NET Core application.

## Technology Stack

| Technology | Purpose |
| --- | --- |
| Python | ML development and inference |
| Jupyter | Interactive development and documentation |
| pandas and NumPy | Data manipulation and numerical processing |
| scikit-learn | Preprocessing, model training and evaluation |
| Matplotlib and Seaborn | Data visualisation |
| joblib | Model serialisation |
| FastAPI | Model inference API |
| ASP.NET Core | Integration with Smart-X |

## Project Structure

* `notebooks/` — Documented ML development notebooks.
* `src/smartx_ml/` — Reusable data-generation, feature-engineering and inference modules.
* `data/` — Synthetic datasets.
* `artifacts/` — Exported model artefacts.
* `reports/` — Evaluation results and visualisations.
* `inference_api/` — Python inference service documentation and implementation.

## Development Environment

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate

```

Install the current notebook dependencies:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt

```

Register the Jupyter kernel:

```bash
python -m ipykernel install --user \
  --name smartx-ml \
  --display-name "Python (Smart-X ML)"

```

## Model Development

The planned workflow covers synthetic-data generation, exploratory data analysis, feature engineering, Random Forest training, evaluation, and model export.

Training and inference will remain separate from the existing Smart-X ASP.NET Core application.

## Project Status

| Phase | Status |
| --- | --- |
| 1. Environment and Project Structure | In Progress |
| 2. Synthetic Telemetry and Command Data | Pending |
| 3. Exploratory Data Analysis | Pending |
| 4. Feature Engineering | Pending |
| 5. Random Forest Training | Pending |
| 6. Model Evaluation and Interpretation | Pending |
| 7. Model Export with joblib | Pending |
| 8. Python Inference API | Pending |
| 9. ASP.NET Core Integration | Pending |
| 10. Suggested Actions UI | Pending |
| 11. End-to-End Verification | Pending |

## Data and Model Disclaimer

The initial training data will be simulated. Model performance on synthetic data does not establish real-world predictive accuracy or prove that a recommended action is causally effective.