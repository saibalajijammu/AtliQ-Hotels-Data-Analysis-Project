Project Goal
This project aims to leverage booking and operational data from AtliQ Hotels across major Indian cities to derive actionable insights related to occupancy rates, revenue realized, and booking platform performance. The primary objective is to identify data-driven opportunities for increasing revenue and optimizing resource management.

📁 Datasets
The analysis utilizes five interconnected datasets:
fact_bookings.csv (Detailed booking transactions)
fact_aggregated_bookings.csv (Daily room capacity and successful bookings)
dim_hotels.csv (Property dimensions: city, category)
dim_rooms.csv (Room dimensions: room category, room class)
dim_date.csv (Date dimensions: week/day type)

🛠️ Tools and Libraries
Language: Python
Libraries: Pandas, NumPy, Matplotlib
Environment: Jupyter Notebook / VS Code⚙️ 

Methodology and Analysis
The project followed a standard data analysis pipeline, with a strong focus on data quality and feature engineering:
1. Data Cleaning and ValidationRigorous data cleaning was performed on the raw booking data to ensure accurate key performance indicators (KPIs).
Invalid Guest Removal: Filtered out records where no_guests was less than or equal to zero.
Outlier Detection (Revenue): Applied the 3-Standard Deviation Rule to the revenue_generated column to identify and remove extreme outliers. This step was crucial for stabilizing financial metrics.
Capacity Validation: Cleaned the aggregate bookings data by handling missing capacity values (imputing the median) and filtering out records where successful_bookings exceeded capacity.

2. Data Transformation and Merging
Feature Engineering: Created the key metric, occ_pct (Occupancy Percentage), by calculating successful_bookings / capacity and converting it to a rounded percentage.
Data Integration: Performed multiple merges using common keys (property_id, room_category, check_in_date) to consolidate all transactional and dimensional data into a single master DataFrame for analysis.

3. Key Performance Insights (KPIs)
The final analysis delivered the following insights:
PerformanceWeekend average occupancy (72.34%) significantly exceeds weekday average occupancy (50.88%).
Top Revenue CityMumbai generated the highest total realized revenue.
Top Occupancy CityDelhi holds the highest average occupancy rate (61.51%).
Room Class PerformanceThe most premium category, Presidential (RT4), achieved the highest average occupancy rate (59.28%).
Platform RevenueA pie chart was generated to show the distribution of revenue across various booking platforms (e.g., others, makeyourtrip, logtrip, direct online).