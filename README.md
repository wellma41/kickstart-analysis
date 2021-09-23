# Kickstarting Challenge

## Overview of Project 
	We analyzed theater and play Kickstarter outcome trends based on launch date and donation goals respectively.

###Purpose 
	This project had two components, theater outcomes by launch date and play outcomes by donation goal. First, the purpose of the launch date analysis was to plot the outcome status of theater Kickstarters over the month the campaign was launched. Second, was a plot of the outcome of "play" Kickstarter campaigns over donation goals broken up in to 12 ranges with intervals of 5,000 dollars spanning from less than 1,000 to over 50,000.

##Analysis

### Theater Outcomes Based on Launch Date
	-First I populated a column using the =YEAR() function to pull the year from each date on the launch date column.
	-Then I created a pivot table using outcomes for the columns, date created for the rows, and count of outcomes for the values. I filtered the table by the theater parent category.
	-Last I produced a chart of the resulting table with count of outcomes on the y axis and months on the x axis.
![Outcomes Based on Launch Date Chart](https://user-images.githubusercontent.com/90660790/134459803-a3358019-a66e-40d9-9629-3a3ff518ccdb.png)

### Outcomes Based on Goals
	-I created a new worksheet
	-Then I made a column containing starting with less than 1,000, increasing with intervals of 5,000, and ending with greater than 50,000.
	- Afterwards I used the =COUNTIFS() function to count the number of plays within a donation goal range based on outcome (successful, failed, canceled).
	- A total projects column was created and populated with the SUM() function for each donation goal range.
	- Using this total projects column I was able to create percentages for each donation category by dividing the number in a cell populated with the COUNTIFS function by its corresponding total projects value.
	- Finally I made a chart with these percentages one the y axis with the donation goal ranges on the x axis 
![Parent Category lesson chart](https://user-images.githubusercontent.com/90660790/134459822-fede5648-2fe9-4e17-9ba1-bfca4358b002.png)

### Challenges and Difficulties Encountered

	The primary difficulty I encountered was using the correct inequality symbol when writing the COUNTIFS() functions.
	For example , I wrote =COUNTIFS(Kickstarter!$D:$D,"<=1000",Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<=4999",Kickstarter!R:R,"plays") for the successful outcomes between 1000 and 4900 dollars
	The first inequality symbol------------------------^ here is wrong, however I hadn't realized it at the time and proceeded to copy and paste this formula for the rest of the cells changing only the dollar amounts in the final product.
	This meant I had to go back an reverse the symbol for every formula that was based off of this one.

## Results

### Conclusions for Theater Outcomes Based on Launch Date

	1. The best time to start a kickstarter for theater appears to be in May.
	2. December seems to be the worst time to start a campaign. The chance that the campaign will be successful this time of year is approximately a fifty-fifty, which is much lower than the rest of the year.

### Conclusions for Outcomes Based on Goals

	1. The lower the donation goal the better. At less than 1000 the percentage for successful outcomes sits at 75% and goes down to 50% at 15999 to 19999. In addition, there is a brief uptick at the range 35000 to 44999 that sits at 67%. However this is only determined by 7 kickstarters total.       

### Limitations of the Dataset

	The most glaring issue I see with the data set is the low count of kickstarters in the higher donation goals range. While this is likely indicative of there being less kickstarters with that high of a donation goal for theater projects, I believe this resulted in an unrepresentative uptick in support.

### Other possible tables and graphs we could create

	One possible graph could just be a bar graph chart that shows the percentages of all the successful kickstarters for all categories to see which parent category receives the most relative support on Kickstarter.
	Another could be a pie chart showing the total money pledged for each parent category so we could determine which category is has the most enthusiastic support base.
