# Cyclistic Bike-Share Analytics: Uncovering Rider Behaviors


## Recap from last time

Before, we analyzed this project by using a spreadsheet. But spreadsheets can't handle massive amounts of data, so we only analyzed data for one month(Jan 2023). This time, we will analyze the whole 2023 year data by using Python and visualization. Although the marketing director wants to convert Casual Riders into annual Members, enhancing growth and profitability, this differs from the question document assigned to us. So, we will keep exploring the same question from last time: **"How do annual members and casual riders utilize Cyclistic bikes differently?"**

## Projects Overview

Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## Background Information

Key information includes:

- **Cyclistic:** A bike-share company based in Chicago with a range of bicycles, including accessible options.
- **Users:** Primarily Casual Riders (single-ride or full-day pass users) and Members (annual membership holders).
- **Goal:** To convert Casual Riders into annual Members, enhancing growth and profitability.

## Data set

Since the data set was too large, I can't upload it to Git Hub. The dataset includes the whole year of original data in 2023 and a file after analysis. You can find the file [here](https://drive.google.com/drive/folders/1_oDLDfeTE8aVMESDThhDMCS1X_qLhkGZ?usp=drive_link).


## Step Approach

Here, I will show the details of all steps and explain what each step is doing and how to finish this. Inside the file, you will see a short step overview.

To complete this analysis, note that this step differs from the seven steps taught in the Google course, and I follow those on spreadsheet analysis. In bachizan, five steps was given. Overall, they are in the same structure.


### Step 1: Ask a question

In this step, we must ask ourselves what we want to know from our analysis. This is a crucial step, the step we begin our data analysis. 

This analysis will explore this question: **"How do annual members and casual riders utilize Cyclistic bikes differently?"**


### Step 2: Data Collection

Since Google provided data, we can skip this step. 

We have multiple ways to collect data: questionnaires, online surveys, internal/external sources, third-party sources, web crawlers, etc.


### Step 3: Data Process and Cleaning

After we collect our data, we need to clean our data. Why do we need clean data? Because some values are not absolute, some values are missing, etc. If we don't do data cleaning, this will cause incorrect or biased results for analysis. 

#### Data Overview

First, we need an overall look for data. What does it look like? How many columns does it have？ It's important to know data structure. We can do that by using the info() function.

#### Data Cleaning

To clean data, I will follow the steps IN ORDER:

##### Missing Value

After we use info() to check data, we need to examine if the data has missing values. If we do, we can consider the following:

1. Delete them. If the missing value is only a small portion, we can just consider deleting them.
2. Fill them. If the columns were unimportant for analysis, we could fill in the missing value by filing in some value, such as "unknown."
3. If we have too many missing values, we must consider re-collecting them. The data we have cannot be regarded as reliable anymore. 

##### Outliers

After checking for missing values, the next thing is to check outliers. Outliers refer to unreasonable values in the data. This limited value usually requires one's judgment on the data set to obtain it.

For this case study, here are some examples of outliers:

1. The company only has two types of users: casual and member. If other value found beside this, that's an outlier.
2. The company only has three types of bikes: electric, classic, and docked. If other value found beside this, that's an outlier.
3. Start and end time. Please note that the end time must be greater than the start time. If the start time exceeds the end time, that's an outlier.
4. Trip Duration. We found trip duration by subtracting from end time to start time. If a trip duration is too short(ex 1 sec) and too large(ex, more than 12 hours), the data is an outlier in this case. 

Check data outliers don't have standard answers/functions; it all depends on the data and scenario we are working on.

##### Duplicated

After we check outliers, we need to ensure the data doesn't contain duplicates. This part is easy to understand. 

After data cleaning, we can move on to the next steps.

### Step 4: Data analysis

This part is an analysis part, and it depends on our question. In this case study, I analyze user Proportion, rideable type Proportion, Trip Duration, separated by casual and member, and day of the week, separated by weekdays and weekends.


### Step 5: Data Visualization and Conclusion

The last step is to use the data we analyze, Visualize the data, and come to a conclusion. 

Below are the conclusion and suggestions for analyzing the data.




## Overall Conclusion & Suggestion

Based on the visualization, we can synthesize the results to answer the question of how annual members and recreational riders use their bikes differently:

1. **Proportion of Rides by User Type:** Members make up a larger proportion of the rides compared to casual users. This suggests that members are the more consistent user group, potentially using the service for regular commutes or as a part of their daily routine.
2. **Proportion of Rides by Rideable Type:** Both electric and classic bikes are used nearly equally by the overall user base, but docked bikes are used much less. This might indicate a preference for versatility and convenience, as electric and classic bikes may offer more flexibility in terms of parking and availability.
3. **Proportion of Casual and Member Users for Each Rideable Type:** Classic bikes and eletric bikes are popular with both types of users. No member users use docked bikes, which may be due to poor convenience or availability.
4. **Average Trip Duration:** Casual users have longer trip durations than member users, suggesting that casual users may be using the service more for leisure or exploration, while member users might be using the bikes for more purposeful and routine trips, such as commuting.
5. **Average Ride Time by User Type and Month:** There is a seasonal trend visible, with ride times generally longer in warmer months, indicating possible weather-related influence on bike usage. Casual users consistently spend more time per ride than members throughout the year.
6. **Ride Counts: Weekday vs Weekend:** There are more rides during weekdays compared to weekends. This could be due to the use of bikes for commuting on weekdays. The difference in the number of rides between casual and member users is much greater on weekdays than on weekends.
7. **Ride Counts by User Type on Weekdays:** Members use the service more than casual users on all weekdays, suggesting a strong habit or need for the service during the workweek, likely for commuting.
8. **Ride Counts on Weekends:** During weekends, the number of rides by casual and member users is more comparable, indicating that members and casual users alike use the service for leisure or non-commuting activities.

From these insights, we can conclude that annual members are likely relying on the bike-sharing service as a regular means of transportation, possibly integrated into their daily routines, particularly on weekdays for commuting. In contrast, casual riders seem to use the service more recreationally, indicated by longer trip durations and a slightly higher proportion of weekend use compared to members.

These patterns can inform Cyclistic’s operational and marketing strategies, suggesting a focus on reliability and quick service for members, especially on weekdays, and potentially more targeted marketing towards casual users to convert them into members by emphasizing the benefits of membership for frequent riders. Moreover, promotional activities could be designed to increase casual user engagement during weekdays and to encourage member usage during weekends, potentially through events or special weekend offers.

---
