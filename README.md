

<span style="font-family: 'Fira Code', monospace;">

# Google Data Analysis Capstone

## Project Overview

This project utilizes a spreadsheet as the main tool for analysis and visualization. In the conclusion, a slideshow visualization for stakeholders will be provided.

### Preliminary Notes
Before diving into the analysis, please note:
1. This file represents an analysis case study of my approach, with visualizations for stakeholders presented at the end.
2. Due to the large volume of data, the analysis is confined to January 2023 data (19,032 rows).
3. The data, provided by the course, is presumed reliable. In practice, we must avoid for bias and make sure data integrity.

## Step 1: Background Information

Key information includes:
- **Cyclistic**: A bike-share company based in Chicago with a range of bicycles, including accessible options.
- **Users**: Primarily Casual Riders (single-ride or full-day pass users) and Members (annual membership holders).
- **Goal**: To convert Casual Riders into annual Members, enhancing growth and profitability.

## Step 2: Ask

The guiding question for the analysis is:
- How do annual members and casual riders utilize Cyclistic bikes differently?

Note: The focus is on usage patterns, not on the reasons for purchasing memberships.

## Step 3: Prepare

Considerations for the analysis include:
- **User Type**: Distinguishing between Member and Casual users.
- **Trip Duration**: Calculating average ride length for **both** user types, based on start and end times.
- **Day of the Week**: Analyzing weekday usage patterns for both user groups(Exclude weekend).

Limitations: The analysis is constrained by the dataset provided. For instance, ride frequency and location data, which could offer further insights, are not available. In real world, we need conisder those factors, too.

## Step 4: Process

Assuming data reliability(provided by course), we need data cleansing to rectify mismatches, empty cells, and capitalization errors, etc. For example, cleaning the casual_member columns can be done using the formula `=IF(ISBLANK(M2), "unknown", IF(OR(LOWER(M2)="casual", LOWER(M2)="member"), LOWER(M2), "invalid"))`. Additionally, start and end times are reformatted for clarity and ease of analysis.

## Step 5: Analyze

The analysis begins with calculating trip durations and categorizing days of the week into weekdays or weekends. 

#### Trip Duration
The start time is column C and end time is in column D.

I use `=MINUS(D2, C2)` to find trip duration, and apply them to all data, name Trip Duration in column O.

Next, I use `=IF(N2 = "casual", MINUS(D2, C2), "")` to find Trip Duration for Casual Riders, and apply to all data, name Trip Duration(Casual).

And, use `=IF(N2 = "member", MINUS(D2, C2), "")` to find Trip Duration for Member riders, and apply to all data, name Trip Duration(Member).

#### Day of the week

I use `=WEEKDAY(C61872, 1)` to find which days a user ride a bike. 

Next, Exclude Weekend: `=IF(OR(W2=1, W2=7), "weekend", "weekday")`, create a new columns names “Day of week(Exclude weekend)”

Next, Separate Day of the Week for Casual and Member

create a new columns names “Day of Week (Casual)”: `=IF(AND(N2 = "casual", X2 = "weekday"), W2, "")`

create a new columns names “Day of Week (Member)” : `=IF(AND(N2 = "member", X2 = "weekday"), W2, "")`


Now, we have complete calculate data, and we have following columns:
- Member_casual(Cleaned)    
- Trip Duration	
- Trip Duration(Casual)	
- Trip Duration(Member)		
- Day of week	
- Day of week(Exclude weekend)	
- Day of Week(Casual)	
- Day of Week(Member)

### Creating a Pivot Table

A pivot table is created to facilitate data visualization, structured as follows:
- Rows: "Day of Week(Exclude weekend)"
- Columns: User Type("member_casual(Cleaned)")
- Values: "Trip Duration" (sorted by average)
- Filters: "Day of Week(Exclude weekend)" column, and only show “weekday”

## Step 6: Share

Here is the pivot table:

<img src="./Pivot Table.png" width="900" alt="Sample Output"/>

From the pivot table, we can see that 

- Casual riders have an average trip duration of 00:12:52 (12 minutes and 52 seconds).
- Members have an average trip duration of 00:09:59 (9 minutes and 59 seconds).
- The overall average trip duration across both user types is 00:10:37 (10 minutes and 37 seconds).

From the pivot table results, we can conclude the following about the usage of Cyclistic bikes by annual members and casual riders during weekdays in January 2023:

Casual riders have longer average trip durations than members. This could indicate that casual riders may use bikes for leisure activities or less frequent but longer exploratory rides.
Members have shorter average trip durations, which might suggest more routine and possibly utilitarian use of the bikes, such as for commuting or running errands.

Suppose we want to take a further step. In that case, Exploring data for other months can reveal whether these patterns hold throughout the year or are specific to January (which can be affected by weather, holidays, etc.). Repeat steps in this docs.

**Note:** Because github can’t upload files more than 25MB, so i will attach my spreadsheet [here](https://docs.google.com/spreadsheets/d/1l3l_s-4j9nLB470mk7upWz7-7tcDf6BK1gQl8j9GnWE/edit?usp=sharing).


## Step 7: Act

It’s visualization time!

The final step involves presenting the findings to stakeholders. The presentation will be available in both presentation and PDF formats, with links to be added.

presentation mode: click here. [link]
PDF mode: [link]

## End of Analysis


---

## Additional Information

This is the additional information I want to add here, notice this part is **NOT** related to these projects at all. 

The additional info I want to add is a project I did two years ago(a high school English project), and I’m doing a case study similar to this one. We were told to select topics we wanted, write a thesis, use statistics(found on our own) to support our idea and come up with a conclusion. Finally, we need to make slides and present them in class. I just want to show visualization here.

Here is some keys info:

Topics: Social Media Addiction

Question: Why are younger generations addicted with the number of followers and likes?

Thesis: Younger generations are addicted to the number of followers and likes, and they are very addicted to social media.

Some key statistics: [use bullet point below]

- 4.48 billion: Number of people use social media in global world
- 210+ Million: Estimates people suffer from internet and social media addictions worldwide
- 2.42 HR: The time do people spend on social media each day globally for users aged 16 to 64 on any device
- 8.4: The average of a person have social media accounts in worldwide
And some additional  statistics such as gender, age, country.

Conclusion: Social media can be beneficial when used in ways that help build deeper connections between us.  

Unfortunately, social media is quickly becoming one of the strongest forces that divide us. We are drawn into the race for likes, competing with our followers, constantly comparing ourselves to an artificial ideal. We need to be conscious of how we use social media platforms so they can bring us together rather than divide us. 

Getting rid of social media altogether is not the solution. The problem is not social media itself, but rather, the way we use social media.


For more information, please see visualization here:

presentation mode(With Annotation): click [here](https://docs.google.com/presentation/d/19scMWq0w5aBeYoFG-gapRXX_Neu_7yTJhUW0zRGNM-o/edit?usp=sharing).

PDF mode(Quick view): <a href="./Additional_Info/Social Media Addiction.pdf" download>Download the file</a>



</span>