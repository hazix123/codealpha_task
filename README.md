💳 Credit Scoring Model

Predicting an individual's creditworthiness from financial history using classical machine learning classifiers, with an interactive Streamlit demo for real-time predictions.

📌 Objective

Given an applicant's financial profile, predict whether they are a **good credit risk (creditworthy)** or a **high credit risk**, and surface the probability behind that decision so the result is explainable rather than a black box.

🧠 Approach

- Classification algorithms: Logistic Regression, Decision Tree, and Random Forest, trained and compared side by side.
- Feature engineering: derived features such as debt-to-income ratio computed from raw financial history.
- Evaluation: Precision, Recall, F1-Score, and ROC-AUC, plus ROC curves and confusion matrices for each model.

🗂️ Features Used

| Feature | Description |
|---|---|
| `income` | Annual income ($) |
| `debt` | Total outstanding debt ($) |
| `credit_history_years` | Length of credit history (years) |
| `num_late_payments` | Late payments in the last 12 months |
| `credit_utilization` | Fraction of available credit currently used |
| `num_open_accounts` | Number of open credit accounts |
| `debt_to_income` | Engineered ratio: `debt / income` |

> The repo ships with a synthetic dataset generator so the project runs end-to-end out of the box. Swap in a real dataset (e.g. UCI Credit Approval, Kaggle "Give Me Some Credit", or your own labelled financial-history data) with the same column names to train on real data.

🏗️ Project Structure

```
credit-scoring-model/
├── credit_scoring_app.py     # Streamlit app: data generation, training, UI
├── requirements.txt
└── README.md
```

⚙️ Installation

```bash
git clone https://github.com/<your-username>/credit-scoring-model.git
cd credit-scoring-model
pip install -r requirements.txt
```

requirements.txt
```
streamlit
scikit-learn
pandas
numpy
matplotlib
```

App walkthrough

1. Predict tab — enter income, debt, credit history length, late payments, utilization, and open accounts; choose a model; click **Predict creditworthiness** to get a label and probability.
2. Model Performance tab — compares Logistic Regression, Decision Tree, and Random Forest on Precision, Recall, F1-Score, and ROC-AUC, with ROC curves and a confusion matrix per model.
3. Dataset tab — preview of the (synthetic) training data.

📊 Results

| Model | Precision | Recall | F1-Score | ROC-AUC |
|---|---|---|---|---|
| Logistic Regression | _fill in after training_ | | | |
| Decision Tree | | | | |
| Random Forest | | | | |

> Metrics regenerate automatically in the app each run since the dataset is freshly sampled; pin a `random_state`/seed (already set to 42) for reproducible numbers, or replace the metrics table above with results from your real dataset.

 🚀 Future Improvements

- Train on a real-world labelled credit dataset instead of synthetic data.
- Add SHAP/feature-importance explanations for individual predictions.
- Hyperparameter tuning (GridSearchCV / Optuna) for each model.
- Persist trained models with `joblib` so the app doesn't retrain on every restart.
📄 License

MIT License — feel free to use, modify, and share

