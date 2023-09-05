## USING PYSPARK FOR DATA CLEANING AND TRANSFORMATION
### CASE STUDY
Myon Clinics & Pharmaceuticals conducted a research on  Naproxen - a drug that has been claimed to normalize the blood pressure of teens and young adults.
The trial was carried out in three of their clinic branches on over 2000 individuals of mixed genders from ages 14 - 22 between February and May 2021.This trial involved two groups - The in-active (Placebo) and active (Naproxen) groups to test the effect of the actual drug (Naproxen).
Records of all procedures were kept; and extracted from the storage for the ML Engineers to develop algorithms for the next stages of the experiment.It was discovered that the dataset needed some Engineering to be performed on it for easier access by the Clinicians & ML Engineers.
You have been hired as a Data Engineer specifically for this purpose.

In this project, we aim to delve deep into the realm of data processing and transformation, leveraging the versatile capabilities of Spark as a formidable Big Data processor, and its Python API, PySpark. We'll also explore the essential concept of data partitioning, which is a fundamental Data Engineering concept that plays a pivotal role in optimizing data workflows. Our goal is to not only understand these concepts but also apply them effectively to cater to the unique needs and data types of our users. 

Here's a personalized breakdown of what we aim to accomplish:

1. Mastering Spark and PySpark:
   - Our journey begins by gaining a comprehensive understanding of Spark as a robust Big Data processing engine. We'll explore its inner workings and its practical applications in handling vast datasets.
   - Additionally, we'll dive into PySpark, the Python API for Spark, which allows us to harness the power of Spark using the Python programming language. This opens up a world of possibilities for Python enthusiasts and data professionals alike.

2. Embracing Data Partitioning:
   - Data partitioning is the cornerstone of efficient data processing at scale. We will unravel the intricacies of this concept, understanding how it involves dividing large datasets into manageable partitions.
   - We'll explore why data partitioning is not just a technical detail but a necessary Data Engineering concept. It significantly impacts the performance, parallelism, and scalability of data workflows, making it an indispensable skill for any data professional.

3. Tailoring Storage Systems to User Needs:
   - One size does not fit all when it comes to data storage. We will delve into various storage systems and databases, understanding their strengths and weaknesses.
   - Our focus will be on aligning storage choices with the specific needs and data types of our users. Whether it's structured, semi-structured, or unstructured data, we'll choose the right storage solution to ensure data accessibility, durability, and performance.

4. Elevating Data Cleaning and Transformation Techniques:
   - Data is often messy and unrefined, but it holds valuable insights. We'll equip ourselves with advanced data cleaning and transformation techniques.
   - Our objective is to transform raw data into actionable insights. We'll explore a range of methods, from data imputation to feature engineering, that empower us to extract meaningful information from diverse datasets.

Throughout this project, we'll not only build technical expertise but also apply these concepts to real-world scenarios. By the end, we aim to empower ourselves and our users with the skills and knowledge needed to harness the full potential of data processing and transformation in the ever-evolving world of data analytics and engineering.

## STEPS
Data cleaning is a crucial step in any data analysis or PySpark project, as it ensures that the data you work with is accurate, consistent, and ready for analysis. Here are the data cleaning steps for your PySpark project, specifically addressing the mentioned tasks:

1. Handling Null Values:

   - Identify Null Values: Begin by identifying columns or fields with missing or null values. You can use PySpark functions like `.isNull()` or `.isNotNull()` to flag these instances.

   - Imputation: Depending on the nature of the data and the analysis goals, you can choose to fill null values with appropriate substitutes. Common techniques include mean, median, mode imputation for numerical data and using the most frequent category for categorical data.

   - Dropping Rows or Columns: If null values cannot be imputed or represent a small portion of the dataset, you may opt to drop rows or columns with significant null values using `.dropna()`.

2. Data Type Conversion:

   - Inspect Data Types: Analyze the data types of each column to ensure they align with the intended analysis. Use `.dtypes` to list the data types of all columns.

   - Type Conversion: Use PySpark functions like `.cast()` to convert columns to the correct data types. For example, if a column should be treated as a date, use `.cast(DateType())` for the conversion.

3. Handling Multi-Values in a Single Cell:

   - Splitting Data: If you have data containing multiple values in a single cell (e.g., comma-separated values), use PySpark's `.split()` function to separate them into distinct columns.

   - Pivoting Data: In some cases, you might need to pivot the data from a long format (multiple rows for each value) to a wide format (each value in a separate column). PySpark's `.groupBy()` and `.pivot()` functions can be useful for this task.

   - Aggregation: After splitting or pivoting, you may need to aggregate data if the multi-values represent counts or sums. PySpark's `.agg()` function can be handy for these calculations.
## DATA TRANSFORMATION
Data transformation is a critical step in any PySpark project, as it shapes the data into a format suitable for analysis and reporting. Here are the data transformation steps for your PySpark project, focusing on the mentioned tasks:

1. Column Names:

   - Rename Columns: If necessary, rename columns to make them more descriptive or user-friendly. Use the `.withColumnRenamed()` function to rename specific columns.

2. Null Values:

   - Handling Null Values: Building on the data cleaning steps, further address null values if any remain after cleaning. Depending on the context, you can apply specific business logic or impute null values as needed.

3. Partitioning & Sorting:

   - Partitioning: If your dataset is large and distributed across multiple nodes, consider partitioning it based on a relevant column. Partitioning can improve query performance significantly. Use the `.repartition()` function to repartition your DataFrame.

   - Sorting: Sorting can be crucial for certain analyses or downstream processes. Use the `.orderBy()` function to sort the data based on one or more columns in ascending or descending order.

4. Date Format Transformation:

   - Date Parsing: If your dataset contains date columns in a different format than required, use PySpark's date functions, such as `to_date()`, to parse and transform date strings into the desired format.

5. Result Representation:

   - Selecting Columns: Choose the specific columns you need for your analysis or reporting. Use the `.select()` function to create a DataFrame with only the desired columns.

   - Aggregations and Summarization: If you need to summarize your data, apply aggregations using functions like `.groupBy()` and `.agg()` to calculate statistics, counts, sums, etc.

   - Collecting Data: If you want to collect and convert your DataFrame into a local data structure (e.g., Pandas DataFrame), use the `.collect()` function. Be cautious with this step if your dataset is large, as collecting data can consume a lot of memory.

   - Saving Results: Save the transformed and processed data as necessary. PySpark allows you to save DataFrames in various formats like Parquet, CSV, or JSON using `.write()` functions.


## TOOLS 

In a PySpark project, you can use a variety of tools and libraries to streamline your data processing, analysis, and reporting tasks. Here are some essential tools and libraries commonly used in PySpark projects:

1. Apache Spark: PySpark itself is a powerful tool, as it provides a Python API for Apache Spark, a distributed data processing framework. You'll primarily use PySpark for data manipulation, transformation, and analysis.

2. Jupyter Notebooks: Jupyter notebooks are an excellent choice for interactive data exploration, analysis, and visualization with PySpark. They allow you to combine code, visualizations, and documentation in a single environment.

3. PyCharm or VSCode: Integrated Development Environments (IDEs) like PyCharm or Visual Studio Code (with the Python extension) provide code editors with powerful debugging capabilities, which can be beneficial for PySpark development.

4. SQL Tools: PySpark includes SQL support, and you can use SQL queries for data manipulation. SQL clients like DBeaver or SQL Workbench/J can be helpful for developing and testing SQL queries.

5. Pandas: While PySpark is great for distributed data processing, Pandas is a popular Python library for data manipulation and analysis on a single machine. You can use Pandas to explore small portions of your data before scaling up with PySpark.

6. Git and Version Control: Using Git for version control is crucial for tracking changes, collaborating with team members, and maintaining a history of your project's codebase.

## INITIAL SCHEMA

root
 |-- ageofparticipant: long (nullable = true)
 |-- clinician: struct (nullable = true)
 |    |-- branch: string (nullable = true)
 |    |-- name: string (nullable = true)
 |    |-- role: string (nullable = true)
 |-- drug_used: string (nullable = true)
 |-- experimentenddate: string (nullable = true)
 |-- experimentstartdate: string (nullable = true)
 |-- noofhourspassedatfirstreaction: long (nullable = true)
 |-- result: struct (nullable = true)
 |    |-- conclusion: string (nullable = true)
 |    |-- sideeffectsonparticipant: string (nullable = true)

 ## FINAL SCHEMA
 root
 |-- age_of_participant: long (nullable = true)
 |-- clinic_branch: string (nullable = true)
 |-- head_clinician: string (nullable = true)
 |-- assistants_role: string (nullable = false)
 |-- drug_used: string (nullable = true)
 |-- experiment_end_date: string (nullable = true)
 |-- experiment_start_date: string (nullable = true)
 |-- no_of_hours_passed_at_first_reaction: long (nullable = true)
 |-- conclusion: string (nullable = false)
 |-- side_effects_on_participant: string (nullable = true)
 |-- starts_ts: timestamp (nullable = true)
 |-- end_ts: timestamp (nullable = true)