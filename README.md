**MLB G8.1 03 AIML Project**

## Student Stress Prediction ML Training & Preprocessing

IT25102446 - Edirisinghe E.M.C.J <br>
IT25100458 - Silva S.N.A <br>
IT25101614 - Gunawardhana V.D.W <br>
IT25103475 - Sihath M.G.V <br>
IT25101340 - Jayasundara D.N <br>
IT25103277 - Amarathunge A.A.M.D.P.C <br>

### Datasets
- `Stress_Dataset.csv` - Rejected: heavily imbalanced (91% of rows in one class) and unrelated to the other dataset.
- `StressLevelDataset.csv` - Used: 1100 entries, 20 features, balanced 3-class target (Low / Medium / High).

### Final models

| Model | Input features | Version |
|---|---|---|
| IT25102446 - KNN | Top-10 (ANOVA) | Tuned |
| IT25101340 - Logistic Regression | Top-10 (ANOVA) | Tuned |
| IT25103277 - Naive Bayes | Top-10 (ANOVA) | Tuned |
| IT25100458 - Random Forest | Top-10 (Random Forest importance) | Tuned |
| IT25101614 - SVM | PCA (2 components) | Untuned (default RBF) |
| IT25103475 - MLP | PCA (2 components) | Tuned |
| IT25103277 - Gradient Boosting | PCA (2 components) | Tuned |
| IT25101340 - Decision Tree | PCA (2 components) | Tuned |
| IT25101614 - Extra Trees | Top-10 (ANOVA) | Tuned |
| IT25103475 - LDA | Top-10 (ANOVA) | Tuned |
| IT25100458 - QDA | Top-10 (ANOVA) | Tuned |
| IT25102446 - K-Means (unsupervised) | Top-10 (ANOVA) | Tuned |

### Results (test set, n = 220)

| Model | Accuracy | Macro-F1 |
|---|---|---|
| IT25102446 - KNN | 0.891 | 0.891 |
| IT25101340 - Logistic Regression | 0.891 | 0.892 |
| IT25103277 - Naive Bayes | 0.895 | 0.898 |
| IT25100458 - Random Forest | 0.886 | 0.887 |
| IT25101614 - SVM | 0.895 | 0.897 |
| IT25103475 - MLP | 0.900 | 0.902 |
| IT25103277 - Gradient Boosting | 0.886 | 0.886 |
| IT25101340 - Decision Tree | 0.882 | 0.882 |
| IT25101614 - Extra Trees | 0.886 | 0.887 |
| IT25103475 - LDA | 0.891 | 0.893 |
| IT25100458 - QDA | 0.905 | 0.906 |
| IT25102446 - K-Means | 0.855 | 0.857 |

The 11 supervised models are statistically comparable (95% CI is about ±4 points). K-Means is unsupervised, so its accuracy is cluster-to-label agreement. See `Model_Comparison.ipynb` for the full evaluation.

### Notebook run order
1. Data Cleaning (IT25103475)
2. Outlier Removal (IT25101340)
3. Scaling (IT25102446)
4. Feature Engineering (IT25100458)
5. Feature Selection (IT25103277)
6. PCA (IT25101614)
7. Model notebooks (KNN, Logistic Regression, Naive Bayes, Random Forest, SVM, MLP, Gradient Boosting, Decision Tree, Extra Trees, LDA, QDA, K-Means)
8. `Model_Comparison.ipynb`

### Deployment (FastAPI)
- Live deployment: https://mindcheck-stress-predictor.onrender.com/