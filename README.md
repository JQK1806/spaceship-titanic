# Spaceship Titanic - Machine Learning Competition

This project uses machine learning to predict whether passengers were transported to an alternate dimension during the Spaceship Titanic's voyage. Based on the [Spaceship Titanic Kaggle competition](https://www.kaggle.com/competitions/spaceship-titanic).

## Table of Contents
- [About](#about)
- [Results](#results)
- [Setup](#setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Methodology](#methodology)

## About
This repository contains a complete machine learning solution for the Spaceship Titanic Kaggle competition. The goal is to predict which passengers were transported to an alternate dimension using passenger data including demographics, cabin information, and onboard services.

### Key Features
- **Comprehensive EDA**: Exploratory data analysis with visualizations
- **Feature Engineering**: Cabin decomposition, categorical encoding, missing value handling
- **Multiple Models**: Logistic Regression, Random Forest, Decision Tree, XGBoost, LightGBM
- **Hyperparameter Tuning**: Grid search optimization for ensemble models
- **Model Comparison**: Performance evaluation across different algorithms

### Technologies Used
- ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) Core programming language
- ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white) & ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white) Data manipulation and numerical computing
- ![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white) Machine learning algorithms and preprocessing
- ![XGBoost](https://img.shields.io/badge/XGBoost-337AB7?style=for-the-badge&logo=xgboost&logoColor=white) & ![LightGBM](https://img.shields.io/badge/LightGBM-00A1F1?style=for-the-badge&logo=lightgbm&logoColor=white) Gradient boosting frameworks
- ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white) & ![Seaborn](https://img.shields.io/badge/Seaborn-000000?style=for-the-badge&logo=seaborn&logoColor=white) Data visualization
- ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white) Interactive development environment

## Results
The project achieved the following validation accuracies:
- **LightGBM**: 81.66% (best performing model)
- **Random Forest**: 81.08%
- **XGBoost**: 80.33%
- **Logistic Regression**: 79.07%
- **Decision Tree**: 75.56%


## Setup
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/spaceship-titanic.git
   cd spaceship-titanic
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download competition data:**
   - Download `train.csv` and `test.csv` from the [Kaggle competition page](https://www.kaggle.com/competitions/spaceship-titanic/data)
   - Place the files in the `data/` directory

## Usage
1. **Run the analysis:**
   ```bash
   jupyter notebook main.ipynb
   ```

2. **Generate predictions:**
   - The notebook will automatically create `submission.csv` with predictions
   - Use this file for Kaggle submission

## Project Structure
```
spaceship-titanic/
├── main.ipynb              # Main analysis and modeling notebook
├── requirements.txt        # Python dependencies
├── submission.csv          # Generated predictions for Kaggle
├── README.md              # Project documentation
├── .gitignore             # Git ignore rules
├── data/                  # Competition data files
│   ├── train.csv          # Training dataset
│   ├── test.csv           # Test dataset
│   └── sample_submission.csv
└── venv/                  # Virtual environment
```

## Methodology

### Data Preprocessing
1. **Missing Value Handling**:
   - Categorical variables: Filled with mode
   - Numerical variables: Filled with median
   - Cabin information: Decomposed into Deck, Number, and Side

2. **Feature Engineering**:
   - One-hot encoding for categorical variables
   - Boolean encoding for CryoSleep and VIP status
   - Cabin decomposition for better feature extraction

3. **Data Scaling**:
   - StandardScaler applied for algorithms requiring scaled features

### Model Development
1. **Baseline Models**: Logistic Regression, Random Forest, Decision Tree
2. **Advanced Models**: XGBoost and LightGBM with hyperparameter tuning

### Key Insights
- **Home Planet**: Significant predictor of transportation
- **CryoSleep**: Strong correlation with transportation outcome
- **Age Distribution**: Different patterns between transported and non-transported passengers
- **Cabin Location**: Deck and side information provides valuable predictive power
