# ⚡ PowerCo Customer Churn Analysis

Investigating whether price sensitivity drives customer churn at an energy provider, using Python and a random forest classifier (BCG X data science job simulation on Forage).

## What it does
PowerCo, an energy provider for small and medium-sized businesses, is losing customers to competitors. Its main suspect is price sensitivity. This project tests that hypothesis by following the 5-step data science process: frame the problem, explore and clean the data, engineer features, train a model, and report the findings. It ends with a one-slide executive summary written for client stakeholders.

## Key Findings
- **Churn is high:** about 1 in 10 of PowerCo's 14,606 customers (9.7%) left. The data is imbalanced, roughly 90% stayed and 10% churned.
- **Price is a contributor, not the main driver.** The five most important features in the model were net and gross power margin, 12-month consumption, forecast meter rent and net margin. 35 of the 61 features are price-related, and together they hold about 40% of the model's total importance, but the highest-ranked price feature came 11th.
- **Accuracy is misleading here.** The baseline model scored 0.90 accuracy, but a model that predicts "stays" for everyone also scores about 0.90. Its recall on churners was only 0.05, meaning it caught about 18 of 366 customers who left (precision 0.77).
- **Rebalancing helped, with a trade-off.** Using `class_weight='balanced'` raised churn recall to 0.15 but lowered precision to 0.44 (F1 0.22): more churners caught, more false alarms.
- **Verdict:** the model is not reliable enough to act on yet.
- **Recommended next steps:** add data that wasn't available (complaints, outages, service history), improve and tune the model, and test directly whether price changes move churn.
- **Caveat:** feature importance shows which columns helped the model, not what causes churn, and a model this weak gives hints, not proof.

## Tools Used
- Python
- Jupyter Notebook
- pandas and NumPy
- Matplotlib and seaborn
- scikit-learn (random forest, train/test split, classification metrics)

## Concepts Covered
- Framing a business problem as a testable hypothesis
- Exploratory data analysis: data types, distributions, skew, churn rate
- Feature engineering: percentage price changes, date-based features (tenure, days to contract end), one-hot encoding, log transform, dropping near-duplicate columns using correlation
- Handling divide-by-zero blanks in derived features
- Class imbalance and why accuracy can mislead
- Precision, recall and F1 per class
- Random forest classification and feature importance
- Communicating results to non-technical stakeholders (executive summary in Situation / Complication / Question / Solution format)

## Repo Structure
```
powerco-churn-analysis/
├── README.md
├── 01_business_understanding.md
├── 02_eda.ipynb
├── 03_feature_engineering.ipynb
├── 04_modeling.ipynb
└── 05_PowerCo_Executive_Summary.pdf
```

## Setup / Dependencies / Files Needed
**Libraries:** Python 3, Jupyter, pandas, NumPy, Matplotlib, seaborn, scikit-learn

**Data files (download from the Forage simulation, not included in this repo):**
- `client_data.csv` and `price_data.csv` (EDA and feature engineering)
- `clean_data_after_eda.csv` (feature engineering)
- `data_for_predictions.csv` (modeling, the final dataset provided in the simulation)

Place the data files in the same folder as the notebooks before running them.

## Note
This is a self-study job simulation. It is not an employment relationship with BCG.

Built step by step, and the real learning was in the questions, not just the code. 🚀
