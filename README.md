# 🛒 E-commerce Data Cleaning & Sales Analysis

A beginner-friendly data analysis project in Python that cleans a messy 30,000-row e-commerce dataset and explores sales patterns using Pandas and Matplotlib.

---

## 📌 Project Overview

Raw e-commerce data often contains inconsistent formatting, wrong data types, missing values, and duplicate rows. This project walks through a complete **data cleaning pipeline** and then performs **exploratory data analysis (EDA)** with visualizations to understand sales by date, city, category, and payment method.

## 📂 Repository Structure

```
├── data.ipynb                         # Jupyter/Colab notebook (cleaning + analysis)
├── messy_ecommerce_30000_rows.csv     # Raw dataset (input)
├── clean_ecommerce_data_set           # Cleaned dataset (output)
└── README.md
```

## 📊 Dataset Description

| Column | Description |
|---|---|
| `OrderID` | Unique order identifier |
| `Customer_Name` | Name of the customer |
| `Order_Date` | Date the order was placed |
| `Product` | Product purchased |
| `Category` | Product category |
| `Quantity` | Number of units ordered |
| `Price` | Price per unit |
| `Total_Sale` | Total sale amount |
| `Payment_Method` | Cash / Credit card / Debit card |
| `City` | Customer city (Islamabad, Karachi, Lahore) |
| `Discount` | Discount applied |

## 🧹 Data Cleaning Steps

1. **Imported libraries** – `pandas`, `numpy`, `matplotlib`
2. **Loaded the dataset** and inspected columns and data types
3. **Converted data types**
   - Text columns → `string`
   - `Price` and `Total_Sale` → `int`
   - `Discount` → numeric (`pd.to_numeric` with `errors='coerce'`)
   - `Order_Date` → `datetime`
4. **Standardized text** using `.str.strip()` and `.str.capitalize()`
5. **Handled missing values** using linear interpolation on numerical columns
6. **Removed duplicate rows** with `drop_duplicates()`
7. **Verified** there are no remaining null values
8. **Exported** the cleaned data to CSV

## 📈 Analysis & Visualizations

- **Total sales over time** – line chart (Jan–Jun 2025)
- **Total sales by region/city** – bar and horizontal bar charts
- **Total sales by category** – pie chart
- **Total sales by payment method** – pie chart

### Key Findings

- 🏙️ **Karachi** generates the highest sales (~8.4M), roughly double Islamabad (~4.2M) and Lahore (~4.2M).
- 💻 **Electronics** is the top-selling category.
- 💳 **Credit card** and **Cash** are the most used payment methods, with **Debit card** noticeably lower.

## ⚠️ Known Limitations / Future Improvements

- Category labels still contain variants of the same thing (`Sport` / `Sports`, `Stationary` / `Stationery`). Merging these would make the category analysis more accurate.
- Casting `Price` and `Total_Sale` to `int` drops decimal values; keeping them as `float` would preserve precision.
- Interpolation on `OrderID` is not ideal for an identifier column.
- The output CSV is saved without a `.csv` extension; use `df.to_csv('clean_ecommerce_data.csv', index=False)`.

## 🛠️ Tech Stack

- Python 3
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook / Google Colab

## 🚀 How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```
2. Install dependencies
   ```bash
   pip install pandas numpy matplotlib jupyter
   ```
3. Place `messy_ecommerce_30000_rows.csv` in the project folder and update the path in the notebook:
   ```python
   df = pd.read_csv("messy_ecommerce_30000_rows.csv")
   ```
4. Launch the notebook
   ```bash
   jupyter notebook data.ipynb
   ```

## 👤 Author

**Your Name**
GitHub: [@your-username](https://github.com/your-username)

---

⭐ If you found this project helpful, please give it a star!
