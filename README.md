# ⚽ FIFA21 Player Value Prediction Analysis

### 👤 Author  
**Sayan Sinha**  
**Roll No:** 2023BCY0006  

---

## 🎯 Objective  

The objective of this project is to **predict a FIFA21 player's market value category** using Machine Learning.  

Instead of predicting an exact value (which is volatile and inconsistent), this project classifies players into **five categories**:  
- 🟢 Very Low  
- 🟡 Low  
- 🔵 Medium  
- 🟠 High  
- 🔴 Very High  

This classification approach offers a more **practical and interpretable** way to estimate player worth.

---

## 🧹 Data Cleaning & Preparation  

The dataset contained **17,125 players** and **107 features**, requiring extensive preprocessing to make it suitable for ML models.

### ✅ Steps Taken:

- **Dropped Irrelevant Columns:** Removed player ID, Name, and photo links.  
- **Monetary Conversion:** Converted values like `"€1.1M"` → `1100000`. Removed players with €0 value/wage.  
- **Unit Standardization:**  
  - Height (e.g., `6'0"`) → centimeters (cm)  
  - Weight (e.g., `181lbs`) → kilograms (kg)  
- **Cleaned Star Ratings:** Converted `"3 ★"` → `3`.  
- **Handled Missing Data:**  
  - **Numeric features:** Filled with **median**  
  - **Categorical features:** Filled with **mode**  

🧠 *Impact:*  
This cleaning process transformed raw, inconsistent data into a **fully numeric, standardized dataset**, essential for robust ML performance.

---

## 📊 Data Visualization Insights  

After cleaning, data visualization revealed key relationships between player features and market value.

### 📈 Key Insights:
- **Value vs Age:** Player value peaks between ages **20–30**, then declines gradually.  
- **Strongest Predictors:**  
  - **OVA (Overall Rating)**  
  - **POT (Potential)**  
  - **Wage_num**  
- **Radar Plot Findings:**  
  - Technical attributes like **Dribbling**, **Short Passing**, and **Shot Power** differ most across value categories.  
  - Physical attributes (e.g., Acceleration, Strength) are similar among high-tier players — implying **technical skill defines elite players**.

---

## 🧠 Model Building  

### 🔧 Feature Engineering
- Encoded categorical data (e.g., `Club`, `Nationality`) based on their **frequency** in the dataset.  
- Created a new **target variable (`Value_q`)** dividing player value into **five equal quantiles (quintiles)** to ensure balanced class distribution.

### 🔄 Data Preprocessing
- Converted all text features (e.g., `Best Position`, `Foot`) to numeric form.  
- Used automated pipelines for imputation and encoding.

---

## 🤖 Model Training & Evaluation  

Two ensemble learning models were trained and evaluated:

| Model          | Training Accuracy | Testing Accuracy | Overfitting Gap |
|----------------|-------------------|------------------|-----------------|
| Random Forest  | 90.06%            | 85.60%           | 4.46%           |
| XGBoost        | 97.36%            | 94.41%           | 2.95%           |

### 📊 Additional Metrics
- **Precision / Recall / F1-score (Macro Average):**
  - Random Forest: `0.86`
  - XGBoost: `0.94`
- **Confusion Matrix:**  
  XGBoost shows a clear diagonal dominance (fewer misclassifications).

---

## 🏁 Conclusion  

- **Best Model:** ✅ XGBoost  
- **Testing Accuracy:** `94.41%`  
- **Overfitting:** Minimal (`2.95%` gap)  
- **Final Verdict:**  
  XGBoost delivers the **most accurate, stable, and generalizable** predictions for FIFA21 player value classification.

---

## 📦 Tech Stack  

- **Language:** Python  
- **Libraries Used:**  
  - `pandas`, `numpy` – Data handling  
  - `matplotlib`, `seaborn` – Visualization  
  - `scikit-learn` – ML preprocessing & evaluation  
  - `xgboost` – Model training  
  - `randomforestclassifier` – Baseline model  

---

## 🚀 Future Improvements  

- Incorporate **deep learning** for enhanced performance.  
- Include **position-based value segmentation** (e.g., GK vs FW).  
- Use **real-time FIFA data updates** for continuous learning.  
- Develop an **interactive web dashboard** for predictions.

---

## 🧾 License  

This project is open-source and available under the **MIT License**.

---

**⭐ If you find this project interesting, give it a star on GitHub!**
