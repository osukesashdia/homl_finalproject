# German Credit Risk Analysis with Explainable AI

## 📋 Project Overview

This project predicts credit risk using the German Credit dataset (1000 samples, 24 features) with machine learning models. It includes explainable AI features to help understand credit decisions and provide actionable recommendations for improvement.

## 🔬 What This Code Does

The notebook trains 4 AI models (Logistic Regression, Random Forest, Gradient Boosting, SVM) to predict credit risk, then uses SHAP and LIME to explain:
- Why someone was approved/denied for credit
- Which factors hurt or help their credit score
- Specific actions to improve credit approval chances
- What-if scenarios showing how changes affect predictions

## 🛠️ Setup Instructions

```bash
# Clone the repository
git clone <your-repo-url>
cd handsonml

# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook finalproject.ipynb
```
