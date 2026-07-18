# Google Play Store Data Analysis

A course notebook that explores, cleans, filters, aggregates, and visualizes a public Google Play Store application dataset. The work emphasizes practical pandas operations and documents each requested analysis task alongside saved outputs.

## Dataset

The repository includes `googleplaystore.xls`, but its contents are comma-separated text with these fields:

`App`, `Category`, `Rating`, `Reviews`, `Size`, `Installs`, `Type`, `Price`, `Content Rating`, `Genres`, `Last Updated`, `Current Ver`, and `Android Ver`.

The notebook expects the same data under the filename `googleplaystore.csv`.

## Verified analysis

- Inspect the first/last rows, dimensions, data types, missing values, and descriptive statistics
- Drop records with a missing app type
- Fill missing ratings with the median rating from the corresponding category
- Convert formatted install counts and prices to numeric values
- Filter free, highly rated, highly installed, and Education-category apps
- Remove duplicate app names for the Education top-three view
- Compare mean ratings by category
- Aggregate median and total installs by content rating
- Estimate gross paid-app revenue as `Price × Installs`
- Plot a rating histogram and the ten most common categories

The notebook also identifies a malformed row whose category is `1.9` and rating is `19.0`. It discusses excluding that value, but the main grouped output is generated before a cleaned replacement DataFrame is applied.

## Tech stack

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib

No dependency versions or automated tests are included.

## Repository structure

```text
.
├── MohammedOthman1221175.ipynb   # Analysis, explanations, plots, and saved outputs
├── googleplaystore.xls           # CSV-formatted source data with an .xls extension
└── README.md
```

## Setup

1. Create and activate a Python environment.
2. Install the direct dependencies:

   ```bash
   python -m pip install jupyter pandas numpy matplotlib
   ```

3. Copy or rename `googleplaystore.xls` to `googleplaystore.csv` in the repository root. The data is CSV text; do not convert it to an Excel workbook.

## Run and usage

Start Jupyter in the repository root:

```bash
jupyter notebook MohammedOthman1221175.ipynb
```

Run cells from top to bottom. The notebook reloads `googleplaystore.csv` at the beginning of the cleaning section, so keep that file in the working directory. Generated tables and Matplotlib charts are displayed inline.

The `Revenue Estimate` field is a simple multiplication of listed price and install count. It does not account for store fees, refunds, taxes, regional pricing, or the fact that install counts are bucketed, so it should be treated as a rough analytical exercise rather than actual revenue.

## Course context

Developed for a **Data Science course** at **Birzeit University**. The notebook filename and section headings identify the student submission and organize the work into six assignment tasks.

## Future improvements

- Rename the dataset in the repository so the notebook runs without manual preparation
- Remove or repair malformed records before all summaries
- Consolidate repeated loading and cleaning into reusable functions
- Define a clear duplicate-handling policy before app-level rankings
- Add source/license metadata for the dataset
- Add a pinned requirements file and data-quality tests
- Separate exploratory outputs from a concise final findings section
