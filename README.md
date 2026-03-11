
# 🛡️ Intrusion Detection System using Machine Learning

## 📝 Project Overview
This project develops a robust Machine Learning-based Network Intrusion Detection System (IDS) to identify and classify malicious network traffic. Utilizing the comprehensive UNSW-NB15 dataset, the system integrates advanced data preprocessing, feature engineering, and state-of-the-art machine learning algorithms. The goal is to build an effective IDS capable of distinguishing between normal and various types of attack traffic, thereby enhancing network security.

## ✨ Features
- **Comprehensive Data Preprocessing:** Handling missing values, data type conversions, and outlier treatment.
- **Advanced Feature Engineering:** Creation of new, insightful features to better capture network traffic characteristics.
- **Class Imbalance Handling:** Implementation of SMOTE (Synthetic Minority Over-sampling Technique) to address the skewed nature of network intrusion datasets.
- **Supervised Learning Models:** Development and evaluation of classification models (Logistic Regression, Random Forest) for attack detection.
- **Dimensionality Reduction:** Application of PCA for efficient data representation.
- **Anomaly Detection:** Integration of clustering algorithms (K-Means) for identifying unusual patterns in network traffic.
- **Performance Evaluation:** Rigorous assessment using key metrics like Accuracy, Precision, Recall, F1-score, and Confusion Matrices.

## 📊 Dataset Information
The project utilizes the **UNSW-NB15 network intrusion dataset**, a modern dataset designed to overcome limitations of older IDS datasets. It comprises:
- Approximately **2.5 million records** of network traffic flows.
- **49 features** detailing various aspects of network connections (e.g., source/destination IP, port, protocol, duration, byte counts, packet counts, connection state, etc.).
- Inclusion of **nine categories of attacks**: Fuzzers, Analysis, Backdoors, DoS, Exploits, Generic, Reconnaissance, Shellcode, and Worms.
- The dataset is divided into training and testing sets, providing a realistic evaluation environment.

## 🛠️ Technology Stack
- **Python**: Core programming language.
- **Scikit-learn**: For machine learning algorithms, preprocessing, and model evaluation.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **imbalanced-learn (SMOTE)**: For handling class imbalance.
- **Matplotlib**: For data visualization.
- **Seaborn**: For enhanced statistical data visualization.
- **Jupyter Notebook**: For interactive development and documentation.

## 🚀 Machine Learning Pipeline
The project follows a structured machine learning workflow:
1.  **Data Loading & Concatenation:** Loading and merging fragmented dataset files (`UNSW-NB15_1.csv` to `UNSW-NB15_4.csv`).
2.  **Initial Data Inspection & Cleaning:** Checking data types, handling duplicates, and filling missing values (e.g., `attack_cat`, `ct_flw_http_mthd`, `is_ftp_login`).
3.  **Exploratory Data Analysis (EDA):** Statistical summaries, unique value checks, outlier detection using box plots, and distribution analysis with histograms.
4.  **Data Transformation:** Outlier treatment by capping and logarithmic transformation to reduce skewness in numerical features.
5.  **Feature Engineering:** Creation of new features (e.g., duration, byte ratios, packet ratios, total bytes, total packets, interaction features) to enhance model predictive power.
6.  **Feature Encoding:** Label encoding for categorical features (e.g., `attack_cat`) and one-hot encoding for others.
7.  **Feature Selection:** Identification and removal of highly correlated features, and selection of top features using `f_regression` and Mutual Information scores.
8.  **Class Imbalance Handling:** Application of `RandomUnderSampler` followed by `SMOTE` to balance the target class distribution.
9.  **Feature Scaling:** Standardization of numerical features using `StandardScaler`.
10. **Model Training & Evaluation (Regression):** Training `LinearRegression` and `SGDRegressor` models to predict flow duration, evaluated using MAE, MSE, RMSE, and R² score.
11. **Model Training & Evaluation (Classification):** Training `LogisticRegression`, `SGDClassifier`, `RandomForest`, `LinearSVC`, and `DecisionTree` models for binary intrusion detection, evaluated using Accuracy, Precision, Recall, F1-score, ROC AUC, and PR AUC.
12. **Anomaly Detection (Clustering):** Application of `MiniBatchKMeans` on a subset of important features for unsupervised anomaly detection, evaluated using Silhouette Score.

## 📁 Project Structure
```
. Intrusion-Detection-System/
├── .ipynb_checkpoints/
├── UNSW-NB15_1.csv
├── UNSW-NB15_2.csv
├── UNSW-NB15_3.csv
├── UNSW-NB15_4.csv
├── UNSW-NB15_LIST_EVENTS.csv
├── UNSW-NB15_features.csv
├── UNSW_NB15_testing-set.csv
├── UNSW_NB15_training-set.csv
├── Intrusion_Detection_System.ipynb  <- Main Jupyter Notebook with full ML pipeline
├── unsw_intrusion_classifier.pkl  <- Saved best classification model (RandomForest)
└── README.md
```

## ⚙️ Installation & Setup Instructions
To set up the project locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Shyamsundaryadav23/Security-Threat-Intrusion-Detection-using-Machine-Learning
    cd Intrusion-Detection-System
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: .venv\Scriptsctivate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn imbalanced-learn jupyter
    ```

## ▶️ How to Run the Project

1.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```

2.  **Open the Notebook:**
    Navigate to and open `Intrusion_Detection_System.ipynb` in your browser.

3.  **Execute Cells:**
    Run all cells in the notebook sequentially to reproduce the data loading, preprocessing, model training, and evaluation steps.

    *Note: Ensure the dataset CSV files are placed in the same directory as the notebook or update the `base_path` variable in the notebook to your dataset location.* 

## 📈 Model Evaluation

### Regression Model (Predicting Flow Duration)
- **Best Model:** `LinearRegression`
- **Key Metrics:**
    - **RMSE:** ~1.169
    - **R² Score:** ~0.735
- **Insights:** The model shows reasonable performance in predicting flow duration, with residual analysis indicating errors centered around zero, though with some spread for higher duration values.

### Classification Model (Detecting Intrusion)
- **Best Model:** `RandomForest`
- **Key Metrics:**
    - **Accuracy:** ~0.992
    - **Precision:** ~0.985
    - **Recall:** ~0.999
    - **F1 Score:** ~0.992
    - **ROC AUC:** ~0.999
    - **PR AUC:** ~0.998
- **Insights:** The RandomForest classifier demonstrates exceptional performance in detecting network intrusions, achieving high scores across all metrics. The high recall and precision, coupled with a high F1-score and AUCs, confirm its effectiveness, especially after addressing class imbalance with SMOTE.

### Clustering Model (Anomaly Detection)
- **Algorithm:** `MiniBatchKMeans`
- **Optimal Clusters:** 2
- **Silhouette Score:** ~0.64
- **Insights:** The clustering analysis successfully identified two distinct groups within the network traffic data, likely corresponding to normal and anomalous traffic. The good silhouette score and visual separation in PCA plots validate the effectiveness of the unsupervised approach for anomaly detection.

## 🔮 Future Improvements
- **Advanced Feature Engineering:** Explore more complex interaction features or time-series based features.
- **Deep Learning Models:** Experiment with Neural Networks, LSTMs, or CNNs for enhanced detection capabilities.
- **Real-time Detection:** Integrate the trained models into a real-time stream processing framework for live intrusion detection.
- **Explainable AI (XAI):** Implement techniques to explain model predictions, providing more transparency for security analysts.
- **Ensemble Methods:** Investigate stacking or boosting techniques to combine multiple models for improved performance and robustness.
- **Hyperparameter Tuning:** Conduct more exhaustive hyperparameter optimization for all models using techniques like GridSearchCV or RandomizedSearchCV.

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
