# Hotel-Revenue-Analysis-Dashboard

## Overview

AtliQ Grands, a chain of five-star luxury and business hotels across India, has been a prominent player in the hospitality industry for the past 20 years. However, due to increased competition and ineffective decision-making, the company has been losing its market share and revenue. To combat this, the management decided to incorporate "Business and Data Intelligence" into their operations. As they lacked an in-house data analytics team, they outsourced this critical task to a third-party service provider. This project represents the efforts to regain market share and revenue by leveraging data analytics.

This project involves analyzing historical booking data to derive key insights and metrics that can assist AtliQ Grands in making informed decisions.

## Project Steps

### 1. **Data Connection**
   - Connected to the provided data sources using Power BI.

### 2. **Data Transformation**
   - Utilized Power Query to clean and transform the data, which included:
     - Removing invalid or irrelevant data.
     - Creating new columns to better structure the dataset for analysis.

### 3. **DAX Calculations**
   - Created calculated columns and measures to derive essential metrics. Some of the key metrics created include:
     - **Revenue**: The total revenue realized.
     - **Total Bookings**: The count of all bookings made.
     - **Total Capacity**: The total room capacity across all hotels.
     - **Occupancy %**: The percentage of successfully booked rooms relative to the total capacity.
     - **ADR (Average Daily Rate)**: The average revenue generated per room booked.
     - **RevPAR (Revenue Per Available Room)**: The revenue generated per available room.
     - **Cancellation %**: The percentage of bookings that were canceled.
     - **Realization %**: The percentage of successful 'checked out' bookings over all bookings.
     - **WoW Change Metrics**: Week-over-week changes in key metrics like revenue, occupancy, ADR, RevPAR, and realization percentage.

### 4. **Dashboard Development**
   - Built an interactive and insightful dashboard following the mock-up provided by stakeholders.
   - The dashboard includes various visualizations and metrics that offer a comprehensive view of the hotel's performance.

### 5. **Insight Generation**
   - Derived additional insights not provided in the metric list or mock-up, highlighting critical areas for improvement and opportunities for growth.

### 6. **Presentation**
   - Prepared the dashboard and insights in a format that is easily understandable and actionable for the stakeholders.

## Dataset

The project utilizes five datasets containing meta information about the bookings, hotels, rooms, and dates:

1. **dim_date.csv**
   - Columns: `date`, `mmm yy`, `week no`, `day_type`
   - Describes dates, weeks, and whether a day is a weekend or weekday.

2. **dim_hotels.csv**
   - Columns: `property_id`, `property_name`, `category`, `city`
   - Provides details about the hotels, including ID, name, category (luxury/business), and city location.

3. **dim_rooms.csv**
   - Columns: `room_id`, `room_class`
   - Information about room types and their respective classes (Standard, Elite, Premium, Presidential).

4. **fact_aggregated_bookings.csv**
   - Columns: `property_id`, `check_in_date`, `room_category`, `successful_bookings`, `capacity`
   - Contains aggregated booking data, including successful bookings and room capacity per hotel.

5. **fact_bookings.csv**
   - Columns: `booking_id`, `property_id`, `booking_date`, `check_in_date`, `check_out_date`, `no_guests`, `room_category`, `booking_platform`, `ratings_given`, `booking_status`, `revenue_generated`, `revenue_realized`
   - Detailed information on individual bookings, including booking status, revenue generated, and customer ratings.

## Key Metrics and Calculations

Below is a summary of some key metrics created for this project:

- **Revenue**: `Revenue = SUM(fact_bookings[revenue_realized])`
- **Total Bookings**: `Total Bookings = COUNT(fact_bookings[booking_id])`
- **Occupancy %**: `Occupancy % = DIVIDE([Total Succesful Bookings],[Total Capacity],0)`
- **ADR (Average Daily Rate)**: `ADR = DIVIDE([Revenue], [Total Bookings],0)`
- **RevPAR (Revenue Per Available Room)**: `RevPAR = DIVIDE([Revenue],[Total Capacity])`
- **Cancellation %**: `Cancellation % = DIVIDE([Total cancelled bookings],[Total Bookings])`
- **Realization %**: `Realization % = 1 - ([Cancellation %] + [No Show rate %])`
- **Week-over-Week Change Metrics**: Calculated using dynamic DAX formulas to capture trends over time.

## Conclusion

This project provided AtliQ Grands with a data-driven approach to understanding their business performance. By analyzing and visualizing key metrics, the revenue management team now has actionable insights to help make strategic decisions aimed at regaining market share and boosting revenue.

## Future Enhancements

Potential improvements and extensions of this project could include:

- Incorporating predictive analytics to forecast future booking trends.
- Expanding the dataset to include more extensive historical data.
- Integrating external data sources such as competitor pricing or customer sentiment analysis from reviews.
