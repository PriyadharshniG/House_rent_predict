##  House Rent Prediction & Data Visualization

### 📌 Project Overview

This project aims to analyze and predict **house rent prices** in Dhaka, Bangladesh using machine learning techniques. The dataset contains features such as location, area, number of bedrooms, bathrooms, and rent (in Thousand or Lakh Taka). The project includes **data cleaning**, **visualization**, and **preparation for modeling**.

---

### 🔧 Features

* Cleaned and standardized prices (from "Thousand" and "Lakh" formats)
* Extracted numeric area from "sqft" strings
* Visualized trends in rental prices across different features
* Grouped top 10 locations by average rent
* Prepared dataset for machine learning modeling

---

### 🧠 Technologies Used

* Python 
* Pandas for data handling
* Matplotlib and Seaborn for visualization
* Jupyter Notebook
* (Optional) Scikit-learn for ML modeling

---

### 📊 Visualizations Included

* Distribution of rent prices
* Area vs Rent (scatter plot)
* Average rent by number of bedrooms
* Box plot of rent by bathrooms
* Top 10 locations by average rent

---

### 📁 Dataset Columns

| Column   | Description                 |
| -------- | --------------------------- |
| Location | Area name in Dhaka          |
| Area     | House area (in sqft)        |
| Bed      | Number of bedrooms          |
| Bath     | Number of bathrooms         |
| Price    | Rent (in "Thousand"/"Lakh") |

---

### 🧹 Data Cleaning Highlights

```python
# Convert 'Price' to numeric value in Taka
def convert_price(price_str):
    if "Thousand" in price_str:
        return float(price_str.replace("Thousand", "").strip()) * 1000
    elif "Lakh" in price_str:
        return float(price_str.replace("Lakh", "").strip()) * 100000

# Clean 'Area'
df['Area'] = df['Area'].str.replace(',', '').str.extract('(\d+)').astype(float)
```

---

### 📈 Sample Visualization

```python
top_locations = df.groupby("Location")["Price"].mean().sort_values(ascending=False).head(10)

sns.barplot(x=top_locations.values, y=top_locations.index)
plt.title("Top 10 Locations by Average Rent")
```

---


### 📬 Author

**Priyadharshni G**
*Aspiring Full Stack Web Developer & ML Enthusiast*



