# 🚗 EV Car Price Prediction Using Linear Regression

## 📌 Project Overview

This project focuses on predicting the **price of Electric Vehicles (EVs)** using **Linear Regression**. The model uses the vehicle's **driving range** as the main input feature to estimate its price.

The project is implemented in **Python using Google Colab** and uses an EV dataset containing information such as brand, model, price, driving range, power, and battery capacity.

---

## 🎯 Objective

The main objectives of this project are:

* Analyze and understand an EV car dataset.
* Perform basic data preprocessing.
* Use **Range** as the input feature.
* Predict the **Price** of electric vehicles.
* Build a **Linear Regression** model.
* Evaluate the model using standard regression metrics.
* Visualize the actual and predicted prices.

---

## 📊 Dataset

The dataset contains **26 EV car records** and **6 columns**.

| Column      | Description                   |
| ----------- | ----------------------------- |
| **Brand**   | Brand of the electric vehicle |
| **Model**   | Model name of the vehicle     |
| **Price**   | Price of the electric vehicle |
| **Range**   | Driving range of the vehicle  |
| **Power**   | Power output of the vehicle   |
| **Battery** | Battery capacity              |

After preprocessing, there are no missing values in the **Range** and **Price** columns used for modeling.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Google Colab**

---

## 🔄 Methodology

### 1. Import Libraries

The project uses Python libraries for data manipulation, visualization, and machine learning.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score
```

### 2. Load the Dataset

The EV dataset is loaded using Pandas.

```python
df = pd.read_csv("ev_car_India_dataset.csv")
```

### 3. Explore the Dataset

The dataset is explored using:

```python
df.head()
df.info()
df.shape
```

The dataset contains **26 rows and 6 columns**.

### 4. Data Preprocessing

Missing values in the **Range** and **Price** columns are removed.

```python
df = df.dropna(subset=["Range", "Price"])
```

### 5. Feature and Target Selection

* **Feature (X):** Range
* **Target (Y):** Price

```python
x = df[["Range"]]
y = df["Price"]
```

### 6. Train-Test Split

The dataset is divided into training and testing sets using an **80:20 split**.

```python
x_train, x_test, y_train, y_test = train_test_split(
    x, y, test_size=0.2, random_state=42
)
```

### 7. Build the Linear Regression Model

A Linear Regression model is created and trained using the training data.

```python
model = LinearRegression()
model.fit(x_train, y_train)
```

### 8. Prediction

The trained model is used to predict EV prices for the test data.

```python
y_pred = model.predict(x_test)
```

### 9. Model Evaluation

The model performance is evaluated using the following regression metrics:

* **Mean Absolute Error (MAE)**
* **Mean Squared Error (MSE)**
* **Root Mean Squared Error (RMSE)**
* **R² Score**

---

## 📈 Results

The model produced the following evaluation results:

| Metric       |    Value |
| ------------ | -------: |
| **MAE**      |  17.5081 |
| **MSE**      | 410.5502 |
| **RMSE**     |  20.2620 |
| **R² Score** |   0.2179 |

### 📐 Linear Regression Equation

The learned regression equation is approximately:

**Price = 0.1414 × Range − 34.3961**

Where:

* **0.1414** → Slope/Coefficient
* **−34.3961** → Intercept
* **Range** → Input feature
* **Price** → Predicted target value

---

## 📉 Visualization

An **Actual vs Predicted Price** plot is created to compare the actual EV prices with the prices predicted by the Linear Regression model.

This visualization helps understand how closely the model's predictions match the actual prices.

---

## 🔍 Conclusion

This project demonstrates the application of **Linear Regression for EV price prediction** using vehicle **Range** as the input feature.

The model shows a **positive relationship between driving range and EV price**. However, the **R² score of 0.2179** indicates that Range alone explains only a limited portion of the variation in EV prices in this dataset.

The prediction performance could potentially be improved by including additional features such as:

* **Power**
* **Battery capacity**
* **Brand**
* **Vehicle specifications**
* Other relevant EV characteristics

Using multiple relevant features could provide the model with more information for predicting EV prices.

---

## 📁 Project Structure

```text
ML_NTask_3/
│
├── ML_NTask_3.ipynb
├── ev_car_India_dataset.csv
└── README.md
```

---

## 👩‍💻 Author

**Arockiya Jeniliya J**

BCA Student | Aspiring Full Stack Developer

