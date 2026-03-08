# Zoo Animal Classification

A predictive modelling project classifying animals into 7 categories
using Decision Tree, Random Forest and Gradient Boosting.

## Dataset
Zoo Dataset — 101 animals, 16 features, 7 classes

## Models Used
- Decision Tree
- Random Forest
- Gradient Boosting (best performer — 90% accuracy, macro F1: 0.73)

## Key Findings
- Gradient Boosting outperformed other models
- Most important features: milk, feathers, fins
- Class imbalance handled using class_weight='balanced'

## Tools
Python, scikit-learn, pandas, matplotlib, seaborn
