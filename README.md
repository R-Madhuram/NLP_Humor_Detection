# 📘 NLP Humor Detection — Business ML Case Study

## 1️⃣ Executive Summary (Business Problem)

This project builds a humor detection NLP classifier using labeled short-form text from the ColBERT Humor Dataset. The objective is to determine whether a given piece of text is humorous or non-humorous, enabling platforms to better understand tone and intent in user-generated content.

Rather than focusing on a single model, this project evaluates multiple modeling strategies across:

* Text normalization choices (stemming vs. lemmatization)

* Vectorization approaches (Count Vectorizer vs. TF-IDF)

* Interpretable classification models

This mirrors how ML systems are developed in industry: compare, measure, and choose the simplest model that performs best.

## 2️⃣ Real-World Applications & Business Impact 

This humor detection capability can be embedded into production systems such as:

### User & Brand Analytics

* Prevent sentiment models from misclassifying sarcasm

* Improve accuracy of engagement and feedback analysis

### Content Platforms

* Improve moderation by distinguishing humor from harmful or serious content

* Prevent over-penalizing sarcastic or playful user interactions

### Conversational AI

* Adjust tone dynamically (serious vs. playful)

* Avoid inappropriate humor in sensitive contexts

In practice, this model would operate upstream of sentiment analysis, recommendation ranking, or AI response generation.

## Models & Metrics (What Was Tested and Why)

### 3️⃣ Models Evaluated

Three commonly deployed NLP classifiers were tested:

* 1. Logistic Regression — strong linear baseline, scalable, easy to interpret

* 2. Decision Tree — rule-based model, useful for interpretability comparisons

* 3. Naive Bayes — probabilistic baseline commonly used in text classification

Each model was evaluated under 12 configurations, combining:

* 1. Stemming vs. Lemmatization

* 2. Count Vectorization vs. TF-IDF

Hyperparameter tuning via grid search

### Metrics Used

* Accuracy (primary metric) — percentage of correctly classified text

Accuracy is appropriate here because:

The task is balanced binary classification

Misclassification cost is symmetric at this stage of evaluation

## 4️⃣ Model Performance Summary & Iteration Insights 

<img width="689" height="470" alt="image" src="https://github.com/user-attachments/assets/c6a98351-da7c-437c-96d5-c7b6d01acc1f" />

The chart above summarizes accuracy across 12 NLP pipelines combining 
*  3 models (Logistic Regression, Decision Tree, Naive Bayes)
*  2 preprocessing strategies (Stemming vs. Lemmatization)
*  2 vectorization methods (Count Vectorizer vs. TF-IDF)

Logistic Regression consistently outperformed Decision Trees and Naive Bayes, achieving close to 90% accuracy across all configurations.
Logistic Regression Is the Clear Winner

### ➡️ Business translation:
A simple, scalable model performs best — ideal for production systems.

Lemmatization provided an incremental but consistent improvement over stemming across most pipelines and Count Vectorization slightly outperformed TF-IDF in peak accuracy that suggests humor detection relies on word presence more than rarity. 

### ➡️ Business translation:
Simpler representations can outperform more complex weighting schemes and Small preprocessing decisions can meaningfully improve downstream accuracy
These results highlight that preprocessing and representation choices had a greater impact on performance than increasing model complexity.

## 5️⃣ Business Impact

From a business standpoint, this project demonstrates:
- Improved user experience, user insights and trust

- Reliable tone detection at scale

- Reduced downstream error propagation

- Lower moderation and review costs

At big tech scale platforms, even a 1–2% improvement in text interpretation accuracy can influence:

- Millions of content decisions

- AI interaction quality

- Platform safety metrics
