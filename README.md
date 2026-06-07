# 🚗 Car Price Prediction

A machine learning project that predicts used car prices in the Indian market using key vehicle attributes — brand, age, fuel type, transmission, and ownership history — with Random Forest achieving 92% accuracy.

---

## 📌 Project Overview

Buying or selling a used car is a high-stakes decision with little price transparency. This project builds an end-to-end ML pipeline — from raw data cleaning to a deployable prediction model — that accurately estimates a car's market value based on its features.

---

## 🏆 Model Performance

| Model | R² Score | Average Error |
|-------|----------|---------------|
| Linear Regression | 70% | ₹1,25,000 |
| Decision Tree | 82% | ₹95,000 |
| **Random Forest** | **92%** | **₹70,000** |

> Random Forest selected as the final model — best accuracy with lowest prediction error.

---

## Project Structure

Here's how I organized everything:
```
car-price-prediction/
├── data/
│   ├── raw/                      # Original CSV file
│   └── processed/                # Cleaned data, train/test splits
├── models/                       # All my trained models saved here
├── images/                       # Plots and visualizations
│   ├── eda/                     
│   └── model_performance/       
├── car_price_prediction.ipynb    # Main notebook with all the code
└── README.md                     
```

## 📊 Dataset

- **Records:** 5,000+ used car listings
- **Features:** Car brand, model, fuel type, transmission, kilometers driven, ownership, location
- **Target:** Price in INR (₹500 to ₹60,00,000)
- **Market:** Indian used car market

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4B8BBE?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## ✨ What's Covered

- 🧹 Data cleaning — year extraction, unit conversion, outlier removal
- 🔍 EDA — price distribution, brand analysis, feature correlations
- ⚙️ Feature engineering — car age calculation, encoding categorical variables
- 🤖 Model training — Linear Regression, Decision Tree, Random Forest
- 📊 Model evaluation — R² score, MAE comparison
- 💾 Model persistence — saved with Pickle for reuse

---

## 🔍 Key Insights

- 🏷️ **Brand matters most** — Maruti Suzuki dominate volume, BMW/Mercedes command premium prices
- 📅 **Age is the biggest depreciator** — every year adds significant price drop
- ⛽ **Diesel holds value better** — diesel cars retain price longer than petrol
- 🔄 **Transmission premium** — automatic cars priced ~15% higher on average
- 👤 **Ownership drop** — each additional owner drops price by roughly 10%

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/shubhamjais04/Car-Price-Prediction.git
cd Car-Price-Prediction
```

**2. Install dependencies**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

**3. Open the notebook**
```bash
jupyter notebook car_price_prediction.ipynb
```

**4. Run all cells in order**

**5. Make a prediction**
```python
predict_price(brand='Maruti', fuel='Petrol', 
              transmission='Manual', age=5, kms=50000)
# Output: ₹3,20,000 (approx)
```

---

## What I Learned

**Technical stuff:**
- Cleaning real-world data is HARD. Way harder than toy datasets from courses.
- Feature engineering matters a lot. Adding "Car Age" improved my model significantly.
- Random Forest is amazing for this kind of problem - better than plain Linear Regression.
- Saving models with pickle is super useful for later deployment.

**Challenges I faced:**
- Extracting year from messy text was annoying (regex saved me)
- Figuring out which outliers to remove vs keep
- Deciding how to handle missing values without losing too much data
- Getting all the encoders and scalers to work together

**What I'd do differently:**
- Would've added more features like city/location
- Could try deep learning just to compare
- Should've done more hyperparameter tuning

---

## 👨‍💻 Author

**Shubham Jaiswal**  
*Predictive modeler | Bringing price transparency to the used car market with machine learning*

---

## 📬 Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/shubhjais04)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/shubhamjais04)

---

## Final Thoughts

If you're learning ML, I highly recommend building something like this. Working with real messy data teaches you way more than clean Kaggle competitions.

**If you found this useful, drop a star!** It really motivates me to build more stuff.

---


Built this to learn, share, and hopefully help someone make a better car-buying decision someday! 
