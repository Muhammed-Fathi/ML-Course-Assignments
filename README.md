# Machine Learning Coursework — Three Assignments, Five Tasks

A clean, beginner-friendly, reproducible Jupyter Notebook repository for three university Machine Learning assignment PDFs. **The PDFs in `assignments/*/source/` are the authoritative requirements.**

## Deliverables

| Assignment | Task | Notebook to produce | Learning objective |
|---|---|---|---|
| 1 | 1 | `assignments/assignment_01/notebooks/01_canada_linear_regression.ipynb` | Predict Canada's 2020 per-capita income with simple linear regression |
| 2 | 1 | `assignments/assignment_02/notebooks/01_canada_gradient_descent.ipynb` | Predict 2020 income using gradient descent implemented from scratch; no scikit-learn modeling |
| 2 | 2 | `assignments/assignment_02/notebooks/02_customer_loyalty_regression.ipynb` | Predict loyalty score using multiple linear regression |
| 3 | 1 | `assignments/assignment_03/notebooks/01_ice_cream_regression_comparison.ipynb` | Compare linear vs. polynomial-features regression |
| 3 | 2 | `assignments/assignment_03/notebooks/02_titanic_survival_classification.ipynb` | Predict survival (0/1) and export competition-format CSV |

The five Arena task prompts live in `prompts/`, one prompt per task. Execute and review them independently.

## Expectations for every notebook

1. Begin with a clear title, assignment/task objective, dataset source, and notebook roadmap.
2. Use a short **Markdown cell before each code cell** to describe what it does and why.
3. Inspect the actual downloaded dataset before assuming its filename, columns, size, or quality.
4. Include appropriate dataset checks, EDA, actionable visualizations, preprocessing, modeling, evaluation, plots, and a brief interpretation.
5. Make train/validation/test handling correct and prevent data leakage.
6. Keep code readable for an undergraduate student; no needless frameworks, apps, dashboards, or advanced architecture.
7. Make notebooks executable locally on Windows, CPU, with relative paths and deterministic splits.
8. **Never fabricate downloaded data, test results, metrics, executed notebook outputs, or Kaggle submissions.** Report any unavailable source honestly.
9. Respect assignment restrictions: Assignment 2, Task 1 requires writing gradient descent from scratch.

## Start locally (Windows PowerShell)

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m jupyter lab
```

If PowerShell activation is blocked, run the following commands from the repository directory instead:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m jupyter lab
```

Data acquisition and exact destination folders are documented in `data/README.md`.

## Original dataset links

- Canada Per Capita Income: https://www.kaggle.com/datasets/gurdit559/canada-per-capita-income-single-variable-data-set/data
- Customer Purchasing Behaviors: https://www.kaggle.com/datasets/hanaksoy/customer-purchasing-behaviors/data
- Ice Cream Selling / Polynomial Regression: https://www.kaggle.com/datasets/mirajdeepbhandari/polynomial-regression/data
- Titanic: https://www.kaggle.com/competitions/titanic/data?select=train.csv


## Project rules

- Do not commit credentials or Kaggle API tokens.
- Raw datasets are stored under `data/` locally and excluded from Git; no silent redistributions.
- The assignment PDFs are tracked and should not be modified.
- Each task should be implemented on its own branch/PR, reviewed before merge.
- Save the Titanic prediction file under `outputs/assignment_03/titanic_submission.csv` after real execution.

## Current status

- **Completed and merged:** Assignment 1 / Task 1 (PR #1), Assignment 2 / Task 1 (PR #2), and Assignment 2 / Task 2 (PR #3).
- **Completed and submitted for review:** Assignment 3 / Task 1 (`assignments/assignment_03/notebooks/01_ice_cream_regression_comparison.ipynb`). Executed on the 49-row Ice Cream Selling dataset comparing Simple Linear Regression against degree-2 Polynomial Regression; this PR is awaiting review.
- **Completed and submitted for review:** Assignment 3 / Task 2 (`assignments/assignment_03/notebooks/02_titanic_survival_classification.ipynb`). Executed on the Titanic competition data (891 train / 418 test); Logistic Regression pipeline (7 features, median/mode imputation + OneHot + StandardScaler, stratified 80/20 split, random_state=42) achieved 80.45% accuracy, 79.31% precision, 66.67% recall, 72.44% F1 on held-out validation (n=179); generated validated `outputs/assignment_03/titanic_submission.csv` (418 rows, PassengerId + Survived); notebook runs end-to-end on Windows CPU with repository dependencies.
