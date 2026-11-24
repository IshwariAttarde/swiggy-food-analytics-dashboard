# KPI Definitions

Business definitions for the Swiggy dashboard. Field names refer to the dataset in `data/`.

| KPI | Definition |
|-----|-----------|
| Total Sales | Sum of `NetSales` in `FactOrders` |
| Total Orders | Count of `OrderID` |
| Active Customers | Distinct count of `CustomerID` with orders in the selected period |
| Average Order Value | Sales / total orders |
| Average Rating | Average of `Rating` |
| Total Restaurants | Distinct count of `RestaurantID` |
| New Customers | Customers in the `New` segment of `DimCustomers` |
| Repeat Customers | Customers who ordered more than once in the selected period |
| Avg Orders per Customer | Total orders / active customers |
| Orders by Time of Day | Order count grouped by the hour in `OrderDateTime` |
| Sales by City / Cuisine | `NetSales` grouped by `City` / `Cuisine` |

`CustomerSegment` in `DimCustomers` has the values New, Regular and Repeat. Any extra tiers shown in the dashboard (such as Loyal) come from the report's own logic.

> Standard calculations are listed here. If your Power BI DAX measures differ, update this file to match. Also see the data notes in `data_dictionary.md` about `NetSales` vs. `OrderValue`.
