# 🛡️ Fraud Detection Model for ASB Bank

> **Strengthening Fraud Detection, Securing Customer Trust**  
> This project builds a robust machine learning model using R to detect fraudulent banking transactions and recommends a two-tier flagging system for ASB Bank to enhance its fraud management framework.

---

## 📖 Background

As ASB Bank navigates a rapidly digitizing landscape, the risk of fraudulent transactions continues to grow. The current detection systems face limitations in identifying evolving fraud patterns, exposing the bank to financial losses and customer trust issues.

Our role as data consultants was to analyze transaction data, build predictive models in R, and design a scalable solution to improve fraud detection accuracy while minimizing false positives that could frustrate legitimate customers.

---

## 💾 Dataset Overview

- **500,000 observations** across **13 variables**  
- **Synthetic data** (May–July 2024)  
- Fraud rate: **~2%**

### Key Variables
| Feature | Description |
|---------|-------------|
| `amount` | Transaction amount |
| `agent_category` | Channel used (ATM, mobile, desktop) |
| `transaction_type` | Withdrawal, purchase, or transfer |
| `transaction_day` | Day of the week |
| `age` | Client age |
| `fraud` | 1 = fraudulent, 0 = non-fraudulent |

---

## 📊 Exploratory Data Insights

- **Older customers** face a higher fraud risk  
- **Withdrawals and transfers** are more fraud-prone than purchases  
- Fraud is **evenly spread** across weekdays  
- Fraudulent transactions typically have a **median amount of $100**  
- **Agent usage**: ATM (34%), Mobile (29%), Desktop (24%), Others (13%)

---

## 🧠 Objective

1. Build a classification model to detect transactions with a high likelihood of fraud  
2. Provide a fraud response strategy (e.g., flagging system)  
3. Prioritize model **sensitivity** and **precision** to balance fraud detection and customer experience

---

## 🛠️ Tools Used

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-00599C?style=for-the-badge)
![LightGBM](https://img.shields.io/badge/LightGBM-3C8031?style=for-the-badge)
![Random Forest](https://img.shields.io/badge/RandomForest-forestgreen?style=for-the-badge)
![Logistic Regression](https://img.shields.io/badge/Logistic_Regression-0A66C2?style=for-the-badge)
![Quarto](https://img.shields.io/badge/Quarto-48C2C5?style=for-the-badge&logo=quarto&logoColor=white)

---

## 🔍 Approach

| Step | Task |
|------|------|
| 1. Data Preparation | Cleaned and transformed the dataset using `tidyverse` and base R |
| 2. EDA | Conducted visual and statistical analysis (T-test, Chi-square) |
| 3. Preprocessing | Encoded categorical variables, normalized features, and applied upsampling |
| 4. Modeling | Built Logistic Regression, Random Forest, LightGBM, and XGBoost models |
| 5. Evaluation | Compared performance based on accuracy, sensitivity, PPV, and ROC-AUC |
| 6. Interpretation | Identified top predictors of fraud |
| 7. Recommendations | Proposed a risk-based fraud response strategy

---

## 🧪 Model Evaluation

| Model | Accuracy | Sensitivity | PPV | ROC-AUC |
|-------|----------|-------------|-----|---------|
| Logistic Regression | 0.672 | 0.717 | 0.048 | — |
| Random Forest | 0.747 | 0.771 | 0.066 | — |
| LightGBM | 0.760 | 0.781 | 0.070 | — |
| **XGBoost** *(Best)* | **0.761** | **0.780** | **0.070** | ✅ |

> Evaluation emphasized **sensitivity** (catching frauds) and **precision** (reducing false alerts).

---

## 🔍 Feature Importance

| Rank | Feature |
|------|---------|
| 1 | Age |
| 2 | Transaction Amount |
| 3 | Transaction Type (Withdrawal) |
| 4 | Transaction Day (Wednesday) |
| 5 | Agent Type (ATM) |

---

## ✅ Recommendation: Two-Tier Fraud Flagging System

| Tier | Trigger | Action |
|------|--------|--------|
| 🔹 Low Risk | <$100, normal activity | Automated alert (SMS/email) |
| 🔸 High Risk | >$500 or suspicious pattern | 2FA + customer service call |

### Additional Suggestions:
- Introduce OTPs and biometric verification
- Set daily limits for high-risk withdrawals and transfers
- Offer security delay (30–60 mins) for flagged transactions
- Automate PIN/security reminders to customers

---

## ⚠️ Disclaimer

This project was developed as part of academic coursework and is shared here for educational and portfolio purposes only.  
Unauthorized use, reproduction, or distribution is not permitted and may violate academic integrity policies.

