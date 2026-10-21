# Women Entrepreneurship in India: State and Regional Insights

A Python data analysis of **women-owned MSMEs across Indian States and UTs**. It combines MSME ownership data with State GDP and literacy rates to ask where women's entrepreneurship is strongest, and how it relates to economic size.

Built with pandas, Seaborn, Matplotlib and GeoPandas.

## Questions explored

1. How does the share of women-owned MSMEs relate to **economic productivity per MSME**?
2. Do the **largest economies** and the **smallest economies** differ in women's ownership and literacy?
3. Which **regions** of India have the highest women's participation?
4. How can the regional pattern be shown on a **map**?

## Data

| Field | Description |
|---|---|
| `State` | State / UT name |
| `Total_MSMEs` | Total MSMEs in the State |
| `Women_Owned_MSMEs` | Number of women-owned MSMEs |
| `Percent_Women_Owned` | Share of MSMEs owned by women (%) |
| `State_GDP_Crore_INR_2023_24` | State GDP, 2023-24 (₹ crore) |
| `Literacy_Rate_Percent` | State literacy rate (%) |

- **Source:** Government publications.
- A GeoJSON of Indian State boundaries (`in.json`) is used for the map.
- **Data note:** The raw dataset is not included in this repo.

## Analysis

### 1. Women's ownership vs. economic value per MSME
- Derived a new metric, **GDP per MSME** (`State GDP ÷ Total MSMEs`).
- Built a **bubble scatter plot**: x = GDP per MSME, y = % women-owned, bubble size = number of MSMEs, with every State labelled.
- Added **average reference lines** that split the chart into four quadrants.


  

### 2. Leaders vs. laggards (top 5 vs. bottom 5 States by GDP)
Compared the five largest and five smallest State economies on average GDP, women's ownership and literacy.

| Metric | Top 5 by GDP | Bottom 5 by GDP |
|---|---|---|
| Avg State GDP (₹ crore) | 27,80,000 | 35,000 |
| Avg women ownership (%) | 36.8 | 51.0 |
| Avg literacy rate (%) | 76.7 | 79.8 |

### 3. Regional analysis
Mapped States into six regions (North, South, East, West, Central, North-East) and compared average women's ownership:

| Region | Avg % women-owned MSMEs |
|---|---|
| East | 51.0 |
| North-East | 50.1 |
| South | 46.6 |
| Central | 37.7 |
| West | 34.0 |
| North | 26.3 |

### 4. Geospatial view
Merged regional averages onto a map of India with GeoPandas and drew a **choropleth** (`YlGnBu`). Regional boundaries were dissolved so each region gets one label showing its name and average.

## Key takeaways

- Women's ownership is **highest in the East and North-East** and **lowest in the North**, a gap of roughly 25 percentage points.
- The **smaller economies** in this sample show a **higher share** of women-owned MSMEs than the largest economies. Higher GDP does not mean higher women's participation.
- Literacy differs little between the top 5 and bottom 5 States, so it is unlikely to explain the gap on its own.

> **Caveat:** These are descriptive comparisons on a small sample of States. They show association, not causation. Regional figures are simple averages of State percentages, not weighted by the number of MSMEs.

## Tech stack

Python · pandas · Seaborn · Matplotlib · GeoPandas · Jupyter Notebook

## Getting started

```bash
pip install pandas matplotlib seaborn geopandas
jupyter notebook insights.ipynb
```

Before running, update the file paths for the CSV and the GeoJSON in the notebook to point to your own copies.

## Project structure

```
.
├── insights.ipynb   # Analysis notebook
├── images/          # Chart screenshots
└── README.md
```


## Author

[Tajveer Singh]

*Built as an independent portfolio project. It is not an official NITI Aayog publication.*
