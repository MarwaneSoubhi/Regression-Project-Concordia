# **🏡 Rental Price Prediction in Canada (2024) 🏡**

## **📌 Project Overview**
This project focuses on predicting **rental prices** for apartments and houses across **Canada in 2024** using **machine learning**. By leveraging real-world data, we build and optimize a **Random Forest Regression model** to estimate rental prices based on key property attributes such as:

- Number of **bedrooms**
- Number of **bathrooms**
- **Square footage**
- **Location (latitude & longitude)**
- **Property type** (apartment, house, condo, etc.)
- **Lease terms** (long-term vs. short-term)
- **Furnishing status**

The project follows a **data science pipeline**, including **data preprocessing, exploratory data analysis (EDA), feature engineering, model training, and evaluation** using real listings from **RentFaster.ca**.

---
## **🛠️ Tech Stack & Libraries**
The following technologies and libraries are used:

- **Programming Language**: Python 🐍
- **Libraries**:
  - `pandas` (data manipulation)
  - `numpy` (numerical computations)
  - `seaborn` & `matplotlib` (data visualization)
  - `sklearn` (machine learning models & evaluation)
  - `GridSearchCV` (hyperparameter tuning)

---
## **📂 Dataset Overview**
The dataset contains rental listings across Canada, including:
- `price`: Rental price (target variable)
- `beds`: Number of bedrooms
- `baths`: Number of bathrooms
- `sq_feet`: Total living space in square feet
- `latitude`, `longitude`: Location data
- `type_*`: One-hot encoded property types (e.g., `type_Apartment`, `type_House`)
- `province_*`: One-hot encoded provinces (e.g., `province_Alberta`, `province_Quebec`)
- `furnishing_*`: Furnishing status (e.g., `furnishing_Unfurnished`)
- `lease_term_*`: Lease duration (e.g., `lease_term_Long Term`)

---
## **📊 Exploratory Data Analysis (EDA)**
We start with **EDA** to explore the dataset:
- **Handling Missing Values**: Imputed missing data using median values
- **Data Cleaning**: Converted categorical variables into numerical features
- **Feature Engineering**: Created new variables like `price_per_sqft`
- **Correlation Analysis**: Identified important predictors of rental price
- **Visualizations**: Heatmaps, scatter plots, and bar charts to understand price trends

---
## **🤖 Model Training & Evaluation**
We trained and compared **three regression models**:

1. **Linear Regression**
2. **Random Forest Regression** ✅ *(Best model!)*
3. **Polynomial Regression Model n**

### **🔍 Model Evaluation Metrics**
Each model was evaluated using the following metrics:
- **Mean Absolute Error (MAE)**: Measures average absolute errors
- **Mean Squared Error (MSE)**: Penalizes larger errors
- **Root Mean Squared Error (RMSE)**: More interpretable error metric
- **R² Score**: Explains variance explained by the model

After evaluation, **Random Forest Regression** was selected as the final model.

---
## **⚡ Hyperparameter Optimization**
To improve performance, we optimized **Random Forest Regression** using `GridSearchCV`:
- **n_estimators** (number of trees)
- **max_depth** (depth of trees)
- **min_samples_split** (minimum samples to split a node)
- **min_samples_leaf** (minimum samples per leaf node)

🔹 **Best Parameters Found**:
```json
{
  "n_estimators": 200,
  "max_depth": None,
  "min_samples_split": 2,
  "min_samples_leaf": 1
}
```

---
## **🏠 Real-World Testing with RentFaster.ca Listings**
To validate the model, we used **three real listings** from RentFaster.ca and compared predictions:

| **Property** | **Actual Rent (CAD)** | **Predicted Rent (CAD)** | **Difference** |
|-------------|-------------------|-------------------|-------------|
| **SODO (Beltline, Calgary)** | **$1750 - $2395** | **$1927.66** | ✅ Within range |
| **Hive (Sunnyside, Calgary)** | **$2125 - $2888** | **$2539.89** | ✅ Within range |
| **Modern Beltline (Calgary)** | **$1879 - $2500** | **$2463.03** | ✅ Within range |

The **model performed well**, predicting prices within the expected range.

---
## **📈 Key Insights & Learnings**
✅ **Feature Engineering Matters**: Including location, property type, and lease terms improved predictions.  
✅ **Real-World Validation is Crucial**: Testing against real listings ensured practical model usability.  
✅ **Further Improvements Possible**: Incorporating additional factors (e.g., amenities, transit access) could enhance accuracy.



---
### **🔗 Credits & References**
- RentFaster.ca (for real-world rental listings)
- Scikit-Learn for machine learning models
- Matplotlib & Seaborn for data visualization


