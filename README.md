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

### 1. Import Libraries & Upload File
```python
from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Upload dataset
uploaded = files.upload()
df = pd.read_excel("DATA[1].xlsx")

