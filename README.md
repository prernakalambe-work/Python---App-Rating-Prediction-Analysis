# App Rating Prediction Analysis (using Python)
### Prerna Mangesh Kalambe

## 📌 Project Overview

With the rapid growth of mobile applications, identifying high-quality and promising apps has become crucial for platforms such as the **Google Play Store**. App ratings provided by users serve as a key indicator of an app’s quality, usability, and acceptance.

The goal of this project is to **build a predictive model that estimates app ratings** based on multiple app attributes such as **reviews, installs, price, size, category, and content rating**.
This analysis helps in identifying apps with high promotion potential and understanding the factors influencing user ratings.

---

## 📂 Dataset Description

* **Dataset Name:** Google Play Store Dataset [(googleplaystore.csv)](https://github.com/prernakalambe-work/Python---App-Rating-Prediction-Analysis/blob/9ecc67ebcc4155b3240d2ef180b7837517eb109d/1569582940_googleplaystore.zip)
* **Source:** Kaggle – Google Play Store Apps Data
* **Python Working File:** [App_Rating_Prediction.ipynb](https://github.com/prernakalambe-work/Python---App-Rating-Prediction-Analysis/blob/08cd2000c8eeffe5b5fe66e8417c536e44f23ca4/App_Rating_Prediction.ipynb)

### Key Features

* **App** – Application name
* **Category** – App category
* **Rating** – User rating (Target Variable)
* **Reviews** – Number of user reviews
* **Size** – App size
* **Installs** – Number of installs
* **Type** – Free or Paid
* **Price** – App price
* **Content Rating** – Target audience
* **Genres** – App genre
* **Last Updated, Current Ver, Android Ver** – App metadata

---

## 🛠️ Tools & Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook
* AI - ChatGPT, Grok

---

## 🔍 Data Loading & Initial Inspection

The dataset was loaded using **Pandas**, followed by initial exploration:

* Dataset shape
* Data types
* Missing values
* Data consistency

📸 **Screenshot**

* > Screenshots/1. Importing Libraries in Python Notebook.png
  <img width="957" height="637" alt="1  Importing Libraries in Python Notebook" src="https://github.com/user-attachments/assets/3c8e634e-0ca6-454b-b5ad-aa1487839be2" />

  <br>
  
* > Screenshots/2. Reading and loading Dataset .png
  <img width="943" height="825" alt="2  Reading and loading Dataset " src="https://github.com/user-attachments/assets/dc701d04-9951-4ef7-9627-e1e86e73c67b" />
  
  <br>
  
* > Screenshots/3. Checking Dataset Shape and Info.png
  <img width="956" height="900" alt="3  Checking Dataset Shape and Info" src="https://github.com/user-attachments/assets/164ffec2-313b-444e-b6ce-e209c26fb97b" />

  <br>
  
* > Screenshots/4.Checking Null Values .png
  <img width="953" height="908" alt="4 Checking Null Values " src="https://github.com/user-attachments/assets/0e429451-fddd-46f1-975f-92e87044109f" />

  <br>

---

## 🧹 Data Cleaning & Type Conversion

Several columns contained inconsistent formats and required cleaning:

* **Removed rows with missing values**
* **Converted Size** from KB/MB to numeric format
* **Converted Reviews** to numeric
* **Cleaned Installs** by removing `+` and commas
* **Cleaned Price** by removing `$` symbol

📸 **Screenshot**

* > Screenshots/5. Drop Rows with Null Values .png

  <img width="922" height="272" alt="5  Drop Rows with Null Values " src="https://github.com/user-attachments/assets/4b826cfb-3a3d-42bf-8182-94641fe5bd2b" />

  <br>
  
* > Screenshots/6. Cleaning the Size Column .png

  <img width="947" height="520" alt="6  Cleaning the Size Column " src="https://github.com/user-attachments/assets/5bb47a38-649b-4e49-b102-1aabaec77dc2" />

  <br>
  
* > Screenshots/7. Convert Reviews to Numeric .png

  <img width="935" height="266" alt="7  Convert Reviews to Numeric " src="https://github.com/user-attachments/assets/ad037a6b-46c8-4fef-b40c-70edd9422348" />

  <br>

* > Screenshots/8. Cleaning Installs and Price Columns .png

  <img width="923" height="423" alt="8  Cleaning Installs and Price Columns " src="https://github.com/user-attachments/assets/81321d2c-2d87-4944-9ea8-d2d8eebee737" />

  <br>
---

## ✅ Sanity Checks

Logical validations were applied to ensure realistic and reliable data:

* Ratings restricted between **1 and 5**
* Records where **reviews > installs** were removed
* Free apps with **non-zero price** were dropped

📸 **Screenshot**

* > Screenshots/9. Sanity Check .png

  <img width="958" height="837" alt="9  Sanity Check " src="https://github.com/user-attachments/assets/7724be2d-3a11-416d-93e5-70fb465d92e6" />

  <br>
---

## 📊 Univariate Analysis

Univariate analysis helped understand individual variable distributions:

* **Price:** Most apps are free or low-priced
* **Reviews:** Highly right-skewed
* **Ratings:** Concentrated towards higher values
* **Size:** Wide variation with some outliers

📸 **Screenshot**

* > Screenshots/10. Boxplot-Price .png

  <img width="958" height="913" alt="10  Boxplot-Price " src="https://github.com/user-attachments/assets/14e2b157-9f64-474a-8ff4-20e384874a7f" />

  <br>
  
* > Screenshots/11. Boxplot-Reviews .png

  <img width="957" height="903" alt="11  Boxplot-Reviews " src="https://github.com/user-attachments/assets/72407869-cf1f-499c-b429-7d398969b35c" />

  <br>
  
* > Screenshots/12. Histogram - Rating .png

  <img width="957" height="910" alt="12  Histogram - Rating " src="https://github.com/user-attachments/assets/06de5f68-fbac-418a-bf0e-bbb6ad4eecf4" />

  <br>

* > Screenshots/13. Histogram - Size .png

  <img width="955" height="905" alt="13  Histogram - Size " src="https://github.com/user-attachments/assets/4de81a08-dd2b-4c41-afb5-8e630f48cde2" />

  <br>
---

## 🚨 Outlier Treatment

Outliers were treated to improve model performance:

* Apps priced above **$200** were removed
* Apps with **more than 2 million reviews** were removed
* Extreme install values handled using percentile-based thresholds

📸 **Screenshot**

* > Screenshots/14. Outliers  .png

  <img width="965" height="885" alt="14  Outliers  " src="https://github.com/user-attachments/assets/760a27f6-8104-48cb-8f1b-f2c3ac1a4ae2" />

  <br>
---

## 📈 Bivariate Analysis

Relationships between **app ratings** and other variables were explored:

* Rating vs Price
* Rating vs Reviews
* Rating vs Content Rating
* Rating vs Category

Key insight:
Higher installs or reviews **do not always guarantee higher ratings**.

📸 **Screenshot**

* > Screenshots/15. Rating vs Price Analysis.png

  <img width="953" height="997" alt="15  Rating vs Price Analysis" src="https://github.com/user-attachments/assets/1db63657-f58d-4b85-86c5-6f8a4b22b823" />

  <br>
  
* > Screenshots/16. Rating vs Review Analysis .png

  <img width="957" height="1007" alt="16  Rating vs Review Analysis " src="https://github.com/user-attachments/assets/25130d3e-5242-49e5-987c-abeec90a4243" />

  <br>
  
* > Screenshots/17. Rating vs Content Rating .png

  <img width="958" height="908" alt="17  Rating vs Content Rating " src="https://github.com/user-attachments/assets/17cb9507-8dd1-4fbf-8d06-ba21369a2674" />

  <br>
  
* > Screenshots/18. Rating Vs Category Analysis.png

  <img width="956" height="911" alt="18  Rating Vs Category Analysis" src="https://github.com/user-attachments/assets/1810b13c-8a63-437b-b998-0297b733b506" />

  <br>
---

## 🔄 Data Preprocessing

Before model building:

* Applied **log1p transformation** on Reviews and Installs
* Dropped non-predictive columns (App name, versions, dates)
* Converted categorical variables using **dummy encoding**

📸 **Screenshot**

* > Screenshots/19. Data Preprocessing .png

  <img width="957" height="465" alt="19  Data Preprocessing " src="https://github.com/user-attachments/assets/99db4614-9830-445d-8d5d-eeb1f03bbdb1" />

  <br>
---

## 🤖 Model Building

* Dataset split into **70% training** and **30% testing**
* **Linear Regression** chosen for simplicity and interpretability
* Initial model threw errors due to null values, which were resolved

📸 **Screenshot**

* > Screenshots/20. Model Building .png

  <img width="921" height="267" alt="20  Model Building " src="https://github.com/user-attachments/assets/0621c8fa-4d1d-462b-89a6-08f0b1d2a2f5" />

  <br>
  
* > Screenshots/21. Linear Regression model throwing error due to null values .png

  <img width="953" height="898" alt="21  Linear Regression model throwing error due to null values " src="https://github.com/user-attachments/assets/583ef236-f97c-42d0-af8f-6e1b7d17b160" />

  <br>
  
* > Screenshots/22. Removing null and Creating Linear Regression Model .png

  <img width="952" height="898" alt="22  Removing null and Creating Linear Regression Model " src="https://github.com/user-attachments/assets/cf0f793d-c6ad-4781-bbdf-232ba8797342" />

  <br>
---

## 📏 Model Evaluation

* Evaluation Metric: **R² Score**
* Compared performance on **training vs test data**
* Results show moderate predictive power, highlighting the subjective nature of app ratings

📸 **Screenshot**

* > Screenshots/23. R square .png

  <img width="925" height="356" alt="23  R square " src="https://github.com/user-attachments/assets/7a449616-f544-4858-a5b4-09de416143b1" />

  <br>
---

## 🏁 Conclusion

This project demonstrates a complete **end-to-end data analysis and machine learning workflow**, including:

* Data cleaning
* Exploratory data analysis
* Feature engineering
* Predictive modeling

While the Linear Regression model provides a solid baseline, app ratings are influenced by many subjective and external factors.
Future improvements may include:

* Advanced regression models
* Feature expansion
* Better outlier handling

