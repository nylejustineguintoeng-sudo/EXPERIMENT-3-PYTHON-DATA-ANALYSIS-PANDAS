# Experiment 3: Python Data Analysis (PANDAS)

**Name:** Guinto, Nyle Justine C.<br>
**Section:** 2ECE-A

---

## 📑 Table of Contents
- [Short Description](#-short-description)
- [Project Overview](#-project-overview)
- [DataFrame Operations Summary](#-dataframe-operations-summary)
- [Problem Specifications & Solutions](#-problem-specifications--solutions)
  - [A. Positional and Label-Based Slicing](#a-positional-and-label-based-slicing)
  - [B. Model Lookup](#b-model-lookup)
  - [C. Multi-Model Subsetting](#c-multi-model-subsetting)
- [Project File Structure](#-project-file-structure)
- [Prerequisites & Requirements](#-prerequisites--requirements)
- [How to Run](#-how-to-run)

---

## 🔗 Short Description
A Pandas lab assignment demonstrating DataFrame slicing using `.iloc`, row filtering with Boolean conditions, and subset extraction without altering the original dataset.

---

## 🔎 Project Overview
This project contains Python solutions for introductory data analysis using the `pandas` library. The tasks demonstrate fundamental data manipulation concepts including:

* Loading a CSV dataset into a Pandas DataFrame.
* Selecting rows and columns using positional and label-based indexing.
* Filtering records using conditions on a DataFrame column.
* Extracting a well-defined subset of data without changing the source data.

---

## ⚙️ DataFrame Operations Summary

| Task | Target Output Variable | Key Pandas Operations | Key Logic |
| :--- | :--- | :--- | :--- |
| **A. Positional & Label-Based Slicing** | `cars_6_to_10` | `.iloc[]`, `[]` (Column labels) | Retrieves rows 6 through 10 using integer location (`.iloc`), then filters specific columns by their exact labels. |
| **B. Model Lookup** | `toyota`, `pontiac` | Boolean Indexing (`==`) | Filters the `Model` column to locate exact matches for specific vehicles without using hard-coded row numbers. |
| **C. Multi-Model Subsetting** | `selected_cars` | `.isin()` | Extracts records for three specific car models and drops unneeded variables to meet the required 3x5 dimension check. |

---

## 📝 Problem Specifications & Solutions

### A. Positional and Label-Based Slicing
This section demonstrates how to inspect a dataset and extract a specific chunk of data using index positions and column names.

* **Inspection:** We first use `cars.shape` to get the dimensions (rows, columns) and `cars.columns` to view all available variables.
* **Row Slicing (`.iloc`):** To get rows 6 through 10, we use `.iloc[5:10]`. Since Pandas uses zero-based indexing, index `5` corresponds to the 6th row, and the slice goes up to (but does not include) index `10`.
* **Column Slicing:** We then filter the resulting DataFrame by passing a list of the specific column strings requested.

```python
# Extracting rows 6 to 10 (indices 5 to 9)
cars_6_to_10 = cars.iloc[5:10]

# Keeping only the required columns
cars_6_to_10 = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
