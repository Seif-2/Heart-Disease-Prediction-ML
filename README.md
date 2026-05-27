# ❤️ Heart Disease Prediction — Graduation Project

A machine learning project for predicting the likelihood of heart disease in patients using clinical and demographic data.

---

## 📌 Overview

Heart disease is one of the leading causes of death worldwide. This project applies machine learning techniques to predict the presence of heart disease based on patient data, enabling early diagnosis and better clinical decision-making.

---

## 📁 Project Structure

```
heart-disease/
├── data/
│   ├── raw/                  # Original dataset files
│   └── processed/            # Cleaned and preprocessed data
├── notebooks/
│   ├── 01_eda.ipynb          # Exploratory Data Analysis
│   ├── 02_preprocessing.ipynb
│   └── 03_modeling.ipynb
├── models/
│   └── best_model.pkl        # Saved trained model
├── src/
│   ├── preprocess.py
│   ├── train.py
│   └── evaluate.py
├── requirements.txt
└── README.md
```

---

## 📊 Dataset

- **Source:** [UCI Heart Disease Dataset](https://archive.ics.uci.edu/ml/datasets/Heart+Disease) (Cleveland)
- **Samples:** 303 patients
- **Features:** 13 clinical attributes

| Feature | Description |
|---|---|
| `age` | Age of the patient |
| `sex` | Sex (1 = male, 0 = female) |
| `cp` | Chest pain type (0–3) |
| `trestbps` | Resting blood pressure (mm Hg) |
| `chol` | Serum cholesterol (mg/dl) |
| `fbs` | Fasting blood sugar > 120 mg/dl |
| `restecg` | Resting ECG results |
| `thalach` | Maximum heart rate achieved |
| `exang` | Exercise-induced angina |
| `oldpeak` | ST depression induced by exercise |
| `slope` | Slope of peak exercise ST segment |
| `ca` | Number of major vessels (0–3) |
| `thal` | Thalassemia type |
| `target` | **1 = Heart disease present, 0 = Absent** |

---

## ⚙️ Methodology

### 1. Exploratory Data Analysis (EDA)
- Distribution of features across target classes
- Correlation heatmap
- Outlier detection

### 2. Preprocessing
- Handling missing values
- Feature scaling (StandardScaler / MinMaxScaler)
- Encoding categorical variables
- Train/test split (80% / 20%)

### 3. Models Trained
- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine (SVM) *(best performing)*
- K-Nearest Neighbors (KNN)

### 4. Evaluation Metrics
- Accuracy
- Precision, Recall, F1-Score
- ROC-AUC Curve
- Confusion Matrix

---

## 📈 Results

| Model | Test Accuracy | CV Accuracy | F1-Score | ROC-AUC | FN Rate |
|---|---|---|---|---|---|
| LR (Baseline) | 75.9% | 76% | 0.712 | — | ~35% |
| Random Forest | 85.2% | 85% | 0.807 | 0.9697 | 14.3% |
| KNN (Tuned) | 88.5% | 89% | 0.800 | 0.9751 | 14.3% |
| **SVM (Tuned) ★** | **91.8%** | **88.5%** | **0.877** | **0.9848** | **10.7%** |

> ✅ **Best Model: Tuned SVM (RBF kernel, C=0.1, gamma=scale)** — highest ROC-AUC (0.9848), lowest FN rate (10.7%), and best single-run accuracy (91.8%)

---

## 🚀 Installation & Usage

### Prerequisites
- Python 3.8+
- pip

### 1. Clone the repository
```bash
git clone https://github.com/your-username/heart-disease-prediction.git
cd heart-disease-prediction
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run preprocessing
```bash
python src/preprocess.py
```

### 4. Train the model
```bash
python src/train.py
```

### 5. Evaluate the model
```bash
python src/evaluate.py
```

---

## 📦 Requirements

```
pandas
numpy
scikit-learn
matplotlib
seaborn
joblib
jupyter
```

---

## 🔮 Future Work

- [ ] **Larger Dataset** — expand beyond 302 patients for greater reliability
- [ ] **Deep Learning** — explore neural networks and attention models for complex pattern detection
- [ ] **Clinical Trial** — formal validation with power analysis and outcome tracking
- [ ] **EHR Integration** — connect CardioPredict to hospital systems for direct clinical use
- [ ] **Severity Model** — ordinal/multi-output classification to recover the 5-class disease severity

---

## 👨‍🎓 Author

**Seif Mahmoud Abdelmonem**
SRN: 202200087
BSc Computer Science (Artificial Intelligence)
University of Hertfordshire GAF | May 2026
Supervisor: Dr. Mohamed Abdelaleem

---

## 📄 License

This project is developed for academic purposes as part of a graduation requirement.

---

> *"Early detection saves lives."*
