# Smart-X Machine Learning

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626.svg?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Scikit-Learn](https://img.shields.io/badge/ML-scikit--learn-F7931E.svg?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![ONNX](https://img.shields.io/badge/Model-ONNX-005CED.svg?logo=onnx&logoColor=white)](https://onnx.ai/)
[![ASP.NET Core](https://img.shields.io/badge/Backend-ASP.NET%20Core-512BD4.svg?logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![Platform](https://img.shields.io/badge/Platform-IoT%20Telemetry-blue.svg)](#smart-x-machine-learning)

A machine-learning component for the Smart-X IoT telemetry platform that analyses sensor telemetry and historical command patterns to recommend likely operator actions. Predictions are exposed through an ONNX model integrated with the Smart-X ASP.NET Core application.

## Objectives

* Generate realistic synthetic telemetry and command-history data.
* Explore and engineer features from time-ordered IoT events.
* Train and evaluate a Random Forest classifier.
* Export the trained model to ONNX for cross-platform inference.
* Generate predictive recommendations through the Smart-X backend.
* Display the latest recommendation and recent prediction history in the Command Centre.

## Technology Stack

| Technology | Purpose |
| --- | --- |
| Python | Data generation, model development and evaluation |
| Jupyter | Interactive development and documentation |
| pandas and NumPy | Data manipulation and feature engineering |
| scikit-learn | Preprocessing, Random Forest training and evaluation |
| Matplotlib and Seaborn | Data visualisation |
| ONNX | Portable model representation |
| ONNX Runtime | Model inference in the ASP.NET Core backend |
| ASP.NET Core | API integration and presentation of recommendations |

## Project Structure - Active Usage

* `notebooks/` — Documented machine-learning development notebooks.
* `data/` — Synthetic telemetry and command-history datasets.
* `artifacts/` — Exported model artefacts.

## Development Environment

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate

```

Install the project dependencies:

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

## Model Development and Inference

The current model is a Random Forest classifier trained on synthetic IoT telemetry and historical command patterns. Its input features include current sensor readings, lagged observations, rolling statistics and recent changes.

The model predicts one of six recommended operator actions:

* `ACTIVATE_PUMP`
* `DEACTIVATE_PUMP`
* `ACTIVATE_FAN`
* `DEACTIVATE_FAN`
* `INSPECT_DEVICE`
* `NO_ACTION`

The trained model is exported to ONNX and loaded by the Smart-X ASP.NET Core backend using ONNX Runtime. The backend exposes endpoints for generating predictions, retrieving the latest prediction and accessing recent prediction history.

Prediction history is maintained in memory, with a maximum of 100 records. It includes the recommended action, timestamp, device category and zone. History is therefore temporary and is cleared when the backend restarts.

Recommendations do not execute device commands automatically. Operators retain control over command execution.

## Project Status

| Component | Status |
| --- | --- |
| Synthetic telemetry and command-history data | Implemented |
| Feature engineering | Implemented |
| Random Forest training and evaluation | Implemented |
| ONNX model export | Implemented |
| ASP.NET Core ONNX inference integration | Implemented |
| Latest prediction endpoint | Implemented |
| In-memory prediction history | Implemented |
| Command Centre prediction display | Implemented |
| Prediction history UI | Implemented |

## Data and Model Disclaimer

The current model is trained on synthetic data. Performance on simulated datasets does not establish real-world predictive accuracy or demonstrate that a recommended action will produce the intended outcome. Further evaluation, improved class representation and validation against representative real-world telemetry are necessary before operational reliance.

---
