# Data Cleaning & Feature Engineering Pipeline

## 📌 Project Overview
This project demonstrates an automated data cleaning pipeline built with Python and Pandas. The goal was to transform a messy, real-world dataset into a clean, analysis-ready format using a single, reusable function.

## 🛠️ The "Transformation Engine"
The core of this project is the `clean_data_project()` function, which handles:
* **Data Coercion:** Converts messy strings into proper Numeric and Datetime objects.
* **Missingness Audit:** Automatically generates boolean "mask" columns (e.g., `age_missing`) to track original data gaps.
* **Statistical Imputation:** Replaces null values using calculated medians and date-anchors to prevent data loss.
* **Outlier Management:** Clips extreme income values at the 99th percentile to stabilize the distribution.
* **String Normalization:** Cleans up text data (removing spaces and fixing casing) for consistent categorization.

## 📊 Metadata Planning Dictionary
This table represents the plan of action used to guide the pipeline logic:

| Feature | Data Type | Cleaning Strategy | Mask Column |
| :--- | :--- | :--- | :--- |
| **Age** | Numeric | Median Imputation | Yes |
| **Income** | Numeric | Median Imputation + 99th Cap | Yes |
| **City** | String | Lowercase & Whitespace Removal | No |
| **Signup Time** | Datetime | Fill with Minimum Date | Yes |

## 🚀 How to Use
1. Open the `.ipynb` file in Google Colab or Jupyter Notebook.
2. Ensure the raw dataset is loaded into the environment.
3. Run the pipeline function to generate the `cleaned_project_data.csv` file.
