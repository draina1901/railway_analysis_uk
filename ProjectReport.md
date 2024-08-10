#### Goals/objectives (Research Questions)

The UK rail network is a critical component of the country's transportation infrastructure, serving millions of passengers daily and playing a vital role in the nation's economy. However, the system faces numerous challenges, including delays, capacity issues, and customer dissatisfaction. Understanding and addressing these challenges is crucial for improving the overall efficiency and quality of rail services in the UK.

Our research focuses on analyzing train service data to uncover patterns and insights that could lead to significant improvements in rail operations and customer experience. By examining factors such as route performance, delay patterns, pricing strategies, and service frequency, we aim to provide valuable information to rail operators, policymakers, and passengers alike.

The importance of our research lies in its potential to drive meaningful changes in the rail industry. To this end, we have formulated specific research questions and obtained answers through our analysis:

- **How do different routes compare in terms of on-time performance and delay occurrences?**

  We aim to identify which routes experience the most delays and which are the most punctual. This information can help prioritize improvements and resource allocation.

  Answer: We found that the route from the Liverpool Lime Street to London Euston route experiences the highest average delays, while the route from Reading to Liverpool Lime Street and London Paddington to Liverpool Lime Street is the most punctual.

- **How significant are train delays based on the time of day or day of the week?**

  By analyzing delay patterns across different times and days, we can identify periods that are most prone to disruptions, allowing for targeted interventions.
  Answer: We found that delays were most significant during late morning to early afternoon, peaking at 11:00 AM with an average delay of 18.21 minutes

- **How do ticket prices vary across different routes and ticket types (standard vs. advance)?**

  Understanding pricing patterns can reveal insights into demand and pricing strategies, potentially leading to more optimal pricing models.
  Answer: We found that standard tickets are on average 30% cheaper than first class tickets, with the greatest price difference observed on long-distance routes.

- **What is the impact of service frequency on the average delay times of trains?**

  This question explores whether increasing service frequency leads to more delays or improves punctuality, informing capacity management decisions.
  Answer: Our results indicate a slight negative correlation between service frequency and delays, suggesting that very high-frequency services may lead to lower delays.

- **How can operational efficiency be improved based on the analysis of train service data?**

  By synthesizing insights from the above analyses, we aim to identify concrete steps that can be taken to enhance overall rail network performance.
  Answer: We identified several potential improvements, including adjusting timetables during peak delay periods, increasing capacity on high-demand routes, and implementing a more dynamic pricing strategy for advance tickets.

**The answers to these research questions have the potential to make a significant difference in the UK rail industry. They could lead to:**

- Improved punctuality and reliability of train services
- Enhanced customer satisfaction and increased ridership
- More efficient allocation of resources and potential cost savings for rail operators
- Data-driven decision making for infrastructure investments and service improvements
- Better informed passengers who can make more strategic travel choices

In a broader context, a more efficient and reliable rail network could contribute to reducing road congestion and lowering carbon emissions, aligning with the UK's sustainability goals. It could also boost economic productivity by ensuring more predictable commute times and improving connectivity between cities and regions.
By leveraging data analysis to address these critical questions, we aim to contribute to the ongoing efforts to modernize and improve the UK rail network. The insights gained from this research could inform strategies for:

- Targeted infrastructure improvements in problematic routes
- Adjusting staffing levels and maintenance schedules during high-risk periods
- Optimizing pricing strategies to balance revenue and ridership
- Refining capacity management and timetable planning
- Implementing new technologies for real-time delay management

These strategies could ultimately lead to a more reliable, efficient, and customer-friendly rail service, benefiting both the industry and the millions of passengers who rely on train services every day. In the following sections, we will delve deeper into our methodology, present detailed findings, and discuss the implications of our results for the future of rail transport in the UK.

#### Data sources and characteristics

**Dataset**

For this project, we utilized a real-world dataset from Maven Analytics' Data Playground. The dataset can be found at:
https://mavenanalytics.io/data-playground

Specifically, we used the "UK Train Stations" dataset, which provides detailed information about train journeys in the United Kingdom. The dataset includes various attributes such as transaction details, journey information, ticket types, prices, and delay information.
Key attributes in the dataset include:

- Transaction ID
- Date and Time of Purchase
- Purchase Type (Online/Station)
- Payment Method
- Railcard Type
- Ticket Class and Type
- Price
- Departure and Arrival Stations
- Date of Journey
- Scheduled Departure and Arrival Times
- Actual Arrival Time
- Journey Status (On Time/Delayed)
- Reason for Delay (if applicable)
- Refund Request Status

#### Procedures/methods/functions used to clean and transform data

**Methodology**

Our analysis followed these key steps:

**Data Cleaning and Preprocessing:**

- We loaded the dataset using pandas in Python.
- We checked for and removed any duplicate entries.
- We handled missing values by either filling them with appropriate values (e.g., 0 for delays when the train was on time) or dropping rows with critical missing information.
- We converted date and time columns to appropriate datetime formats for easier manipulation.

**Feature Engineering:**

- We created a 'Delay Duration' column by calculating the difference between the actual and scheduled arrival times.
- We extracted 'Day of Week' from the journey date.
- We categorized 'Time of Day' based on the departure time (Night: 10PM-6AM, Morning: 6AM-12PM, Afternoon: 12PM-6PM, Evening: 6PM-10PM).
- We calculated 'Time to Journey' as the difference between the purchase date and journey date.
- We created a Route Column which has routes calculated by Departure and Arrival destination.

**Route Performance Analysis:**

- We grouped the data by departure and arrival stations.
- We calculated average delay times for each route.
- We visualized the results using a bar plot to compare route performances.

**Time-based Delay Analysis:**

- We grouped the data by 'Day of Week' and 'Time of Day'.
- We calculated average delays for each group.
- We created bar plots to visualize delay patterns across different times and days.

**Ticket Price Analysis:**

- We grouped the data by route and ticket type.
- We calculated average prices for each group.
- We created a bar plot to compare prices across routes and ticket types.

**Service Frequency and Delay Correlation:**

- We calculated the service frequency for each route.
- We computed the average delay for each route.
- We created a scatter plot to visualize the relationship between frequency and delays.
- We calculated the correlation coefficient between frequency and average delay.

**Operational Efficiency Analysis:**

- We identified routes and times with the highest delays.
- We analyzed the reasons for delays where available.
- We examined the relationship between ticket types, prices, and delays.

**Statistical Analysis:**

- We performed t-tests to compare delays between different groups (e.g., weekdays vs. weekends, peak vs. off-peak hours).

**Data Visualization:**
We used matplotlib and seaborn libraries in Python to create various visualizations, including:

- Bar plots for route performance and time-based delay analysis
- Scatter plots for frequency vs. delay analysis
- Heat maps for correlation analysis between different variables

**Interpretation and Recommendations:**

Based on the results of our analyses, we interpreted the findings and formulated recommendations for improving operational efficiency, pricing strategies, and overall service quality.

This methodology allowed us to comprehensively analyze the UK train service data, addressing our research questions and uncovering valuable insights for potential improvements in the rail network.

#### Analysis (descriptive or inferential) strategy, results, visualizations, models (if applicable) and conclusions (tie in with your research questions).

Our analysis of the UK train service data yielded several interesting findings. We'll discuss each research question separately, focusing on the most significant results and their implications.

**How do different routes compare in terms of on-time performance and delay occurrences?**

**Results:** We found significant variations in on-time performance across routes. Five routes, including Reading to Liverpool Lime Street and London Paddington to Liverpool Lime Street, showed 100% on-time performance. In contrast, the Liverpool Lime Street to London Euston route had only 19.87% on-time performance, with 780 delayed and 99 cancelled journeys out of 1097 total.

**Interpretation:** The perfect performance of some routes suggests effective management or less complex journeys. The poor performance of others, particularly long-distance routes, indicates systemic issues affecting punctuality.

**Implications:** Focus should be on understanding and replicating the success factors of high-performing routes. For poorly performing routes, a comprehensive review of factors causing delays and cancellations is crucial. This could lead to targeted improvements in infrastructure, scheduling, or operations on these problematic routes

**How significant are train delays based on the time of day or day of the week?**

**Results:** We found that delays were most significant during late morning to early afternoon, peaking at 11:00 AM with an average delay of 18.21 minutes. Wednesday showed the highest average daily delay (3.48 minutes), while Tuesday had the lowest (3.13 minutes). Early morning and late evening hours showed no delays.

**Interpretation:** The midday delay peak is unexpected and could be due to accumulated effects from morning rush hour, scheduled maintenance, or crew changeovers. The minimal variation in delays across weekdays suggests consistent performance throughout the week.

**Implications:** These findings suggest that resources and contingency plans should focus on the 10:00 AM - 1:00 PM period rather than traditional rush hours. The consistency across weekdays indicates that day-specific strategies may be less critical than time-of-day interventions. Investigation into the causes of midday delays could reveal systemic issues that, if addressed, could significantly improve overall punctuality.

**How do ticket prices vary across different routes and ticket types (standard vs. advance)?**

**Results:** Prices vary significantly across routes and classes. The Manchester Piccadilly to London Paddington route is the most expensive (First Class: £173.86, Standard: £107.68), while Birmingham New Street to Wolverhampton is the least expensive (First Class: £5.00, Standard: £1.43). First Class tickets are consistently pricier, with differences ranging from £2.27 to £66.18.

**Interpretation:** Price variations largely reflect journey distance and market segmentation strategies. Shorter routes show smaller absolute price differences between classes.

**Implications:** This pricing allows for customer choice based on budget and comfort. However, the wide price variations suggest potential for demand-based pricing optimization, especially for routes with very high First Class premiums.

**What is the impact of service frequency on the average delay times of trains?**

**Results:** Surprisingly, we found a slight negative correlation (r = -0.02) between service frequency and average delays.

**Interpretation:** This suggests that increasing service frequency may not effectively reduce delays, possibly due to congestion on busy routes, knock-on delays, and infrastructure limitations.

**Implications:** The findings caution against relying solely on frequency increases to improve punctuality. They highlight the need for infrastructure upgrades and advanced scheduling to enhance operational efficiency and reliability.

**How can operational efficiency be improved based on the analysis of train service data?**

**Results:** Based on our comprehensive analysis, we identified several potential areas for improvement:

Adjusting timetables during peak delay periods (afternoon and wednesdays)
Implementing more dynamic pricing strategies for advance tickets
Focusing infrastructure improvements on longer, more delay-prone routes
Reassessing the balance between service frequency and reliability on high-frequency routes

**Interpretation:** These recommendations address the key pain points identified in our analysis: time-based delay patterns, pricing inefficiencies, route-specific performance issues, and the complex relationship between frequency and reliability.

**Implications:** Implementing these changes could lead to improved punctuality, more efficient resource allocation, and potentially increased customer satisfaction. However, it's important to note that these changes would need to be carefully planned and implemented, with continuous monitoring to assess their effectiveness.

In conclusion, our analysis has revealed several key insights into the UK rail network's performance. While some findings, such as the higher delays on longer routes and during peak hours, were expected, others, like the relationship between service frequency and delays, were surprising. These results provide a data-driven foundation for decision-making in the rail industry, potentially leading to significant improvements in service quality and operational efficiency.
