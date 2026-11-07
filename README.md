# Melbourne Property Pricing Dynamics: Exploratory Data Analysis

An exploratory analysis of **13,580 Melbourne property sales** in Python, looking at what drives prices across regions, property types, distance from the CBD and size.

## Objective
Understand how price relates to location, property type, rooms, distance from the CBD and sale method, and surface patterns useful for buyers, sellers and investors.

## Dataset
- File: `melb_data.csv`
- Source: Melbourne Housing Snapshot (Kaggle)
- Rows: 13,580, Columns: 21
- Key columns: Price, Suburb, Rooms, Type, Method, Distance, Bathroom, Car, Landsize, BuildingArea, YearBuilt, Regionname, Date

## Tools Used
- Python, pandas, NumPy
- Plotly (Express and Graph Objects) for interactive charts
- Jupyter Notebook (`Melbourne House.ipynb`)

## Analysis Steps
1. **Data cleaning:**
   - dropped 8 redundant location and detail columns, renamed key columns, removed 1 duplicate row
   - filled missing `BuildingArea` (47.5%), `YearBuilt` (39.6%) and `Car` (0.5%) with the median
   - fixed data types, and decoded `Type` and `Method` codes into full names
   - created `SalesYear`, `SalesMonth`, `PropertyAge` and `PricePerSqm`
   - removed 612 price outliers using the IQR method (13,579 to 12,967 rows)
2. **Univariate analysis:** price distribution, property type and sale method shares
3. **Bivariate analysis:** price vs property type, region, distance from the CBD and number of rooms
4. **Multivariate analysis:** region x property type price matrix, price per sqm by sale method, correlation matrix

## Key Insights
- **Property type:** houses average about $1.12M, townhouses about $916k and units about $603k.
- **Region:** Southern Metropolitan ($1.17M) and Eastern Metropolitan ($1.07M) are the most expensive, while Western Victoria ($398k) is the cheapest.
- **Distance:** price falls as distance from the CBD grows (correlation -0.15), with the highest prices and most transactions within about 15 km of the centre.
- **Size:** rooms (0.49) and bathrooms (0.38) correlate most strongly with price among physical features; land size and building area correlate only weakly.
- **Market mix:** houses are 68% of sales, and "Property Sold" is the dominant sale method (about 67%).
- **Seasonality:** average prices dip around June to July each year and recover in spring.

## Visuals
<img width="1545" height="441" alt="Screenshot 2026-11-07 152735" src="https://github.com/user-attachments/assets/91d69a9d-01b4-425b-872e-f75ba2333c9a" />
<img width="1578" height="427" alt="Screenshot 2026-11-07 152748" src="https://github.com/user-attachments/assets/68e9a461-42e0-4f32-aa78-8630bb687c56" />
<img width="1517" height="412" alt="Screenshot 2026-11-07 152825" src="https://github.com/user-attachments/assets/2ea0753e-cee4-474f-8bbd-816f9bb50624" />

## How to Run
```bash
git clone https://github.com/arjunajikumar-svg/Melbourne-Property-Pricing-Dynamics-An-Exploratory-Analysis.git
pip install pandas numpy plotly statsmodels jupyter
jupyter notebook "Melbourne House.ipynb"
```

