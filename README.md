# Spark-Based Market-Basket Analysis using the Apriori Principle on IMDB Top 1000 Movies

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/eliguseynli/market-basket-analysis-imdb/blob/main/market_basket_analysis_imdb_updated.ipynb)

This project implements a market-basket analysis system using the IMDB Top 1000 Movies dataset (Kaggle, CC0 license).

Each movie is treated as a transaction (basket), and actors listed under Star1–Star4 are treated as items.

The implementation is aligned with the course methodologies and is based on Apache Spark (PySpark). The mining logic follows the Apriori principle by generating candidate pairs only from frequent singletons, exploiting the monotonicity property of the Apriori algorithm.

The project includes:
- Data download via Kaggle API
- Pre-processing and basket construction
- Frequent singleton discovery
- Apriori-based candidate pruning
- Frequent actor pair counting using Spark distributed operations
- Scalability experiments on increasing dataset sizes
- Runtime analysis and discussion

## Method Overview

The dataset is loaded into a Spark DataFrame. 

Frequent single actors are computed using:
- `explode` to flatten actor arrays
- `groupBy().count()` for support computation

Frequent single actors are first identified using a minimum support threshold. 
Following the Apriori principle, candidate actor pairs are generated only from actors that are frequent as singletons. This pruning step significantly reduces the number of candidate itemsets compared to a brute-force enumeration.
Support for candidate pairs is then computed using Spark distributed transformations.

Scalability is evaluated by running the pipeline on different dataset sizes and measuring runtime.

## Running the Notebook

To run the notebook:

1. Upload your Kaggle API credentials (`kaggle.json`) in Colab.
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
