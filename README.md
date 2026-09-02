# Netflix-Analysis-Dashboard-Power-BI-DAX

An interactive Power BI dashboard analyzing Netflix's content catalog, using DAX (Data Analysis Expressions) and Power Query to explore trends across titles, genres, ratings, and release years.

# Project Overview

This project delivers an end-to-end content analytics dashboard that transforms Netflix's raw catalog data into actionable insights. It covers the full analytics workflow — data cleaning, data modeling, DAX measure creation, and interactive visualization — enabling users to explore Netflix's global content library by type, genre, rating, country, and release year.

Business problem solved: With thousands of titles spanning decades and countries, understanding Netflix's content strategy from raw data alone is difficult. This dashboard turns that catalog into a visual, filterable report for spotting trends in content type, genre popularity, and audience ratings.

Dataset: Netflix titles dataset containing 8,808 records covering movies and TV shows, spanning release years from 1925 to 2021, across 750 countries/regions.

# Key Objectives
Consolidate Netflix catalog data into a single, reliable data model
Track total titles, movies, TV shows, and countries represented
Analyze content distribution by type, genre, and maturity rating
Monitor how content additions have trended over time
Enable filtering by content type (Movie/TV Show) and release year range
Present a clean, executive-ready view of Netflix's content library
# Tools & Technologies
Category	Tools Used
Data Visualization	Microsoft Power BI (Power BI Desktop)
Data Modeling / Calculations	DAX (Data Analysis Expressions)
Data Transformation	Power Query (M Language)
Data Source	Excel / CSV (Netflix titles dataset)
Data Modeling Concepts	Star Schema, Relationships, Calculated Columns, Measures
# Dashboard Features
KPI Summary Cards — Total Countries, Total Titles, Total TV Shows, and Total Movies at a glance
Content Type Toggle — Buttons to switch focus between Movie and TV Show views
Show ID by Type — Donut chart comparing the split between Movies (73.08%) and TV Shows (26.92%)
Count of Title by Year — Trend line showing title additions from 2015 to 2021
Count of Show ID by Rating — Treemap breaking down titles by maturity rating (TV-MA, TV-14, TV-PG, R, PG-13, TV-Y, etc.)
Top 10 Genres — Bar chart ranking the most common genres (TV Shows, TV Dramas, TV Horror, TV Sci-Fi & Fantasy, and more)
Show ID by Year — Area chart showing catalog growth from 2008 to 2020
Interactive Filters — Release year range slider (1925–2021) to explore titles across decades
# Sample DAX Measures
Total Titles = DISTINCTCOUNT(Netflix[show_id])

Total Movies = 
CALCULATE(
    [Total Titles],
    Netflix[type] = "Movie"
)

Total TV Shows = 
CALCULATE(
    [Total Titles],
    Netflix[type] = "TV Show"
)

Total Countries = DISTINCTCOUNT(Netflix[country])

Titles by Year = 
CALCULATE(
    [Total Titles],
    FILTER(ALL('Date'), 'Date'[Year] = SELECTEDVALUE('Date'[Year]))
)

# These reflect the KPI cards shown (Total Titles: 8,808 | Total TV Shows: 2,676 | Total Movies: 6,131 | Total Countries: 750). 

# Data Model
Star schema design with a central Netflix fact table
Supporting dimension tables: Type, Genre, Rating, Country, Date
Relationships built for one-to-many filtering across all visuals
Data cleaned and transformed using Power Query (handling nulls, multi-value genre/country columns, and inconsistent date formats)
# Key Insights
Netflix's catalog contains 8,808 total titles, spanning content from 750 countries
Movies make up 73.08% of the catalog (6,131 titles), while TV Shows account for 26.92% (2,676 titles)
TV-MA is the most common maturity rating, followed by TV-14 and TV-PG
TV Shows, TV Dramas, and TV Horror rank among the top genres by title count
Title additions grew steadily from 2015 onward, accelerating notably after 2018
Catalog growth peaked around 2018–2019 before tapering off toward 2020
# How to Use
Clone or download this repository
Open Netflix_Analysis_Dashboard.pbix in Power BI Desktop
Refresh the data source connection (if using your own dataset)
Use the Movie/TV Show toggle and year range slider to explore the data interactively
# Repository Structure
├── Netflix_Analysis_Dashboard.pbix
├── Data/
├── Screenshots/
└── README.md
```
```

## 📬 Connect With Me

If you found this project useful or have feedback, feel free to connect or reach out!

- LinkedIn: [linkedin.com/in/veligandlaharinath]
- Email: veligandlaharinath470@gmail.com

⭐ If you like this project, consider giving it a star on GitHub!
