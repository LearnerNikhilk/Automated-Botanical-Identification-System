# 🌸 Automated Botanical Identification System 

**🚀 Live Web Application:** [Test the live model here!](https://species-scout.lovable.app)

## 📌 Project Overview
Botanical research centers study various species of Iris flowers. Traditionally, botanists manually identify flower species by measuring sepal and petal dimensions. This manual process is time-consuming, prone to human error, and difficult to scale. 

The objective of this project was to build and deploy an end-to-end **Machine Learning classification system** that automatically predicts the exact species of an Iris flower based on its physical measurements, culminating in an interactive web application for researchers.

## 🛠️ Tech Stack
* **Machine Learning & Data Processing:** Python, Pandas, Scikit-learn, NumPy
* **Algorithms Evaluated:** K-Nearest Neighbors (KNN), Naive Bayes, Multinomial Logistic Regression
* **Frontend & Deployment:** Lovable (Interactive Web UI with browser-based inference)

## 🧠 Methodology & Model Training
1. **Data Preprocessing:** Loaded the dataset and isolated the target variable (`Species`).
   * **Crucial Step:** Removed the `Id` column to prevent data leakage. Since `Id` is a sequential identifier and not a physical measurement, stripping it ensures the models learned actual biological patterns rather than artificially memorizing data rows.
2. **Feature Scaling:** Applied `StandardScaler` to normalize dimensions, which is critical for distance and gradient-based algorithms.
3. **Model Training & Evaluation:** Split the data into 80% training and 20% testing sets to ensure valid results on unseen data. 

## 🏆 Model Selection & Results
All three models achieved perfect performance metrics on the `X_test` unseen data due to the highly distinct linear separability of the dataset:
* **Accuracy:** 100% 
* **Precision (Weighted):** 100% 
* **Recall (Weighted):** 100% 

**Final Recommendation for Deployment: Logistic Regression**
While all models tied in accuracy, **Multinomial Logistic Regression** was selected as the production model. Unlike KNN (which is lazy and memory-heavy), Logistic Regression is incredibly fast, highly scalable, and outputs exact **probability scores** (e.g., "98% confident this is Iris-setosa"). This provides researchers with a quantifiable confidence metric rather than just a hard categorical output.

## 🌐 Web App Deployment
The winning Logistic Regression model and the `StandardScaler` parameters were extracted and deployed into a live, user-friendly frontend. 

**How to use the app:**
1. Visit the [Species Scout Web App](https://species-scout.lovable.app).
2. Adjust the sliders to input the exact Sepal Length, Sepal Width, Petal Length, and Petal Width (in cm).
3. Click **Predict Species** to instantly view the model's classification along with visual probability bars for all three potential species.
