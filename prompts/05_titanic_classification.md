# Arena AI Agent — Assignment 3 / Task 2

Implement **Assignment 3, Task 2 only**.

**Source PDF:** `assignments/assignment_03/source/assignment 3.pdf` (PAGE 2, Task 2)
**Competition / dataset:** https://www.kaggle.com/competitions/titanic/data?select=train.csv
**Local data directory:** `data/titanic/`
**Deliverable:** `assignments/assignment_03/notebooks/02_titanic_survival_classification.ipynb`
**Prediction output after a genuine run:** `outputs/assignment_03/titanic_submission.csv`

## Exact instructor objective

For each passenger in Titanic's external `test.csv`, predict whether they **survived (1)** or **did not survive (0)** using passenger attributes such as age, gender, and socio-economic class. The task is **binary classification**, not regression.

## Implementation directions

- Respect Kaggle's competition access and rules. The user may need to authenticate and accept rules before files can download. Never add a replacement Titanic dataset or fabricate test labels. Inspect `train.csv`, `test.csv` and `gender_submission.csv` when available.
- EDA on training data: show sample rows, dimensions, missingness, target distribution, survival by sex and passenger class, and a suitable age/fare analysis. Use clear charts with short interpretations.
- Start with a manageable feature set drawn from real columns: `Pclass`, `Sex`, `Age`, `Fare`, `SibSp`, `Parch`, `Embarked` where present. Avoid complex text extraction, high-cardinality ticket/name memorization, and ID leakage.
- Use a single reproducible `train_test_split(..., stratify=y, random_state=42)` on labeled `train.csv` for validation. Build a scikit-learn pipeline with `SimpleImputer` for missing values, one-hot encoding for categorical values, and (if appropriate) standardization for numeric columns. A beginner-friendly `LogisticRegression` is the default model; a simple decision tree or random forest is optional only if clearly justified by the PDF and kept small.
- Evaluate only on labeled validation data: accuracy, precision, recall, F1, confusion matrix, classification report. Explain 0 vs 1 and major errors. Don't compute accuracy on unlabeled external `test.csv`.
- Refit the chosen simple final pipeline on all labeled training rows, predict exactly 0/1 for external `test.csv`. Save CSV with exactly two columns named **`PassengerId` and `Survived`**, same number of rows and IDs as `test.csv`; validate no missing values, no duplicate IDs and binary outputs. Never claim Kaggle leaderboard score or competition submission unless a real submission was made and confirmed.
- Show a short preview of the output CSV, explain where it is saved and how to use it for Kaggle submission.

## Non-negotiable standards for this task

1. **Read the exact source PDF** at the specified path before coding. The PDF requirements override assumptions and common internet tutorials. Verify the original Kaggle URL and inspect the real downloaded data.
2. Work only on this task in a dedicated `arena/<descriptive-task>` branch and open a pull request when complete; **do not merge your own PR**. Do not alter the other task notebooks or the original PDFs.
3. Produce ONE self-contained `.ipynb` at the exact requested path. No Streamlit app, no deployment, no overengineered packages, no excessive abstractions. Beginner-readable Python using pandas, numpy, matplotlib/seaborn and scikit-learn ONLY where permitted.
4. Begin with a polished title and concise Markdown introduction (dataset, objective, approach). **Every code cell must have a meaningful Markdown cell immediately preceding it** explaining what the cell will do, including why, not merely a generic heading. Use orderly sections: Dataset Loading -> Inspection -> EDA -> Cleaning/Preprocessing -> Training -> Evaluation -> Results/Conclusion (adapt as appropriate).
5. Start with actual inspection: `head`, `shape`, `dtypes`, columns, missing values, duplicates, descriptive statistics, target checks and sensible plots. Only clean problems that really exist. Explain each decision. Show helpful visualizations with readable titles, axis labels, legends and short interpretations. Do not add irrelevant plots.
6. Avoid leakage: split appropriately, fit imputers/encoders/scalers on training partitions only, never train with target/IDs accidentally. Fix `random_state=42` for any randomized operations. Handle date/year data appropriately.
7. Use robust data paths relative to the repository root (independent of notebook launch directory). Look under `data/` as documented. If data is unavailable due to Kaggle authentication/rules, **do not generate synthetic replacement data**, fake metrics, or mark the notebook tested. Instead provide exact manual download instructions and leave honest status.
8. The notebook must run from top to bottom with a fresh Jupyter kernel on a Windows CPU (using `requirements.txt`) once the dataset is in place. Use modern supported library APIs; avoid deprecated functions. No GPU or external cloud service should be required.
9. Include relevant regression/classification metrics; plots should be derived from real outputs. Finish with a concise Markdown section explaining results, limits, and the assignment question's answer; if blocked, explain blocker instead of inventing an answer.
10. Before reporting completion: inspect the notebook JSON, verify every code cell has preceding Markdown, execute it against **real available files** (if accessible), confirm meaningful outputs/no errors, report actual execution evidence or exact blocker. Update README/requirements only if needed. In the PR summary, list changed files, checks performed, dataset provenance, actual performance (if executed), and anything the owner must do locally.

**Important:** Keep code simple enough for the student to explain every line in a discussion with the instructor. Professional presentation is about clarity, correctness, and interpretability, not complexity. Do not overfit the rubric with extras.
