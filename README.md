# Experiment 3: Python Data Analysis (PANDAS)

**Name:** Guinto, Nyle Justine C.
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

* Loading a CSV dataset into a Pandas DataFrame[span_0](start_span)[span_0](end_span).
* Selecting rows and columns using positional and label-based indexing[span_1](start_span)[span_1](end_span).
* Filtering records using conditions on a DataFrame column[span_2](start_span)[span_2](end_span).
* Extracting a well-defined subset of data without changing the source data[span_3](start_span)[span_3](end_span).

---

## ⚙️ DataFrame Operations Summary

| Task | Target Output Variable | Key Pandas Operations | Key Logic |
| :--- | :--- | :--- | :--- |
| **A. Positional & Label-Based Slicing** | `cars_6_to_10` | `.iloc[]`, `[]` (Column labels) | Retrieves rows 6 through 10 using integer location (`.iloc`), then filters specific columns by their exact labels[span_4](start_span)[span_4](end_span). |
| **B. Model Lookup** | `toyota`, `pontiac` | Boolean Indexing (`==`) | Filters the `Model` column to locate exact matches for specific vehicles without using hard-coded row numbers[span_5](start_span)[span_5](end_span). |
| **C. Multi-Model Subsetting** | `selected_cars` | `.isin()` or `|` (OR operator) | Extracts records for three specific car models and drops unneeded variables to meet the required 3x5 dimension check[span_6](start_span)[span_6](end_span). |

---

## 📝 Problem Specifications & Solutions

### A. Positional and Label-Based Slicing
After loading the dataset, this section performs the following operations:
* Displays the shape and complete list of column names of the `cars` dataset[span_7](start_span)[span_7](end_span).
* Uses positional slicing (`.iloc`) to create `cars_6_to_10` containing rows 6 through 10[span_8](start_span)[span_8](end_span).
* From `cars_6_to_10`, extracts and displays only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, in that strict order using column labels[span_9](start_span)[span_9](end_span).

### B. Model Lookup
This section uses Boolean indexing on the `Model` column to locate records dynamically:
* Extracts the complete row for the **Toyota Corolla** and stores it in `toyota`[span_10](start_span)[span_10](end_span).
* For the **Pontiac Firebird**, it extracts only the `Model`, `mpg`, `hp`, and `wt` variables, storing the result in `pontiac`[span_11](start_span)[span_11](end_span).

### C. Multi-Model Subsetting
This task filters the dataset for multiple specific vehicles:
* Creates a DataFrame named `selected_cars` containing only the records for the **Datsun 710**, **Lotus Europa**, and **Ferrari Dino**[span_12](start_span)[span_12](end_span).
* Retains only the `Model`, `mpg`, `cyl`, `hp`, and `gear` variables[span_13](start_span)[span_13](end_span). 
* Performs a final shape check to ensure the resulting DataFrame contains exactly three rows and five columns[span_14](start_span)[span_14](end_span).

---

## 📂 Project File Structure

```text
├── GUINTO_ECE2112_PA3.ipynb   # Main Jupyter Notebook containing all executed cells and logic
├── README.md                  # Project documentation (this file)
└── cars.csv                   # Source dataset containing vehicle variables

