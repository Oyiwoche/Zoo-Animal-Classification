# 🐾 Zoo Animal Classification — Predictive Modelling Project

A complete end-to-end machine learning project that classifies animals into 7 biological categories using physical traits. Built as a learning walkthrough covering every stage of a real data science workflow.

---

## 📌 Project Overview

Given 16 physical features of an animal (such as whether it has milk, feathers, fins, or a backbone), the goal is to predict which of 7 animal classes it belongs to:

| Class | Examples |
|-------|---------|
| Mammal | Lion, Dog, Dolphin |
| Bird | Eagle, Penguin, Flamingo |
| Reptile | Tortoise, Pitviper |
| Fish | Tuna, Carp, Shark |
| Amphibian | Frog, Newt, Toad |
| Bug | Wasp, Moth, Honeybee |
| Invertebrate | Crab, Octopus, Worm |

---

## 📂 Dataset

- **Source:** [UCI Machine Learning Repository — Zoo Dataset](https://archive.ics.uci.edu/ml/datasets/Zoo)
- **Size:** 101 animals, 16 features, 7 classes
- **Features:** Binary traits (hair, feathers, eggs, milk, airborne, aquatic, predator, toothed, backbone, breathes, venomous, fins, tail, domestic, catsize) + legs (count)
- **Challenge:** Class imbalance — Mammals make up 40% of the dataset while Amphibians have only 4 samples

---

## 🔬 Methodology

The project follows a structured 7-step workflow:

1. **Understand the Problem** — define the task, identify inputs and outputs
2. **Exploratory Data Analysis** — class distribution, feature patterns, correlations
3. **Preprocessing** — drop non-predictive columns, separate features (X) and target (y)
4. **Train/Test Split** — 80/20 stratified split to preserve class proportions
5. **Model Training** — three tree-based classifiers compared
6. **Evaluation** — accuracy, macro F1, confusion matrices, cross-validation
7. **Interpretation** — feature importance analysis

---

## 🤖 Models Used

| Model | Train Accuracy | Test Accuracy | Macro F1 |
|-------|---------------|---------------|----------|
| Decision Tree | 86% | 76% | 0.62 |
| Random Forest | 100% | 86% | 0.62 |
| **Gradient Boosting** | **100%** | **90%** | **0.73** |

> **Winner: Gradient Boosting** — highest test accuracy and macro F1 score

---

## 🔑 Key Findings

- **Gradient Boosting** outperformed both Decision Tree and Random Forest on unseen data
- **Milk, feathers and fins** were the three most important features — directly aligned with how biologists classify animals in the real world
- **Class imbalance** was handled using `class_weight='balanced'` to prevent the model from being biased toward the majority class (Mammals)
- Random Forest and Decision Tree had identical macro F1 scores (0.62) despite different overall accuracies — demonstrating why accuracy alone is not a sufficient evaluation metric on imbalanced datasets
- The single Mammal in the test set was misclassified by all three models — a direct consequence of having very few test samples for minority classes

---

## 📊 Evaluation Approach

Beyond simple accuracy, the project uses:

- **Macro F1 Score** — treats all classes equally regardless of size; better metric for imbalanced data
- **Confusion Matrix** — reveals exactly which classes are being confused with each other

---

## 🛠️ Tools & Libraries

- **Python 3**
- **pandas** — data loading and manipulation
- **scikit-learn** — model training, evaluation, and splitting
- **matplotlib & seaborn** — visualisation

---

## 📁 Repository Structure

```
zoo-animal-classification/
│
├── zoo.csv                          # Animal features dataset
├── class.csv                        # Class label mappings
├── zoo_predictive_modelling.ipynb   # Full step-by-step notebook
└── README.md                        # Project overview (this file)
```

---

## 🚀 How to Run

1. Clone this repository
```bash
git clone https://github.com/your-username/zoo-animal-classification.git
```

2. Install dependencies
```bash
pip install pandas scikit-learn matplotlib seaborn
```

3. Open the notebook
```bash
jupyter notebook zoo_predictive_modelling.ipynb
```

4. Run all cells from top to bottom

---

## 💡 Lessons Learned

- Always check class balance before modelling — accuracy alone can be misleading
- Use `stratify=y` when splitting small or imbalanced datasets
- Tree-based models require minimal preprocessing — no scaling needed
- Feature importance is a powerful tool for validating that a model has learned real-world patterns

---
