# Market-Basket Analysis on IMDB Top 1000 Movies

This project implements a frequent itemset mining system using the IMDB Top 1000 Movies dataset (Kaggle, CC0 license).

Each movie is treated as a transaction (basket), and actors listed under Star1–Star4 are treated as items.

The project includes:
- Data download via Kaggle API
- Pre-processing and basket construction
- Vertical-format frequent itemset mining (ECLAT-style)
- Scalability experiments on increasing dataset sizes
- Runtime analysis and discussion

## Method Overview

We build a vertical index mapping each actor to the set of transaction IDs in which the actor appears.

Frequent itemsets are computed by intersecting transaction-ID sets, avoiding repeated full scans of the dataset.

We analyze:
- Frequent single actors
- Frequent actor pairs
- Scalability as dataset size increases

## Running the Notebook

To run the notebook:

1. Provide Kaggle API credentials (username and key).
2. Run all cells.
3. The dataset will be downloaded automatically.
4. Results and runtime analysis will be reproduced.

## Repository Structure
market-basket-imdb/
│
├── market_basket_imdb.ipynb
├── report/
│ ├── report.tex
│ ├── report.pdf
│ ├── runtime_plot.png
│
└── README.md

## Reproducibility

The dataset is downloaded directly from Kaggle using the Kaggle API.
Sensitive credentials are not included in the public version.
