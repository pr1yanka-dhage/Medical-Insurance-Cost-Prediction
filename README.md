# 💰 Insurance Cost Prediction

## 📖 Overview

This project predicts **medical insurance charges** based on personal and lifestyle features using **Linear Regression**. 🏥📊

The dataset includes demographic and health-related factors such as age, sex, BMI, children, smoking habits, and region. The goal is to build a regression model that can accurately estimate insurance costs.

---

## 📂 Dataset

* **File**: `insurance.csv`
* **Rows**: 1338
* **Columns**: 7

### Features

* 🎂 **Age** – Age of the primary beneficiary
* ⚧ **Sex** – Gender (male/female)
* ⚖️ **BMI** – Body Mass Index
* 👨‍👩‍👧 **Children** – Number of children/dependents covered
* 🚬 **Smoker** – Smoker (yes/no)
* 🌍 **Region** – Residential area (northeast, northwest, southeast, southwest)
* 💰 **Charges** – Medical insurance cost (Target)

✅ No missing values in the dataset.

---

## ⚙️ Preprocessing

1. 🔄 Encoded categorical variables:

   * Sex → male = 1, female = 0
   * Smoker → yes = 1, no = 0
   * Region → southeast = 0, southwest = 1, northeast = 2, northwest = 3
2. ✂️ Separated **features (X)** and **target (Y)**
3. 📚 Split into **train (80%)** and **test (20%)** datasets

---

## 📊 Exploratory Data Analysis (EDA)

* 📈 Age distribution → centered around 39 years
* 👥 Sex distribution → nearly balanced (676 males, 662 females)
* ⚖️ BMI distribution → average ~30.6, indicates many overweight individuals
* 👨‍👩‍👧 Children → most beneficiaries have 0–2 children
* 🚭 Smoking → 274 smokers, 1064 non-smokers
* 🌍 Regions → almost evenly distributed across 4 regions
* 💰 Charges → highly skewed with some very high-cost outliers

---

## 🧠 Model Training

* Algorithm: **Linear Regression**
* Train/Test split: **1070 / 268 records**

---

## 📈 Model Evaluation

### On Training Data:

* 📉 MSE Loss: **36,174,978**
* 📊 R² Score: **0.669**

### On Test Data:

* 📉 MSE Loss: **38,337,035**
* 📊 R² Score: **0.661**

The model generalizes well with consistent train and test performance. ✅

---

## 📊 Visualizations

* Age, BMI, Charges distributions (with KDE plots)
* Count plots: Sex, Children, Smoker, Region
* 📈 Scatter plots of Actual vs Predicted (train & test)
* 📉 Line plots comparing Actual vs Predicted values

Key Findings:

* 🚬 Smoking significantly increases insurance cost
* 📈 BMI and age also have strong positive correlation with charges

---

## 🚀 Predictive System Example

```python
sample = [23, 1, 23.845, 0, 0, 2]  # Example input
input_data_reshaped = np.array(sample).reshape(1, -1)

prediction = model.predict(input_data_reshaped)
print("Predicted Cost:", prediction[0])
```

💡 Example Output:

```
Predicted Cost: 1520.59
```

---

## 📦 Dependencies

* 🐼 pandas
* 🔢 numpy
* 📊 matplotlib
* 🎨 seaborn
* 🤖 scikit-learn

---

## 📝 Conclusion

* Linear Regression provides a **baseline model** for predicting insurance charges 💰
* Charges are strongly influenced by **smoking habits, BMI, and age** 🚬⚖️🎂
* This workflow can be extended using advanced models like **Random Forest, Gradient Boosting, or Neural Networks** for better accuracy 🚀
