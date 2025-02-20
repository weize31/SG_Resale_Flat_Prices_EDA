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

### Next Steps

There is the potential for geospatial analysis by adding longitude and latitude coordinates based on `block` and `street_name` columns using geocoding services such as Google Maps API and Singapore's OneMap API. This can enhance the analysis by allowing for spatial visualizations and geographic insights.
