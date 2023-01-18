# Analyzing Kickstarter Data With Excel

## Purpose
Evaluate the outcomes of Kickstarter campaigns based on launch date and financing goals to determine ideal conditions for launching a successful compaign.

## Analysis

### Theater Outcomes Based On Launch Date
Using information provided on the details of 4,114 Kickstarter compaigns launched between 2009-2017, data was first analyzed using a pivot table to determine the number of successful, failed, and canceled campaigns based on the months in which they were launched. It was further filtered by Parent Category to view only results labeled "theater". The option to filter by Year was also included, though not used in this analysis. 

This data was visualized with a line graph. 

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/111674383/190319037-b425868d-ee38-4b52-85b5-e76dd750b45f.png)

### Outcomes For Plays Based On Goals
The next analysis used the same Kickstarter campaign data to compare the outcomes (successful, failed, or canceled) of campaigns in the "plays" subcategory to their financing goals. 

Campaign goals were broken into 12 data ranges starting with "less than 1,000", ending with "50,000 or more", and then divided equally into 10 ranges between those amounts. The CountIfs() function was used to calculate how many of each outcome occurred in each financing goal range. After calculating the total projects within each range, the percentage of succesful, failed, and canceled campgaigns for each goal range was calculated. 

This data was also visualized with a line graph.

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/111674383/190318009-dc77cd18-885c-4f18-ae5c-7cee27570d17.png)

## Challenges And Difficulties
In order to analyze the original dataset, additional columns had to be made to convert column data into usable category and date formats. 

The first formulas written using the CountIfs function used relative instead of absolute cell references. When the formulas were subsequently copied into other rows and columns, the columns referenced in the Kickstarter dataset automatically shifted and returned inaccurate calculations. A Testing sheet was added to the workbook, and within it a pivot table was used to count the number of each campaign outcome at individual funding amounts. These amounts were then grouped into the ranges used in the original calculations to check the accuracy of the data. This highlighted the error within the original formula, and further formulas used absolute cell references appropriately.  

Also within the CountIfs formulas, the data ranges are hard-coded into the calculations. In the future, adding a column to transform the text data in the Goal column to mathematical representations (e.g., "<1000" instead of "Less than 1000") would provide greater flexibility as well as fewer opportunities for errors. 

## Results

### Theater Outcomes Based on Launch Date
* The number of failed campaigns in the Theater category does not fluctuate dramatically over the course of a year. With the exception of December (when succesful and failed campgaign numbers are nearly equal) the number of failed campaigns correlates with the increase or decrease in succesful campaigns across months (e.g., the number of both successful and failed campaigns in February are higher than they were in January. From February to March, both numbers decrease).
* The best month to launch a succesful Kickstarter campaign in the Theater category is May. It has the highest rate of success when compared to the rest of the year, and the corresponding rise in failed campaigns from April to May (12) is not nearly as high as the rise in succesful campaigns (40).

### Outcomes Based on Goals
* For a successful campaign within the Plays subcategory, the ideal amount of money to ask for is less than $1,000. Of all the data ranges, this one has the highest percentage rate for success and the lowest for failure. 
* The next best option for a succesful Plays campaign is a goal amount from $1,000-$4,999. The percentages of success and failure at this level are very close to the lowest data range, but the number of campaigns launched is much greater (534 projects compared to 186). That provides a more robust data set to calculate with, particularly since the next highest rates of success have fewer than 10 total projects in that data range. 

## Limitations
* Both graphs differ on how they are filtered (one is by a Parent category, the other a Subcategory). To best compare the ideal conditions for a successful campaign, it would help to keep that variable consistent.
* There are very few campaigns within the Plays subcategory in the higher goal amounts, which means that in some specific data ranges there are fewer than 10 total projects with which to calculate the percentages (a 67% success rate sounds pretty good until you realize there were only 3 total projects in that range). It would help to have a dataset that included information from a longer time span to confirm the accuracy of the percentages which are calculated using a small number of total projects. 

## Additional Analysis
* It would be useful to have the same sets of graphs for each variable being evaluated. 
  * That would include using a pivot table to calculate the raw number of successful, failed, and canceled projects when evaluated by launch date and funding goal. 
  * It would also include calculations to convert the raw data to percentages when evaluating the outcomes by launch date and funding goal.
* Similarly, it would be interesting to see how the data changes when it is filtered across both domains by the same categories/subcategories.
  * Having a chart of Play outcomes based on Launch Date would be an interesting contrast to Theater outcomes based on Launch Date.
  * Including a chart of Theater outcomes based on Goals would provide a larger dataset than Plays based on Goals, and it would be useful to find out if the percentages change dramatically when drilling down to a Subcategory from a Parent Category.
* Other useful domains to evaluate outcomes by would be whether or not the campaign was a Staff Pick or Spotlighted. This could influence decisions on whether or not it is useful to spend time/money paying or campaigning to receive either designation. 
