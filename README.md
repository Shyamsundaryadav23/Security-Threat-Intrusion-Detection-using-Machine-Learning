ntrusion Detection System using Machine Learning - Complete Implementation
🎯 Project Overview

A machine learning–based Network Intrusion Detection System (IDS) designed to detect malicious network activities using the UNSW-NB15 dataset.
The project implements a complete ML workflow including data preprocessing, feature engineering, class imbalance handling, supervised classification, and anomaly detection to identify cyber attacks in network traffic.

📋 Implemented Modules
Module 1: Data Collection & Loading ✅

Imported UNSW-NB15 network intrusion dataset

Combined multiple CSV files into a unified dataset

Processed 2M+ network traffic records

Handled dataset inconsistencies

Module 2: Data Preprocessing ✅

Missing value handling

Encoding categorical features

Removing redundant attributes

Dataset shuffling and cleaning

Preparing data for ML models

Module 3: Feature Engineering & Selection ✅

Correlation analysis for redundant feature removal

Mutual information analysis

Feature importance analysis

Top feature selection using statistical methods

Module 4: Class Imbalance Handling ✅

Identified imbalance between normal traffic and attack samples

Applied SMOTE (Synthetic Minority Oversampling Technique)

Balanced dataset to improve attack detection accuracy

Module 5: Supervised Machine Learning Models ✅
Logistic Regression

Baseline classification model

Fast and interpretable

Used for comparison

Random Forest

Ensemble learning approach

Higher accuracy and robustness

Handles non-linear relationships

Module 6: Dimensionality Reduction ✅

Applied Principal Component Analysis (PCA)

Reduced feature space

Improved model training performance

Visualized variance distribution

Module 7: Anomaly Detection (Unsupervised Learning) ✅
K-Means Clustering

Grouped network traffic patterns

Identified abnormal clusters

DBSCAN

Density-based clustering

Detected outliers representing potential attacks

💻 Technology Stack
Machine Learning

Python

Scikit-learn

imbalanced-learn (SMOTE)

Pandas

NumPy

Data Visualization

Matplotlib

Seaborn

Development Environment

Jupyter Notebook
🚀 Quick Start
1️⃣ Clone Repository
git clone https://github.com/Shyamsundaryadav23/Security-Threat-Intrusion-Detection-using-Machine-Learning.git
cd Security-Threat-Intrusion-Detection-using-Machine-Learning
2️⃣ Install Dependencies
pip install -r requirements.txt
3️⃣ Run the Project
jupyter notebook ML_Project.ipynb

Run all cells to execute the complete machine learning pipeline.

📡 Machine Learning Workflow
Step 1 — Data Preprocessing

Load UNSW-NB15 dataset

Clean and normalize data

Handle missing values

Encode categorical variables

Step 2 — Feature Engineering

Correlation analysis

Feature importance calculation

Selection of relevant features

Step 3 — Handle Class Imbalance

Apply SMOTE

Balance attack and normal samples

Step 4 — Train Models

Logistic Regression

Random Forest

Step 5 — Model Evaluation

Precision

Recall

F1 Score

Confusion Matrix

Step 6 — Anomaly Detection

PCA dimensionality reduction

K-Means clustering

DBSCAN clustering

📊 Dataset Information

This project uses the UNSW-NB15 dataset, a modern intrusion detection dataset created by UNSW Canberra Cyber.

Dataset Characteristics
Feature	Description
Records	~2.5 Million
Features	49
Attack Types	9
Categories	Normal + Malicious Traffic
Attack Types Include

DoS

Exploits

Fuzzers

Reconnaissance

Shellcode

Worms

📈 Model Evaluation

Performance metrics used:

Accuracy

Precision

Recall

F1 Score

Confusion Matrix

Random Forest achieved better detection accuracy and recall for attack classes compared to Logistic Regression.

🧪 Testing Workflow
Model Training

Load dataset

Perform preprocessing

Balance dataset using SMOTE

Train ML models

Evaluation

Generate predictions

Compute performance metrics

Compare model results

Anomaly Detection Testing

Apply PCA

Perform clustering

Identify anomaly clusters

📦 Dependencies
Essential Libraries

pandas

numpy

scikit-learn

imbalanced-learn

matplotlib

seaborn

jupyter

Example installation:

pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn jupyter
🚢 Future Improvements

Hyperparameter tuning with GridSearchCV

Deep learning models (CNN / LSTM)

Real-time intrusion detection system

Deployment using Flask / FastAPI

Integration with SIEM tools

🐛 Troubleshooting
Notebook not running

Ensure Python version ≥ 3.8

Install required libraries

Memory issues

Use smaller dataset sample

Increase RAM allocation

Model training slow

Reduce dataset size

Use GPU acceleration
🎓 Learning Resources

Python: https://python.org

Scikit-learn: https://scikit-learn.org

Machine Learning: https://www.coursera.org/learn/machine-learning

Network Security: https://owasp.org

📎 Project Link

GitHub Repository
https://github.com/Shyamsundaryadav23/Security-Threat-Intrusion-Detection-using-Machine-Learning

📄 License

This project is provided for educational and research purposes.
