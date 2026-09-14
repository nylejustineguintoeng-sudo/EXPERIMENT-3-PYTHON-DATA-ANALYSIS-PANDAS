# Experiment 3: Python Data Analysis (PANDAS)

**Name:** Guinto, Nyle Justine C.  
**Section:** 2ECE-A  

---

## Short Description

A collection of data analysis and manipulation solutions in Python using **Pandas**, featuring positional and label-based DataFrame slicing (`.iloc`, column labels), specific model record lookup via custom Boolean conditions, and non-destructive multi-model subsetting with shape verification[cite: 1].

---

## Project Overview

This repository contains the completed Jupyter Notebook for **Experiment 3** of the course **ECE 2112: Advanced Computer Programming and Algorithms**[cite: 1].

The primary objective of this laboratory is to load a CSV dataset into a Pandas DataFrame, perform positional and label-based indexing, filter records using conditional statements, and extract specified subsets without mutating the underlying source dataset (`cars.csv`)[cite: 1].

---

## Problem Explanations

### Problem A: Positional and Label-Based Slicing

* **Objective:** Load the `cars.csv` dataset into a DataFrame named `cars`, inspect its dimensions and column names, and slice specific row/column subsets[cite: 1].
* **Implementation:** Uses `cars.shape` and `cars.columns` to inspect metadata[cite: 1]. Performs positional slicing with `.iloc[5:10]` to extract rows 6 through 10 into `cars_6_to_10`, then selects only `'Model'`, `'mpg'`, `'cyl'`, `'hp'`, and `'gear'` using label-based indexing[cite: 1].
* **Verification:** Displays dataset shape `(32, 12)`, column lists, intermediate positional row slices, and the final 5-column subset directly in executed notebook cells[cite: 1].

---

### Problem B: Model Lookup

* **Objective:** Retrieve specific vehicle records dynamically from the `Model` column using Boolean indexing without hard-coding row index numbers[cite: 1].
* **Implementation:** Applies the equality operator `cars['Model'] == 'Toyota Corolla'` to store the complete record in `toyota`[cite: 1]. Similarly, masks `'Pontiac Firebird'` to extract a subset containing only `'Model'`, `'mpg'`, `'hp'`, and `'wt'`, storing it in `pontiac`[cite: 1].
* **Verification:** Validates that both subsets return the precise matching records without using hard-coded integer indices[cite: 1].

---

### Problem C: Multi-Model Subsetting

* **Objective:** Extract records for three specific models (`Datsun 710`, `Lotus Europa`, and `Ferrari Dino`) while retaining only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`[cite: 1].
* **Implementation:** Uses `.isin(['Datsun 710', 'Lotus Europa', 'Ferrari Dino'])` on the `Model` column to filter rows by value and stores the result in a new DataFrame named `selected_cars`[cite: 1].
* **Verification:** Confirms that `selected_cars.shape` strictly evaluates to `(3, 5)` (exactly 3 rows and 5 columns) while preserving the original dataset row order[cite: 1].

---

## File Structure

```text
.
├── GUINTO_ECE2112_PA3.ipynb # Jupyter Notebook containing code solutions and outputs
├── cars.csv                 # Source dataset file
└── README.md                # Project documentation
