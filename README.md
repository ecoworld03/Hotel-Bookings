# Hotel-Bookings
## Hotel Booking Report
### Introduction
This project focuses on analyzing hotel booking data to uncover key performance indicators (KPIs) and insights that can guide decision-making. The dataset contains booking details for both resort and city hotels, including information about cancellations, revenue, distribution channels, customer segments, and other relevant attributes.
  The aim is to develop a Power BI dashboard that provides hotel management with an interactive and insightful view of their business performance, highlighting trends, problem areas, and opportunities for revenue growth.

### Data Source
- File name: hotel bookings.xlsx
- Number of records: 50,000 rows
- Columns: 15 (hotel type, booking status, lead time, meal type, country, distribution channel, deposit type, charges, reservation date, etc.)
- Source type: Excel file provided by hotel management.
- Time period covered: Dates range across multiple years based on reservation status dates.

[hotel bookings.xlsx](https://github.com/user-attachments/files/22084420/hotel.bookings.xlsx)

### Objectives
- Identify and track key hotel performance metrics (e.g., revenue, cancellation rate, occupancy performance).
- Understand customer booking behavior, including lead time, repeat guests, and preferred distribution channels.
- Detect patterns in cancellations and evaluate the impact of deposit types and booking channels.
- Visualize geographical booking trends (countries of origin).
- Develop actionable recommendations to improve revenue and reduce cancellations.

### Technical Skills Used in Project
- Data Analysis & Cleaning: Microsoft Excel, Power BI Query Editor
- Data Transformation: Power Query (M Language)
- Data Modeling: Power BI relationships, calculated columns, DAX measures
- Visualization: Power BI interactive dashboard (cards, slicers, bar charts, line charts, Donot charts, matrices)
- Business Intelligence Concepts: KPI tracking, performance benchmarking, trend analysis

### Data Cleaning / Transformation / Modelling
Steps performed:
1. Column removal: Dropped irrelevant columns (Unnamed: 12, Unnamed: 13, and hotel.1).
2. Missing values: Filled missing 'country' values with 'Unknown'.
3. Duplicate check: Verified no duplicate records using Power BI’s “Remove Duplicates.”
4. Data standardization: Trimmed and cleaned text fields such as meal, distribution_channel, and deposit_type.
5. Date extraction: Created calculated columns for Booking Year and Booking Month.
6. DAX measures for KPIs:
   - Total Bookings = COUNTROWS('Table')
   - Canceled Bookings = CALCULATE(COUNTROWS('Table'), 'Table'[is_canceled]=1)
   - Cancellation Rate (%) = DIVIDE([Canceled Bookings], [Total Bookings], 0) * 100
   - Total Revenue = SUM('Table'[Charge])
   - Avg Lead Time = AVERAGE('Table'[lead_time])
   - Repeat Guest % = DIVIDE(CALCULATE(COUNTROWS('Table'), 'Table'[is_repeated_guest]=1), [Total Bookings], 0) * 100

![Table View](https://github.com/user-attachments/assets/8560e8f4-c64a-4bfd-9916-8d6245a1beaa)

![Model view](https://github.com/user-attachments/assets/6f4a8ebc-b2b5-48f5-b5e2-71f0b7cf1617)

### Data Analysis / Visualization
Key visualizations included in Power BI:
- KPI Cards: Total Bookings, Total Revenue, Total Revenue, Cancellation Rate %
- Line Chart: Monthly bookings and cancellations trend over time
- Bar Chart: Revenue and bookings by distribution channel
- Donot Chart: Share of meal types and deposit types
- Matrix: Monthly Bookings by Year
- Filters (Slicers): Hotel type, Yea, Country, Room Type

![Hotel Bookings Report Dashboard](https://github.com/user-attachments/assets/bb1d98b5-93ef-4d7a-b3c8-d17fff9d88ea)

### Interpretation / Insights
- Cancellation Trends: A significant percentage of bookings are canceled, particularly for specific distribution channels and non-refundable deposit types.
- Revenue Concentration: Certain booking channels (e.g., TA/TO) generate higher revenue but also have a higher cancellation rate.
- Geographic Patterns: Majority of bookings come from a few countries; targeting marketing efforts here could yield quick wins.
- Lead Time Behavior: Longer lead times may be correlated with higher cancellations, indicating a need for stricter policies for early bookings.
- Repeat Guest Loyalty: Repeat guests make up a smaller portion of total bookings but tend to have a lower cancellation rate.
- Room Allocation Issues: Some mismatches between reserved and assigned room types may indicate overbooking or operational inefficiencies.

### Conclusion / Recommendations
Conclusion:
The Power BI dashboard provides a comprehensive view of hotel performance, tracking revenue, cancellations, guest profiles, and booking patterns. By using interactive filters, management can drill down to specific countries, channels, or hotel types to make data-driven decisions.

Recommendations:
1. Reduce Cancellations: Introduce stricter deposit policies or offer flexible rates only for trusted channels.
2. Target High-Value Markets: Focus marketing campaigns on countries and channels with strong revenue contribution.
3. Strengthen Loyalty Programs: Encourage repeat guests with special offers, as they have more reliable booking behavior.
4. Optimize Room Allocation: Monitor differences between reserved and assigned room types to improve operational efficiency.
5. Lead Time Strategy: Consider dynamic pricing or cancellation policies for very early bookings to minimize losses.

