

# AcademicInsight ML

### Student Performance Classification System with FastAPI & Gradio

AcademicInsight ML is an end-to-end machine learning application designed to predict student academic outcomes using a Decision Tree classification model.

The project demonstrates full lifecycle ML development including:

* Synthetic data generation
* Model training and evaluation
* Model serialization
* API deployment with FastAPI
* Interactive frontend with Gradio

This repository showcases how a trained machine learning model can be deployed as a production-style prediction service.

---

## Author

**imroshan18**

---

## Project Objective

The goal of AcademicInsight ML is to determine whether a student is likely to pass or fail based on measurable academic indicators.

The system evaluates three primary features:

* Study Hours (daily average)
* Attendance Percentage
* Previous Examination Score

The model outputs:

* Predicted Outcome (Pass / Fail)
* Confidence Score
* Feature Importance Breakdown

This provides both prediction and interpretability.

---

## System Architecture

The application follows a modular ML deployment structure.

### 1. Data Generation Layer

`data_generation.py` creates a synthetic dataset simulating realistic academic performance distributions. This ensures:

* Balanced class representation
* Meaningful feature relationships
* Controlled experimentation

---

### 2. Model Training Layer

`train_model.py`:

* Trains a Decision Tree Classifier
* Evaluates model performance
* Saves trained model (`model.pkl`)
* Saves metadata (`metadata.pkl`)
* Generates a visual tree representation (`tree_plot.png`)

---

### 3. Backend API (FastAPI)

`app.py` exposes a RESTful prediction endpoint.

Responsibilities:

* Load serialized model
* Accept feature inputs via JSON
* Return prediction results
* Provide health check endpoint
* Generate Swagger documentation

---

### 4. Frontend Interface (Gradio)

`ui.py` provides:

* Interactive sliders for input parameters
* Real-time prediction results
* Visual model explanation
* Feature importance display

---

### 5. Orchestration Layer

`run.py` coordinates:

* Dataset generation
* Model training
* Backend startup
* Frontend launch

This simulates a full ML deployment workflow.

---

## Technology Stack

| Component           | Technology    |
| ------------------- | ------------- |
| Machine Learning    | Scikit-learn  |
| Backend API         | FastAPI       |
| Frontend            | Gradio        |
| Data Handling       | Pandas, NumPy |
| Model Serialization | Pickle        |
| Language            | Python 3.8+   |

---

## Installation Guide

### 1. Install Dependencies

```bash id="ak29dp"
pip install -r requirements.txt
```

---

### 2. Launch the Full System

```bash id="r4pm82"
python run.py
```

This will:

* Generate synthetic data
* Train the model
* Save artifacts
* Start FastAPI backend (port 8000)
* Start Gradio frontend (port 7860)

---

## Using the Application

1. Open your browser:

```
http://127.0.0.1:7860
```

2. Adjust:

   * Study Hours
   * Attendance Percentage
   * Previous Score

3. Click “Predict”.

4. View:

   * Pass/Fail result
   * Confidence level
   * Feature importance breakdown
   * Decision tree visualization

---

## API Access

While the system is running:

### Swagger Documentation

```
http://127.0.0.1:8000/docs
```

### Health Endpoint

```
http://127.0.0.1:8000/health
```

### Prediction Endpoint

```
POST /predict
```

Example request body:

```json
{
  "study_hours": 5,
  "attendance": 85,
  "previous_score": 70
}
```

---

## Project Structure

```
AcademicInsight-ML/
│
├── app.py               # FastAPI backend
├── ui.py                # Gradio frontend
├── run.py               # Unified launcher
├── train_model.py       # Model training pipeline
├── data_generation.py   # Synthetic dataset generator
├── utils.py             # Utility helpers
├── model.pkl            # Trained model
├── metadata.pkl         # Model metadata
├── tree_plot.png        # Decision tree visualization
├── requirements.txt
└── README.md
```

---

## Design Principles

* Clear separation of training and serving
* Reproducible model pipeline
* Interpretability through feature importance
* Modular architecture
* Deployment simulation via FastAPI

---

## Potential Improvements

* Replace synthetic data with real academic dataset
* Add model comparison (Random Forest, XGBoost)
* Add cross-validation metrics dashboard
* Integrate database for prediction logging
* Dockerize for production deployment
* Deploy on cloud infrastructure

---

## Professional Positioning

This project demonstrates:

* End-to-end ML workflow implementation
* REST API model serving
* Interactive ML application design
* Model interpretability techniques
* Production-style deployment simulation


