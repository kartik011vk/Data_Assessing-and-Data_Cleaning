# Data Assessment and Data Cleaning

## Project Overview

This project focuses on assessing and cleaning clinical trial data using Python and Pandas. The objective was to identify and resolve both data quality and data tidiness issues, transforming the datasets into a clean and analysis-ready format.

The clinical trial was conducted to evaluate the effectiveness of **Auralin**, an oral insulin treatment, compared with **Novodra**, a commonly used injectable insulin treatment.

---

## Dataset Summary

The dataset contains information about **500 patients**, of which **350 patients participated in a clinical trial**.

Prior to the study:

* None of the participants were using Auralin or Novodra as their primary insulin treatment.
* All participants were experiencing elevated HbA1c levels.

Study Design:

1. All 350 participants were initially treated with Novodra to establish baseline HbA1c levels and insulin dosage requirements.
2. After four weeks:

   * 175 patients switched to Auralin for 24 weeks.
   * 175 patients continued treatment with Novodra for 24 weeks.
3. Adverse reactions experienced during treatment were also recorded.

---

## Datasets Included

The project contains four datasets:

### 1. Patients

Contains demographic and personal information about patients.

### 2. Treatment

Contains treatment information, insulin dosage ranges, and HbA1c measurements.

### 3. Treatment Cut

A modified version of the treatment dataset used during the data-cleaning process.

### 4. Adverse Reactions

Contains information about adverse reactions reported by patients during treatment.

---

# Column Descriptions

## Patients Table

| Column       | Description                                   |
| ------------ | --------------------------------------------- |
| patient_id   | Unique identifier assigned to each patient    |
| assigned_sex | Patient's assigned sex at birth (male/female) |
| given_name   | Patient's first name                          |
| surname      | Patient's last name                           |
| address      | Primary residential address                   |
| city         | City corresponding to the address             |
| state        | State corresponding to the address            |
| zip_code     | Postal ZIP code                               |
| country      | Country of residence                          |
| contact      | Combined phone number and email information   |
| birthdate    | Date of birth of the patient                  |
| weight       | Patient weight in pounds (lbs)                |
| height       | Patient height in inches (in)                 |
| bmi          | Body Mass Index (BMI)                         |

---

## Treatment and Treatment_Cut Tables

| Column       | Description                                                                |
| ------------ | -------------------------------------------------------------------------- |
| given_name   | Patient first name                                                         |
| surname      | Patient last name                                                          |
| auralin      | Starting and ending daily insulin dosage for patients switched to Auralin  |
| novodra      | Starting and ending daily insulin dosage for patients remaining on Novodra |
| hba1c_start  | HbA1c level at the beginning of treatment                                  |
| hba1c_end    | HbA1c level at the end of treatment                                        |
| hba1c_change | Difference between starting and ending HbA1c levels                        |

---

## Adverse_Reactions Table

| Column           | Description                                            |
| ---------------- | ------------------------------------------------------ |
| given_name       | Patient first name                                     |
| surname          | Patient last name                                      |
| adverse_reaction | Reported adverse reaction experienced during treatment |

---

# Data Cleaning Tasks Performed

## Data Quality Assessment

The following quality issues were identified and addressed:

* Missing values
* Duplicate records
* Inconsistent formatting
* Incorrect data types
* Mixed information stored within a single column
* Invalid or incomplete records

---

## Data Cleaning Steps

### 1. Missing Value Assessment

* Identified missing values using:

  * isnull()
  * info()
  * describe()

### 2. Duplicate Detection

* Checked duplicate records using:

  * duplicated()

### 3. Contact Information Extraction

The contact column contained both phone numbers and email addresses in a single field.

Examples:

* [951-719-9170ZoeWellish@superrito.com](mailto:951-719-9170ZoeWellish@superrito.com)
* [PamelaSHill@cuvox.de](mailto:PamelaSHill@cuvox.de)+1 (217) 569-3204

Regex was used to extract:

* Email addresses
* Phone numbers

into separate columns.

### 4. Data Reshaping

The treatment dataset contained treatment types stored as separate columns.

Pandas melt() was used to convert the data from:

* Wide format

to

* Long/Tidy format

making analysis easier.

### 5. Dosage Range Splitting

Dosage ranges such as:

41u-48u

were separated into:

* dosage_start
* dosage_end

using string operations.

### 6. Column Standardization

Column values were standardized to improve consistency and readability.

### 7. Data Type Verification

Verified data types and ensured columns contained appropriate values for analysis.

---

# Skills Demonstrated

This project demonstrates practical experience with:

* Data Assessment
* Data Cleaning
* Data Wrangling
* Data Transformation
* Missing Value Handling
* Duplicate Detection
* Pandas
* NumPy
* Regular Expressions (Regex)
* String Manipulation
* Data Reshaping
* Exploratory Data Preparation

---

# Technologies Used

* Python
* Pandas
* NumPy
* Google Colab
* GitHub
* Regular Expressions (Regex)

---

# Repository Structure

```text
Data_Assessing_and_Data_Cleaning/
│
├── Data_cleaning.ipynb
├── README.md
```

---

# Key Learning Outcomes

Through this project I learned how to:

* Assess real-world datasets for quality issues.
* Clean messy data using Pandas.
* Handle missing values and duplicates.
* Use Regular Expressions (Regex) for text extraction.
* Reshape datasets using melt().
* Prepare data for downstream analysis and machine learning workflows.

---

# Conclusion

The clinical trial datasets were successfully assessed, cleaned, and transformed into a tidy format suitable for further statistical analysis, visualization, and machine learning applications.

