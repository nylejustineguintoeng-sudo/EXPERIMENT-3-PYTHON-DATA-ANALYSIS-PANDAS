# Experiment 3: Python Data Analysis (PANDAS)

**Name:** Guinto, Nyle Justine C.  
**Section:** 2ECE-A  

---

## Short Description

A Pandas lab assignment demonstrating DataFrame slicing using `.iloc`, row filtering with Boolean conditions, and subset extraction without altering the original dataset.

---

## Project Overview

This repository contains the completed Jupyter Notebook for **Experiment 3** of **ECE 2112: Advanced Computer Programming and Algorithms**. 

The main goal is to load `cars.csv` into Pandas, extract specific rows and columns using positional and label-based indexing, filter records by model names, and verify the resulting DataFrame shapes.

---

## Problem Explanations

### Problem A: Positional and Label-Based Slicing

* **Objective:** Inspect dataset dimensions, view column names, and slice rows 6 through 10.
* **Implementation:** Uses `cars.shape` and `cars.columns` for inspect design. Uses `.iloc[5:10]` to extract rows 6 to 10 into `cars_6_to_10`, then selects only `'Model'`, `'mpg'`, `'cyl'`, `'hp'`, and `'gear'` using column labels.
* **Verification:** Displays the total dataset shape `(32, 12)`, column names, and the sliced outputs using standard print statements.

---

### Problem B: Model Lookup

* **Objective:** Find specific car models dynamically using Boolean conditions instead of hard-coded row numbers.
* **Implementation:** Filters `cars['Model'] == 'Toyota Corolla'` for all columns, and `cars['Model'] == 'Pontiac Firebird'` for only `'Model'`, `'mpg'`, `'hp'`, and `'wt'`.
* **Verification:** Displays both filtered records, saving them into `toyota` and `pontiac`.

---

### Problem C: Multi-Model Subsetting

* **Objective:** Extract records for three target models (`Datsun 710`, `Lotus Europa`, `Ferrari Dino`) and keep only specified columns.
* **Implementation:** Uses `.isin()` on the `Model` column to pick the three rows and selects the `'Model'`, `'mpg'`, `'cyl'`, `'hp'`, and `'gear'` columns to create `selected_cars`.
* **Verification:** Displays the DataFrame and checks that `selected_cars.shape` equals `(3, 5)`.

---

## File Structure

```text
.
├── GUINTO_ECE2112_PA3.ipynb # Jupyter Notebook containing code solutions and outputs
├── cars.csv                 # Source dataset file
└── README.md                # Project documentation
