# Airbnb Market Analysis & Data Sanitization

## 📌 Project Overview
This project focuses on the end-to-end data cleaning and exploratory data analysis (EDA) of an "unclean" Airbnb dataset. The goal was to transform a raw, inconsistent dataset into a professional, analysis-ready format and derive insights into the NYC rental market.

As a former Software Engineer transitioning into Data Science, I emphasized **data integrity**, **memory optimization**, and **custom visualization** using native Python libraries.

## 🛠️ Tech Stack
- **Language:** Python 3.x
- **Libraries:** Pandas, NumPy, Matplotlib
- **Environment:** Jupyter Notebook / VS Code

## 🧹 Key Data Cleaning Challenges & Solutions

### 1. Smart Imputation (Neighborhood-Based)
Instead of using a global mean for missing prices—which would skew results—I implemented a neighborhood-based median imputation. 
- **Logic:** Prices in Manhattan differ significantly from Queens. Using `df.groupby('neighbourhood')['price'].transform('median')` ensured that missing values were replaced with locally realistic estimates.

### 2. Handling Encoding & "Ghost" Characters
Handled `utf-8-sig` encoding issues and removed hidden Byte Order Marks (BOM) often found in Excel-generated CSV files that cause column-naming errors.

### 3. Categorical Standardization
- Resolved inconsistent naming (e.g., "manhatan" vs "Manhattan").
- Applied Title Casing and whitespace stripping across all text-based features to ensure accurate grouping.

### 4. Memory Optimization & Type Casting
Converted high-cardinality `object` columns to `category` types and transformed illogical `float` counts (like 1.5 nights) into `int64` to improve processing speed and data logic.

## 📊 Visualizations
For this project, I chose to use **Native Matplotlib** over Seaborn to demonstrate a deeper understanding of the underlying plotting engine and to exercise full control over the visualization aesthetics.

- **Neighborhood Price Comparison:** A horizontal bar chart identifying the most expensive rental zones.
- **Price Distribution & Outliers:** A box plot analysis identifying ultra-luxury outliers in the market.
