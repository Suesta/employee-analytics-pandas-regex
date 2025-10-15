# Employee Analytics with Pandas & Regex — UOC MSc Data Science (PEC1)

**Author:** Víctor Suesta Arribas
**Notebook:** `Víctor_Suesta_Arribas_PEC1.ipynb` (if your OS has issues with accents, use `Victor_Suesta_Arribas_PEC1.ipynb`)
**Course:** *Programming for Data Science* – UOC MSc in Data Science

## Overview

This repo contains a single Jupyter/Colab notebook delivering **PEC1**, the first assessed activity of the course.
The notebook performs a compact end-to-end analysis on a small employee dataset using **pandas** and **regular expressions**, covering:

* Data loading with **relative paths** and basic sanity checks
* Descriptive stats and **grouped aggregates** (by department)
* Feature engineering (**Age**, **Initials**, and a **Job Category** from job titles)
* Custom utility function with **type hints**
* **Regex** validation (Spanish phone numbers) and **time pattern extraction**

The work is intentionally simple and readable, following **PEP 8** and a clear, personal commenting style suitable for an early-stage MSc project.

---

## Files

```
.
├── Víctor_Suesta_Arribas_PEC1.ipynb   # main notebook (solutions for Exercises 1–5)
└── data/
    └── employees.xlsx                 # input dataset
```

> If cloning on a system that struggles with accents, rename the notebook to `Victor_Suesta_Arribas_PEC1.ipynb`.

---

## Dataset

* **Path:** `data/employees.xlsx`
* **Fields:** `EmployeeID, FirstName, LastName, JobTitle, Department, DateOfBirth, Salary`
* The notebook assumes the dataset is present at the relative path above.

---

## What’s inside the notebook

* **Setup (Colab-friendly):** mounts Drive (if used), sets working directory, lists contents for a quick pre-flight check.
* **Exercise 1:**

  * Load the dataset → `DataFrame`
  * Basic stats (count, min, max, mean), department counts
  * New columns: `Age` (from `DateOfBirth`) and `Initials` (e.g., “J.S.”)
  * Top-5 salaries and IT salary median
* **Exercise 2:**

  * **Mean salary by department** and department with the highest mean
  * **Employee count by department** (descending)
  * Employees with salaries **above the overall mean**
* **Exercise 3:**

  * `rango_empleados(df, min_edad, max_edad) -> {"conteo": int, "salario_medio": float}`
  * Age-range filter + average salary with simple edge-case handling
* **Exercise 4:**

  * **Regex**: validate Spanish phone numbers (`+34` / `0034`, separators allowed)
  * **Regex**: extract times in formats `HH:MM` and `HH:MM:SS` with proper ranges
* **Exercise 5:**

  * Map `JobTitle` → `Categoria_Trabajo` (`Engineering`, `Management`, `Education`, `Other`)
  * Count per category (dict comprehension) → **OrderedDict** (desc) and display

---

## How to run

### Option A — Google Colab (recommended)

1. Open the notebook in Colab.
2. Run the first setup cell to mount Drive (if applicable) and set the working directory.
3. Ensure `data/employees.xlsx` exists relative to the notebook path.
4. **Runtime → Run all**.

### Option B — Local (Jupyter)

1. Python **3.10+** recommended.
2. Install dependencies:

   ```bash
   pip install pandas numpy
   ```
3. Launch Jupyter and run the notebook:

   ```bash
   jupyter notebook Víctor_Suesta_Arribas_PEC1.ipynb
   ```
4. Keep the folder structure so `data/employees.xlsx` is found via a **relative path**.

---

## Key techniques & choices

* **PEP 8** style (imports grouped, spacing, line length, type hints).
* **Defensive reading** of dates (`errors="coerce"`) and safe string ops with `fillna("")`.
* Age computed via year difference with birthday check; clear and sufficient for this context.
* **Comprehensions** for concise filtering and counting.
* **Regex** patterns constrained to valid Spanish formats and valid time ranges.

---

## Reproducibility & environment

* **Python:** 3.10+
* **Dependencies:** `pandas`, `numpy` (implicit via pandas), `re` (stdlib)
* **Runtime:** Works in Google Colab and standard Jupyter.

---

## License

MIT License. See `LICENSE`.

