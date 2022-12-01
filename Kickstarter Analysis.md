# Kickstarting with Excel

## Overview of Project
The purpose of this project is to provide Louise with a clear look at the trends related of past kickstarter events. One of the deliverables was to highlight what time of year has historically been the most successful. The other key piece of information needed from this analysis is to see how much she should set as her goal based off of previous successful and unsuccessful kickstarters. 
### Purpose
Louise just recently finiched a fundraising campaign and now wants to know how/why some campaigns are more successful than others. She initially tried to review historical data from past fundraising events but she quickly learned that there was an immense ammount of data but with everything being displayed in a raw linear chart, it was really just a lot of "noise" and painted no picture at all. She has asked me to drill into the data and organinze it in such a fashion she would quickly be able to understand the following:
- Funding amount goals
- Amounts pledged
- Campaign launch dates
## Analysis and Challenges
It was very clear what Louise wanted to deduce from the data set, the challenge was figuring out how to organize the data in an way that made sense and answered her questions.
> *"Data analytics is the science of analyzing raw data to make conclusions about that information"*
>                                                 *-[Investopedia](https://www.investopedia.com/terms/d/data-analytics.asp)*                               

I knew this was going to be more than just applying some filters and sorting the data. I was going to need to peel back the layers of the onion in order to expose the key aspects of the data and create a visual product that quickly, neatly, and clearly displays the answers to Louis's questions.Below I explain just how I was able to do that.
### Analysis of Outcomes Based on Launch Date
**Analysis -** My first step to determine outcomes based on the launch date was to create a pivot table that grouped the event type. Firstly, we know we wanted to look at only the **"theater"** category so that was the first filter I applied to the pivot table. Next I organzied the results into the months that they were completed. The biggest challenge I encotuntered when extracting the data from the raw spreasheet that had I not done so it would have prevented me from being able to report on the launch date.
- The date format was in [Epoch format](https://www.epochconverter.com/). I had to determine the correct excel formula needed in order to convert the dates to a human readable format that made sense and could be translated when viewd in a chart or graph. The formula used that made for a clean conversion was ```=(((J2/60)/60)/24)+DATE(1970,1,1)```. The use of this conversion made it possible to break out all the Theater campaigns into their repsective months. After pulling in the relevant data points into the pivot table, I created a line chart that showed a linear line graph with the 3 requested outcomes represented by their own colored line. The X-axis showing the month of completion, and the Y-axis showing the sum of the Theater campaignsthat were either successful, canceled, or failed.
**Outcomes -** The outcomes are displayed below. The first being the pivot chart showing Theater campaigns by month. The second outcome displayed is the line graph providing the visual results.
  
![Outcomes vs Launch Date Pivot](https://github.com/TONY-H83/kickstarter-analysis/blob/main/Resources/Outcomes%20vs%20launch%20Date.png)

![Outcomes Based on Launch Date](https://github.com/TONY-H83/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)
### Analysis of Outcomes Based on Goals
**Analysis -** In order to find the number of theater campaings that successfully met their pledge goals, I needed to create a chart that pulled in all the measures from the raw data sheet. I was given the range of the pledge goals to group the results by. I was able to accomplish this by using a nested IF statement within my first chart column of "successful outcomes". I then just had to alter my formula to look at the different outcomes. The nested IF statement is something I have used before so it was not incredibly challenging but can easily be written incorrectly. Here is my IF statement for both a single goal amount and a goal range. 
- Single goal ```=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")```
- Goal range ```=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<=4999",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")```
The next part of the analysis was to calcualte the percentage of those theater campaigns that were successful, failed, or canceled. That required some simple SUM formulas that looked at the number successful, failed, and canceled/total number of projects for a given goal range. 
**Outcomes -** The outcomes are displayed below. The first being the chart showing theater campaigns by goal range, outcome cum, and outcome percentages. The second outcome displayed is the line graph providing the visual results.

![Outcomes by goal chart](https://github.com/TONY-H83/kickstarter-analysis/blob/main/Resources/Outcomes%20by%20goal%20chart.png)

![Outcomes Based on Goals](https://github.com/TONY-H83/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png). 
### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some other possible tables and/or graphs that we could create?
