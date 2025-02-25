# Exploratory Data Analysis (EDA) of Singapore's Resale Flat Prices from 2017 to 2024

### Project Overview

This project aims to explore and analyze the trends, patterns, and key factors influencing the resale prices of flats in Singapore from 2017 to 2024. The dataset contains detailed information on resale prices, location of flats, flat type, flat model, floor area and lease details. Through data visualization and statistical analysis, the goal is to derive actionable insights into how these factors affect flat prices.

### Business Understanding

Singapore's real estate market is competitive and influenced by various factors such as location, flat type, and remaining lease. Understanding the dynamics of resale prices can help potential buyers make informed decisions. In addition, these can also assist real estate agents in assessing market trends. The key objectives of this analysis are:

- Identify trends in resale prices over time.

- Examine how different flat types and different locations affect resale prices.

- Evaluate the impact of lease age and floor area on pricing.

- Provide data-driven insights to support better decision-making in the housing market.

### Data Understanding

The initial dataset in this project includes 180,974 rows and 11 columns with the following attributes:

- `month`: The month and year of each resale transaction.

- `town`: The residential area where the flat is located.

- `flat_Type`: Classification based on the number of rooms (e.g., 2-Room, 3-Room, 4-Room).

- `block`: The block number of the flat.

- `street_name`: The street where the flat is located.

- `storey_range`: The floor range where the flat is situated.

- `floor_area_sqm`: Total interior area of the flat.

- `flat_model`: The design model of the flat.

- `lease_commence_date`: The year when the lease started.

- `remaining_lease`: Duration of the remaining lease (in years and months).

- `resale_price`: The transaction price of the flat.

Key Data Transformations:

- Datetime Formatting: Converted the month column into datetime format and then split them into 2 separate columns `year` and `month`.

- Feature Creation: Dervied a `region` column based on the `town` column. Derived `lease_age` and `remaining_lease_months` based on `remaining_lease` column. Transformed `storey_range` into low, mid, and high levels using ordinal encoding.

### Findings

1. floor_area_sqm ($3556.86 per sqm)

   - For every additional square meter of floor area, the resale price increases by 3,556.86 SGD. This positive coefficient aligns with the expectation that larger flats are more expensive.

2. lease_age (-$3988.27 per year)

   - For each additional year of lease age (older flats), the resale price decreases by 3,988.27 SGD. This reflects the depreciation effect as older flats typically have shorter remaining leases, reducing their value.

3. storey_level ($32864.81 per level category)

   - Higher storey levels are associated with a significant price increase of 32,864.81 SGD per category (Low → Mid → High). Flats on higher floors are often preferred due to better views, ventilation, and reduced noise.

4. flat_type (Compared to 1-ROOM Flat as Baseline Category)

   - 2 ROOM: +24,082.99 SGD
   - 3 ROOM: +64,767.43 SGD
   - 4 ROOM: +77,403.99 SGD
   - 5 ROOM: +98,671.89 SGD
   - EXECUTIVE: +150,081.75 SGD
   - MULTI-GENERATION: +246,296.52 SGD

   Resale prices increase progressively as the flat type increases in size and functionality.

   Multi-Generation flats have the largest premium (+246,296.52 SGD), likely due to their larger living spaces.

   2 ROOM flats, being the smallest, have the lowest added value compared to other categories.

5. Region (Compared to Baseline Region: Central)

   - East: -98,058.99 SGD
   - North: -185,059.63 SGD
   - Northeast: -134,508.35 SGD
   - West: -160,457.10 SGD

   Resale prices in all regions are lower compared to the Central region (baseline). This align with the premium pricing of central locations due to better amenities, transportation, and proximity to the CBD.

   The North region shows the largest negative impact (-185,059.63 SGD), suggesting that flats here are relatively more affordable.

### Overall Insights

1. Size, Lease age and Floor level matters:

   - Larger flats command higher prices, while older leases reduce value.
   - Higher floors significantly increase resale prices, suggesting demand for better views and quieter environments.

2. Flat Type greatly influences price:

   - Upgrading from one flat type to another comes with substantial price jumps, reflecting differences in space, design, and desirability.

3. Location drives value:
   - The Central region serves as the premium benchmark, with other regions priced more affordably.

### Next Steps

There is the potential for geospatial analysis by adding longitude and latitude coordinates based on `block` and `street_name` columns using geocoding services such as Google Maps API and Singapore's OneMap API. This can enhance the analysis by allowing for spatial visualizations and geographic insights.
