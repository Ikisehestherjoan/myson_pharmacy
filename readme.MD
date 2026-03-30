---

# ⚡ PySpark Data Cleaning & Transformation Project

## 📌 Case Study Overview

**Myson Clinics & Pharmaceuticals** conducted a clinical study on **Naproxen**, a drug claimed to help normalize blood pressure in teenagers and young adults.

* **Participants:** 2,000+ individuals
* **Age Range:** 14 – 22 years
* **Duration:** February – May 2021
* **Groups:**

  * Active Group (Naproxen)
  * Control Group (Placebo)

The experiment was conducted across three clinic branches, and detailed records were collected for analysis. However, the dataset required significant cleaning and transformation before it could be effectively used by clinicians and machine learning engineers.

As the **Data Engineer**, the objective of this project is to prepare and transform the dataset for downstream analytics and machine learning tasks using **PySpark**.

---

## 🎯 Project Objectives

* Clean and preprocess raw clinical data
* Transform data into an analysis-ready format
* Optimize data processing using Spark
* Enable efficient access for analytics and ML workflows

---

## 🚀 Key Concepts Covered

### 1. Apache Spark & PySpark

* Leveraged **Apache Spark** for distributed data processing
* Used **PySpark** to perform scalable data transformations using Python

### 2. Data Partitioning

* Improved performance by splitting data into partitions
* Enabled parallel processing for large datasets
* Optimized query execution and scalability

### 3. Storage Optimization

* Evaluated storage formats (Parquet, CSV, JSON)
* Selected efficient storage strategies based on data type and use case

### 4. Data Cleaning & Transformation

* Converted raw, inconsistent data into structured and usable formats
* Applied feature engineering techniques to enhance analysis

---

## 🧹 Data Cleaning Steps

### 1. Handling Null Values

* Identified missing values using `.isNull()`
* Applied imputation strategies (mean, median, mode)
* Dropped records where necessary using `.dropna()`

### 2. Data Type Conversion

* Inspected schema using `.dtypes`
* Converted columns using `.cast()` (e.g., string → date)

### 3. Handling Multi-Value Fields

* Split columns using `.split()`
* Restructured data using `.groupBy()` and `.pivot()`
* Aggregated results using `.agg()`

---

## 🔄 Data Transformation Steps

### 1. Column Standardization

* Renamed columns using `.withColumnRenamed()` for clarity

### 2. Null Handling (Post-cleaning)

* Applied business logic to remaining null values

### 3. Partitioning & Sorting

* Used `.repartition()` for performance optimization
* Sorted data using `.orderBy()`

### 4. Date Transformation

* Converted date strings using `to_date()`
* Created timestamp fields for better time-based analysis

### 5. Data Output & Reporting

* Selected relevant columns using `.select()`
* Performed aggregations using `.groupBy()`
* Exported processed data using `.write()` (Parquet, CSV, JSON)

---

## 🛠️ Tools & Technologies

* **Apache Spark / PySpark** – Distributed data processing
* **Jupyter Notebook** – Interactive development
* **VS Code / PyCharm** – Development environment
* **Pandas** – Lightweight data exploration
* **SQL** – Querying and transformation
* **Git** – Version control

---

## 🧬 Schema Evolution

### 🔹 Initial Schema

```id="0n0p7c"
root
 |-- ageofparticipant: long
 |-- clinician: struct
 |    |-- branch: string
 |    |-- name: string
 |    |-- role: string
 |-- drug_used: string
 |-- experimentenddate: string
 |-- experimentstartdate: string
 |-- noofhourspassedatfirstreaction: long
 |-- result: struct
 |    |-- conclusion: string
 |    |-- sideeffectsonparticipant: string
```

---

### 🔹 Final Schema (Transformed)

```id="6j6z1k"
root
 |-- age_of_participant: long
 |-- clinic_branch: string
 |-- head_clinician: string
 |-- assistants_role: string
 |-- drug_used: string
 |-- experiment_end_date: string
 |-- experiment_start_date: string
 |-- no_of_hours_passed_at_first_reaction: long
 |-- conclusion: string
 |-- side_effects_on_participant: string
 |-- starts_ts: timestamp
 |-- end_ts: timestamp
```

---

## 📌 Key Improvements

* Flattened nested structures (`struct` fields)
* Standardized column naming conventions
* Created timestamp fields for time-based analysis
* Improved data accessibility and usability

---

## 📊 Outcome

The transformed dataset is:

* Clean and consistent
* Optimized for large-scale processing
* Ready for machine learning and analytics

This ensures clinicians and ML engineers can efficiently derive insights and build predictive models for the next phase of the study.

---


