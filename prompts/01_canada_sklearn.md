# Arena AI Agent — Assignment 1 / Task 1

You are working in an undergraduate Machine Learning course repository. Implement **Assignment 1, Task 1 only**.

**Source PDF:** `assignments/assignment_01/source/assignment_1.pdf`
**Dataset:** https://www.kaggle.com/datasets/gurdit559/canada-per-capita-income-single-variable-data-set/data
**Local data directory:** `data/canada/`
**Deliverable:** `assignments/assignment_01/notebooks/01_canada_linear_regression.ipynb`

## Exact instructor objective

Predict Canada's per-capita income for the year **2020** using **beginner-level single-variable linear regression**, with `Year` as the input and `per capita income` as the target. This assignment does **not** ban scikit-learn; the ban in Assignment 2 Task 1 does not apply here.

## Implementation directions

- Identify the real filename and column names by inspecting the actual CSV; no hardcoded invented column names.
- Inspect missing years/values, duplicates, data types, outliers, and the year-to-income relationship; report what you found, not what you expected. Create a clean chronological scatter plot.
- To predict 2020 fairly, **do not include 2020 or later observations in model training even if present**. Explain which rows are used. If there is enough data, use a simple chronological holdout of earlier pre-2020 years for honest MAE/RMSE/R² evaluation, then refit a `sklearn.linear_model.LinearRegression` on all eligible years before predicting 2020. If a meaningful holdout is infeasible, say so explicitly. Never claim 2020 was unseen if it was used in training.
- Visualize the fitted straight line vs actual historic points, highlight predicted 2020 value, show regression coefficient and intercept in plain language. Optionally compare to a historical 2020 actual **only if actually present**, kept outside model fitting.
- Report the numerical **2020 prediction** with units/limitations; don't invent a value if not executed.
- Keep the notebook educational, uncluttered, and fully runnable locally.

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
