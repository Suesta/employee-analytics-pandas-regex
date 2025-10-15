# Employee Analytics with Pandas & Regex (UOC MSc Data Science · PEC1)

[![Made with: Python](https://img.shields.io/badge/Python-3.10%2B-blue)]() [![Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)]() [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)]()

**Author:** Víctor Suesta Arribas
**Notebook:** `Víctor_Suesta_Arribas_PEC1.ipynb`
**Course:** *Programming for Data Science* — UOC MSc in Data Science (PEC1)

---

## Overview

Single-notebook project that explores a small **employee** dataset using **pandas** and **regular expressions**. The work is intentionally clear and compact (PEP 8), focusing on lightweight feature engineering, grouped statistics, and a simple function with type hints — aligned with the first assessed activity of the course.

**Highlights**

* Loading via **relative paths** + quick sanity checks
* Descriptive stats and **department-level** aggregates
* New fields: **Age**, **Initials**, and **Job Category** (from `JobTitle`)
* Custom function with **type hints**: `rango_empleados(...)`
* **Regex**: Spanish phone validation and time extraction

---

## Repository Structure

```
.
├── Víctor_Suesta_Arribas_PEC1.ipynb   # solutions for Exercises 1–5
├── data/
│   └── employees.xlsx                  # input dataset
├── README.md
├── LICENSE
└── .gitignore
```

> If your OS struggles with accents, rename the notebook to `Victor_Suesta_Arribas_PEC1.ipynb`.

---

## What the notebook covers

* **Setup (Colab-friendly)**: mount Drive (if needed), set working dir, list contents.
* **Exercise 1**: Load DataFrame; stats (min/max/mean), counts by department; **Age** & **Initials**; top-5 salaries; IT **median** salary.
* **Exercise 2**: Mean salary by department; department with highest mean; employee counts; employees **above global mean**.
* **Exercise 3**: `rango_empleados(df, min_edad, max_edad) -> {"conteo": int, "salario_medio": float}` with basic edge-case handling.
* **Exercise 4**: Regex for Spanish phones (`+34`/`0034`, separators allowed) and **time** extraction (`HH:MM` or `HH:MM:SS`, valid ranges).
* **Exercise 5**: Map `JobTitle` → **Categoria_Trabajo** (`Engineering`, `Management`, `Education`, `Other`); count per category (dict comprehension) → **OrderedDict** (desc).

---

## How to run

### A) Google Colab

1. Open the notebook in Colab.
2. Run the first setup cell (mount Drive if you use it).
3. Ensure `data/employees.xlsx` exists relative to the notebook.
4. **Runtime → Run all**.

### B) Local (Jupyter)

* Python **3.10+** recommended.
* Install deps:

  ```bash
  pip install pandas numpy
  ```
* Launch:

  ```bash
  jupyter notebook "Víctor_Suesta_Arribas_PEC1.ipynb"
  ```
* Keep the `data/` structure so the relative path works.

---

## Implementation choices

* **PEP 8**: grouped imports, spacing, sensible line lengths, type hints.
* Defensive parsing: `pd.to_datetime(..., errors="coerce")` and safe string ops with `.fillna("")`.
* Age computed by year delta + birthday check — simple and adequate for this dataset.
* **Comprehensions** for concise filtering/counting; **OrderedDict** for sorted outputs.
* Regex patterns constrained to valid **Spanish** formats and valid **time** ranges.

---

## License

Released under the **MIT License**. See `LICENSE`.
