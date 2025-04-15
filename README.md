# 🏆 NBA MVP Prediction Project

Welcome to the **NBA MVP Prediction Project**! This is my take at building a machine learning model to predict who might win the NBA MVP award. I used player stats, team records, and some cool advanced numbers to figure it out. The 2025 MVP race is super exciting with **Nikola Jokić** and **Shai Gilgeous-Alexander** going head to head, so I thought it'd be fun to see what the data says!

---

## 🌟 Project Goal

The main goal is to **predict MVP award shares** using a supervised regression approach. The player with the highest share value is the MVP. The project leverages historical NBA data from 1982 to 2024 to forecast which players are most likely to win based on stats, impact metrics, and team performance.

This project explores:

- 🧠 The logic behind MVP voting system
- 🔬 Filtering out  players and balancing the dataset with SMOTE
- 🧪 Feature selection using the Boruta method 
- 🤖 Regression modeling using Random Forest and XGBoost
- 📈 Season-by-season validation of model accuracy
- 🔮 Making predictions for the 2025 seasons

---

## 💃️ Data Sources

The dataset includes:

- 🏀 **Player Per Game Stats**
- 📈 **Advanced Player Metrics**
- 📊 **Team Summaries**
- 🥇 **MVP Award Share Data**  All sourced from [Kaggle: NBA Stats 1947–present](https://www.kaggle.com/datasets/sumitrodatta/nba-aba-baa-stats).

---

## 🔧 Data Transformation

Key steps in preparing the data:

- 🧹 **Cleaning and Merging**: Combined multiple CSV files into a unified dataset.
- ↻ **Player Filtering**: Kept only the final team ("TOT") row for players traded mid-season.
- ❌ **Seasonal Scope**: Used data from 1982–2023 for training; 2024 for testing; 2025 for prediction.
- 📉 **Handling Nulls**: Filled in missing values, dropped irrelevant columns.
- 📊 **Feature Engineering**: Removed redundant features and added new ones.
- ⚖️ **Balancing the Dataset**: Used SMOTE to add synthetic data for the minority class.

---

## 🚀 Model Building

- 🌲 **Random Forest Regressor**: A tree-based model that's great for handling complex datasets and avoids overfitting pretty well.
- ⚡ **XGBoost Regressor**: A boosting method that builds strong models from many weak learners—known for its speed and performance in competitions.

### 🔍 Feature Selection

- Used the **Boruta algorithm** to select the most relevant features.
- Retained only metrics proven statistically significant in MVP outcomes.

### 📈 Model Evaluation & Yearly Predictions

I used a leave-one-season-out validation approach—training the model on all seasons except one and testing it on the season left out. This helped me evaluate how well the model generalizes to unseen years.

The model performance was measured by:

- **Mean Absolute Error (MAE)** of predicted award shares
- **Whether the predicted MVP matched the actual winner**
- **Whether the actual MVP was ranked in the top 2 or 3 of the model’s predictions**

---

## 🧰 Tools & Libraries Used

- **Python**: Core language
- `pandas`, `numpy`: Data manipulation
- `matplotlib`, `seaborn`: Visualization
- `scikit-learn`: Predictions
- `XGBoost`: Gradient boosting regressor used for high-performance prediction
- `BorutaPy`: Feature selection
- `SMOTE`: Oversampling minority class

---

## 🔧 Further Improvements

This project is a solid starting point for MVP prediction. The model performs well, correctly identifying top MVP candidates and getting the actual winner right about 80% of the time.

To improve:
- 📊 Use a two-step model: first predict MVP candidates, then refine predictions using a second model trained only on players who received MVP votes.
- 📅 Build era-specific models to account for how the game has evolved (e.g. three-point era vs. 90s).

## 🛡️ License

This project is licensed under the [MIT License](LICENSE).You’re free to use and adapt the code with proper credit.
