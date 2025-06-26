# Supplier-information-system-project
Python and Jupyter Notebook solutions for the supplier information system case study and analysis

## Table of Contents
1. [Overview](#overview)
2. [Project Features](#project-features)
3. [Data Summary](#data-summary)
4. [Preprocessing Steps](#preprocessing-steps)
5. [Core Code & Analysis](#core-code--analysis)
6. [Key Insights](#key-insights)
7. [How to Run the Project](#how-to-run-the-project)
8. [Results](#results)
9. [Future Improvements](#future-improvements)
10. [Acknowledgments](#acknowledgments)

---

## Overview
This project implements a Python-based supplier information system as a case study in information systems design and business data processing. The notebook demonstrates practical Python skills for business applications, focusing on data wrangling, validation, functional programming, and object-oriented design using real-world supplier records.

---

## Project Features
- **Comprehensive Data Processing:** Manipulates and cleans supplier data stored in JSON format.
- **Dictionary and List Operations:** Access, update, and filter supplier records using Python’s core data structures.
- **Functional Programming:** Leverages `map`, `filter`, and lambda functions for efficient data handling.
- **Data Validation & Cleaning:** Adds, updates, and deletes suppliers as per system requirements.
- **Date and Regex Handling:** Formats dates and extracts area codes from phone numbers using Python's `datetime` and `re` modules.
- **Object-Oriented Programming:** Defines and demonstrates a custom `Supplier` class for extensible supplier management.
- **Reusable Functions:** Implements user-defined functions for descriptive statistics and reporting.

---

## Data Summary
- **Dataset:** `suppliers.json` (sample supplier database)
- **Key Features:**
  - `supplier_id`, `supplier_name`, `contact_firstname`, `contact_lastname`, `city`, `state`, `country`, `phone`, `email`, `notes`
- **Project Notebook:** `Supplier information system project.ipynb`

---

## Preprocessing Steps
1. Loaded supplier data from a JSON file.
2. Displayed and checked all supplier fields and values.
3. Performed updates to supplier records as described in the case study.
4. Added and removed supplier records according to business requirements.
5. Filtered data for business reporting (e.g., VIC/NSW suppliers).

---

## Core Code & Analysis
- **A1:** Extracted and validated dictionary keys/values, checked for specific attributes, and cleared dictionaries for demo purposes.
- **A2:** Updated supplier records, appended new entries, and removed others using list operations.
- **A3:** Defined and used summary statistics functions for Python lists.
- **A4:** Generated lists and joined strings for reporting supplier names.
- **A5:** Created product information as sample dictionaries.
- **A6:** Filtered suppliers by state (VIC/NSW) using Python’s `filter`.
- **A7:** Applied functional programming with `map` and `lambda` for concise display of supplier information.
- **A8:** Handled Australian-style dates using the `datetime` module.
- **A9:** Used regular expressions to extract area codes from supplier phone numbers.
- **A10:** Defined and demonstrated a `Supplier` class with custom setter/getter methods for contact management.

---

## Key Insights
- Python's core data structures enable robust, flexible business data processing.
- Functional and object-oriented paradigms provide scalable, readable, and reusable code.
- Regex and date formatting are essential for real-world business data quality.
- Filtering and mapping allow for targeted business reports and compliance checks.

---

## How to Run the Project

1. Clone or download this repository to your local computer.
2. Ensure you have Python 3.x installed ([Download Python](https://www.python.org/downloads/)).
3. Place both `Supplier information system project.ipynb` and `suppliers.json` in the same folder.
4. Open the notebook with [Jupyter Notebook](https://jupyter.org/) or VS Code (with the Jupyter extension).
5. Run all code cells in sequence to reproduce the analysis and data processing.

**Dependencies:**
- All standard libraries: `json`, `re`, `datetime`
- Jupyter Notebook for interactive code execution  
To install Jupyter, run:
```bash
pip install notebook
```bash
jupyter notebook
```

## Results
- All required tasks from the supplier information system case study have been successfully implemented.
- Supplier data can be reliably loaded, manipulated, filtered, and reported.
- The project code is ready for further extension and business use.

---

## Future Improvements
- Add data visualization (e.g., supplier counts by state) with matplotlib or seaborn.
- Integrate error handling and logging for more robust data processing.
- Develop a basic web or GUI interface for supplier management.
- Expand the OOP model to encompass a broader range of suppliers and business operations.

---

## Acknowledgments
- Case Study & Data: Provided by RMIT University, Information Systems Solutions and Design.
- Libraries Used: re, datetime (Python Standard Library).

---

## Author

Nik Phan | RMIT University  
Final year student, Bachelor of Business Information Systems (Expected November 2025)

---
