# 💤 Sleep Apnea Prediction Using Machine Learning

### Predicting Sleep Apnea Severity from Polysomnography (PSG) Signals

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Machine%20Learning-Scikit--learn-orange?logo=scikitlearn" alt="Machine Learning">
  <img src="https://img.shields.io/badge/Interface-Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit">
  <img src="https://img.shields.io/badge/Status-Development-yellow" alt="Project Status">
</p>

<p align="center">
  A machine learning application that analyzes Polysomnography (PSG) signals to estimate the Apnea-Hypopnea Index (AHI) and classify sleep apnea severity.
</p>

<p align="center">
  <a href="https://sleep-disorder-ml-project.streamlit.app/"><strong>🚀 Live Demo</strong></a>
  &nbsp; • &nbsp;
  <a href="https://github.com/manthansharma6767/Sleep-Disorder"><strong>📂 GitHub Repository</strong></a>
  &nbsp; • &nbsp;
  <a href="https://physionet.org/content/sleep-edfx/1.0.0/"><strong>📊 Dataset</strong></a>
</p>

---

## 📌 Table of Contents

* [Overview](#-overview)
* [Features](#-features)
* [Machine Learning Models](#-machine-learning-models)
* [Data and Signals](#-data-and-signals)
* [Model Performance](#-model-performance)
* [Project Structure](#-project-structure)
* [Installation and Setup](#-installation-and-setup)
* [Dataset Setup](#-dataset-setup)
* [Running the Application](#-running-the-application)
* [Future Improvements](#-future-improvements)
* [Disclaimer](#-disclaimer)
* [Acknowledgements](#-acknowledgements)

---

## 🔍 Overview

Sleep apnea is a sleep-related disorder characterized by repeated interruptions in breathing during sleep.

This project explores the use of machine learning to analyze **Polysomnography (PSG)** recordings and estimate sleep apnea indicators.

PSG recordings can contain multiple physiological signals, including respiratory airflow and electroencephalography (EEG). The application processes relevant signals to estimate sleep duration, identify potential apnea or hypopnea events, predict the Apnea-Hypopnea Index (AHI), and classify sleep apnea severity.

The project combines signal processing techniques with trained machine learning models in an interactive Streamlit application.

### 🎯 Objectives

* Process PSG recordings in EDF format.
* Analyze respiratory and EEG signals.
* Estimate sleep duration using EEG delta-band power.
* Detect potential apnea and hypopnea events.
* Predict AHI using a regression model.
* Classify sleep apnea severity using a classification model.

---

## ✨ Features

| Feature                         | Description                                                                   |
| ------------------------------- | ----------------------------------------------------------------------------- |
| 📈 AHI Prediction               | Estimates the Apnea-Hypopnea Index using a trained regression model.          |
| 🧠 Severity Classification      | Classifies sleep apnea severity into four categories.                         |
| 🌬️ Respiratory Signal Analysis | Processes respiratory airflow signals to identify potential breathing events. |
| 🌙 Sleep Time Estimation        | Estimates sleep duration using EEG delta-band power.                          |
| 📂 EDF File Support             | Accepts compatible Polysomnography recordings in EDF format.                  |
| 🖥️ Interactive Interface       | Provides a user interface built with Streamlit.                               |

### Sleep Apnea Severity Categories

The application uses the following categories:

* No Sleep Apnea
* Mild Sleep Apnea
* Moderate Sleep Apnea
* Severe Sleep Apnea

The reliability of these classifications depends on the training data, preprocessing pipeline, and model validation.

---

## 🤖 Machine Learning Models

The project includes two pretrained machine learning models.

| Model                        | File               | Purpose                                  |
| ---------------------------- | ------------------ | ---------------------------------------- |
| Random Forest Regressor      | `rf_regressor.pkl` | Predicts the Apnea-Hypopnea Index (AHI). |
| Support Vector Machine (SVM) | `best_svm.pkl`     | Classifies sleep apnea severity.         |

### Technologies Used

* **Python** — Core programming language
* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical computations
* **SciPy** — Scientific signal processing
* **MNE** — Neurophysiological signal analysis
* **PyEDFlib** — EDF file processing
* **Scikit-learn** — Machine learning algorithms
* **Imbalanced-learn** — Tools for imbalanced datasets
* **Matplotlib** — Data visualization
* **Streamlit** — Interactive web application

---

## 📊 Data and Signals

The application works with Polysomnography (PSG) recordings in EDF format.

### Signals Analyzed

| Signal                                  | Purpose                                                            |
| --------------------------------------- | ------------------------------------------------------------------ |
| Respiratory airflow (oro-nasal airflow) | Used to identify potential apnea and hypopnea events.              |
| EEG (Fpz-Cz)                            | Used to estimate sleep duration through delta-band power analysis. |

### Dataset Source

The project references the **Sleep-EDF Expanded dataset**, available through PhysioNet.

* **Dataset:** [Sleep-EDF Expanded](https://physionet.org/content/sleep-edfx/1.0.0/)
* **Provider:** PhysioNet

Refer to the dataset documentation for its terms of use, file descriptions, and applicable attribution requirements.

---

## 📈 Model Performance

The existing project README reports the following cross-validation results for the SVM classifier:

| Fold              |   Accuracy |
| ----------------- | ---------: |
| 1                 |     94.74% |
| 2                 |     78.95% |
| 3                 |     94.59% |
| 4                 |     94.59% |
| 5                 |     91.89% |
| **Mean Accuracy** | **90.95%** |

**Reported mean cross-validation accuracy: 90.95%.**

These are the metrics reported by the existing project documentation. They have not been independently reproduced or verified as part of this README update.

Accuracy alone does not establish clinical reliability. Further evaluation should include precision, recall, F1-score, confusion matrices, subject-level data separation, and validation on independent recordings.

---

## 📁 Project Structure

```text
Sleep-Disorder/
│
├── main.py
├── training_code.py
├── Data_collection_&_processing.py
├── psg_file_viewer.py
│
├── best_svm.pkl
├── rf_regressor.pkl
│
├── sleep_apnea_data_filtered.csv
├── sleep_apnea_data_numeric.csv
├── sleep_apnea_data_resampled.csv
│
├── requirements.txt
├── readme.md
├── .gitignore
│
└── .devcontainer/
    └── devcontainer.json
```

**File descriptions:**

* `main.py` — Streamlit application entry point.
* `training_code.py` — Machine learning model training code.
* `Data_collection_&_processing.py` — Data collection and preprocessing pipeline.
* `psg_file_viewer.py` — EDF file viewing utility.
* `best_svm.pkl` — Serialized SVM classification model.
* `rf_regressor.pkl` — Serialized Random Forest regression model.
* `requirements.txt` — Python dependencies.
* `sleep_apnea_data_*.csv` — Processed datasets used by the project.

The raw PSG sample file is not included in the repository because of its size.

---

## ⚙️ Installation and Setup

### Prerequisites

* Git
* Python compatible with the pinned project dependencies
* pip
* A Windows, macOS, or Linux environment

> **Compatibility note:** The current `requirements.txt` pins older package versions. Python 3.14 may not be compatible with all of them. Use a compatible Python version, such as Python 3.11, and verify installation before running the application.

### 1. Clone the Repository

```bash
git clone https://github.com/manthansharma6767/Sleep-Disorder.git
cd Sleep-Disorder
```

### 2. Create a Virtual Environment

**Windows PowerShell:**

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS/Linux:**

```bash
python3.11 -m venv .venv
source .venv/bin/activate
```

If Python 3.11 is not installed, install it first or use another Python version that is compatible with the project's dependencies.

### 3. Upgrade pip

```bash
python -m pip install --upgrade pip
```

### 4. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

If installation fails, check the Python version and the error message before changing the pinned package versions.

---

## 📥 Dataset Setup

The sample PSG file `SC4001E0-PSG.edf` is approximately 46 MB and is intentionally excluded from this GitHub repository.

### Download Instructions

1. Visit the [PhysioNet Sleep-EDF Expanded dataset](https://physionet.org/content/sleep-edfx/1.0.0/).
2. Locate and download `SC4001E0-PSG.edf`, if available in the dataset version you are using.
3. Place the file in the project root directory.

Your local directory should then contain:

```text
Sleep-Disorder/
├── main.py
├── SC4001E0-PSG.edf
├── requirements.txt
└── ...
```

The raw EDF file is excluded through `.gitignore`, so it should remain local and will not be included in ordinary Git commits.

**Note:** The application may require specific channels and annotations. Confirm that the selected EDF recording is compatible with the implementation.

---

## 🚀 Running the Application

After installing the dependencies and placing the required EDF file in the project directory, run:

```bash
python -m streamlit run main.py
```

Streamlit will display a local URL in the terminal, typically:

```text
http://localhost:8501
```

Open that URL in your browser to access the application.

### Live Demo

You can also try the existing hosted application:

**[Open Sleep Apnea Prediction Tool](https://sleep-disorder-ml-project.streamlit.app/)**

Availability and functionality of the hosted demo may change.

---

## 🔮 Future Improvements

Potential areas for further development include:

* Add automated unit and integration tests.
* Improve input validation and error handling.
* Evaluate models using precision, recall, F1-score, and confusion matrices.
* Validate performance on independent subjects and recordings.
* Improve signal preprocessing and artifact handling.
* Add clearer visualizations of physiological signals and predictions.
* Document the training methodology and dataset splits.
* Add reproducible model-training and evaluation scripts.

These are proposed improvements, not claims about features already implemented.

---

## ⚠️ Disclaimer

**This project is intended for educational and research purposes only.**

The predictions generated by this application are not a substitute for professional medical evaluation, a clinical sleep study interpretation, or a diagnosis by a qualified healthcare professional.

The reported model performance does not establish clinical validity or suitability for medical decision-making.

---

## 🙏 Acknowledgements

* [PhysioNet](https://physionet.org/) for hosting physiological datasets.
* [Sleep-EDF Expanded Dataset](https://physionet.org/content/sleep-edfx/1.0.0/).
* The developers and maintainers of Python, Streamlit, NumPy, Pandas, SciPy, MNE, PyEDFlib, and Scikit-learn.

---

<p align="center">
  <strong>Sleep Apnea Prediction Using Machine Learning</strong><br>
  Built with Python and Streamlit.
</p>
