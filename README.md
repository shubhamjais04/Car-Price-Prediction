# Car Price Prediction

A machine learning project I built to predict used car prices in India. This was a fun challenge to work with real-world messy data.

---

## What This Project Does

If you're buying or selling a used car, how do you know if the price is fair? That's the problem I tried to solve. I built a model that predicts car prices based on features like brand, age, fuel type, and how much it's been driven.

Turns out, my Random Forest model got pretty good - around 92% accuracy!

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

---

## The Dataset

I worked with data from 5,050 used cars listed in India. The dataset had:

- Car brand and model
- Year (which I had to extract from the model name - that was tricky!)
- Fuel type (Petrol, Diesel, CNG, LPG)
- How many kilometers it's been driven
- Transmission type (Manual vs Automatic)
- Number of previous owners
- Location
- **Price** - this is what I'm trying to predict

**Price range:** ₹50,000 to ₹50,00,000 (that's like $600 to $60,000 USD)

---

## What I Found (EDA Insights)

Before building any models, I spent a lot of time just exploring the data. 
**1. Price Distribution:**
Most cars are in the ₹3-7 lakh range (around $4,000-$8,000). Makes sense for the Indian market.

**2. Brands:**
Maruti Suzuki dominates - they're everywhere! But luxury brands like Mercedes and BMW have way higher average prices.

**3. Fuel Type:**
Diesel cars cost about 15% more than petrol. I think it's because diesel is cheaper to run long-term in India.

**4. Transmission:**
Only 15% of cars are automatic, and they're priced higher. Manual is still king in India.

**5. Ownership:**
First owner cars are obviously pricier. Each additional owner drops the price by roughly 20%.

---

## How I Built This

### Step 1: Cleaning the Data

The data was messy! Some challenges I faced:
- Kilometers had commas and "KM" text (like "50,000 KM")
- Years were hidden inside the model name (like "Maruti Swift (2015)")
- Some missing values here and there

I used regex to extract the year, converted everything to proper numbers, and dropped rows where critical info was missing.

### Step 2: Feature Engineering

I created a "Car Age" feature because I figured age matters more than year. A 2015 car in 2022 is 7 years old - that's what buyers care about.

### Step 3: Trying Different Models

I trained three models and compared them:

| Model | How It Did (R² Score) | Average Error |
|-------|----------------------|---------------|
| Linear Regression | 78% | ₹1,85,000 |
| Random Forest | **92%** | **₹95,000** |
| Gradient Boosting | 90% | ₹1,05,000 |

**Random Forest won!** It gave me 92% accuracy on unseen data.

---

## What Matters Most?

The model told me which features affect price the most:

1. **Car Age** (35%) - No surprise, newer = pricier
2. **Brand** (28%) - BMW costs more than Maruti, obviously
3. **Kilometers Driven** (18%) - Lower mileage = better
4. **Fuel Type** (12%) - Diesel holds value better
5. **Transmission** (7%) - Automatic is a premium feature

---

## How to Run This

**Need:**
- Python 3.8 or higher
- Jupyter Notebook

**Steps:**

1. Clone my repo:
```bash
git clone https://github.com/shubhamjais04/car-price-prediction.git
cd car-price-prediction
```

2. Install libraries:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Open the notebook:
```bash
cd notebooks
jupyter notebook car_price_prediction.ipynb
```

4. Run all the cells and watch it work!

---

## Example: Making a Prediction

Say you want to know the price of a 5-year-old Maruti Swift with 50,000 km:
```python
# Load my saved model
import pickle

model = pickle.load(open('../models/best_model.pkl', 'rb'))
scaler = pickle.load(open('../models/scaler.pkl', 'rb'))

# Your car details
car = {
    'Brand': 'Maruti',
    'Fuel': 'Petrol',
    'Kilometers': 50000,
    'Transmission': 'Manual',
    'Owner': '1st Owner',
    'Age': 5
}

# Predict (after preprocessing...)
predicted_price = model.predict(processed_data)
print(f"Price: ₹{predicted_price:,.0f}")
```

The model would probably say around ₹4-4.5 lakhs.

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

## What's Next?

Some ideas I'm thinking about:

- Build a simple web app where you input car details and get instant price
- Add more features like service history, accident history
- Try using car images to predict price (that would be cool!)
- Deploy it somewhere so people can actually use it

---

## Tools I Used

- **Python** - for everything
- **Pandas & NumPy** - data wrangling
- **Matplotlib & Seaborn** - making plots
- **Scikit-learn** - the ML models
- **Jupyter Notebook** - where I wrote all the code

---

## Contact

Hey! I'm **Shubham Jaiswal**, a data science student learning by building projects.

- GitHub: [@shubhamjais04](https://github.com/shubhamjais04)
- LinkedIn: [linkedin.com/in/shubhamjaiswal2004](https://linkedin.com/in/shubhamjaiswal2004)
- Email: shubhjais.in@gmail.com

Feel free to reach out if you have questions or suggestions!

---

## Final Thoughts

If you're learning ML, I highly recommend building something like this. Working with real messy data teaches you way more than clean Kaggle competitions.

**If you found this useful, drop a star!** It really motivates me to build more stuff.

---

**Last updated:** February 2026

Built this to learn, share, and hopefully help someone make a better car-buying decision someday! 
