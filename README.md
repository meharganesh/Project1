# BigMart Sales Prediction

## Project Overview
The BigMart Sales Prediction project aims to build a predictive model that estimates the sales of products across different BigMart outlets. The dataset includes sales data for 1559 products from 10 stores in various cities during 2013. By leveraging this data, the goal is to predict the sales for each product at its respective outlet and gain insights into the key factors influencing sales performance.

This project utilizes various machine learning techniques for data preprocessing, feature selection, and model development. The final model will help BigMart identify critical product and outlet attributes that drive sales, contributing to their business strategy and growth.

## Dataset Description
The dataset consists of two files:
- **train.csv**: Contains both input features and the target variable (sales).
- **test.csv**: Contains the input features, for which sales predictions are to be made.

### Features in the Dataset:
- **Item_Identifier**: Unique identifier for each product.
- **Item_Weight**: Weight of the product.
- **Item_Fat_Content**: Whether the product is low-fat or regular.
- **Item_Visibility**: Percentage of the product's display area in the store.
- **Item_Type**: Category of the product (e.g., dairy, snacks, etc.).
- **Item_MRP**: Maximum Retail Price of the product.
- **Outlet_Identifier**: Unique identifier for each outlet.
- **Outlet_Size**: Size of the outlet (Small, Medium, or Large).
- **Outlet_Location_Type**: Type of location of the outlet (Urban or Rural).
- **Outlet_Type**: Type of outlet (Grocery Store, Supermarket Type 1, etc.).
- **Outlet_Estd**: Year the outlet was established.
- **Item_Weight_Category**: Weight category of the item.
- **Item_Visibility_Normalized**: Normalized visibility of the product.
- **Price_Per_Weight**: Price per unit weight of the product.
- **Weight_MRP_Interaction**: Interaction term between item weight and MRP.
- **Item_Weight_Outlet_Size_Ratio**: Ratio of item weight to outlet size.
- **Outlet_Age_To_MRP_Ratio**: Ratio of outlet age to MRP.
- **Total_MRP_per_Outlet**: Total MRP of products in the outlet.
- **Outlet_Age_to_Visibility_Ratio**: Ratio of outlet age to product visibility.
- **Item_Identifier_Categories**: Categories based on item identifier.

## Objective
- **Predict sales** of products across different BigMart outlets.
- **Identify key factors** that influence sales by analyzing the relationship between product and outlet features.
- **Handle missing values** and perform **feature selection** to improve model accuracy.

## Methodology

### 1. **Data Preprocessing**
   - **Handling Missing Data**: Imputation techniques (mean, mode) were used to fill missing values.
   - **Encoding Categorical Variables**: Categorical variables like `Item_Fat_Content`, `Outlet_Identifier`, and others were transformed into numerical format using techniques like One-Hot Encoding.
   - **Normalization and Standardization**: Continuous features such as `Item_Weight`, `Item_Visibility`, and `Item_MRP` were normalized to bring them onto a similar scale.

### 2. **Feature Engineering**
   - **Interaction Features**: New features like `Price_Per_Weight` and `Weight_MRP_Interaction` were created to capture interactions between product properties.
   - **Derived Features**: Additional features such as `Item_Weight_Outlet_Size_Ratio` and `Outlet_Age_to_Visibility_Ratio` were introduced to improve model performance.

### 3. **Feature Selection**
   - **Variance Inflation Factor (VIF)** was used to check for multicollinearity among features.
   - **Recursive Feature Elimination (RFE)** was employed to select the most relevant features by recursively eliminating the least significant ones.

### 4. **Model Building**
   - A **Voting Regressor** was implemented by combining multiple models (e.g., Linear Regression, Decision Tree, Random Forest) to improve predictive performance.
   - **GridSearchCV** was used for hyperparameter tuning to identify the best parameters for the regression models.
   - Models were evaluated based on performance metrics such as **RMSE (Root Mean Squared Error)** and **R² (Coefficient of Determination)**.

## Steps to Run the Project

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/bigmart-sales-prediction.git
