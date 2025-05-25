# 💳 Credit Card Fraud Detection App

This project detects fraudulent credit card transactions using **unsupervised machine learning (Isolation Forest)** and provides an easy-to-use **Gradio web interface** for interactive testing.

---

## 🚀 Project Overview

Every day, thousands of credit card transactions happen—and a small portion of them are fraudulent. The goal of this project is to detect those **anomalous (suspicious)** transactions without needing millions of labeled fraud examples.

We use:
- ✅ Real-world anonymized credit card dataset
- 🧠 Isolation Forest (anomaly detection algorithm)
- 🌐 Gradio interface to make detection interactive

---

## 🛠️ How It Works

1. **Data Preprocessing**  
   - Scales `Time` and `Amount` features.
   - Drops unscaled versions and prepares 30 total features:  
     `Time`, `Amount`, and 28 anonymized features (`V1` to `V28`).

2. **Model Training**  
   - Uses **Isolation Forest**, an unsupervised model that identifies outliers (i.e., frauds) in the data.
   - Trained only on `X_train`, no explicit labels used during training.

3. **Fraud Prediction**  
   - The trained model predicts whether a new transaction is:
     - **Legitimate (0)**
     - **Fraudulent (1)**

4. **Gradio Interface**  
   - Users can input transaction data through a simple web interface.
   - The model instantly returns whether the transaction is suspicious.

---

## 📊 Dataset

- 📂 File: `creditcard.csv`
- 🔍 Source: [Kaggle Credit Card Fraud Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- ⚠️ Highly imbalanced:
  - Legitimate: ~284,000+
  - Fraud: ~490

---

## 📈 Evaluation Metrics

| Metric      | Value (Approx.) |
|-------------|-----------------|
| Accuracy    | ~99.9%          |
| Fraud Recall| ~30–33%         |
| Fraud Precision| ~30%        |

> Most transactions are legitimate, so accuracy is very high.
> But we're more focused on identifying rare fraudulent activity (recall, precision).

---

## 🧪 Example Input for Gradio App

To test a transaction, you'll need to input:

```text
Time: 100000  
Amount: 50.00  
V1 to V28: Random values between -5.0 and 5.0 (for testing)
