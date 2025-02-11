# Data Cleaning, Exploration, and Feature Engineering with Python

This repository contains a collection of Jupyter Notebooks demonstrating various data manipulation techniques using Python libraries like Pandas, NumPy, Matplotlib, Seaborn, and Fuzzywuzzy.  These notebooks cover data loading, cleaning, visualization, fuzzy matching, and feature scaling.

## Notebook 1: Exploratory Data Analysis and Visualization

This notebook focuses on exploring and visualizing a car dataset (`Cars93.csv`).  It demonstrates how to:

* Load data from a CSV file using Pandas.
* Create various plots using Matplotlib and Seaborn, including:
    * Box plots to compare distributions of a variable across different categories (e.g., `Rev.per.mile` for different car manufacturers).
    * Histograms to visualize the distribution of a single variable (e.g., `MPG.city` and `MPG.highway`).
    * Line plots to explore the relationship between two variables (e.g., `Wheelbase` vs. `Turn.circle`).
    * Bar plots to compare the average value of a variable across different categories (e.g., `Horsepower` by `Type`).
* Customize plots with titles, labels, and legends.

**Key Libraries:** Pandas, Matplotlib, Seaborn

## Notebook 2: Data Cleaning and Fuzzy Matching

This notebook tackles data cleaning challenges, specifically focusing on inconsistent country names in a dataset (`store_income_data_task.csv`).  It showcases how to:

* Load data and inspect unique values in a column.
* Use Fuzzywuzzy library for fuzzy string matching to identify similar country names.
* Implement a function to replace inconsistent country names with standardized versions.  This includes handling variations like "uk," "u.k.," "england," etc., and mapping them to "United Kingdom."
* Handle missing values by replacing empty strings, slashes, and periods with NaN (Not a Number) and then potentially imputing or dropping them (although this notebook only replaces with NaN).
* Convert a date column (`date_measured`) to datetime objects using Pandas' `to_datetime` function.
* Calculate the difference between a date and today's date to create a new feature (`days_ago`).

**Key Libraries:** Pandas, NumPy, Fuzzywuzzy, chardet (potentially)

## Notebook 3: Data Preprocessing and Feature Scaling

This notebook explores data preprocessing techniques, particularly focusing on handling missing values and feature scaling. It includes:

* Loading data from a space-separated file (`balance_missing.txt`).
* Calculating and visualizing the percentage of missing values in the dataset.
* Demonstrating different strategies for handling missing data:
    * Removing rows with missing values using `dropna()`.
    * Removing columns with missing values using `dropna(axis=1)`.
    * Filling missing values with a specific value (e.g., 0) using `fillna()`.
    * Forward fill and then filling remaining NaNs with 0 using `bfill()` and `fillna()`.
* Explaining and applying feature scaling using:
    * StandardScaler for standardizing data (mean=0, standard deviation=1).  This is demonstrated on normally distributed data.
    * MinMaxScaler for normalizing data (scaling to a range between 0 and 1).  This is demonstrated on exponentially distributed data.
* Applying MinMaxScaler to a real-world dataset (`countries.csv`) to normalize the "IT.CEL.SETS.P2" (mobile cellular subscriptions) and "EG.ELC.ACCS.ZS" (access to electricity) columns.  It also shows how to visualize the original and scaled data side-by-side.

**Key Libraries:** Pandas, NumPy, Scikit-learn (MinMaxScaler, StandardScaler), Matplotlib, Seaborn

## Datasets

The following datasets are used in the notebooks:

* `Cars93.csv`:  Data on various car models.
* `store_income_data_task.csv`: Store income data with inconsistent country names.
* `balance_missing.txt`:  Dataset with missing values.
* `countries.csv`:  World development indicators data, including mobile cellular subscriptions and access to electricity.

## How to Run the Notebooks

1. Clone this repository.
2. Ensure you have the required Python libraries installed. You can install them using pip:
   ```bash
   pip install pandas numpy matplotlib seaborn fuzzywuzzy scikit-learn
