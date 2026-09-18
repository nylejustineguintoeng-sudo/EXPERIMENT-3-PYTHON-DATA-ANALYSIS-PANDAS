# 📌Experiment 3: Python Data Analysis (PANDAS)

**Name:** Guinto, Nyle Justine C.<br>
**Section:** 2ECE-A

---

## 📑 Table of Contents
- [Short Description](#-short-description)
- [Project Overview](#-project-overview)
- [DataFrame Operations Summary](#-dataframe-operations-summary)
- [Problem Specifications & Solutions](#-problem-specifications--solutions)
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

This section covers the core tasks of the experiment, demonstrating various Pandas data extraction techniques:

* **A. Positional and Label-Based Slicing:** Uses `.iloc[5:10]` to extract rows 6 through 10 (since Pandas uses zero-based indexing, this corresponds to indices 5 to 9) and filters for specific columns by name.
* **B. Model Lookup:** Uses Boolean indexing (`cars['Model'] == '...'`) to dynamically search for the **Toyota Corolla** (retaining the full row) and the **Pontiac Firebird** (filtering for specific columns).
* **C. Multi-Model Subsetting:** Uses the highly efficient `.isin()` method to filter for multiple vehicles simultaneously (**Datsun 710**, **Lotus Europa**, and **Ferrari Dino**) and chains column selection to meet the required 3x5 dimension check.

```python
import pandas as pd

# Load the dataset
cars = pd.read_csv('cars.csv')

# ---------------------------------------------------------
# A. Positional and Label-Based Slicing
# ---------------------------------------------------------
# Extracting rows 6 to 10 (indices 5 to 9) and keeping specific columns
cars_6_to_10 = cars.iloc[['Model', 'mpg', 'cyl', 'hp', 'gear']]

# ---------------------------------------------------------
# B. Model Lookup
# ---------------------------------------------------------
# Full row extraction using a Boolean mask
toyota = cars[cars['Model'] == 'Toyota Corolla']

# Row extraction combined with specific column selection
pontiac = cars[cars['Model'] == 'Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt']]

# ---------------------------------------------------------
# C. Multi-Model Subsetting
# ---------------------------------------------------------
# Defining the target models
target_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']

# Extracting rows that match the target models, and keeping specific columns
selected_cars = cars[cars['Model'].isin(target_models)][['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

---

## 📂 Project File Structure

```text
├── GUINTO_ECE2112_PA3.ipynb   # Main Jupyter Notebook containing all executed cells and logic
├── README.md                  # Project documentation (this file)
└── cars.csv                   # Source dataset containing vehicle variables
```

---

## 🛠️ Prerequisites & Requirements

To run the notebook successfully, ensure the following are installed:
* **Python 3.x**
* **Jupyter Notebook** or an IDE that supports `.ipynb` files (like VS Code)
* **Pandas Library** (Can be installed via `pip install pandas`)

---

## 🚀 How to Run

### Using Jupyter Notebook / VS Code
1. Clone the repository `https://github.com/nylejustineguintoeng-sudo/EXPERIMENT-3-PYTHON-DATA-ANALYSIS-PANDAS.git` to your local machine.
2. Ensure that `cars.csv` and `GUINTO_ECE2112_PA3.ipynb` are located in the same directory.
3. Open `GUINTO_ECE2112_PA3.ipynb` in your preferred Jupyter environment.
4. Select **Run All** (or execute each cell sequentially using `Shift + Enter`) to load the DataFrame and generate the requested subsets.
