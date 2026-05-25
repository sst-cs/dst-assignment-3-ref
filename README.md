# Assignment 03 – Data Visualisation

Edit only `assignment.ipynb`. Do not rename any files.

## Dataset
`movies.csv` — 200 rows, columns: `title`, `year` (2000–2024), `genre`, `rating`, `votes`, `revenue_million`.

---

## Required Variables (exact names)

### Data Loading & Cleaning
| Variable | Description |
|---|---|
| `df` | Raw DataFrame loaded from `movies.csv` |
| `df_shape` | Tuple — shape of `df` |
| `summary_stats` | `df.describe()` result |
| `df_clean` | DataFrame with outliers removed (see Task 2) |
| `df_clean_shape` | Tuple — shape of `df_clean` |

### Feature Engineering
| Variable | Description |
|---|---|
| `df_clean['decade']` | New column: decade string, e.g. `'2000s'`, `'2010s'`, `'2020s'` |
| `genre_stats` | GroupBy genre → mean, std, count of `rating` and `revenue_million` |
| `top_genres` | Series: genres ranked by **mean revenue descending** |
| `top_movies` | Top 10 rows from **`df`** by `rating` descending |

### Figures (all must have a title)
| Variable | Chart type | Data |
|---|---|---|
| `fig1` | Histogram with KDE overlay | `rating` column of `df_clean` |
| `fig2` | Bar chart with **error bars** (mean ± std) | `rating` per `genre` from `df_clean` |
| `fig3` | Scatter with **regression line** | `votes` vs `revenue_million` from `df_clean` |
| `fig4` | Line plot | Average `revenue_million` per `year` from `df_clean` |
| `fig5` | Heatmap with **annotated values** | Correlation matrix of numeric columns in `df_clean` |
| `fig6` | Box plot | `rating` distribution per `genre` from `df_clean` |
| `fig7` | Violin plot | `revenue_million` distribution per `decade` from `df_clean` |
| `fig8` | Pair plot | All numeric columns of `df_clean` (use `sns.pairplot`) |

---

## Task Details

### Task 2 – Outlier Removal (IQR Method)
Remove rows where `rating` **or** `revenue_million` is outside `[Q1 − 1.5×IQR, Q3 + 1.5×IQR]`.  
Apply the filter to **both** columns (sequentially or together). Store the result in `df_clean`.

### Task 3 – Decade Column
Derive `df_clean['decade']` by flooring `year` to the nearest decade and formatting as a string:
```python
df_clean['decade'] = (df_clean['year'] // 10 * 10).astype(str) + 's'
# e.g. 2013 → '2010s',  2003 → '2000s'
```

### Figure Requirements
- Every figure **must have a title**.
- `fig1`, `fig2`, `fig3`, `fig4` must label both axes.
- Close each figure with `plt.close()` after storing it.
- Use `seaborn` where specified (histplot/KDE, barplot, regplot, heatmap, boxplot, violinplot, pairplot).

---

## Rules
- Do **not** rename any files.
- Use the **exact variable names** in the tables above.
- `top_movies` comes from **`df`** (the raw data), not `df_clean`.
