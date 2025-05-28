
# DRW Crypto Market Prediction 🚀

This repository contains my complete pipeline for the [DRW x Kaggle Crypto Prediction Challenge](https://www.kaggle.com/competitions/drw-crypto-market-prediction). The objective is to develop a model that can predict short-term price movements in the cryptocurrency market using both proprietary and public trading data.

---

## 📌 Project Overview

- **Goal**: Predict the short-term returns of crypto assets using microstructure trading data.
- **Challenge**: Extremely noisy data with low signal-to-noise ratio.
- **Evaluation Metric**: R² score (coefficient of determination).

---

## 🗂️ Project Structure

```

drw-crypto-market-prediction/
├── data/                    # Sample files (train/test .parquet files ignored)
│   └── sample\_submission.csv
├── notebooks/               # EDA notebooks
│   └── eda.ipynb
├── src/                     # All modular code files
│   ├── load\_data.py
│   ├── preprocess.py
│   ├── train\_model.py
│   ├── train\_lightgbm.py
│   └── predict\_submission.py
├── submission\_final.csv     # Final submission (optional)
├── requirements.txt         # Python dependencies
├── .gitignore
└── README.md

````

---

## 📈 Baseline Results

| Step              | Details                          |
|-------------------|----------------------------------|
| Model             | LightGBM Regressor               |
| Features          | 895 raw features + VarianceThreshold |
| Validation (local)| R² ≈ 0.41                        |
| Kaggle Public LB  | R² = **-0.00131** (first baseline) |

---

## ⚙️ Pipeline Summary

1. **EDA**:
   - Checked nulls, label distribution, and time trends
   - Visualized `label` — highly centered, low variance

2. **Preprocessing**:
   - VarianceThreshold to remove low-variance columns
   - Standard missing value handling (none present in baseline)

3. **Modeling**:
   - `LGBMRegressor` from LightGBM
   - R² used as the core evaluation metric
   - Trained/tested on provided `.parquet` datasets

4. **Submission**:
   - Format aligned with `sample_submission.csv`
   - Output: `submission_final.csv`

---

## 🔮 Next Steps

- [ ] Add rolling window features (mean, std of `volume`, `buy_qty`, etc.)
- [ ] Use lag-based features (returns, volatility)
- [ ] Optimize LightGBM hyperparameters
- [ ] Explore XGBoost and ensembling
- [ ] Apply time-aware cross-validation (Purged K-Fold or sliding windows)

---

## 💼 Why This Matters

This project demonstrates:
- ✅ Practical handling of time-series financial data
- ✅ End-to-end ML pipeline for noisy datasets
- ✅ Feature engineering and model tuning under constraints
- ✅ Clean reproducible code and results

---

## 📦 Installation

```bash
git clone https://github.com/Nstar9/Crypto-market--Prediction.git
cd Crypto-market--Prediction
pip install -r requirements.txt
````

---

## 📬 Contact

If you're hiring or interested in collaboration:

**Niraj Patil**
📧 [LinkedIn](https://www.linkedin.com/in/yourprofile) • 🌐 [Portfolio Site](https://yourportfolio.com) (add links!)

---

## 📜 License

This project is under the MIT License.

```

