# PWC Power BI Virtual work experience- Call Centre Trends

![Screenshot 2023-09-17 112239](https://github.com/murekarmansi/PWC_Task-1_Call_Center_Trends_Dashboards/assets/135413496/bf20fef5-ae55-485c-a303-11046a9f1ef9)

# Table Of Contents 
1) Problem Statment
2) Datasource
3) Data Prepreation
4) Data Modeling
5) Data analysis (DAX)
6) Data Visulization Dashboard 
7) Insights 

# Problem Statment:
Created a dashboard in Power BI for Client that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

Possible KPIs include:

Overall customer satisfaction
Overall calls answered/abandoned
Calls by time
Average speed of answer
Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

# Datasource :
Dataset used for this task was presented by Pwc and call centre trends dataset:

Dataset: Call Centre Trends

# Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Call Centre Trends dataset is give table named:

     Call Center trends dataset which has 10 columns and 5000 rows of observation. Call center trends table rename to performance.
     
Data Cleaning for the dataset was done in the power query editor as follows:

     Removed Unnecessary columns and rows.
     
     Removed Duplicates and NULL Values.
     
     Each of the columns in the table were validated to have the correct data type.

# Data Modeling
     After Data Prepration dataset was cleaned and transformed, it was ready to the data modeled.
     
     ![image](https://github.com/murekarmansi/PWC_Task-1_Call_Center_Trends_Dashboards/assets/135413496/ada95286-b899-4baa-8856-33c6e719d35a)

     ![image](https://github.com/murekarmansi/PWC_Task-1_Call_Center_Trends_Dashboards/assets/135413496/cf73febd-6170-468b-9e88-37a349fc9a74)

# Data Analysis (DAX):

Measures used in all visualization are:

Average of seed of answerd = AVERAGE('call centre trends'[Speed of answer in seconds])

Average of statisfaction = AVERAGE('call centre trends'[Satisfaction rating])

Count satisfation rating = COUNT('call centre trends'[Satisfaction rating])

Overall Customer Satisfation = DIVIDE([Possitive satisfation rating],[Count satisfation rating],0)

Possitive satisfation rating = CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))

resolved calls = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])

Unresolved calls = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])

total calls = CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswred])

total calls answered = COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])

total calls unanswred =COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])

# Data Visualization (Dashboard) :
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Call Center Trends :

![image](https://github.com/murekarmansi/PWC_Task-1_Call_Center_Trends_Dashboards/assets/135413496/3815c4fa-e912-4ab9-a96a-5ef31061ef65)

# Insights 

1. The majority of customer satisfaction ratings for each call fall within the range of 3 to 4. The average satisfaction rating has declined over three months, with the highest in January and the lowest in March.

2. The percentage of issues resolved was highest in January, slightly decreased in February, and then increased again in March.

3. Most calls are received in the morning.

4. Joe has the highest average speed of answering calls.

5. Jim has the highest call resolution rate, despite his lower average speed of answering calls compared to Joe, Martha, and Dan. Jim also handles a higher number of calls.

6. Becky has the slowest speed of answering calls but a higher call resolution rate, placing her in the 5th position for call resolution rate.

7. Martha has the highest speed of answering calls in the second position.

