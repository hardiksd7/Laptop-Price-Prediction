# Laptop-Price-Prediction
This project focuses on predicting laptop prices using various regression techniques based on a comprehensive dataset of laptop specifications. The primary goal is to build a robust machine learning model capable of accurately estimating laptop selling prices.

## Project Overview

The project involves data loading, extensive feature engineering, data preprocessing, and the implementation and evaluation of several regression models. Key steps include:

* **Data Loading:** Reading the laptop price dataset from `laptop_price_prediction.zip`.
* **Feature Engineering:**
    * Created a new feature `Total_Storage` by combining `PrimaryStorage` and `SecondaryStorage`.
* **Data Preprocessing:**
    * Identified and dropped irrelevant columns such as `Product`, `PrimaryStorage`, `SecondaryStorage`, `ScreenW`, and `ScreenH`.
    * Applied Label Encoding to ordinal categorical features like `Screen` and `PrimaryStorageType` to convert them into numerical representations.
    * Performed One-Hot Encoding on other nominal categorical features to prepare them for model training.
* **Model Training & Evaluation:**
    * Split the dataset into training and testing sets (70% training, 30% testing).
    * Implemented and evaluated the following regression models:
        * **Linear Regression:** Served as a baseline model to understand initial performance.
        * **Lasso Regression:** Utilized for regularization and feature selection, aiming to prevent overfitting.
        * **Ridge Regression:** Another regularization technique applied to mitigate overfitting by penalizing large coefficients.
    * Model performance was assessed using key regression metrics: R-squared ($R^2$), Mean Absolute Error (MAE), and Mean Squared Error (MSE).

## Dataset

The dataset used for this project is `laptop_price_prediction.zip`. It contains 1275 entries and 23 initial columns. After preprocessing, the dataset expands to 262 columns due to one-hot encoding. Key columns include:

* `Company`: Manufacturer of the laptop.
* `Product`: Name/model of the laptop (dropped as an ID-type column).
* `TypeName`: Type of laptop (e.g., Ultrabook, Notebook).
* `Inches`: Screen size in inches.
* `Ram`: RAM in GB.
* `OS`: Operating System.
* `Weight`: Weight of the laptop.
* `Price_euros`: Selling price of the laptop in Euros (target variable).
* `Screen`: Screen type (e.g., Standard, Full HD, Quad HD+, 4K Ultra HD).
* `Touchscreen`: Whether the laptop has a touchscreen.
* `IPSpanel`: Whether the laptop has an IPS panel.
* `RetinaDisplay`: Whether the laptop has a Retina display.
* `CPU_company`: Manufacturer of the CPU.
* `CPU_freq`: CPU frequency.
* `CPU_model`: Model of the CPU.
* `PrimaryStorage`: Primary storage size (converted to `Total_Storage`).
* `SecondaryStorage`: Secondary storage size (converted to `Total_Storage`).
* `PrimaryStorageType`: Type of primary storage (e.g., SSD, HDD).
* `SecondaryStorageType`: Type of secondary storage.
* `GPU_company`: Manufacturer of the GPU.
* `GPU_model`: Model of the GPU.
* `Total_Storage`: Combined primary and secondary storage (engineered feature).

## Installation

To run this notebook, you'll need the following Python libraries:

```bash
pip install pandas scikit-learn
Usage
Clone the repository:
Bash

git clone [https://github.com/your-username/Laptop-Price-Prediction.git](https://github.com/your-username/Laptop-Price-Prediction.git)
cd Laptop-Price-Prediction
Place the laptop_price_prediction.zip dataset in the project directory.
Open and run the Laptop_Price_Prediction.ipynb notebook in a Jupyter environment.
Results
The models were evaluated based on R-squared, MAE, and MSE.

Linear Regression:

$R^2$: 0.7727
MAE: 242.59
MSE: 120016.61
Lasso Regression (alpha=10):

$R^2$: 0.7388
MAE: 269.52
MSE: 137949.36
Ridge Regression (alpha=10000000):

$R^2$: 0.0208
MAE: 553.12
MSE: 517138.49
Linear Regression demonstrated the best performance among the tested models, achieving the highest $R^2$ score and lowest MAE and MSE.
