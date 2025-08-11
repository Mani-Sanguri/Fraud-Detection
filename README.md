# 🕵️‍♂️ Fraud Detection: EDA & Predictive Modeling

A comprehensive data analysis and machine learning project for detecting fraudulent transactions using **Python**, **Pandas**, **Matplotlib/Seaborn**, and **Scikit-learn**. The project includes **exploratory data analysis (EDA)**, identification of fraud patterns, and a machine learning model built to detect fraudulent activity.

---

## 📂 Dataset Overview
- **Rows:** 1,296,675 transactions  
- **Features:** 13 columns  
- **Period Covered:** Jan 2019 – Jun 2020  
- **Target Variable:** `is_fraud` (Boolean)

### **Feature Description**
| Column      | Description |
|-------------|-------------|
| merchant    | Merchant name |
| category    | Transaction category |
| amt         | Transaction amount (₹) |
| gender      | Customer gender |
| street, city, state | Customer location details |
| job         | Customer occupation |
| trans_num   | Transaction ID |
| is_fraud    | Fraud label |
| date, time  | Transaction date & time |
| name        | Customer name |

---

## 🔍 EDA Highlights

### **1. Temporal Patterns**
- **Weekends (Sat/Sun):** Highest fraud activity.
- **Months:** March & May peak; July/August lowest.
- **Hours:** 40% of frauds occur between **22:00–23:59**.

### **2. Transaction Value**
- Majority of frauds in the **₹1–₹100 range**.
- High-value frauds (>₹5,000) are rare.

### **3. Category-Level Risk**
- **High Risk:** `shopping_net`, `grocery_pos`, `misc_net`.
- **Moderate Risk:** `shopping_pos`, `gas_transport`.
- Digital/online channels have higher exposure.

### **4. Geographic/Demographic Risk**
- States with highest fraud volume & value: **TX, NY, CA**.
- Male-linked accounts have slightly higher total fraud amounts.

### **5. Repeat Offenders**
- Names like *Scott Martin* & *Jennifer Scott* appear 20+ times in fraud cases.
- Common traits: hundreds of merchants, uniform categories, daily activity.

---

## ⚠️ Key Fraud Red Flags
| Red Flag | Implication |
|----------|-------------|
| Weekend & night spike | Increase after-hours monitoring |
| Small value transactions | Add micro-transaction alerts |
| Repeat offenders | Possible organized fraud network |
| High-risk states | Deploy localized detection models |

---

## 🤖 Modeling
- **Algorithm:** Logistic Regression (with SMOTE for class imbalance)
- **Metrics:**
  - Recall: **75%**
  - Precision: **5%**
  - ROC-AUC: **0.90+**
- **Interpretation:**
  - High recall → catches most frauds (good for internal alerts)
  - Low precision → needs threshold tuning to reduce false positives

### **Top Predictors**
1. `amt` (High transaction amounts linked to fraud)
2. `category_gas_transport`
3. `category_grocery_pos`
4. `category_personal_care`
5. `category_kids_pets`

---

## 📈 Recommendations

**Immediate:**
- Monitor weekends, night hours, and small-value transactions in high-risk categories.
- Flag repeat offender accounts.

**Strategic:**
- Build state-specific detection models.
- Enhance authentication for online transactions.
- Layer models to reduce false positives.

---

## 🛠 Tech Stack
- **Languages:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Imbalanced-learn
- **ML Techniques:** Logistic Regression, SMOTE, Feature Engineering
- **Visualization:** Seaborn, Matplotlib

---

## 📜 Project Structure
```plaintext
├── data/                  # Raw and processed data files
├── notebooks/             # Jupyter notebooks for EDA & modeling
├── scripts/               # Python scripts for preprocessing and training
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies
