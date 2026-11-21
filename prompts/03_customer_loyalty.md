# Arena AI Agent — Assignment 2 / Task 2

Implement **Assignment 2, Task 2 only**.

**Source PDF:** `assignments/assignment_02/source/assignment 2.pdf` (PAGE 2, Task 2)
**Dataset:** https://www.kaggle.com/datasets/hanaksoy/customer-purchasing-behaviors/data
**Local data directory:** `data/customer/`
**Deliverable:** `assignments/assignment_02/notebooks/02_customer_loyalty_regression.ipynb`

## Exact instructor objective

Predict **loyalty score** with a **linear regression model** from: **age, annual income, purchase amount, purchase frequency, and region**. The PDF describes a score possibly grouped into categories but still expressly requires linear regression: follow that request rather than silently converting it to classification.

## Implementation directions

- Inspect the real dataset schema, target distribution, unique values, missing/duplicate data, invalid ranges, region values and potential outliers. The PDF's mentioned column labels are conceptual; use actual CSV names/case based on inspection.
- Do NOT use user/customer ID as a predictive feature. Target is not an input feature. Check whether loyalty score is continuous, integer, ordinal-coded, or category labels; explain any interpretability limitations of using regression if target is discrete. Do not silently fabricate targets or scores.
- EDA visuals should include a sensible target distribution, numeric feature correlations (where meaningful), at least one key relationship to target and regional breakdown. Label visuals and explain findings.
- Use reproducible train/test split (e.g. 80/20), use `ColumnTransformer` plus `OneHotEncoder(handle_unknown='ignore')` for region and simple numeric imputation/scaling where appropriate, all within a fitted scikit-learn `Pipeline` to avoid leakage. Fit `LinearRegression`.
- Report MAE, RMSE, R² on held-out real data; show an actual-vs-predicted scatter plot and a residual plot. Explain what high/low scores mean, and discuss why predictions can fall outside an ordinal scale if the score is discrete. Do not round/clamp predictions without justification.
- Include a small, clearly labeled example prediction from an **actual held-out row**, not a fabricated customer, and interpret it cautiously.

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
