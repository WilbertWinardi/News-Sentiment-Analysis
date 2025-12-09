# News Sentiment Analysis using Transformer Models

Research about NLP models performance with news sentimen analysis

**Author:** Wilbert Winardi (NIM: 2702238716)

## 📌 Project Overview
This project performs **Sentiment Analysis** on news articles to classify them into **Positive**, **Neutral**, or **Negative** categories. The primary focus is to compare the efficiency and accuracy of various Transformer-based models to determine the optimal solution for this task.

## 📂 Dataset Information
* **Source:** [Kaggle - News Sentiment Analysis](https://www.kaggle.com/datasets/clovisdalmolinvieira/news-sentiment-analysis)
* **Total Samples:** 3,500 rows.
* **Features Used:** * Input: `Description` (News summary).
    * Target: `Sentiment` (Encoded as 0, 1, 2).

## 🛠️ Methodology
1.  **Preprocessing:** Lowercasing, removing URLs, punctuation (`[^\w\d\s\-]`), and numbers (`\d+`) to reduce bias.
2.  **Vectorization/Tokenization:** Using Pre-trained Tokenizers (e.g., `google/electra-small-discriminator`).
3.  **Data Split:** 80% Training / 20% Testing.

## 📊 Model Evaluation & Results
We experimented with 4 models using GPU T4 acceleration. **ELECTRA** was selected as the best model due to its superior training speed with comparable accuracy.

| Model | Accuracy | Training Time | Status |
| :--- | :---: | :---: | :--- |
| **ELECTRA** | **89%** | **2 min 59 sec** | **✅ Selected** |
| DistilBERT | 90% | 7 min 4 sec | - |
| RoBERTa | 89% | 14 min 54 sec | - |
| DeBERTa | 90% | 18 min 17 sec | - |

### ELECTRA Performance Report
```text
              precision    recall  f1-score   support

    negative       0.75      0.70      0.72       115
     neutral       0.91      0.87      0.89       158
    positive       0.91      0.94      0.93       427

    accuracy                           0.89       700
   macro avg       0.86      0.84      0.85       700
weighted avg       0.88      0.89      0.88       700
