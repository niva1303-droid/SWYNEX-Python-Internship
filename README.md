# 🏋️‍♂️ Gym Membership Dataset – Data Cleaning Project

## 📌 Project Overview

This project focuses on cleaning and preparing the **Gym Membership Dataset – Exploring Membership Trends**.

The dataset was examined for common data-quality issues, including missing values, duplicate records, incorrect data types, inconsistent categorical values, and inconsistent column naming.

The cleaning process was performed using **Python and Pandas in Google Colab**.

---

## 📓 Dataset

The dataset contains **1,000 records and 17 columns** related to gym members and their membership behavior.

The dataset includes information such as:

* Gender
* Birthday
* Age
* Membership type
* Weekly gym visits
* Workout days
* Group lesson participation
* Favorite group lesson
* Average check-in and check-out times
* Average time spent in the gym
* Drink subscription
* Favorite drink
* Personal training
* Personal trainer
* Sauna usage

---

## 💪✅ Data Quality Checks

The following data-quality areas were investigated during the cleaning process.

### 1. Missing Values

Missing values were identified in three columns:

| Column                  | Missing Values |
| ----------------------- | -------------: |
| `fav_group_lesson`      |            497 |
| `fav_drink`             |            504 |
| `name_personal_trainer` |            482 |

Cross-tabulation was used to investigate the reason for these missing values.

The analysis showed that:

* Members who did not attend group lessons had no favorite group lesson.
* Members without a drink subscription had no favorite drink.
* Members without personal training had no personal trainer name.

Therefore, these were identified as **conditional missing values** rather than random missing data.

The missing values were replaced with **"Not Applicable"**.

### 2. Duplicate Records

The dataset was checked for both complete duplicate rows and duplicate member IDs.

No duplicate records or duplicate IDs were identified.

Therefore, no records were removed from the dataset.

### 3. Data Type Validation

The data types of all columns were reviewed.

* Numerical fields were stored as integer values.
* `birthday` was stored as a datetime value.
* Boolean fields were stored as `True/False`.
* Average check-in and check-out values were verified as `datetime.time` objects.

No unnecessary data-type conversions were required.

### 4. Inconsistent Values

Categorical columns were examined using unique-value frequency counts.

Some columns contained multiple selections stored in different orders.

For example:

`orange, black_currant`

and

`black_currant, orange`

represent the same combination but could be interpreted as separate categories.

To improve consistency, multiple values were stripped of unnecessary spaces and alphabetically sorted in the following columns:

* `days_per_week`
* `fav_group_lesson`
* `fav_drink`

This ensures that equivalent combinations are represented consistently throughout the dataset.

### 5. Column Name Cleaning

The original column:

`abonoment_type`

was renamed to:

`membership_type`

Column headers were also formatted consistently in the final cleaned dataset.

---

## 🧰 Tools Used

* Python
* Pandas
* Google Colab
* Microsoft Excel

---

## 🧹 Cleaning Summary

| Data Quality Issue                  | Action Taken                                                |
| ----------------------------------- | ----------------------------------------------------------- |
| Missing values                      | Replaced conditional missing values with `"Not Applicable"` |
| Duplicate records                   | Checked; no duplicate records found                         |
| Duplicate IDs                       | Checked; no duplicate IDs found                             |
| Incorrect data types                | Reviewed and validated                                      |
| Inconsistent multi-value categories | Standardized the order of values                            |
| Misspelled column name              | Renamed `abonoment_type` to `membership_type`               |
| Column headers                      | Standardized for consistency                                |

---

## 📦 Final Dataset

The cleaned dataset contains:

* **1,000 records**
* **17 columns**
* **No missing values**
* **No duplicate records**
* Consistently formatted categorical values and column headers

No rows were unnecessarily removed during the cleaning process.

The cleaned dataset was exported as:

`gym_membership_cleaned.xlsx`

---

## 📂 Project Files

The repository contains:

* Original Gym Membership Dataset
* Python/Google Colab data-cleaning notebook
* `gym_membership_cleaned.xlsx`
* `README.md`

---

## ∴ Conclusion

The **Gym Membership Dataset** was successfully reviewed and cleaned by handling conditional missing values, checking duplicate records, validating data types, standardizing multi-value categorical fields, and improving column naming consistency.

The cleaned dataset is now ready for **Exploratory Data Analysis (EDA), visualization, and potential Machine Learning applications**.
