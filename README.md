EV Car Price Prediction using Linear Regression
📌 Project Overview

This project uses Linear Regression to predict the price of electric vehicles (EVs) based on their driving range.

The project is implemented in Python using Google Colab and uses a dataset containing information about EV brands, models, price, range, power, and battery capacity.
🎯 Objective

The main objective of this project is to:

    Analyze an EV car dataset.
    Use Range as the input feature.
    Predict the Price of an electric vehicle.
    Build a Linear Regression model.
    Evaluate the model using different regression metrics.

📊 Dataset

The dataset contains 26 EV car records and 6 columns:
Column 	Description
Brand 	Brand of the electric vehicle
Model 	Model name of the vehicle
Price 	Price of the EV
Range 	Driving range of the EV
Power 	Power of the vehicle
Battery 	Battery capacity

The dataset contains no missing values in the Range and Price columns after preprocessing.
🛠️ Technologies Used

    Python
    Pandas
    NumPy
    Matplotlib
    Seaborn
    Scikit-learn
    Google Colab

🔄 Methodology
1. Import Libraries

The project uses Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn libraries.
2. Load the Dataset

The EV dataset is loaded using Pandas.

df = pd.read_csv("ev_car_India_dataset.csv")

3. Explore the Dataset

The dataset is inspected using:

    df.head()
    df.info()
    df.shape

The dataset contains 26 rows and 6 columns.
4. Data Preprocessing

Missing values in the Range and Price columns are removed.

df = df.dropna(subset=["Range", "Price"])

5. Feature and Target Selection

    Feature (X): Range
    Target (Y): Price

x = df[["Range"]]
y = df["Price"]

6. Train-Test Split

The dataset is divided into training and testing data using an 80:20 split.

x_train, x_test, y_train, y_test = train_test_split(
    x, y, test_size=0.2, random_state=42
)

7. Build the Linear Regression Model

A Linear Regression model is created and trained using the training data.

model = LinearRegression()
model.fit(x_train, y_train)

8. Prediction

The trained model predicts EV prices for the test data.

y_pred = model.predict(x_test)

9. Model Evaluation

The model is evaluated using:

    Mean Absolute Error (MAE)
    Mean Squared Error (MSE)
    Root Mean Squared Error (RMSE)
    R² Score

📈 Results

The model produced the following results:
Metric 	Value
MAE 	17.5081
MSE 	410.5502
RMSE 	20.2620
R² Score 	0.2179

These values are directly obtained from the notebook's model evaluation.

The learned linear regression equation is approximately:

Price = 0.1414 × Range − 34.3961

The slope and intercept are obtained from the trained model.
📉 Visualization

An Actual vs Predicted plot is created to compare the actual EV prices with the prices predicted by the Linear Regression model.
🔍 Conclusion

This project demonstrates how Linear Regression can be applied to predict EV prices using vehicle range as a feature.

The model shows a positive relationship between range and price, but the relatively low R² score of 0.2179 indicates that Range alone does not explain most of the variation in EV prices in this dataset.

Using additional features such as Power, Battery capacity, Brand, and other vehicle specifications could potentially improve the prediction performance.
📁 Project Structure

ML_NTask_3/
│
├── ML_NTask_3.ipynb
├── ev_car_India_dataset.csv
└── README.md

👩‍💻 Author

Arockiya Jeniliya J

BCA Student | Aspiring Full Stack Developer
