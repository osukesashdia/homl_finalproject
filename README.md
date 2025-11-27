# German Credit Risk Analysis with Explainable AI

A comprehensive machine learning project for predicting credit risk using the German Credit dataset, with explainable AI features to provide actionable insights.

## 📋 Project Overview

This project implements multiple AI models to predict credit risk and uses explainable AI techniques (SHAP and LIME) to help people understand:
- Why they were denied/approved for credit
- What factors hurt their credit score
- What actions they can take to improve their credit
- Simulations showing how improvements would affect their approval chances

## 🚀 Features

- **Multiple AI Models**: Logistic Regression, Random Forest, Gradient Boosting, SVM
- **Model Comparison**: Automatic selection of best-performing model
- **Explainable AI**: 
  - SHAP (global and local explanations)
  - LIME (alternative interpretations)
  - Feature importance analysis
  - Individual prediction explanations
- **Actionable Insights**: Personalized recommendations for credit improvement
- **What-If Analysis**: Simulate feature changes and see predicted outcomes
- **Comprehensive Visualizations**: Confusion matrices, ROC curves, feature impact plots

## 📊 Dataset

The project uses the **Statlog German Credit Data** dataset:
- 1000 samples
- 24 features (credit history, employment, loan details, etc.)
- Binary classification: Good Credit (0) vs Bad Credit (1)

## 🛠️ Setup Instructions

### Option 1: Using pip (Recommended for most users)

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

### Option 2: Using conda

```bash
# Clone the repository
git clone <your-repo-url>
cd handsonml

# Create conda environment from file
conda env create -f environment.yml

# Activate the environment
conda activate credit-risk-analysis

# Launch Jupyter Notebook
jupyter notebook finalproject.ipynb
```

## 📁 Project Structure

```
handsonml/
├── finalproject.ipynb       # Main notebook with all analysis
├── requirements.txt          # Python dependencies (pip)
├── environment.yml           # Conda environment file
├── README.md                 # This file
└── .gitignore               # Git ignore file
```

## 📝 Usage

1. **Run All Cells**: Execute cells sequentially to train models and generate explanations
2. **Explore Results**: Review model performance metrics and visualizations
3. **Analyze Individuals**: Use `explain_any_person(index)` to analyze specific people
4. **Run What-If Scenarios**: See how feature improvements affect predictions
5. **Customize**: Modify parameters, try different models, or add new features

## 🎯 Key Functions

### `predict_credit_risk(new_data)`
Predict credit risk for new customer data

### `explain_any_person(person_index, X_test, y_test, model, scaler, explainer, feature_names)`
Generate complete explainability report for any person in the dataset

### `simulate_credit_improvement(person_data, model, scaler, feature_names, modifications)`
Simulate what happens when someone improves certain features

## 📈 Results

The notebook automatically:
- Trains 4 different models
- Selects the best performer
- Provides accuracy and ROC-AUC scores
- Generates confusion matrices and ROC curves
- Explains predictions using SHAP and LIME
- Offers personalized improvement recommendations

## 🔍 Understanding the Output

### SHAP Values
- **Positive SHAP** = Increases bad credit risk
- **Negative SHAP** = Decreases bad credit risk (improves credit)
- **Magnitude** = How much impact the feature has

### Color Coding
- 🔴 **Red** = Factors hurting credit (need improvement)
- 🟢 **Green** = Factors helping credit (maintain these)

## 🤝 Contributing

Feel free to:
- Report issues
- Suggest improvements
- Add new features
- Improve documentation

## 📄 License

This project is for educational purposes.

## 📧 Contact

For questions or collaboration, please reach out to the project maintainer.

---

**Note**: Make sure you have the German Credit dataset (`german.data-numeric`) in the specified path or update the path in the notebook.
