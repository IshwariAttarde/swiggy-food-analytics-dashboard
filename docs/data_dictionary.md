# Data Dictionary

Source file: `data/Swiggy_PowerBI_Dataset_Jan2022_May2026.xlsx` (Jan 2022 – May 2026). Column names, types and examples are read directly from the workbook.

Note: date columns (`OrderDate`, `OpeningDate`, `SignupDate`, `Date`) are stored as Excel serial numbers; Power BI converts them when the column type is set to Date.


## FactOrders

*150,000 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `OrderID` | text | SW0000001 |
| `OrderDate` | integer | 45562 |
| `OrderDateTime` | decimal | 45562.88333333333 |
| `Year` | integer | 2024 |
| `MonthNumber` | integer | 9 |
| `MonthName` | text | Sep |
| `Quarter` | text | Q3 |
| `CustomerID` | text | C000001 |
| `RestaurantID` | text | R00001 |
| `City` | text | Gurgaon |
| `State` | text | Haryana |
| `Cuisine` | text | Biryani |
| `RestaurantType` | text | Cloud Kitchen |
| `AgeGroup` | text | 18-24 |
| `Gender` | text | Male |
| `OrderType` | text | Delivery |
| `PaymentMode` | text | UPI |
| `OrderStatus` | text | Delivered |
| `Quantity` | integer | 3 |
| `GrossSales` | decimal | 1107.34 |
| `DiscountAmount` | decimal | 55.36 |
| `NetSales` | decimal | 10527.86 |
| `DeliveryFee` | integer | 20 |
| `TaxAmount` | decimal | 52.6 |
| `OrderValue` | decimal | 1124.58 |
| `Rating` | decimal | 4.4 |
| `DeliveryMinutes` | decimal | 14.0 |

## DimRestaurants

*15,000 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `RestaurantID` | text | R00001 |
| `RestaurantName` | text | Wok Express 00001 |
| `City` | text | Gurgaon |
| `State` | text | Haryana |
| `Cuisine` | text | Biryani |
| `RestaurantType` | text | Cloud Kitchen |
| `RestaurantRating` | decimal | 4.4 |
| `OpeningDate` | integer | 44713 |
| `IsActive` | text | Yes |

## DimCustomers

*78,000 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `CustomerID` | text | C000001 |
| `SignupDate` | integer | 44644 |
| `AgeGroup` | text | 18-24 |
| `Gender` | text | Male |
| `HomeCity` | text | Bengaluru |
| `State` | text | Karnataka |
| `PreferredCuisine` | text | Burger |
| `CustomerSegment` | text | New |

## DimDate

*1,612 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `Date` | integer | 44562 |
| `Year` | integer | 2022 |
| `Quarter` | text | Q1 |
| `MonthNumber` | integer | 1 |
| `MonthName` | text | January |
| `MonthShort` | text | Jan |
| `YearMonth` | text | 2022-01 |
| `Weekday` | text | Saturday |
| `IsWeekend` | boolean | True |

## MonthlySummary

*53 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `Orders` | integer | 14100 |
| `NetSales` | decimal | 9328584.76 |
| `OrderValue` | decimal | 10074894.35 |
| `Quantity` | integer | 43585 |
| `AverageRating` | decimal | 4.02 |
| `YearMonth` | text | 2022-01 |

## Data notes

- `NetSales` in `FactOrders` is roughly 10x `GrossSales - DiscountAmount`, while `OrderValue` equals `GrossSales - DiscountAmount + DeliveryFee + TaxAmount`. Check which measure your reports should use before comparing figures.
- The full dataset totals 150,000 orders, 78,000 customers, 15,000 restaurants and a `NetSales` total of about ₹987M across Jan 2022 – May 2026. A 2023–2024 filter returns fewer orders.
- Cities appear under the name used in the data (for example `Bengaluru`), which may differ from the label shown in the dashboard visuals.

