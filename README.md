# Handling_Imputation_Techniques
Data Preprocessing and Missing Values Handling

Overview

This project demonstrates data preprocessing techniques in Python, including handling missing values using various imputation methods (mean, median, and mode). The steps are illustrated using datasets related to diabetes and company profits/success. The workflow includes reading datasets, identifying and handling missing values, and cleaning the data for further analysis.

Files

diabetes.csv: Dataset containing diabetes-related metrics.

CompanyProfit.csv: Dataset containing profit data for companies.

CompanyProfit_new.csv: A modified version of the profit dataset with additional missing values.

CompanySuccess.csv: Dataset containing company success metrics.

Steps in Data Preprocessing

Diabetes Dataset

Reading the Dataset

Loaded the dataset using pd.read_csv().

Displayed the first few rows using data.head().

Exploratory Data Analysis

Checked the dataset dimensions using data.shape.

Generated basic statistics using data.describe().

Replacing Zeroes with NaN

Replaced zero values in specific columns (Glucose, BloodPressure, SkinThickness, Insulin, BMI) with NaN using:

data[columns[1:6]] = data[columns[1:6]].replace(0, np.NaN)

Handling Missing Values

Counted null values using data.isnull().sum().

Dropped rows with missing values using data.dropna(inplace=True).

Company Profit and Success Datasets

Handling Missing Values with Imputation

Mean Imputation

Used the mean method for normally distributed data in the Profit ($) column:

col = data['Profit ($)']
col.fillna(col.mean(), inplace=True)

Median Imputation

Used the median method for skewed data in the Profit ($) column:

col = data1['Profit ($)']
col.fillna(col.median(), inplace=True)

Mode Imputation

Used the mode method for categorical data in the Success column:

col = data2['Success']
col.fillna(col.mode()[0], inplace=True)

Visualization

Visualized data distributions using seaborn to determine the appropriate imputation technique:

sns.distplot(data['Profit ($)'])

Results

Successfully handled missing values in all datasets using various imputation techniques.

Verified changes by checking null values post-processing.

Requirements

Python 3.x

Pandas

NumPy

Seaborn

How to Run

Place the datasets (diabetes.csv, CompanyProfit.csv, CompanyProfit_new.csv, CompanySuccess.csv) in the project directory.

Execute the Python script to preprocess and clean the data.

Notes

Mean imputation is suitable for normally distributed data.

Median imputation works best for skewed data.

Mode imputation is ideal for categorical data.

Future Work

Extend preprocessing to include feature scaling and encoding.

Automate the selection of imputation techniques based on distribution analysis.
