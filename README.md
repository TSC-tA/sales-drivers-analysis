# 🛍️ Sales Drivers Analysis — Men's Fashion Stores (Netherlands, 1990)

A regression-based analysis to identify the key drivers of annual sales in Dutch men's fashion stores, using cross-sectional data from 400 retail outlets.

---

## 📋 Dataset

**Source:** Verbeek, Marno (2004) *A Guide to Modern Econometrics*, John Wiley and Sons, chapter 3.

The dataset (`Clothing.csv`) contains 400 observations of men's fashion stores in the Netherlands (1990), with the following variables:

| Variable | Description |
|----------|-------------|
| `tsales` | Annual sales (Dutch guilders) — **target variable** |
| `sales` | Sales per square meter |
| `margin` | Gross-profit margin |
| `nown` | Number of owners/managers |
| `nfull` | Number of full-time workers |
| `npart` | Number of part-time workers |
| `naux` | Number of temporary helpers |
| `hoursw` | Total hours worked |
| `hourspw` | Hours worked per worker |
| `inv1` | Investment in shop premises |
| `inv2` | Investment in automation |
| `ssize` | Sales floor space (m²) |
| `start` | Year the business started |

---

## 🎯 Objective

Predict **annual sales (`tsales`)** using store characteristics via **Ordinary Least Squares (OLS) multiple linear regression**.

---

## 🔍 Analysis Steps

1. **Data loading & exploration** — preview, shape, and structure of the dataset
2. **Exploratory Data Analysis (EDA)** — distributions, correlations, and visualizations
3. **Feature selection** — selecting predictors for the regression model
4. **Model training** — OLS regression with an 80/20 train-test split
5. **Model evaluation** — RMSE, MAE, and MAPE on the test set

---

## 📊 Results

| Metric | Value |
|--------|-------|
| R² (train) | 0.287 |
| RMSE | 460,718 |
| MAE | 292,873 |
| MAPE | 57.80% |

**Key finding:** `hourspw` (hours worked per worker) was the strongest and only statistically significant predictor (p < 0.001), with a coefficient of ~37,090. Other variables such as `margin`, `nown`, `inv1`, `inv2`, and `start` were not significant at the 5% level.

The relatively low R² suggests that store-level sales are influenced by factors not captured in this dataset (e.g., location, product mix, marketing).

---

## 🛠️ Tech Stack

- Python 3
- `pandas` — data manipulation
- `numpy` — numerical operations
- `statsmodels` — OLS regression & model summary
- `seaborn` / `matplotlib` — visualization
- `scikit-learn` — train/test split & evaluation metrics

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/sales-drivers-analysis.git
cd sales-drivers-analysis
```

### 2. Install dependencies

```bash
pip install pandas numpy statsmodels seaborn scikit-learn
```

### 3. Run the notebook

Open `Sales_Drivers.ipynb` in Jupyter or Google Colab.

> **Note:** If running locally (not on Colab), remove the Google Drive mount cells at the top of the notebook. The CSV file is included in this repository.

---

## 📁 Project Structure

```
sales-drivers-analysis/
│
├── Clothing.csv             # Dataset (400 observations)
├── Sales_Drivers.ipynb      # Main analysis notebook
└── README.md                # Project documentation
```

---

## 📚 Reference

Verbeek, M. (2004). *A Guide to Modern Econometrics* (2nd ed.). John Wiley & Sons.
