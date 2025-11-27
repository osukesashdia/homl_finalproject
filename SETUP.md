# Quick Setup Guide for Coworkers

## 🎯 Quick Start (5 minutes)

### Step 1: Clone the Repository
```bash
git clone <repository-url>
cd handsonml
```

### Step 2: Set Up Environment

**Option A - Using pip (Easier)**
```bash
python -m venv venv
source venv/bin/activate  # On macOS/Linux
# OR
venv\Scripts\activate     # On Windows

pip install -r requirements.txt
```

**Option B - Using conda (Recommended if you have Anaconda)**
```bash
conda env create -f environment.yml
conda activate credit-risk-analysis
```

### Step 3: Get the Data
Download the German Credit dataset and place it in:
`/Users/RS/Downloads/statlog+german+credit+data/german.data-numeric`

Or update the `data_path` variable in the notebook to your data location.

### Step 4: Run the Notebook
```bash
jupyter notebook finalproject.ipynb
```

### Step 5: Execute All Cells
Click "Cell" → "Run All" or press Shift+Enter through each cell

## 🔧 Troubleshooting

### Package Installation Issues
If `shap` or `lime` fails to install:
```bash
pip install --upgrade pip
pip install shap lime --no-cache-dir
```

### Jupyter Not Found
```bash
pip install jupyter notebook
```

### Kernel Issues
If the kernel crashes:
1. Restart kernel: Kernel → Restart
2. Clear outputs: Cell → All Output → Clear
3. Run cells again

## 💡 Tips

- **First time running?** It may take 2-3 minutes to install SHAP and train models
- **Memory issues?** Reduce `shap_sample_size` in the explainability section
- **Want to analyze someone specific?** Use `explain_any_person(index)` with any index from 0-199

## 📞 Need Help?

- Check the main README.md for detailed documentation
- Review cell outputs for error messages
- Make sure all dependencies are installed correctly

---
Happy analyzing! 🚀
