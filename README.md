<p align="center">
  <img src="assets/title_image.png" width="65%" style="border-radius: 10px;">
</p>

<h1 align="center">📊 Rossmann Store Sales Prediction</h1>

<p align="center" style="font-size: 16px;">
An end-to-end Machine Learning project to forecast daily sales for thousands of drug stores using tree-based models, feature engineering, and interpretable ML insights.
</p>

---

## 📌 Problem Statement

Rossmann, one of Europe’s largest drugstore chains, aims to accurately forecast **daily sales for each of its stores**. The goal is to optimize key business operations like inventory planning, workforce management, and promotional strategies by leveraging historical data, promotions, and store characteristics.

---

## 🎯 Project Aim

To develop a robust and interpretable machine learning model that predicts daily store sales with high accuracy while uncovering insights into what drives performance across various stores and timelines.

---

## 🔍 Project Objectives

- 📦 Preprocess and merge training & store data
- 🔧 Engineer time-based, promotion, and competition features
- 📈 Perform exploratory data analysis (EDA) to identify trends and seasonality
- 🧠 Train multiple regression models including:
  - Linear, Ridge, Lasso Regression
  - Random Forest, XGBoost, AdaBoost, Gradient Boosting
- 🧪 Evaluate models using:
  - RMSE, MAE, and R² score
- 📊 Select important features using both Random Forest & XGBoost
- 📈 Interpret top features with **Partial Dependence Plots (PDP)**
- 🔧 Tune hyperparameters of the best model
- 📤 Generate a prediction-ready submission file

---

## 🧾 Dataset Overview

The project uses two CSV files:
- `train.csv` — daily sales, promotions, and store ID
- `store.csv` — store type, assortment, competition details, promo info

| Column               | Description                                    |
|----------------------|------------------------------------------------|
| `Store`              | Unique ID for each store                      |
| `Date`               | Date of the record                            |
| `Sales`              | Target variable: daily sales                  |
| `Promo`              | Whether a store ran a promotion               |
| `StateHoliday`       | Holiday flag (a/b/c/0)                        |
| `SchoolHoliday`      | Indicates school closure                      |
| `StoreType`          | Store classification                          |
| `Assortment`         | Type of assortment offered                    |
| `CompetitionDistance`| Distance to nearest competitor                |
| `Promo2`             | Continuity of promotion campaigns             |

Additional engineered features include:
- `Year`, `Month`, `Day`, `WeekOfYear`, `IsWeekend`, `IsPromoMonth`, `Promo2Active`, `CompetitionOpenTimeMonths`, etc.

---

## 📊 Exploratory Data Analysis (EDA)

Visualizations included:
- Monthly Sales Trend
- Impact of Promotions
- Sales by Store and Assortment Type
- Weekend vs Weekday Trends
- Holiday & SchoolHoliday Impact
- Competition Distance Analysis

> These insights guided feature selection and modeling strategies.

---

## 🤖 Models Trained & Evaluated

| Model                 | RMSE (All Features) | RMSE (Selected Features) |
|-----------------------|---------------------|---------------------------|
| Random Forest         | ✅ **989.67**        | 1213.30                   |
| XGBoost               | 1207.77             | 1452.77                   |
| Gradient Boosting     | 2464.13             | 2535.88                   |
| Linear/Ridge/Lasso    | ~2807               | ~2864                     |
| AdaBoost              | 5696.37             | 5097.00                   |

**Random Forest** was selected as the best-performing model and was further fine-tuned using GridSearchCV.

---

## 🧠 Model Interpretation

- Used **Random Forest and XGBoost feature importances** to select key features.
- Generated **Partial Dependence Plots (PDP)** to visualize how features like `Promo`, `StateHoliday`, and `CompetitionDistance` influence sales.
- Identified that not all promotions have positive effects and that weekend and holiday patterns significantly vary by store.

---

## 🛠️ Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-Learn, XGBoost
- SHAP (attempted), PDP, GridSearchCV
- Jupyter Notebook
- Git & GitHub

---

## 📤 Submission

Final predictions were generated using the trained Random Forest model and submitted in the required format:

| Id | Sales |
|----|-------|
| 1  | 5263  |
| 2  | 6741  |

---

## ✅ Key Takeaways

- Model accuracy can be significantly improved with tailored feature engineering and ensemble models.
- Not all promotions drive sales — targeting and timing are critical.
- Distance to competition and store-specific identity are strong predictors.
- Weekends generally underperform weekdays for most stores.

---

## 🚀 Future Work

- Incorporate weather data and store events
- Build store-specific models for better accuracy
- Deploy the model using Flask or FastAPI
- Real-time dashboard for business users

---

## Note: The model file wasn't upload to github due to its large size but you can generate one by running the code. 

## 🙋‍♂️ Author

**Abdullah Shahzad**  
📧 [abdullahhunjra@gmail.com](mailto:abdullahshahzadhunjra@gmail.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/abdullahhunjra)  
💻 [GitHub](https://github.com/abdullahhunjra)

---

> ⭐ If you found this project helpful, feel free to star the repo or connect!
