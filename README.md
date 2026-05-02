# 🚦 Road Accident Severity Prediction

> Predicting the severity of road accidents (Slight · Serious · Fatal) using supervised machine learning on 300,000+ UK accident records.

---

## 📌 Project Overview

Road accident severity prediction has real-world applications in **emergency response planning**, **traffic policy**, and **road safety analysis**. This project builds and compares three classification models to identify which conditions most contribute to serious or fatal accidents.

**Best Result → Random Forest: ~88%+ Accuracy**

---

## 📊 Dataset

| Field | Detail |
|-------|--------|
| Source | UK Road Accident Records |
| Records | 300,000+ |
| Features | 21 (raw) → engineered |
| Target | `Accident_Severity` |
| Classes | Slight · Serious · Fatal |
| Train/Test Split | 80% / 20% |

**Key features used:** `Weather_Conditions`, `Road_Type`, `Speed_limit`, `Light_Conditions`, `Number_of_Casualties`, `Vehicle_Type`, `Hour`, `Urban_or_Rural_Area`

---

## ⚙️ Preprocessing Steps

1. **Drop columns** — Removed `Accident_Index` and `Local_Authority_(District)`
2. **Date/Time parsing** — Extracted `Year`, `Month`, `Day`, `Hour`
3. **Missing values** — Mode for categorical · Median for numeric
4. **Label correction** — Fixed typo: `'Fetal'` → `'Fatal'`
5. **Encoding** — `LabelEncoder` on all categorical columns
6. **Scaling** — `StandardScaler` applied to all features
7. **SMOTE** — Oversampled minority classes on training split only (no data leakage)

---

## 🤖 Models & Results

| Model | Test Accuracy | Rank |
|-------|:---:|:---:|
| Logistic Regression | ~77% | 3rd |
| Decision Tree | ~85% | 2nd |
| **Random Forest** | **~88%+** | **🥇 1st** |

---

## 🔑 Top Features (Random Forest Importance)

```
Number_of_Casualties   ██████████████████████  Strongest signal
Speed_limit            ██████████████████       Higher = more severe
Hour                   ██████████████           Night hours riskier
Road_Type              ████████████             Motorways more fatal
Light_Conditions       ██████████               Darkness amplifies risk
```

---

## 🛠️ Tech Stack

```
pandas          → Data wrangling & feature engineering
numpy           → Numerical operations
matplotlib      → Plotting foundation
seaborn         → Statistical visualisations
scikit-learn    → Models, metrics, preprocessing
imbalanced-learn→ SMOTE oversampling
```

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/road-accident-severity-ml.git
cd road-accident-severity-ml
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```

### 3. Run the notebook
```bash
jupyter notebook road_accident.ipynb
```
> Run all cells top to bottom. Plots, classification reports, and feature importance will generate automatically.

---

## 📁 Project Structure

```
road-accident-severity-ml/
│
├── Road_Accident_Data.csv        # Dataset
├── road_accident.ipynb           # Main notebook
├── README.md                     # Project documentation
└── Road_Accident_ML_Documentation.docx  # Full project report
```

---

## 📈 Visualisations Generated

- **Severity Distribution** — Class imbalance overview
- **Weather vs Severity** — Fine weather most common; fog/ice → higher severity
- **Road Type vs Severity** — Single carriageways dominate; motorways more fatal
- **Correlation Heatmap** — `Number_of_Casualties` strongest numeric correlate
- **Confusion Matrix** — Random Forest prediction breakdown
- **Feature Importance Bar Chart** — Ranked by Gini importance

---

## 🔮 Future Improvements

- [ ] Hyperparameter tuning with `GridSearchCV`
- [ ] Try `XGBoost` / `LightGBM` for higher accuracy
- [ ] k-Fold cross-validation for robust evaluation
- [ ] Deploy as REST API using Flask / FastAPI
- [ ] Build a real-time prediction web dashboard
- [ ] Geospatial hotspot mapping using Latitude & Longitude

---

## 👤 Author

**Your Name**
- GitHub: https://github.com/mnoorulameen/road-accident-severity-ml
- LinkedIn:


---

> ⭐ If you found this project useful, consider giving it a star!
