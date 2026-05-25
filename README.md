# Assignment 03 – Data Visualisation

Edit only `assignment.ipynb`. Do not rename any files.

## Dataset
`movies.csv` — 200 rows, columns: `title`, `year`, `genre`, `rating`, `votes`, `revenue_million`.

## Required Outputs
Your notebook must define these variables with **exact names**:

| Variable | Description |
|---|---|
| `df` | The full DataFrame loaded from `movies.csv` |
| `df_shape` | Tuple — shape of `df` |
| `summary_stats` | `df.describe()` result |
| `fig1` | Histogram of the `rating` column |
| `fig2` | Bar chart — average `rating` per `genre` |
| `fig3` | Scatter plot — `votes` vs `revenue_million` |
| `fig4` | Line plot — average `revenue_million` per `year` |
| `fig5` | Heatmap of the correlation matrix of numeric columns |
| `top_movies` | Top 10 rows sorted by `rating` descending |

## Plot Requirements
- Every figure **must have a title** (`ax.set_title(...)` or `plt.title(...)`).
- `fig1` and `fig3` must label both axes.
- Store each figure as the return value of `plt.figure()` or `fig, ax = plt.subplots()`.
- Close figures with `plt.close()` after storing them so the notebook does not display duplicates.

## Rules
- Do **not** rename the files listed above.
- Use the **exact variable names** in the table.
