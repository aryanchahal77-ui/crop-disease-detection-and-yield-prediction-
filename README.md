# crop-disease-detection-and-yield-prediction-
crop-disease-detection-and-yield-prediction)
AI-Powered Crop Disease Detection and Yield Prediction System

An integrated, end-to-end AgTech platform combining deep learning computer vision and machine learning regression to assist farmers and agronomists with early plant disease diagnosis and accurate seasonal yield forecasting.

📌 Table of Contents

Overview

Key Features

Repository Link

System Architecture

Tech Stack

Datasets Used

Getting Started

Prerequisites

Installation

Usage

Project Directory Structure

Model Performance

Author & Contact

License

🔬 Overview

Modern agriculture faces dual challenges: unmanaged crop pathologies that cause massive financial losses and unpredictable harvest outputs driven by micro-climatic shifts.

The AI-Powered Crop Disease Detection and Yield Prediction System solves these problems by providing:

Visual Leaf Pathology Classifier: Uses transfer learning convolutional neural networks (MobileNetV2 / ResNet50) to instantly detect diseases from RGB leaf images across 38+ plant-disease categories.

Predictive Yield Engine: Employs ensemble machine learning models (Random Forest / XGBoost) to forecast crop output (metric tons per hectare) based on soil pH, temperature, annual rainfall, and fertilizer usage.

✨ Key Features

Instant Leaf Disease Identification: Upload crop leaf images to classify healthy vs. infected crops with confidence scores.

Remediation & Treatment Guide: Automatically suggests chemical, organic, and fertilizer treatment plans based on identified leaf diseases.

Multi-Variable Yield Forecasting: Input local climatic and soil parameters to get data-driven yield estimates.

Interactive Streamlit Web Dashboard: Simple, accessible interface designed for both non-technical farmers and field agronomists.

🔗 Repository Link

GitHub Repository: https://github.com/aryanchahal77-ui/crop-disease-detection-and-yield-prediction

git clone https://github.com/aryanchahal77-ui/crop-disease-detection-and-yield-prediction.git


🏗 System Architecture

                       ┌──────────────────────────────┐
                       │      Streamlit Web UI        │
                       └──────────────┬───────────────┘
                                      │
                   ┌──────────────────┴──────────────────┐
                   │                                     │
         [Image Upload Input]                [Tabular Soil/Weather Input]
                   │                                     │
                   ▼                                     ▼
     ┌───────────────────────────┐         ┌───────────────────────────┐
     │  Computer Vision Engine   │         │  Yield Forecasting Engine │
     │  (MobileNetV2 / PyTorch)  │         │ (Random Forest / XGBoost) │
     └─────────────┬─────────────┘         └─────────────┬─────────────┘
                   │                                     │
                   ▼                                     ▼
     ┌───────────────────────────┐         ┌───────────────────────────┐
     │  38 Pathology Classes +   │         │ Predicted Crop Output     │
     │  Treatment Advice         │         │ (Metric Tons / Hectare)   │
     └───────────────────────────┘         └───────────────────────────┘


🛠 Tech Stack

Language: Python 3.9+

Deep Learning / CV: PyTorch, torchvision, OpenCV, Pillow

Machine Learning & Data Processing: scikit-learn, pandas, numpy, xgboost

Frontend / Web UI: Streamlit

Visualization: matplotlib, seaborn

📊 Datasets Used

Leaf Disease Dataset (PlantVillage):

54,000+ high-resolution RGB images across 38 class labels (Tomato, Potato, Corn, Apple, Grape, etc.).

Agronomic & Yield Dataset:

Tabular dataset containing parameters: Location_Zone, Crop_Type, Rainfall_mm, Temperature_C, Soil_pH, Fertilizer_Tonnes, and target Yield_Per_Hectare.

🚀 Getting Started

Prerequisites

Ensure Python 3.9+ and Git are installed on your machine.

Download Python 3.9+

Download Git

Installation

Clone the repository:

git clone https://github.com/aryanchahal77-ui/crop-disease-detection-and-yield-prediction.git
cd crop-disease-detection-and-yield-prediction


Create and activate a virtual environment:

Windows:

python -m venv venv
venv\Scripts\activate


macOS / Linux:

python3 -m venv venv
source venv/bin/activate


Install dependencies:

pip install -r requirements.txt


Launch the Streamlit web application:

streamlit run app.py


💻 Usage

1. Training Disease Detection Model

To fine-tune the MobileNetV2 architecture on your custom dataset:

python src/train_cnn.py --data_dir data/raw/plantvillage --epochs 10 --batch_size 32


2. Training Yield Predictor Regressor

To train the Random Forest / XGBoost regressor:

python src/train_yield.py --dataset_path data/processed/crop_yield.csv


📂 Project Directory Structure

crop-disease-detection-and-yield-prediction/
├── data/
│   ├── raw/                  # PlantVillage images and raw CSVs
│   └── processed/            # Normalized and encoded data
├── models/
│   ├── disease_classifier.pth# Trained PyTorch CNN model weights
│   └── yield_predictor.pkl   # Serialized Random Forest model
├── notebook/
│   ├── 01_disease_detection.ipynb
│   └── 02_yield_prediction.ipynb
├── src/
│   ├── dataset.py            # PyTorch dataset loaders & transforms
│   ├── train_cnn.py          # Model training pipeline for vision
│   └── train_yield.py        # ML regression pipeline for yield
├── app.py                    # Streamlit web interface
├── requirements.txt          # Python dependencies
├── PROJECT_DESCRIPTION.md    # Detailed project documentation
└── README.md                 # Project README


📈 Model Performance

Disease Classification Accuracy: ~96.4% Top-1 validation accuracy on PlantVillage dataset using fine-tuned MobileNetV2.

Inference Speed: ~45 ms per image inference.

Yield Forecasting Performance: R² Score = 0.91 with low Root Mean Squared Error (RMSE) using Random Forest Regressor.

👤 Author & Contact

Aryan Chahal

Email: aryanchahal77@gmail.com

GitHub Profile: aryanchahal77-ui

Repository: crop-disease-detection-and-yield-prediction

📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
