# Quantifying Digital Distractions  
### Predictive Productivity Modeling Using Multi-Model AI, Deep Learning, and Explainable AI

---

## Project Overview

This project investigates the impact of digital lifestyle patterns—particularly social media usage—on actual productivity levels. Leveraging machine learning, deep learning, and explainable AI (LIME), it builds predictive models that quantify distraction and offer interpretable insights.

The work combines behavioral analysis with modern AI techniques to enhance our understanding of digital distraction in professional and academic settings.

---

## Dataset Summary

- **Filename**: `social_media_vs_productivity.csv`
- **Records**: 30,000
- **Description**: Simulated behavioral dataset capturing individual digital habits, such as:
  - Social media usage patterns
  - Sleep and work habits
  - Notification count
  - Stress and burnout indicators
  - Actual vs perceived productivity scores

### Selected Features

- **Demographics**: `age`, `gender`, `job_type`
- **Digital Behavior**: `daily_social_media_time`, `social_platform_preference`, `screen_time_before_sleep`, `number_of_notifications`
- **Wellness**: `stress_level`, `coffee_consumption_per_day`, `days_feeling_burnout_per_month`
- **Work Context**: `work_hours_per_day`, `breaks_during_work`, `job_satisfaction_score`, `internet_speed`, `noise_level_during_work`
- **Digital Interventions**: `uses_focus_apps`, `has_digital_wellbeing_enabled`
- **Targets**: `actual_productivity_score`, `perceived_productivity_score`

---

## Exploratory Data Analysis Highlights

- Strong negative correlation observed between notification frequency and actual productivity.
- Excessive screen time before sleep linked to lower productivity.
- Focus app usage and digital wellbeing features positively influence productivity outcomes.
- Non-linear patterns suggested the need for model ensembles and feature engineering.

---

## Feature Engineering

To extract deeper behavioral insights, the following features were engineered:

- `productivity_gap = perceived_productivity_score - actual_productivity_score`
- `screen_sleep_ratio = screen_time_before_sleep / daily_social_media_time`
- `offline_ratio = weekly_offline_hours / (7 * 24)`

These features enhanced model explainability and predictive performance.

---

## Model Training and Evaluation

A wide range of regression models were trained and evaluated using R², MAE, and RMSE:

### Linear Models
- Linear Regression
- Ridge
- Lasso
- ElasticNet

### Ensemble and Tree-Based Models
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost
- AdaBoost
- CatBoost

### Kernel Method
- Support Vector Regressor (SVR)

**Observation**: CatBoost and Random Forest delivered the best performance across most evaluation metrics.

---

## Deep Learning Model

Implemented a fully connected feedforward neural network with the following configuration:

- Input: Normalized continuous and encoded categorical features
- Layers: Dense → Batch Normalization → LeakyReLU → Dropout
- Output: Single neuron for regression output
- Loss Function: Mean Squared Error (MSE)
- Optimizer: Adam with learning rate decay

The model showed strong convergence and robust generalization, with performance on par with tree-based models.

---

## Explainable AI: LIME

LIME (Local Interpretable Model-agnostic Explanations) was used to interpret individual predictions.

It allowed localized analysis for each user, revealing which features most influenced productivity—for example:

- High stress level and low offline hours were dominant contributors to lower productivity predictions.
- Individuals with frequent breaks and digital wellbeing features active showed better predicted scores.

---

## Key Takeaways

- Digital distractions can be modeled with measurable impact using machine learning.
- Engineered features like productivity gap and screen-sleep ratio provided valuable behavioral insights.
- Deep learning matched ensemble models in performance when regularized effectively.
- LIME added interpretability, enhancing ethical transparency of predictions.

---

## Project Structure

```bash
quantifying-digital-distraction/
├── data/
│   ├── raw/
│   │   └── social_media_vs_productivity.csv
│   └── processed/
│       └── processed_data.csv
│
├── notebook/
│   └── quantifying-digital-distraction.ipynb
│
├── outputs/
│   ├── evaluation_report.txt
│   ├── learn_error.tsv
│   ├── model_results.csv
│   └── predictions.csv
│
├── visualizations/
│   ├── eda/
│   │   ├── Plot1.png
│   │   ├── Plot-2.png
│   │   ├── ...
│   │   └── Plot-18.png
│   └── explainability/
│       ├── Plot-24.png
│       └── Screenshot 2025-06-28 233903.png
│
├── model/
│   └── (trained model files go here)
│
├── docs/
│   ├── dataset.md
│   ├── eda.md
│   ├── feature_engineering.md
│   ├── models.md
│   ├── deep_learning.md
│   ├── explainability.md
│   └── takeaways.md
│
├── requirements.txt
└── README.md
---
```

## 🤝 Contributing

We welcome contributions of all kinds — whether it's fixing bugs, enhancing documentation, or proposing new models and ideas.

Before getting started, please refer to our [CONTRIBUTING.md](./CONTRIBUTING.md) guide for best practices and setup instructions.

## How to Run

### install Dependencies
```bash
pip install -r requirements.txt

