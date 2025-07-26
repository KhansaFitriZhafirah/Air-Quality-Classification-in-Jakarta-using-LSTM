# 🌫️ Air Quality Classification in Jakarta using LSTM

This project is the final assignment of the **Data Mining (KOM1338)** course at IPB University. We aimed to classify air quality conditions in **Jakarta** based on historical ISPU data using the **Long Short-Term Memory (LSTM)** model based on historical air pollution data from 2010 to 2021. The dataset is sourced from the Jakarta Environmental Agency and focuses on multivariate time-series data involving pollutants such as PM10, PM2.5, CO, SO₂, NO₂, and O₃.

---

## 📌 Project Highlights

- 📍 **Location**: Jakarta (Bundaran HI air quality station)
- 📈 **Model**: Stacked Multivariate LSTM for Multiclass Classification 
- 📊 **Accuracy**: 83.45% (testing data)
- 🧠 **Libraries**: TensorFlow, Scikit-learn, Pandas, Matplotlib, Seaborn, Sklearn

---

## 🧪 Methodology

### 1. 📥 Data Collection
- Sourced from **Kaggle** and **Satu Data Jakarta**
- Total records: 4383, spanning from 2010–2021

### 2. 🔧 Preprocessing
- Data cleaning & reduction (drop unused/duplicate columns)
- Imputation using forward fill (LOCF)
- Categorical encoding for target class (`Baik`, `Sedang`, `Tidak Sehat`)
- Normalization using `StandardScaler`
- Sliding Window (7-day input → 1-day prediction)

### 3. 🤖 Model Building
- Stacked LSTM with:
  - 2 LSTM layers (128 and 64 units)
  - Dropout: 0.2
  - Dense Softmax output
- Optimizer: `Adam` | Loss: `SparseCategoricalCrossentropy`
- Early Stopping: Yes

### 4. 📊 Evaluation
- Accuracy: **83.45%**
- F1-score: **0.8128**
- ROC-AUC: 0.85–0.90 across all classes
- Confusion matrix analysis

---

## 🧠 Insights

- The LSTM model was able to learn temporal air quality trends fairly well.
- The model struggles with minority class (`Tidak Sehat`) due to class imbalance.
- Potential improvements include class balancing or threshold tuning.


