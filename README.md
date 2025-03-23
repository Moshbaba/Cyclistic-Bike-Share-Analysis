# Cyclistic-Bike-Share-Analysis
A data analytics capstone project analyzing Cyclistic bike-share user trends using Excel and Tableau. 

# Cyclistic Bike-Share Analysis Overview

## 1. Business Task (ASK Phase)
This analysis follows the Ask, Prepare, Process, Analyze, Share, and Act phases of the Google Data Analytics framework.

### Objective
Cyclistic, a bike-share company, wants to increase revenue by converting casual riders into annual members. The analysis aims to answer:

- **How do annual members and casual riders use Cyclistic bikes differently?**
- **Why would casual riders buy Cyclistic annual memberships?**
- **How can Cyclistic use digital media to influence casual riders to become members?**

The insights from this analysis will help guide targeted marketing strategies to drive membership growth.

## 2. Data Sources (PREPARE Phase)
The dataset is sourced from **[Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html)** and contains 12 months of historical ride data from **March 4, 2024, to February 5, 2025**. The specific dataset files range from `202402-divvy-tripdata.zip` to `202501-divvy-tripdata.zip`.

### Data Fields:
- `ride_id` – Unique trip identifier.
- `rideable_type` – Type of bike used (e.g., classic, electric).
- `started_at` / `ended_at` – Timestamps for trip start and end.
- `start_station_name` / `start_station_id` – Starting station details.
- `end_station_name` / `end_station_id` – Ending station details.
- `start_lat` / `start_lng` – Start location coordinates.
- `end_lat` / `end_lng` – End location coordinates.
- `member_casual` – User type (casual vs. annual member).

## 3. Data Cleaning & Processing (PROCESS Phase)

### Steps Taken:
- Merged all 12 months of data into a single dataset.
- Checked for and removed null and duplicate values to ensure data consistency.
- Dropped unnecessary columns that were not relevant to the analysis:
  - `ride_id`
  - `start_station_name`, `start_station_id`, `end_station_name`, `end_station_id`
  - `start_lat`, `start_lng`, `end_lat`, `end_lng`

### Extracted Time-Based Insights:
Created new columns from `started_at`:
- **Month** – To analyze seasonal trends.
- **Day** – To compare weekday vs. weekend usage.
- **Hour** – To identify peak riding hours.

### Ride Duration Calculation:
- `Ride_time = ((ended_at - started_at) * 24 * 60)` → Converted to decimal format for accuracy.

### Ride Duration Categorization:
- **Under 10 minutes**
- **10 to 30 minutes**
- **30 to 60 minutes**
- **Over 60 minutes**

Replaced `ride_time` with a new categorical column (`custom`), then removed `started_at` and `ended_at`.

### Final Dataset Includes:
- `rideable_type` – Type of bike used.
- `member_casual` – User type (casual vs. member).
- `month` – Ride distribution across months.
- `day` – Weekday vs. weekend usage patterns.
- `hour` – Peak ride hours.
- `custom` – Categorized ride durations.
- `count` – Number of rides in each category.

### Tools Used:
- **Excel (Power Query) for data cleaning, transformation, and aggregation.**
- **Tableau Public for data visualization.**

## 4. Data Analysis (ANALYZE Phase)

The cleaned dataset was analyzed to identify key trends in user behavior, ride frequency, and trip duration.

### User Trends & Ride Patterns:
- **User Type Distribution:** Annual members take more rides compared to casual users, indicating a strong base of frequent riders.
- **Bike Type Preference:** Classic bikes are the most commonly used, followed by electric bikes. Scooters have significantly lower usage.
- **Daily Ride Patterns:** Ride activity is highest on Saturdays, suggesting that casual riders contribute heavily to weekend usage.
- **Hourly Ride Trends:** Peak ride time is **5:00 PM (17:00)**, likely coinciding with evening commutes.

### Seasonal & Duration-Based Insights:
- **Monthly Ride Trends:** Ride activity peaks during summer (June to September) and drops significantly in winter.
- **Ride Duration Distribution:** Most rides are under 10 minutes, suggesting short, frequent trips.
- **User Type Behavior Over Time:**
  - Members ride consistently throughout the year.
  - Casual users ride more frequently in summer, possibly due to tourism or recreational cycling.
- **Ride Duration Comparison by User Type:** Casual users tend to take longer rides compared to members, reinforcing that they use the service more for leisure than commuting.

## 5. Visualizations & Insights (SHARE Phase)

The following interactive visualizations were created in **[Tableau Public](https://public.tableau.com/views/MoshoodsCapstoneProject/CapstoneProject?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link):**

### Key Visualizations:
- **Pie Chart:** Ride distribution by user type (members vs. casual riders).
- **Bar Chart:** Total rides by day of the week (Sunday to Saturday).
- **Bar Chart:** Most popular bike types (classic bike, electric bike, scooter).
- **Bar Chart:** Ride duration breakdown by user type (under 10 min, 10–30 min, 30–60 min, over 60 min).
- **Line Chart:** Ride frequency by the hour of the day (0 to 24 hours).
- **Line Chart:** Monthly ride trends across all users (12 months).
- **Line Chart:** Monthly ride trends split by user type (members vs. casual riders over 12 months).

### Key Takeaways:
- Casual riders take longer rides and prefer weekends, indicating they use the service more for leisure or tourism.
- Members take shorter trips but ride more frequently, suggesting they use the service primarily for commuting.
- Marketing efforts should focus on casual riders by highlighting membership benefits tailored to their riding habits.

## 6. Recommendations (ACT Phase)

Based on the analysis, here are key recommendations to help Cyclistic convert casual riders into annual members:

- **Offer Weekend Membership Plans**
  - Casual riders use bikes more on weekends. Cyclistic can introduce a weekend-only membership at a lower price.
- **Promote Membership Benefits for Longer Rides**
  - Since casual riders take longer trips, Cyclistic can highlight discounts on extended rides to encourage sign-ups.
- **Target Digital Ads to Casual Riders**
  - Use social media and email marketing to promote membership perks, focusing on casual users who ride often in summer and on weekends.
- **Introduce a Seasonal Membership Option**
  - Many casual riders use bikes mainly in summer. A 3-month or summer-only membership can help convert them into paying members.
- **Improve Bike Availability at Popular Times**
  - Since peak usage happens at **5 PM and on Saturdays**, ensure enough bikes are available at key locations.

These recommendations focus on casual rider habits and use targeted marketing to increase membership conversions.


