# Yassir AI Market Challenge - Product Recommendation System 🚀

## 🏆 Hackathon Project

This is a **Hackathon submission** for the **Yassir AI Market Challenge** - a product recommendation system designed to predict the top 10 products each user is likely to purchase in their next order based on historical purchase data.

---

## 📋 Overview

This notebook implements a **comprehensive product recommendation system** combining:

- **Feature Engineering**: User-product interactions, recency, frequency, and popularity metrics
- **Scoring System**: Weighted scoring with multiple boosting strategies
- **Cold-Start Handling**: Popular product recommendations for new users

---

## 🔧 Recommendation System Type

This is a **hybrid rule-based recommendation system** with the following characteristics:

- **Personalized**: Uses user-product interaction history, recency, frequency, and user-specific reorder rates
- **Content-based**: Leverages user and product features (not just collaborative filtering)
- **Popularity-based fallback**: For cold-start users, recommends globally popular products
- **No ML model**: All logic is based on engineered features and weighted scoring

**Summary:** A feature-engineered, rule-based, hybrid recommender system that combines personalized, content-based, and popularity-based strategies for robust product recommendations.

---

## 📂 Project Structure

```
yassir-ai-market-challenge/
├── README.md                                    # This file
├── .gitignore                                   # Git ignore rules
├── requirements.txt                             # Python dependencies
├── yassir-notebook-final.ipynb                 # Main Jupyter notebook
└── yassir_marekt_data_09_2025 2/               # Dataset directory
    ├── category_df.csv                          # Product categories
    ├── sub_category_df.csv                      # Product sub-categories
    ├── products_df.csv                          # Product information
    ├── users_df.csv                             # User information
    ├── orders_df.csv                            # Order history
    ├── orders_products_df.csv                   # Order-product relationships
    └── test_new_version.csv                     # Test dataset
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook
- pandas, numpy, pickle

### Installation

1. **Clone/Download the repository:**

   ```bash
   cd yassir-ai-market-challenge
   ```

2. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Ensure dataset is in place:**
   - The `yassir_marekt_data_09_2025 2/` folder should contain all CSV files

### Running the Notebook

```bash
jupyter notebook yassir-notebook-final.ipynb
```

---

## ⚙️ Key Configuration Parameters

### Feature Engineering

- **Recency Decay**: 0.2 (exponential decay rate)
- **Frequency Cap**: 10 (normalization cap)

### Scoring Weights

- **Recency**: 25% - Recent purchase importance
- **Frequency**: 15% - Order frequency importance
- **Reorder Rate**: 20% - User's tendency to reorder
- **Popularity**: 10% - Product popularity
- **User Habit**: 30% - User's overall reorder behavior

### Boost Multipliers

- Last order boost: 1.5x
- 2nd last order boost: 1.3x
- 3rd last order boost: 1.15x
- 5+ orders boost: 1.2x
- 10+ orders boost: 1.3x
- Perfect reorder rate boost: 1.15x
- High frequency boost: 1.1x

### Prediction Settings

- **Top N Recommendations**: 10 products per user
- **Score Threshold**: 0.10 (minimum score)
- **Popular Products**: 30 (for cold-start users)

---

## 📊 Data Processing Steps

1. **Load Data**: Import all CSV files from the dataset directory
2. **Data Exploration**: Analyze user, product, and order statistics
3. **Feature Engineering**: Create interaction features, recency scores, frequency metrics
4. **Score Calculation**: Apply weighted scoring with boosting
5. **Recommendation Generation**: Select top 10 products per user
6. **Prediction Output**: Generate submission file with recommendations

---

## 🎯 Output

The notebook generates:

- **submission.csv**: Final predictions with top 10 products per user
- **trained_models_final.pkl**: Serialized models and feature data

---

## 📝 Notebook Sections

1. **Import Libraries & Setup** - Load necessary dependencies
2. **Configuration Settings** - Set all parameters and hyperparameters
3. **Load Data** - Import datasets from CSV files
4. **Exploratory Data Analysis** - Understand data distribution
5. **Feature Engineering** - Create recommendation features
6. **Scoring System** - Calculate product scores
7. **Model Training/Preparation** - Prepare recommendation engine
8. **Prediction & Submission** - Generate final recommendations

---

## 🔍 Key Algorithms

### Feature Engineering

- **Recency Score**: Time-weighted exponential decay for recent orders
- **Frequency Score**: Normalized order count with cap
- **Reorder Rate**: Percentage of reordered products per user
- **Popularity Score**: Product purchase frequency across all users

### Scoring Logic

```
Final Score = w1*recency + w2*frequency + w3*reorder_rate + w4*popularity + w5*user_habit
             × (boost multipliers based on order recency and frequency)
```

---

## 👨‍💻 Author

**Hackathon Submission** - Yassir AI Market Challenge

---

## 📄 License

This project is submitted for the Yassir AI Market Challenge Hackathon.

---

## 💡 Notes

- All recommendations are personalized based on user purchase history
- Cold-start users (no purchase history) receive the top 30 most popular products
- The system uses rule-based logic without requiring model training
- All feature engineering and scoring are configurable via the CONFIG dictionary

---

**Last Updated**: October 2025
