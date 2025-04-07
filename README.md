# NYC Green Taxi Analysis: Exploratory Data Analysis (January 2023)

## Project Overview
This capstone project focuses on performing an **Exploratory Data Analysis (EDA)** of NYC Green Taxi trip data for January 2023. The goal is to uncover patterns, trends, and insights into taxi usage, including temporal and spatial distributions, fare structures, trip durations, and the impact of external factors like weather. The analysis is presented through a combination of Python-based visualizations and a comprehensive, interactive Tableau dashboard.

### Objectives
- Analyze the temporal patterns of taxi trips (e.g., peak hours, days of the week).
- Explore spatial distributions of pickups and dropoffs across NYC boroughs.
- Investigate relationships between trip distance, fare amount, and tip behavior.

## Dataset
The dataset used in this project contains NYC Green Taxi trip records for January 2023. It includes detailed information about each trip, such as pickup and dropoff times, locations, distances, fares, and weather conditions.

### Data Source
- **Source**: The dataset is a sample of NYC Green Taxi trip data, likely derived from the NYC Taxi & Limousine Commission (TLC) public data, augmented with geopandas and weather information.
    - [NYC Green Taxi January Data (PARQUET)](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
    - [NYC Taxi Zone Lookup](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
    - [Weather Data](https://www.ncei.noaa.gov/cdo-web/datatools/findstation)
- **Time Period**: January 1, 2023, to January 31, 2023.
- **File Format**: CSV (`NYC TLC Trip Record.csv`).

### **Description of the dataset**
| Column Name         |Description  | API Field Name | Data Type |
|:-------------------:|:------------|:--------------:|:---------:|
|VendorID|A code indicating the TPEP provider that provided the record.|vendorid|Number|
|lpep_pickup_datetime|The date and time when the meter was engaged.|lpep_pickup_datetime|Floating Timestamp|
|lpep_dropoff_datetime|The date and time when the meter was disengaged.|lpep_dropoff_datetime|Floating Timestamp|
|store_and_fwd_flag|This flag indicates whether the trip record was held in vehicle before sending to the vendor, aka "store and forward", because the vehicle did not have a connection to the server.|store_and_fwd_flag|Text|
|RatecodeID|The final rate code in effect at the end of the trip.|ratecodeid|Number|
|PULocationID|TLC Taxi Zone in which the taximeter was engaged.|pulocationid|Number|
|DOLocationID|TLC Taxi Zone in which the taximeter was disengaged.|dolocationid|Number|
|passenger_count|The number of passengers in the vehicle.|passenger_count|Number|
|trip_distance|The elapsed trip distancen in miles reported by the taximeter.|trip_distance|Number|
|fare_amount|The time-and-distance fare calculated by the meter. For additional information on the following columns.|fare_amount|Number|
|extra|Miscellaneous extras and surcharges.|extra|Number|
|mta_tax|Tax that is automatically triggered based on the metered rate in use.|mta_tax|Number|
|tip_amount|This field is automatically populated for credit card tips. Cash tips are not included.|tip_amount|Number|
|tolls_amount|Total amount of all tolls paid in trip.|tolls_amount|Number|
|ehail_fee|*Currently unused*|ehail_fee|Text|
|improvement_surcharge|Improvement surcharge assessed trips at the flag drop.|improvement_surcharge|Number|
|total_amount|The total amount charged to passengers. Does not include cash tips.|total_amount|Number|
|payment_type|A numeric code signifying how the passenger paid for the trip.|payment_type|Number|
|trip_type|A code indicating whether the trip was a street-hail or a dispatch that is automatically assigned based on the metered rate in use but can be altered by the driver.|trip_type|Number|
|congestion_surcharge|Total amount collected in trip for NYS congestion surcharge.|congestion_surcharge|Number|

### Data Preprocessing
- Removed rows with missing values in critical columns (`'store_and_fwd_flag', 'RatecodeID', 'passenger_count', 'payment_type', 'trip_type', 'congestion_surcharge'`).
- Converted `lpep_pickup_datetime` and `lpep_dropoff_datetime` to datetime format for temporal analysis.
- Created derived fields like `speed_mph` and `fare_per_mile` for analysis support.

## Tools and Technologies
- **Python**: Used for initial EDA and creating out-of-the-ordinary visualizations.
- **Tableau**: Used to build a comprehensive and dynamic dashboard for interactive analysis.
- **Environment**: Jupyter Notebook for Python analysis, Tableau Desktop for dashboard creation.


## Setup and Installation

### Prerequisites
- **Python 3.8+**: For running the EDA notebook.
- **Tableau Desktop**: For viewing and interacting with the dashboard (version 2023.1 or later recommended).
- **Libraries**:
    ```
    numpy
    pandas
    geopandas
    matplotlib
    seaborn
    contextily
    jupyter
    ```

## Links
- **GitHub Repository**: [Click here.](https://github.com/alexandrandraa/NYC-Green-Taxi-Jan-2023/tree/main)
- **Tableau Public Dashboard**: [Click here.](https://public.tableau.com/views/Dashboard_17440419888870/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
- **Presentation**: [Click here.](https://www.canva.com/design/DAGjxLZ3lps/4saCPo9V68YQRQ9hCawPWg/edit?utm_content=DAGjxLZ3lps&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)