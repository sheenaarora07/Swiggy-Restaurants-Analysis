# 🍽️ Swiggy Restaurant Analytics --- Power BI Dashboard

An interactive **Power BI dashboard for analysing Swiggy restaurant
listings**, with a focus on restaurant presence, location coverage,
cuisine mix, ratings, pricing, vegetarian availability, and promotional
offers.

The project combines a raw restaurant dataset with Power Query
transformations, DAX calculations, and business-focused visual
storytelling to turn 140K+ records into an executive-friendly dashboard.

------------------------------------------------------------------------

## 📌 What This Project Answers

The dashboard is designed to answer practical business questions such
as:

-   Where is restaurant supply most concentrated?
-   Which cuisine combinations appear most frequently?
-   How are restaurant ratings distributed?
-   How does pricing vary across locations?
-   Is there a visible relationship between restaurant price and rating?
-   What share of restaurants are Pure Veg?
-   How widespread are promotional offers?
-   Which locations show unusually high average pricing?

------------------------------------------------------------------------

## 📊 Dataset at a Glance

The source file is `Swiggy_Dataset.csv`.

  Attribute                       Details
  ------------------------- -------------
  Restaurant records          **140,657**
  Columns                          **10**
  Locations                       **581**
  Unique restaurant names       **100K+**
  Pure Veg share                **\~42%**
  Records with offers         **\~98.7%**

### Source Columns

  Column                Business Meaning
  --------------------- --------------------------------
  `Restaurant Name`     Restaurant listing name
  `Cuisine`             Cuisine or cuisine combination
  `Rating`              Customer rating
  `Number of Ratings`   Rating/review-count bucket
  `Average Price`       Approximate price for two
  `Number of Offers`    Number of offers available
  `Offer Name`          Promotional offer details
  `Area`                Restaurant operating area
  `Pure Veg`            Vegetarian classification
  `Location`            City/location

------------------------------------------------------------------------

## 🧹 Data Preparation

The raw dataset contains fields that are not immediately analysis-ready.
The data was prepared in **Power Query** before building the dashboard.

### Key transformations

-   Converted `Rating` into a numeric field.
-   Treated non-numeric rating values such as `NEW` and `--`
    appropriately for numerical analysis.
-   Removed the currency symbol and text such as `for two` from
    `Average Price`.
-   Converted average price into a numeric measure.
-   Prepared `Number of Ratings` for quantitative analysis using
    rating-count buckets/lower-bound values.
-   Standardised categorical fields such as `Pure Veg` and `Location`.
-   Reviewed missing values in cuisine, area, offer-name and
    rating-count fields.
-   Created rating buckets for distribution analysis.
-   Prepared fields required for location, cuisine, offer and vegetarian
    analysis.

The raw file contains **14,542 missing values in `Number of Ratings`**,
**1,808 missing `Offer Name` values**, **27 missing cuisine values**,
and **2 missing area values**. These were considered during the
preparation stage rather than treating the raw file as analysis-ready.

------------------------------------------------------------------------

# 📈 Dashboard Overview

The dashboard is structured as a **restaurant performance overview** so
that a user can move from high-level KPIs into location, cuisine,
rating, pricing and Pure Veg patterns.

## 🔢 KPI Summary

The dashboard currently highlights:

  KPI                            Dashboard Value
  ---------------------------- -----------------
  🍴 Total Restaurants                  **139K**
  📍 Total Locations                     **581**
  ⭐ Average Rating                     **4.04**
  ₹ Average Price                    **₹272.94**
  🌿 Pure Veg %                       **41.99%**
  🏷️ Restaurants with Offers             **99K**

These cards provide an immediate snapshot before the user starts
exploring individual dimensions.

------------------------------------------------------------------------

## 📍 Restaurant Distribution by Location

A horizontal bar chart compares restaurant listings across locations.

The dashboard highlights locations such as:

-   Kanpur
-   Central-Goa
-   Indore
-   Nagpur
-   Vadodara
-   Lucknow
-   Hyderabad
-   Jaipur

This view helps identify areas with a high concentration of restaurant
listings and provides a starting point for geographical comparison.

------------------------------------------------------------------------

## 🍜 Cuisine Mix

The treemap shows the relative presence of cuisine
categories/combinations.

Examples visible in the dashboard include:

-   North Indian, Chinese
-   Indian
-   Chinese
-   Indian, Chinese
-   North Indian
-   Bakery
-   South Indian
-   Biryani

The visualization is useful for understanding which cuisine groups
occupy a larger share of the restaurant landscape.

------------------------------------------------------------------------

## ⭐ Rating Distribution

Restaurant ratings are grouped into buckets:

``` text
< 2.5
2.5 – 3.0
3.0 – 3.5
3.5 – 4.0
4.0 – 4.5
4.5 – 5.0
```

The **4.0--4.5** bucket is the largest category in the dashboard, with
approximately **54K restaurant records**.

This provides a quick view of the overall rating profile rather than
focusing only on the average rating.

------------------------------------------------------------------------

## ₹ Pricing by Location

The average-price chart compares restaurant pricing across locations.

One notable observation in the dashboard is **Lalitpur**, which has a
substantially higher average price than the other locations displayed.

This type of comparison can help identify locations that may require
additional investigation into restaurant mix, pricing structure, or data
quality.

------------------------------------------------------------------------

## 📊 Price vs Rating

The scatter plot places:

-   **Average Price** on the X-axis
-   **Rating** on the Y-axis
-   Rating-count information into the bubble representation

The purpose is not simply to find the most expensive restaurants, but to
explore whether higher prices appear alongside stronger ratings and
where unusual observations occur.

------------------------------------------------------------------------

## 🌿 Pure Veg Distribution

The dashboard uses a donut chart to compare Pure Veg and non-Pure-Veg
restaurants.

### Dashboard result

-   **Pure Veg: 41.99%**
-   **Non-Pure Veg: 58.01%**

The green treatment for Pure Veg makes this KPI visually distinct while
maintaining the dashboard's orange Swiggy-inspired theme.

------------------------------------------------------------------------

# 💡 Key Findings

### 1. Restaurant supply is geographically broad

The dataset covers **581 locations**, giving the analysis substantial
geographical breadth.

### 2. Ratings are concentrated around 4.0--4.5

The **4.0--4.5** rating bucket is the largest group shown in the
dashboard, at approximately **54K records**.

### 3. North Indian and Indian cuisine groups have strong representation

The cuisine treemap shows North Indian/Chinese, Indian and
Chinese-related categories among the most prominent groups.

### 4. Pure Veg represents a substantial segment

Around **42%** of the dashboard's restaurant records are classified as
Pure Veg.

### 5. Offers are widespread

The dashboard shows approximately **99K restaurants with offers**, while
the raw dataset contains offers on roughly **98.7% of records** when
`Number of Offers > 0` is used as the indicator.

### 6. Pricing varies substantially by location

Lalitpur stands out in the dashboard's average-price comparison and is
therefore a useful location for further investigation.

------------------------------------------------------------------------

# 🎯 Recommendations

The dashboard can support several follow-up business actions:

-   Investigate high-price locations to understand whether pricing is
    driven by cuisine mix, restaurant positioning, or data anomalies.
-   Segment restaurant promotions by location and cuisine instead of
    treating all offers uniformly.
-   Examine lower-rated restaurants separately to identify opportunities
    for service-quality improvement.
-   Use cuisine-level analysis to understand where restaurant supply is
    concentrated and where potential gaps may exist.
-   Track Pure Veg restaurants as a distinct segment for targeted
    discovery and promotional analysis.
-   Combine rating with rating-count information before interpreting a
    restaurant as a strong performer.

------------------------------------------------------------------------

# 🎛️ Interactive Experience

The dashboard includes slicers for:

-   📍 **Location**
-   🍜 **Cuisine**
-   🌿 **Pure Veg**
-   🏪 **Restaurant**

It also includes navigation controls such as:

-   **Reset** --- clears selected filters.
-   **Forward** --- moves to the next analysis view when available.

The visuals respond to the selected filters, allowing the user to move
from an overall market view to a specific location, cuisine or
restaurant.

------------------------------------------------------------------------

# 🧮 Power BI & DAX

The project uses DAX measures for KPI and analytical calculations.

Examples include:

``` dax
Total Restaurants =
DISTINCTCOUNT('Swiggy'[Restaurant Name])
```

``` dax
Total Locations =
DISTINCTCOUNT('Swiggy'[Location])
```

``` dax
Average Rating =
AVERAGE('Swiggy'[Rating])
```

``` dax
Average Price =
AVERAGE('Swiggy'[Average Price])
```

Additional calculations were used for:

-   Pure Veg percentage
-   Restaurant offer availability
-   Rating buckets
-   Cuisine counts
-   Rating-count analysis
-   Location-level comparisons
-   Restaurant-level analysis

> Measure names may vary slightly depending on the final Power BI model.

------------------------------------------------------------------------

# 🛠️ Technology Stack

### Power BI

-   Dashboard development
-   Data modelling
-   Interactive visuals
-   KPI cards
-   Slicers and navigation
-   Business storytelling

### Power Query

-   Data cleaning
-   Data type conversion
-   Text transformation
-   Missing-value handling
-   Feature preparation

### DAX

-   Measures
-   Aggregations
-   Percentages
-   Distinct counts
-   Conditional business metrics

### CSV

Used as the primary source data format.

------------------------------------------------------------------------

# 📁 Suggested Repository Structure

``` text
swiggy-restaurant-analysis/
│
├── Dashboard/
│   └── Swiggy_Dashboard.pbix
│
├── Dataset/
│   └── Swiggy_Dataset.csv
│
├── Screenshots/
│   └── Restaurant_Overview.png
│
└── README.md
```

------------------------------------------------------------------------

# 🚀 How to Explore the Project

1.  Download or clone the repository.
2.  Open `Dashboard/Swiggy_Dashboard.pbix` in **Power BI Desktop**.
3.  Refresh the dataset if required.
4.  Use the slicers to filter by location, cuisine, Pure Veg status or
    restaurant.
5.  Hover over charts to inspect detailed values.
6.  Use the navigation controls to move between available dashboard
    views.

------------------------------------------------------------------------

# 💼 Skills Demonstrated

This project demonstrates practical skills in:

`Power BI` · `Power Query` · `DAX` · `Data Cleaning` ·
`Data Transformation` · `Data Analysis` · `Data Visualization` ·
`KPI Design` · `Interactive Dashboarding` · `Business Intelligence` ·
`Data Storytelling`

------------------------------------------------------------------------

# 👩‍💻 Author

## Sheena Charaya

**Data Analytics \| Power BI \| SQL \| Excel \| Python**

📧 **Email:** <sheena.charaya@gmail.com>

🔗 **[LinkedIn](https://www.linkedin.com/in/sheena-charaya/)**

------------------------------------------------------------------------

## ⭐ Project Note

This project was created as a practical data analytics portfolio project
to demonstrate an end-to-end workflow:

``` text
Raw Restaurant Data
        ↓
Data Understanding
        ↓
Data Cleaning & Transformation
        ↓
Power Query
        ↓
DAX & KPI Development
        ↓
Interactive Visualizations
        ↓
Dashboard Design
        ↓
Business Insights & Recommendations
```

The objective is to transform a large restaurant dataset into a clear,
interactive and business-oriented analytical view.
