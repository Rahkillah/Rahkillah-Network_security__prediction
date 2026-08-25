# 🛡️ Network Intrusion Detection System (NIDS)

[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-%234A8C8C.svg?style=for-the-badge&logo=seaborn&logoColor=white)](https://seaborn.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

## 🔍 Overview

This project implements a comprehensive **Network Intrusion Detection System** using multiple machine learning classifiers to distinguish between normal network traffic and anomalous (potentially malicious) behavior. The system is built on the widely-used **NSL-KDD** dataset, a refined version of the classic KDD Cup 1999 dataset, which is a benchmark in the field of network security.

The core objective is to develop and evaluate a predictive model capable of accurately identifying network intrusions in real-time or near real-time, which is crucial for maintaining the security and integrity of modern network infrastructures.

## 📁 Project Structure

network_security_prediction/
│
├── network_security_prediction.ipynb # Main Jupyter Notebook
├── Train_data.csv # Training dataset (NSL-KDD)
├── Test_data.csv # Testing dataset (NSL-KDD)
└── README.md # Project documentation


## 🧠 Algorithms & Techniques

The project explores a variety of classification algorithms, leveraging both classical and ensemble methods:

- **Decision Tree Classifier (DTC)**
- **Random Forest Classifier (RFC)** – *for feature importance analysis*
- **K-Nearest Neighbors (KNN)**
- **Logistic Regression (LGR)**
- **Naive Bayes Classifier (BernoulliNB)**

**Additional Techniques:**
- **Feature Scaling** using `StandardScaler`
- **Label Encoding** for categorical features
- **Feature Selection** using Recursive Feature Elimination (RFE)
- **Cross-Validation** to ensure model robustness
- **Performance Metrics**: Accuracy, Confusion Matrix, Classification Report

## 📊 Dataset: NSL-KDD

The dataset used is the **NSL-KDD** dataset, a widely accepted benchmark for intrusion detection. It contains a variety of network connection records, each labeled as either `normal` or `anomaly`.

- **`Train_data.csv`**: 25,192 instances
- **`Test_data.csv`**: 22,544 instances

**Key Features** (41 total):
- `duration`, `protocol_type`, `service`, `flag`
- `src_bytes`, `dst_bytes`, `land`, `wrong_fragment`
- `urgent`, `hot`, `num_failed_logins`, `logged_in`
- `num_compromised`, `root_shell`, `su_attempted`, `num_root`
- `num_file_creations`, `num_shells`, `num_access_files`
- `is_host_login`, `is_guest_login`
- `count`, `srv_count`, `serror_rate`, `srv_serror_rate`
- `rerror_rate`, `srv_rerror_rate`, `same_srv_rate`
- `diff_srv_rate`, `srv_diff_host_rate`, `dst_host_count`
- `dst_host_srv_count`, `dst_host_same_srv_rate`
- `dst_host_diff_srv_rate`, `dst_host_same_src_port_rate`
- `dst_host_srv_diff_host_rate`, `dst_host_serror_rate`
- `dst_host_srv_serror_rate`, `dst_host_rerror_rate`
- `dst_host_srv_rerror_rate`

## 📈 Results & Performance

The models were evaluated on the test set with the following accuracy scores:

| Model | Test Accuracy |
|------|---------------|
| **Decision Tree** | **100%** |
| **K-Nearest Neighbors** | **~99.4%** |
| **Naive Bayes** | **~90.7%** |
| **Logistic Regression** | **~95.5%** |

> *Note: The Decision Tree model achieved perfect accuracy on the test split of the training set, but caution is advised against potential overfitting. Cross-validation scores provide a more realistic estimate of performance.*

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.8+ installed. Then install the required libraries:

pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

### Running the Notebook

1. Clone this repository:
```bash
git clone https://github.com/yourusername/network-security-prediction.git

cd network-security-prediction
```
2. Launch Jupyter Notebook:
```bash
   jupyter notebook
```
3. Open `network_security_prediction.ipynb` and run all cells.

## 🔬 Key Steps in the Notebook

1. **Data Loading & Exploration**
   - Load `Train_data.csv` and `Test_data.csv`
   - Perform descriptive statistics and data inspection

2. **Data Preprocessing**
   - Drop redundant columns (e.g., `num_outbound_cmds`)
   - Scale numerical features using `StandardScaler`
   - Encode categorical features with `LabelEncoder`

3. **Feature Engineering & Selection**
   - Use Random Forest to evaluate feature importance
   - Apply Recursive Feature Elimination (RFE) to select top 15 features

4. **Model Training & Evaluation**
   - Train multiple classifiers on the processed data
   - Evaluate using cross-validation, accuracy, confusion matrix, and classification report

5. **Prediction & Visualization**
   - Predict on unseen test data
   - Visualize results with bar charts

## 📋 Example Output

============================== Decision Tree Classifier Model Evaluation ==============================

Cross Validation Mean Score:
 0.9956333771928133

Model Accuracy:
 1.0

Confusion matrix:
 [[8245    0]
 [   0 9389]]

Classification report:
               precision    recall  f1-score   support

     anomaly       1.00      1.00      1.00      8245
      normal       1.00      1.00      1.00      9389

    accuracy                           1.00     17634

## 📌 Note on Overfitting

While the **Decision Tree** model achieved 100% accuracy on the training test split, it is important to consider cross-validation scores (~99.56%) and test on completely unseen data to ensure generalizability. Overfitting is a common concern with complex models like Decision Trees on high-dimensional datasets.

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements, feature additions, or bug fixes, please open an issue or submit a pull request.

## 📄 License

This project is open-source and available under the **MIT License**.

## 👤 Author

**Your Name**  
[GitHub](https://github.com/yourusername) | [LinkedIn](https://linkedin.com/in/yourprofile)

---

🌟 If you find this project useful, please give it a star on GitHub!

