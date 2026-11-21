# Arena AI Agent — Assignment 3 / Task 1

Implement **Assignment 3, Task 1 only**.

**Source PDF:** `assignments/assignment_03/source/assignment 3.pdf` (PAGE 1, Task 1)
**Dataset:** https://www.kaggle.com/datasets/mirajdeepbhandari/polynomial-regression/data
**Local data directory:** `data/ice_cream/`
**Deliverable:** `assignments/assignment_03/notebooks/01_ice_cream_regression_comparison.ipynb`

## Exact instructor objective

Predict number of **ice cream units sold** from **temperature**, using linear regression once **without polynomial features** and once **with polynomial features**, then explain and visualize the difference.

## Implementation directions

- Inspect actual dataset CSV name/columns, row count, missing or duplicate temperatures/sales, numeric types and realistic data ranges; create a temperature-vs-units scatter plot and explain if it appears nonlinear.
- Split the dataset once into common train/test partitions (fixed random state) if dataset size allows; both methods MUST use exactly the same split. If dataset is tiny, use a defensible simple validation strategy, explain it, and avoid overclaiming metrics.
- Model A: `LinearRegression` with temperature as the only numeric feature. Model B: beginner-readable `Pipeline([('polynomial', PolynomialFeatures(degree=2, include_bias=False)), ('regression', LinearRegression())])`. Consider degree 3 only if justified by a small train-only validation comparison; never choose degree based on test results.
- Show both fits on one temperature-scatter chart with a smooth sorted temperature grid; avoid connecting unsorted points with zigzag lines. Also show test-set actual vs predicted or another useful diagnostic figure.
- Compare held-out MAE, RMSE, R² in a small table; explain differences, generalization risk and where polynomial regression is appropriate. PolynomialFeatures changes the inputs; the underlying estimator remains linear regression.
- Provide one clearly labeled temperature example from the actual input range and the two models' predictions. Do not extrapolate to unrealistic temperatures or invent numbers.

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
