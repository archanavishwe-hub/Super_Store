# Super_Store
# 🛒 KNN Regression – Sales Prediction Web Application

## 📌 Project Overview

This project is a **Machine Learning-based Sales Prediction Web Application** developed using the **K-Nearest Neighbors (KNN) Regression** algorithm.

The application uses product and outlet-related information such as item weight, fat content, visibility, MRP, outlet size, location type, establishment year, item type, and outlet type to generate a prediction.

The trained KNN model is integrated into a **Flask web application**, allowing users to enter input values through a web interface and obtain a prediction.

---

## 🎯 Objectives

* To implement **KNN Regression** for prediction.
* To preprocess categorical and numerical data.
* To use one-hot encoding for categorical variables.
* To save and load the trained Machine Learning model.
* To develop a user-friendly web interface using Flask.
* To generate predictions based on user-provided product and outlet information.

---

## 🧠 Machine Learning Algorithm

### K-Nearest Neighbors (KNN) Regression

KNN Regression predicts the output value by finding the nearest data points to the given input and calculating the prediction based on those neighboring observations.

In this project, the trained KNN model is loaded using Python's `pickle` module.

```python
with open("knn_regression_model.pkl", "rb") as file:
    model = pickle.load(file)
```

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Flask**
* **Pandas**
* **Scikit-learn**
* **HTML/CSS**
* **Pickle**
* **KNN Regression**

---

## 📊 Input Features

The application accepts the following input features:

### Numerical Features

* Item Weight
* Item Fat Content
* Item Visibility
* Item MRP
* Outlet Size
* Outlet Location Type
* Outlet Establishment Year

### Categorical Features

* Item Type
* Outlet Identifier
* Outlet Type

The Flask application receives these values from the HTML form and converts them into a Pandas DataFrame before prediction.

---

## 🔄 Project Workflow

```text
User Input
    ↓
Web Form
    ↓
Flask Application
    ↓
Data Preprocessing
    ↓
One-Hot Encoding
    ↓
KNN Regression Model
    ↓
Prediction
    ↓
Display Result
```

---

## 🔢 Data Preprocessing

Categorical variables are converted into dummy/one-hot encoded columns.

For example:

```text
Item Type
   ↓
Item_Type_Dairy
Item_Type_Meat
Item_Type_Snack Foods
Item_Type_Soft Drinks
...
```

Similarly, outlet identifiers and outlet types are converted into dummy variables.

The application ensures that the prediction input follows the **same feature order used during model training**, which is important for KNN prediction.

---

## 🌐 Flask Web Application

The Flask application contains two main routes.

### Home Route

```python
@app.route("/")
def home():
    return render_template("index.html")
```

This displays the main web page.

### Prediction Route

```python
@app.route("/predict", methods=["POST"])
def predict():
```

This route receives the values entered by the user, prepares the input data, sends it to the trained KNN model, and returns the prediction.

---

## 📁 Project Structure

```text
KNN-Regression/
│
├── app.py
├── KNN Regression.ipynb
├── knn_regression_model.pkl
│
├── templates/
│   └── index.html
│
├── static/
│   └── style.css
│
└── README.md
```

> Make sure `knn_regression_model.pkl` is present in the project directory because the Flask application loads this file when it starts.

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
```

### 2. Open the Project Folder

```bash
cd your-repository-name
```

### 3. Install Required Libraries

```bash
pip install flask pandas scikit-learn
```

### 4. Run the Flask Application

```bash
python app.py
```

### 5. Open in Browser

Open:

```text
http://127.0.0.1:5000/
```

---

## 🚀 How It Works

1. User opens the Flask web application.
2. User enters product and outlet information.
3. Flask receives the submitted form data.
4. Input values are converted into the required format.
5. Categorical features are converted into dummy variables.
6. The input columns are arranged according to the trained model.
7. The KNN Regression model generates the prediction.
8. The prediction is displayed on the web page.

The final prediction is generated using:

```python
prediction = model.predict(input_data)[0]
```

and displayed after rounding to two decimal places.

---

## ✨ Features

* 📊 Machine Learning-based prediction
* 🤖 KNN Regression algorithm
* 🌐 Flask web application
* 🧮 Numerical and categorical input handling
* 🔢 One-hot encoded categorical features
* 📱 Simple user interface
* ⚡ Fast prediction
* 💾 Pre-trained model integration

---

## 🔮 Future Enhancements

* Improve the prediction accuracy by testing different K values.
* Add model performance metrics such as MAE, MSE and R² score.
* Add graphs and visualizations.
* Improve the web interface using Bootstrap.
* Deploy the application online.
* Add multiple Machine Learning algorithms for comparison.
* Add input validation and error handling.

---




