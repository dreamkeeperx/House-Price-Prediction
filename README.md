# EN

# House Price Prediction — Exploratory Data Analysis

Exploratory analysis of 4,600 residential real estate sales in Washington State (Seattle, Bellevue, Redmond, and surrounding King County cities), framed around a simple business scenario: helping a real estate agency decide which cities to prioritize for expansion.

## Contents
- `house_price_prediction_en.ipynb` — full analysis notebook, English
- `house_price_prediction_ru.ipynb` — full analysis notebook, Russian
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
5. **Summary report** — findings (final section of the notebook).

## Key findings
- Median price **$465K**, right-skewed distribution with a long luxury tail up to $7.06M — median, not mean, is the more representative statistic.
- `sqft_living` is the strongest real price driver (r = 0.70); lot size, condition, and renovation year barely correlate with price.
- Median price by city spans **$150K to $2.10M** — a 14x range, led by Medina, Yarrow Point, and Clyde Hill; South King County towns lag furthest behind.
- Waterfront access roughly **doubles** median price; view rating shows a clean upward trend; renovation status alone is not a reliable price signal.

Full reasoning are in the "Summary Report" section at the end of the notebook.

## Requirements
```
pandas
numpy
matplotlib
seaborn
```


# RU

# Прогнозирование цен на недвижимость — разведочный анализ данных (EDA)

Разведочный анализ 4 600 сделок по продаже жилой недвижимости в штате Вашингтон (Сиэтл, Беллевью, Редмонд и другие города округа Кинг), построенный вокруг простого бизнес-сценария: помочь агентству недвижимости выбрать города для приоритетного расширения.

## Содержимое
- `house_price_prediction_en.ipynb` — полный аналитический ноутбук, английская версия
- `house_price_prediction_ru.ipynb` — полный аналитический ноутбук, русская версия
- `README_en.md` / `README_ru.md` — этот файл на обоих языках

## Датасет
Датасет Kaggle «House Price Prediction» (debayank2024) — 4 600 строк × 18 столбцов: `date`, `price`, `bedrooms`, `bathrooms`, `sqft_living`, `sqft_lot`, `floors`, `waterfront`, `view`, `condition`, `sqft_above`, `sqft_basement`, `yr_built`, `yr_renovated`, `street`, `city`, `statezip`, `price_per_sqft`.

## Бизнес-вопросы
1. Каково общее качество данных — пропущенные значения, дубликаты, аномалии (`price == 0`) — и как их обрабатывать?
2. Как распределена `price` и есть ли выбросы?
3. Какие признаки сильнее всего коррелируют с ценой?
4. Как цена варьируется по городам — есть ли явные лидеры и аутсайдеры по медианной цене и цене за кв.фут?
5. Влияют ли наличие водоёма, оценка вида и статус реконструкции на цену?

## Подход
1. **Аудит качества данных** — пропущенные значения, дубликаты, некорректные цены, экстремальные значения `price_per_sqft`.
2. **Очистка** — удалены продажи по $0 и экстремальные выбросы `price_per_sqft`; столбец `date` приведён к формату datetime.
3. **Генерация признаков** — `house_age`, `was_renovated`, `has_basement`.
4. **Разведочный анализ** — распределение цены, матрица корреляций, цена в зависимости от спален/ванных/жилой площади, цена по городам, влияние воды/вида/реконструкции.
5. **Итоговый отчёт** — выводы (последний раздел ноутбука).

## Ключевые выводы
- Медианная цена **$465 тыс.**, распределение с правосторонней асимметрией и длинным «хвостом» элитных продаж до $7,06 млн — медиана, а не среднее, лучше отражает типичный рынок.
- `sqft_living` — главный реальный драйвер цены (r = 0,70); площадь участка, состояние и год реконструкции почти не коррелируют с ценой.
- Медианная цена по городам варьируется **от $150 тыс. до $2,10 млн** — разница в 14 раз, лидируют Медина, Йерроу-Пойнт и Клайд-Хилл; города южной части округа Кинг отстают сильнее всего.
- Наличие водоёма примерно **удваивает** медианную цену; оценка вида показывает чёткий рост; статус реконструкции сам по себе не является надёжным ценовым сигналом.

Полное обоснование — в разделе «Итоговый отчёт» в конце ноутбука.

## Требования
```
pandas
numpy
matplotlib
seaborn
```
