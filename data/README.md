# Download the original datasets here (not tracked in Git)

Dataset access is external. The PDFs contain links. Do not generate dummy data or claim to have run notebooks before real downloads.

After installing the Kaggle CLI (`python -m pip install kaggle`) and authenticating your own Kaggle account, run these commands from the **repository root** in PowerShell or CMD:

```text
kaggle datasets download -d gurdit559/canada-per-capita-income-single-variable-data-set -p data/canada --unzip
kaggle datasets download -d hanaksoy/customer-purchasing-behaviors -p data/customer --unzip
kaggle datasets download -d mirajdeepbhandari/polynomial-regression -p data/ice_cream --unzip
kaggle competitions download -c titanic -p data/titanic
```

For Titanic, first sign in on Kaggle and accept the competition rules, then unzip the downloaded file into `data/titanic/` (usually contains `train.csv`, `test.csv`, `gender_submission.csv`). The other datasets may have different actual CSV filenames; inspect them rather than guessing. If Kaggle CLI access is unavailable, download each dataset from the PDF's web link and manually extract it to the same folder.

The same Canada data should be reused by Assignment 1 / Task 1 and Assignment 2 / Task 1. Avoid uploading copies to GitHub unless their licenses expressly allow it.

Notebook code should find the repository root from a notebook's working directory and read files by `root / 'data' / ...`. Fail with a helpful message if data is absent; do not silently switch datasets.
