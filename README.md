# ☕ Coffee Shop Sales Analysis (Google Colab Project)

This project analyzes **Coffee Shop Sales data** using **Google Colab, Python, Pandas, and Excel**.  
The goal is to identify **sales patterns, customer trends, and insights** to improve business decisions.  

---

## 📌 Project Overview
- Cleaned and processed raw sales data (Excel).
- Performed **data preprocessing** (handling missing values, converting columns).
- Created **visualizations** for sales trends.
- Built a **correlation matrix** to find relationships between sales, quantity, and other factors.
- Suggested strategies for business improvement based on analysis.

---

## 📂 Dataset
- The dataset contains coffee shop transaction details:
  - **Transaction Date**
  - **Product Category**
  - **Quantity**
  - **Total Amount**
  - **Customer Details** (if available)

---

## 🛠️ Technologies Used
- **Google Colab** (Python execution environment)
- **Python** (Data Analysis)
- **Pandas** (Data manipulation & cleaning)
- **Matplotlib / Seaborn** (Data visualization)
- **Excel (.xlsx)** (Raw dataset input)

---

## 📊 Topics Covered
1. Importing and reading Excel data in Colab  
2. Data Cleaning:
   - Converting numeric columns
   - Handling missing values
   - Converting date column  
3. Exploratory Data Analysis (EDA):
   - Sales trends over time
   - Quantity vs. Amount analysis
   - Category-wise sales  
4. Correlation Matrix:
   - Understanding relationships between sales metrics  
5. Visualizations:
   - Line Charts
   - Bar Charts
   - Heatmaps  
6. Business Insights & Suggestions  

---

## 💻 Code Snippets
```python
from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Upload dataset
uploaded = files.upload()
df = pd.read_excel("DATA[1].xlsx")

# Convert numeric columns
df["Total Amount"] = pd.to_numeric(df["Total Amount"], errors="coerce")
df["Quantity"] = pd.to_numeric(df["Quantity"], errors="coerce")

# Convert Date
df["Transaction Date"] = pd.to_datetime(df["Transaction Date"], errors="coerce")

# Drop missing values
df = df.dropna(subset=["Total Amount", "Quantity", "Transaction Date"])
# Convert numeric columns
df["Total Amount"] = pd.to_numeric(df["Total Amount"], errors="coerce")
df["Quantity"] = pd.to_numeric(df["Quantity"], errors="coerce")

# Convert Date
df["Transaction Date"] = pd.to_datetime(df["Transaction Date"], errors="coerce")

# Drop missing values
df = df.dropna(subset=["Total Amount", "Quantity", "Transaction Date"])
monthly_sales = df.resample("M", on="Transaction Date")["Total Amount"].sum()
plt.figure(figsize=(10,5))
monthly_sales.plot(kind="line", marker="o", color="b")
plt.title("Monthly Sales Trend")
plt.xlabel("Month")
plt.ylabel("Total Sales")
plt.grid(True)
plt.show()
category_sales = df.groupby("Product Category")["Total Amount"].sum().sort_values(ascending=False)
plt.figure(figsize=(8,5))
category_sales.plot(kind="bar", color="teal")
plt.title("Sales by Product Category")
plt.ylabel("Total Sales")
plt.show()
plt.figure(figsize=(6,4))
sns.heatmap(df[["Quantity", "Total Amount"]].corr(), annot=True, cmap="coolwarm", linewidths=0.5)
plt.title("Correlation Matrix")
plt.show()
Coffee-Shop-Sales-Analysis/
│── DATA[1].xlsx                # Dataset
│── Coffee_Shop_Sales.ipynb     # Google Colab Notebook
│── README.md                   # Project Documentation


