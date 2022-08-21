# CapstoneProject-CyclisticBike-Share

Below are the links to everything related to the Capstone Project.

1. [FinalAnalysis.R](https://github.com/praveenS2303/-CapstoneProject-CyclisticBike-Share/blob/main/AnalysisCode.R) - analyzed the data set from case study 1 in the Google Data Analytics Course using R. I did not do any data visualization in R.

2. [FinalAnalysisTableau.R](https://github.com/praveenS2303/-CapstoneProject-CyclisticBike-Share/blob/main/FinalAnalysisTableau) - used code to create a specific data frame to use in Tableau. Deleted unncessary columns to make the code run quicker in Tableau.

3. [Tableau Dashboard](https://public.tableau.com/app/profile/praveen.singh8077/viz/GoogleCapstoneProjectCyclisticBike-share/CyclisticProject) - created a dashboard in Tableau summarizing the data


# BACKGROUND
Cyclistic is a fictional bike sharing program which features more than 5,800 bikes and 600 docking stations. It offers reclining bikes, hand tricycles, and cargo bikes, making it more inclusive to people with disabilities and riders who can't use a standard two-wheeled bike. It was founded in 2016 and has grown tremendously into a fleet of bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime. 


Previously, Cyclistic's marketing strategy tried to build the general awareness and appeal to broad consumers. It has flexible pricing plans: single-ride passes, full-day passes, and annual memberships. Those who purchase single-ride or full-day passes are referred to as casual riders while those who purchase annual memberships are Cyclistic members. 


My Role: In this scenario I am a junior data analyst at Cyclistic and my team has been tasked with the overall goal (see below) of designing marketing strategies 


Overall Goal: Design marketing strategies aimed at converting casual riders into annual members.


Business Question: "How do annual members and casual riders use Cyclistic bikes differently?"


Below I will describe step-by-step the process I used to for this project. If you want to skip ahead to the business suggestions move onto the section "Insights".


 
# PROCESS:
Overview: I first analyzed the data separately (each month) in Excel, then used R to analyze the data as a whole (one year). Finally I created a dashboard in Tableau.
# R 
I began downloading the data from [divvy-tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html) .I originally wanted to use SQL but the files were too big to upload and I couldn't figure out how to utilize Google Cloud Platform. Instead I used R to analyze the data because it could handle all of the information quicker than Excel, and I wanted to work on my R skills. Below is my general process in R. 


View my full code on my Github for this capstone project [here](https://github.com/praveenS2303/-CapstoneProject-CyclisticBike-Share/blob/main/AnalysisCode.R). 

  1. Load all of the libraries I used: tidyverse, lubridate, hms, data.table 

  2. Uploaded all of the original data from the data source divytrip into R using read_csv function to upload all individual csv files and save them in separate data frames. 

  3. Merged the 12 months of data together using rbind to create a one year view

  4. Created a new data frame called cyclistic_date that would contain all of my new columns 

  5. Created new columns for:

    a. Ride Length - did this by subtracting end_at time from start_at time

    b. Day of the Week 

    c. Month 

    d. Day 

    e. Year

    f. Time - convert the time to HH:MM:SS format

    h. Hour 

    i. Season - Spring, Summer, Winter or Fall

    j. Time of Day - Night, Morning, Afternoon or Evening

   6. Cleaned the data by:

    a.Removing duplicate rows

    b. Remove rows with NA values (blank rows)

    c. Remove where ride_length is 0 or negative (ride_length should be a positive number)

    d. Remove unnecessary columns: ride_id, start_station_id, end_station_id, start_lat, start_long, end_lat, end_lng

  7. Calculated Total Rides for:

    a. Total number of rides which was just the row count = 4,152,139

    b. Member type - casual riders vs. annual members 

    c. Type of Bike - classic vs docked vs electric; separated by member type and total rides for each bike type

    d. Hour - separated by member type and total rides for each hour in a day

    e. Time of Day - separated by member type and total rides for each time of day (morning, afternoon, evening, night)

    f. Day of the Week - separated by member type and total rides for each day of the week

    g. Day of the Month - separated by member type and total rides for each day of the month

    h. Month - separated by member type and total rides for each month

    i. Season - separated by member type and total rides for each season (spring,  summer, fall, winter)

  8. Calculated Average Ride Length for:

    a. Total average ride length

    b. Member type - casual riders vs. annual members 

    c. Type of Bike - separated by member type and average ride length for each bike type

    d. Hour - separated by member type and average ride length for each hour in a day

    e. Time of Day - separated by member type and average ride length for each time of day (morning, afternoon, evening, night)

    f. Day of the Week - separated by member type and average ride length for each day of the week

    g. Day of the Month - separated by member type and average ride length for each day of the month

    h. Month - separated by member type and average ride length for each month

    i. Season - separated by member type and average ride lengths for each season (spring,  summer, fall, winter)

# Tableau 
While I learned the basics of Tableau in the Google Course I wanted more practice with visualizing data and creating dashboards.
To view my completed dashboard click [here](https://public.tableau.com/app/profile/praveen.singh8077/viz/GoogleCapstoneProjectCyclisticBike-share/CyclisticProject).

  1. The dataframe created in R is used and downloaded into a .csv file which I uploaded to Tableau

  2. Created following graphs :

    a. User Type 

    b. Total Rides by Bike Type

    c. Ride Length by Weekday

    d. Total Rides by Weekday

    e. Total Rides by Hour

    f. Total Rides by Month
    
    g. Total Rides by Season 

  3. Edited graphs in Tableau 

  4. Made bar graphs round

  5. Added annotations

  6. Highlights to specific important notes 

Made minor edits to design elements and created final dashboard.

# Final Summary

  1. The most popular bike among with riders was the classic.

  2. Busiest time was afternoon and the peak time was at 5PM for both casual riders and members. 

  3. Busiest weekday was Saturday, casual riders used the service the most on the weekends. 

  4. Busiest season was Summer for both types of riders. 

  5. Most rides by User Type was members but casual riders weren't far behind. 

  6. The average ride length was 19 minutes but casual riders on average ride 14 minutes longer than members. 
# BUSINESS SUGGESTIONS
This was the hardest part for me for the whole project. I have never provided suggestions for a business nor worked in marketing. Any feedback here would be appreciated. 

These are my suggestions for the marketing team to convert casual riders to annual members:

 1. Personalize discounts and show perks in the membership program based on their preferences and riding habits.

 2. Emphasize the benefits of memberships, including discounts during busy times of the year like during Summer, or on the weekends. 

 3. Have existing members to share their stories about how using Cyclistic's system has changed their life, to create a sense of community, offer a discount if they do so this will help encourage new riders to join the program.
 4. 
# WHAT I LEARNED
Below is what I learned/practiced from over 40 hours spent on this project: 

 1. Pivot Tables in Microsoft Excel

 2. Practice using R for data analysis and cleaning specifically using the tidyverse package for data analysis 

 3. Graphs in Tableau, edited visual elements along with creating different charts and filters. 

 4. Design elements of an effective dashboard
 


