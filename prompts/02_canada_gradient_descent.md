# Arena AI Agent — Assignment 2 / Task 1

Implement **Assignment 2, Task 1 only**, independent of Assignment 1 even though the dataset is shared.

**Source PDF:** `assignments/assignment_02/source/assignment 2.pdf` (PAGE 1, Task 1)
**Dataset:** https://www.kaggle.com/datasets/gurdit559/canada-per-capita-income-single-variable-data-set/data
**Local data directory:** `data/canada/`
**Deliverable:** `assignments/assignment_02/notebooks/01_canada_gradient_descent.ipynb`

## Exact instructor objective

Predict Canada's income per capita for **2020**, implementing beginner-level **linear regression using gradient descent FROM SCRATCH**; the instructor explicitly disallows model-building libraries such as scikit-learn for this task.

## Implementation directions

- Inspect the actual CSV and make a simple time-series scatter plot, missing-values/data-types checks, and explanation of the input and target. Use real CSV columns only.
- Exclude 2020 and later rows from training if they exist; use a chronological holdout from pre-2020 rows for evaluation if feasible, then refit on all pre-2020 rows for the final prediction.
- Derive and display the beginner-friendly formulas in Markdown: `y_hat = w*x + b`, MSE/cost function, `dw` and `db` gradients, and gradient descent updates.
- **Implement gradient descent manually with beginner-readable Python and/or NumPy**. Do NOT import or use scikit-learn linear models, scaling, metrics, optimization methods, or `np.polyfit`/closed-form fitting as the model. Pandas/NumPy for data handling and matplotlib/seaborn for plots are allowed.
- For numerical stability, center/scale the year feature using statistics computed only from the fitting split; then apply the same learned transformation to validation and to year=2020. Explain why this matters. Don't include target leakage.
- Choose reasonable learning rate, maximum epochs, zero/seeded initialization and a basic stopping/monitoring approach. Plot training MSE loss over iterations. Report final learned weights, intercept, simple manually computed MAE/RMSE/R² when meaningful, and show the fitted line and 2020 predicted point.
- Demonstrate that loss decreases, check for `NaN`/divergence, and explain what loss/convergence means. If 2020 actually exists in the file, optionally show it after predicting, without training on it.
- This notebook should clearly show that **the student wrote gradient descent rather than calling a library fit method**.

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
