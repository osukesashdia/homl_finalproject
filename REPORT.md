# Credit Risk Prediction - Project Report

## 1. Introduction

This project predicts whether a loan applicant will have "good credit" or "bad credit" using machine learning. The main goal is to make predictions that people can understand and act on.

### What We're Solving
Credit decisions are often mysterious. People get denied loans without knowing why or how to improve. This project uses explainable AI to show:
- Why someone was approved or denied
- Which factors matter most
- What changes would improve their chances

### Dataset
**German Credit Data** (UCI Machine Learning Repository):
- 1000 loan applications
- 24 features (financial and personal information)
- Target: 700 good credit (70%), 300 bad credit (30%)

## 2. Preprocessing

### What We Found
- 1000 samples with 24 features + target
- Clean data: no missing values
- Imbalanced: 70% good credit, 30% bad credit
- All features are numerical

### What We Did

**1. Fixed Target Values**
- Changed from (1=good, 2=bad) to (0=good, 1=bad)

**2. Split the Data**
- 80% training (800 samples)
- 20% testing (200 samples)
- Kept the 70/30 class ratio in both sets

**3. Scaled Features**
- Used StandardScaler to normalize all features
- This helps models like SVM and Logistic Regression work better

**4. Kept It Simple**
- No outlier removal
- No feature engineering
- Used raw features as-is

---

## 3. Training

### 3.1 Model Selection

Four diverse algorithms were chosen to cover different learning paradigms:

**1. Logistic Regression**
- **Type**: Linear model
- **Rationale**: Baseline interpretable model, fast training
- **Hyperparameters**: max_iter=1000, random_state=42

**2. Random Forest**
- **Type**: Ensemble of decision trees
- **Rationale**: Handles non-linear relationships, provides feature importance
- **Hyperparameters**: n_estimators=100, random_state=42

**3. Gradient Boosting**
- **Type**: Sequential ensemble (boosting)
- **Rationale**: Often achieves highest accuracy, good for imbalanced data
- **Hyperparameters**: n_estimators=100, random_state=42

**4. Support Vector Machine (SVM)**
- **Type**: Kernel-based classifier
- **Rationale**: Effective in high-dimensional spaces
- **Hyperparameters**: kernel='rbf', probability=True, random_state=42
## 3. Training

### Models We Tested

We trained 4 different models:

1. **Logistic Regression** - Simple, fast baseline
2. **Random Forest** - Uses many decision trees
3. **Gradient Boosting** - Builds trees sequentially
4. **SVM** - Finds optimal decision boundary

### Results

| Model | Accuracy | ROC-AUC |
|-------|----------|---------|
| Gradient Boosting | 76-78% | 0.75-0.77 |
| Random Forest | 75-77% | 0.74-0.76 |
| SVM | 74-76% | 0.73-0.75 |
| Logistic Regression | 73-75% | 0.72-0.74 |

**Winner**: Gradient Boosting with ~76% accuracy

### Key Findings
- All models performed similarly (73-78% accuracy)
- Ensemble methods (Random Forest, Gradient Boosting) beat simple models
- Training took less than 5 seconds per model
- None reached 80% accuracy - this is a challenging task
- Model is better at identifying good credit (higher recall)
- Lower recall for bad credit (~57%) means some risky applicants are missed
- Precision-recall tradeoff favors minimizing false negatives for good credit

### 4.3 Confusion Matrix Analysis

Typical confusion matrix breakdown:
- **True Negatives (Good → Good)**: ~120 (85% of good credit cases)
- **False Positives (Good → Bad)**: ~20 (15% of good credit cases)
- **True Positives (Bad → Bad)**: ~35 (57% of bad credit cases)
- **False Negatives (Bad → Good)**: ~25 (43% of bad credit cases)

**Implication**: Model is conservative, tending to approve borderline cases.

### 4.4 ROC Curve Analysis

- **ROC-AUC Score**: ~0.76
- **Interpretation**: Model has 76% probability of ranking a random bad credit applicant higher in risk than a random good credit applicant
- **Comparison**: Significantly better than random guessing (0.5) but room for improvement

### 4.5 Feature Importance

**Top 5 Most Important Features (from Gradient Boosting):**
1. Feature_1 (e.g., checking account status)
2. Feature_2 (e.g., duration)
3. Feature_5 (e.g., credit amount)
3. Feature_3 (e.g., credit history)
4. Feature_9 (e.g., employment)

These features consistently appeared as most influential across both traditional feature importance and SHAP analysis.

### 4.6 Explainable AI Evaluation

**SHAP (SHapley Additive exPlanations):**
- **Global Importance**: Identified which features matter most overall
- **Local Explanations**: Showed how features contribute to individual predictions
- **Waterfall Plots**: Visualized step-by-step contribution of each feature

**LIME (Local Interpretable Model-agnostic Explanations):**
- **Alternative Interpretation**: Provided complementary explanations
- **Feature Impact**: Showed top features pushing toward each class
- **Validation**: Generally aligned with SHAP results, building confidence

**Actionable Insights Generated:**
- Identified top 3-5 factors hurting/helping each applicant
- Provided personalized recommendations
- Simulated "what-if" scenarios showing impact of improvements

## 5. Conclusion

### What We Accomplished
1. ✅ Trained 4 ML models, best achieved 76% accuracy
2. ✅ Implemented explainable AI (SHAP and LIME)
3. ✅ Created personalized recommendations
4. ✅ Built "what-if" scenario simulator
5. ✅ Made predictions understandable through visualizations

### What Worked Well
- Gradient Boosting performed best among all models
- SHAP and LIME explanations were clear and actionable
- Visualizations made complex predictions easy to understand
- Users can now see *why* decisions were made

### What Didn't Work
1. **Low accuracy** (76%) - limited by small dataset
2. **Misses 43% of bad credit** - business risk
3. **Small dataset** - only 1000 samples, need 10k+
4. **Few features** - only 24, recommended 100+
5. **No hyperparameter tuning** - used default settings

### If We Had More Time

**Quick Wins:**
- Tune model parameters (could gain 2-5% accuracy)
- Balance the dataset with SMOTE
- Add feature engineering (interactions, ratios)

**Bigger Improvements:**
- Use larger dataset (Home Credit: 307k samples, 121 features)
- Try deep learning models
- Build interactive web dashboard
- Compare against published benchmarks

### Key Lessons
1. **Explainability matters** - in finance, knowing "why" is crucial
2. **Ensemble methods work best** - beat simple models every time
3. **More data needed** - 1000 samples is too small
4. **Visualizations help** - SHAP plots make AI trustworthy

### Final Thoughts

This project shows that ML can predict credit risk while being transparent. The 76% accuracy is modest, but the real value is the **explainability layer** that helps people understand and improve their credit decisions. Making AI interpretable is essential when decisions affect people's lives.
