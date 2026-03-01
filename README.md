# Market-Basket Analysis on IMDB Top 1000 Movies
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eliguseynli/market-basket-analysis-imdb/blob/main/market_basket_analysis_imdb_updated.ipynb)

This project implements a market-basket analysis system using the IMDB Top 1000 Movies dataset (Kaggle, CC0 license).

Each movie is treated as a transaction (basket), and actors listed under Star1–Star4 are treated as items.

The implementation is aligned with the course methodologies and is based on Apache Spark (PySpark) using distributed DataFrame transformations.

The project includes:
- Data download via Kaggle API
- Pre-processing and basket construction
- Frequent single and pair itemset counting using Spark (explode, groupBy, count)
- Scalability experiments on increasing dataset sizes
- Runtime analysis and discussion

## Method Overview

The dataset is loaded into a Spark DataFrame. 

Frequent single actors are computed using:
- `explode` to flatten actor arrays
- `groupBy().count()` for support computation

Frequent pairs are generated per transaction and counted using Spark aggregations, following a MapReduce-style counting pattern implemented via Spark transformations.

Scalability is evaluated by running the pipeline on different dataset sizes and measuring runtime.

## Running the Notebook

To run the notebook:

1. Provide Kaggle API credentials (username and key).
2. Run all cells.
3. The dataset will be downloaded automatically.
4. All Spark-based experiments will be reproduced.

## Repository Structure

- `market_basket_analysis_imdb.ipynb`
- `report/report.tex`
- `report/report.pdf`
- `report/runtime_plot.png`
- `README.md`

## Reproducibility

The dataset is downloaded directly from Kaggle using the Kaggle API.
Sensitive credentials are not included in the public version.
The notebook is executable on Google Colab via the badge above.
