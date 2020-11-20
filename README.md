# Module One Kickstarter Challenge


# Overview of Project
The purpose of this analysis is to provide a detailed breakdown of how different campaigns fared in relation to their launch dates and their funding goals. Specifically, we will provide recommendations on the ideal time to launch a campaign, and how much money the campaign should seek to raise, while still successfully meeting or exceeding its funding goals. We will specifically be focusing on campaigns in the "plays" subcategory on Kickstarter. At the end of this analysis, an individual seeking to launch a Kickstarter campaign to fund a play will have the information they need to maximize their campaign's chances of being funded.


# Analysis and Challenges
This section explains how the analysis was performed, and details any challenges encountered. It is divided between the main variables we are looking at: 

1. How the launch date for the campaign affects the campaign outcome.
2. How the goal amount affects the campaign outcome. 

## Theater Outcomes by Launch Date

### Analysis

For the first part of our analysis, we looked at the success of campaigns in the "Theater" category, based on the month they were launched in. To do this, we created a pivot table from the raw data. We applied the filters "Parent Category" and "Years", set the columns to show the outcome (successful, failed, or canceled), set the rows to show the date the campaign was created, and the values to the number in each outcome category. Using the filters, we set the table to show only campaigns that had "Theater" as their primary category. We also grouped the dates by month, removing the year and quarter distinctions. Once the pivot table was filtered, we generated the below line graph. 

![Theater Outcomes vs Launch](https://github.com/jbalooshie/Kickstarter-Data/blob/main/Theater_Outcomes_vs_Launch.png)

### Challenges

The main challenge here was determining how to set the rows to just show the months. For date categories, the version of excel being used automatically added fields for "Quarters" and "Years". Once these were removed only months were shows.

## Outcomes Based on Goals

### Analysis 

For the second part of our analysis, we looked at the percentage of successful campaigns in the "Plays" subcategory, based on their fundraising goals. First, we created 12 different dollar amount ranges between $0-50,000 (<$1000, $1000 - $4999, $5,000 - $9,999, etc.). We then used the COUNTIF function to count the number of successful, failed, and canceled campaigns within each range. Here is the formula used to determine the number of successful campaigns in the $1000 - $4999 band:

`=COUNTIFS(Kickstarter!$D:$D,">=1000", Kickstarter!$D:$D,"<=4999",Kickstarter!$F:$F,"Successful",Kickstarter!$P:$P,"Plays")`

This was done for reach fundraising range and outcome. We then totaled the number of campaigns in each range. From the total, we then calculated the percentage of each outcome within each fundraising range. Using those percentages, we created the following line chart:

![Outcomes vs Goals](https://github.com/jbalooshie/Kickstarter-Data/blob/main/Outcomes_vs_Goals.png)

### Challenges

For this section, the main challenge was a typo in one of the ranges. Instead of creating two separate ranges: $30000 - $34999 and $35000 - $39999, one range was created combining the two: $30000 - $39999. This resulted in the line chart not matching the example provided. Once this range was fixed and the formulas updated, the chart matched the example.



# Results
Based on the analysis above, here are conclusions we can draw from this data. 

1. What are two conclusions you can draw about the Theater Outcomes by Launch Date?
  - The highest amount of successful campaigns occurs between the months of May - August. May has the highest amount of successful campaigns. 
  - The month with the smallest amount of successful campaigns is December. 
  - If you are seeking to launch a campaign, try to plan to launch it May, June, or July. Avoid launching it in December. 
  
2. What can you conclude about the Outcomes based on Goals?
  - If your play does not need substantial funding, you should set your fundraising goal at less than $4999. 73% of campaigns that ask for less than $4999 are successful. If you ask for less than $1000, then the percentage of successful campaigns increases to 76%. If you need a larger sum of money for your production, then the next "sweet spot" is between $35000 - $44999. Campaigns in this fundraising band were successful 67% of the time. Going beyond  $44999 is not recommended. Out of the 13 campaigns analyzed above than band, only 2 met their fundraising goals. 
  
3. What are some limitations of this dataset?
  - The dataset provided only covers Kickstarter campaigns between the year 2009 - 2017. The analysis and conclusions presented here are not applicable to a campaign launched being launched in 2020 or 2021, due to the global pandemic. It does offer interesting insights into trends prior to the pandemic. However, it is difficult to say if any of these conclusions will be true for the upcoming years. Tastes and behaviors on the platform might changes as a result of the pandemic. 

4. What are some other possible tables and/or graphs that we could create?
  - For further analysis, we could investigate if there is any correlation between the length of the campaign and the success rate. This could provide insight into the ideal campaign length, to go along with the ideal time to launch the campaign. We could set this up similar to how we determined the outcomes based on the goal amount. We can create bands for certain periods of time, I.E. 0-15 days, 16-30, 31-45, 45+. We can then use a COUNTIF function to count the number of successful and failed campaigns in each band, and caluclate the percentages for each. From there we can create a line graph and see if there are any obvious trends. 
