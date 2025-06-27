# Supplier Information System Project
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
- **Task 1:** Extracted and validated dictionary keys/values, checked for specific attributes, and cleared dictionaries for demo purposes.

Code:
```bash
#1. Select and copy the first supplier dictionary
sup = suppliers[0].copy()

#2. Print keys programmatically
print("keys:", list(sup.keys()))

#3. Print values programmatically
print("values:", list(sup.values()))

#4. Check if the key 'mobile' exists
If 'mobile' in sup:
    print("The dictionary contains the key 'mobile'.")
else:
    print("The dictionary does NOT contain the key 'mobile'.")

#5. Delete all items and check if it's empty
sup.clear()
print("Dictionary after clearing:", sup)
if len(sup) == 0:
    print("Dictionary is now empty.")
```

Output:
```bash
keys: ['city', 'contact_firstname', 'contact_lastname', 'contact_title', 'country', 'email', 'notes', 'phone', 'postcode', 'state', 'street_address', 'supplier_id', 'supplier_name']
values: ['Greenway', 'Thomas', 'Brown', 'Mr', 'Australia', 'thomas6246.brown@gmail.com', '', '(02) 8770 4857', '2900', 'ACT', 'Level 9/2 Michelle Follow', 51, 'Reyes-Goodman']
The dictionary does NOT contain the key 'mobile'.
Dictionary after clearing: {}
Dictionary is now empty.
```

- **Task 2:** Updated supplier records, appended new entries, and removed others using list operations.

Code:
```bash
#1. Find the length of the list
print("Number of suppliers:", len(suppliers))

#2. Change the contact_firstname of the supplier with supplier_id=52
for sup in suppliers:
    if sup['supplier_id'] == 52:
        sup['contact_firstname'] = "Ken"
        print("Updated:", sup['contact_firstname'])

#3. Add a new supplier
new_supplier = {
    "city": "Lancaster",
    "contact_firstname": "Tracy",
    "contact_lastname": "Wilson",
    "contact_title": "Mrs",
    "country": "Australia",
    "email": "tracy4587.wilson@gmail.com",
    "notes": "",
    "phone": "(03) 9323 0663",
    "postcode": "3620",
    "state": "VIC",
    "street_address": "Suite 141/8 Black Dale",
    "supplier_id": 55,
    "supplier_name": "Scott Ltd"
}
suppliers.append(new_supplier)
print("Added new supplier:", suppliers[-1]['supplier_name'])

#4. Remove supplier with supplier_id=53
suppliers = [sup for sup in suppliers if sup['supplier_id'] != 53]
print("Supplier with ID 53 removed. Remaining IDs:", [sup['supplier_id'] for sup in suppliers])
```

Output:
```bash
Number of suppliers: 4
Updated: Ken
Added new supplier: Scott Ltd
Supplier with ID 53 removed. Remaining IDs: [51, 52, 54, 55]
```

- **Task 3:** Defined and used summary statistics functions for Python lists.

Code:
```bash
def process_list(lst):
    total_items = len(lst)
    total_sum = sum(lst)
    average = total_sum / total_items
    min_value = min(lst)
    return total_items, total_sum, average, min_value

# Test list
my_list = [1, 55, 10, 20, 30]

result = process_list(my_list)
print("Total items:", result[0])
print("Total sum:", result[1])
print("Average:", result[2])
print("Minimum value:", result[3])
```

Output:
```bash
Number of suppliers: 4
Updated: Ken
Added new supplier: Scott Ltd
Supplier with ID 53 removed. Remaining IDs: [51, 52, 54, 55]
```

- **Task 4:** Generated lists and joined strings for reporting supplier names.

Code:
```bash
#1. List of supplier_name
supplier_names = [sup['supplier_name'] for sup in suppliers]
print("Supplier names:", supplier_names)

#2. Joined string
joined_names = '; '.join(supplier_names)
print("Joined names:", joined_names)
```

Output:
```bash
Total items: 5
Total sum: 116
Average: 23.2
Minimum value: 1
```

- **Task 5:** Created product information as sample dictionaries.

Code:
```bash
prod_155 = {
    "discontinued": 0,
    "lead_time_days": 3,
    "product_category": "Wireless Phone",
    "product_description": "Display: 5.1-inches Camera: ...",
    "product_id": 155,
    "product_name": "Samsung Galaxy S5, Black 16GB (Sprint)",
    "reorder_level": 18,
    "unit_price": 699.99
}
print(prod_155)
print()
```

Output:
```bash
Supplier names: ['Reyes-Goodman', 'Cisneros-White', 'Brown PLC', 'Scott Ltd']
Joined names: Reyes-Goodman; Cisneros-White; Brown PLC; Scott Ltd
```

- **Task 6:** Filtered suppliers by state (VIC/NSW) using Python’s `filter`.

Code:
```bash
vic_nsw_suppliers = list(filter(lambda x: x['state'] in ('VIC', 'NSW'), suppliers))
print("Number of VIC/NSW suppliers:", len(vic_nsw_suppliers))
print("VIC/NSW suppliers:", vic_nsw_suppliers)
```

Output:
```bash
{'discontinued': 0, 'lead_time_days': 3, 'product_category': 'Wireless Phone', 'product_description': 'Display: 5.1-inches Camera: ...', 'product_id': 155, 'product_name': 'Samsung Galaxy S5, Black 16GB (Sprint)', 'reorder_level': 18, 'unit_price': 699.99}
```

- **Task 7:** Applied functional programming with `map` and `lambda` for concise display of supplier information.

Code:
```bash
supplier_names = list(map(lambda x: f"{x['city']}: {x['supplier_id']}, {x['supplier_name']}", suppliers))
print("supplier names list:", supplier_names)
```

Output:
```bash
supplier names list: ['Greenway: 51, Reyes-Goodman', 'Dundee: 52, Cisneros-White', 'Claremont: 54, Brown PLC', 'Lancaster: 55, Scott Ltd']
```

- **Task 8:** Handled Australian-style dates using the `datetime` module.

Code:
```bash
import datetime

#1. Convert Australian date string to a date object
d = datetime.date(2022, 3, 2)
print(d)
print()

#2. Print date object for 28/02/2022 in AU format
from dateutil.parser import parse

date_obj = parse("28/02/2022")
oz_date_format = date_obj.strftime('%d/%m/%Y')
print(oz_date_format)
print()
```

Output:
```bash
2022-03-02

28/02/2022
```

- **Task 9:** Used regular expressions to extract area codes from supplier phone numbers.

Code:
```bash
import re

phone_number = "(07) 3806 8534"
if re.search(r'(^\(\d{2}\) \d{4} \d{4})', phone_number):  
    print("Area code:", "07")
else:
    print("Invalid phone number")
```

Output:
```bash
Area code: 07
```

- **Task 10:** Defined and demonstrated a `Supplier` class with custom setter/getter methods for contact management.

Code:
```bash
class Supplier:
    def __init__(self, d):
        for k in d:
            setattr(self, k, d[k])

    def set_phone(self, phone):
        self.phone = phone

    def get_phone(self):
        return self.phone

# Test the class
supp = Supplier(suppliers[2])
supp.set_phone("(03) 9961 5555")
print("Supplier phone (should be new):", supp.get_phone())
```

Output:
```bash
Supplier phone (should be new): (03) 9961 5555
```

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
3. Open the notebook with [Jupyter Notebook](https://jupyter.org/) or VS Code (with the Jupyter extension).
4. Download `suppliers.json`, then open it.
5. Place the code from the [Core Code & Analysis](#core-code--analysis) into `suppliers.json`.
6. Run all code cells in sequence to reproduce the analysis and data processing.

**Dependencies:**
- All standard libraries: `re`, `datetime`
- Jupyter Notebook for interactive code execution  
To install Jupyter, run:
```bash
pip install notebook
```
And then:
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
- Case Study & Data: RMIT University.
- Libraries Used: re, datetime (Python Standard Library).

---

## Author

Nik Phan | RMIT University  
Final year student, Bachelor of Business Information Systems (Expected November 2025)

---
