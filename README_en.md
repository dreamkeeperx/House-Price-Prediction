# House Price Prediction — Exploratory Data Analysis

Exploratory analysis of 4,600 residential real estate sales in Washington State (Seattle, Bellevue, Redmond, and surrounding King County cities), framed around a simple business scenario: helping a real estate agency decide which cities to prioritize for expansion.

## Contents
- `house_price_prediction_en.ipynb` — full analysis notebook, English
- `house_price_prediction_ru.ipynb` — full analysis notebook, Russian (translated; see note below on regenerating charts)
- `README_en.md` / `README_ru.md` — this file, in both languages

## Dataset
Kaggle dataset "House Price Prediction" (debayank2024) — 4,600 rows × 18 columns: `date`, `price`, `bedrooms`, `bathrooms`, `sqft_living`, `sqft_lot`, `floors`, `waterfront`, `view`, `condition`, `sqft_above`, `sqft_basement`, `yr_built`, `yr_renovated`, `street`, `city`, `statezip`, `price_per_sqft`.

## Business questions
1. What is the overall data quality — missing values, duplicates, anomalies (`price == 0`) — and how should they be handled?
2. How is `price` distributed, and are there outliers?
3. Which features correlate most strongly with price?
4. How does price vary by city — clear leaders and laggards by median price and price/sqft?
5. Do waterfront, view, and renovation status affect price?

## Approach
1. **Data quality audit** — missing values, duplicates, invalid prices, extreme `price_per_sqft` values.
2. **Cleaning** — dropped $0 sales and extreme `price_per_sqft` outliers; converted `date` to datetime.
3. **Feature engineering** — `house_age`, `was_renovated`, `has_basement`.
4. **Exploratory analysis** — price distribution, correlation matrix, price vs. bedrooms/bathrooms/living area, price by city, waterfront/view/renovation effects.
5. **Summary report** — findings translated into business recommendations for city-expansion decisions (final section of the notebook).

## Key findings
- Median price **$465K**, right-skewed distribution with a long luxury tail up to $7.06M — median, not mean, is the more representative statistic.
- `sqft_living` is the strongest real price driver (r = 0.43); lot size, condition, and renovation year barely correlate with price.
- Median price by city spans **$150K to $2.10M** — a 14x range, led by Medina, Yarrow Point, and Clyde Hill; South King County towns lag furthest behind.
- Waterfront access roughly **doubles** median price; view rating shows a clean upward trend; renovation status alone is not a reliable price signal.

Full reasoning and business recommendations are in the "Summary Report" section at the end of the notebook.

## Requirements
```
pandas
numpy
matplotlib
seaborn
```

## Note on the Russian notebook
The Russian version was translated from the original: markdown commentary, code comments, and every chart title/axis label/legend. Since the source data file wasn't available for re-execution here, its cell outputs were cleared to avoid Russian-labelled code sitting under stale English-labelled charts. Run all cells once (Kernel → Restart & Run All) to regenerate every table and chart with Russian labels — it's the same data and code, just not yet executed.
