# US-State-Tax-Collections
Case Study 3: Correlation between type of tax collected (property, income, ect.) and the amounts collected.

---
title: "US-State-Tax-Collections" 
output: html_document
author: China Gaines
date: 08-13-2021
---
![Banner_Image](banner_img.jpg)

## Introduction 🚗
The U.S. Census Bureau is a government agency with the United States designed to serve the country with information about it's population and the economy. With the United States boasting a population of 328.2 million people (est. 2018 census), there is an increased interest in how the public finance and employment data for of the nation's state and local government sector. This case study explores the amount of state tax collected depending on what kind of type of tax. \

**Business Task** \
1️⃣. Use the 'State Tax Collections by Category: US and States 2016 - 2020' found on the U.S. Census Bureau website. \
2️⃣. Organize and analyze the data to determine the type of tax that states generate the most capital from. \


**Questions for Analysis** 
- What type of tax generates the most capital per year? The least? And on average? \
- What years had the highest taxes collected? The least? The average? \

**Key Stakeholders** \
Key stakeholders in this analysis would include the Internal Revenue Service (IRS), and the U.S. Department of Treasury.

**Data Source**\
The [State Tax Collections by Category: US and States 2016 - 2020](https://data.census.gov/cedsci/table?q=United%20States&tid=GOVSTIMESERIES.GS00TC02&hidePreview=true) dataset includes details about the public finance and public employment data for the U.S. national state and local government sector. This data was released on June 21st, 2021 and it comes from the census of governments and its annual files related on a flow basis. Information in this dataset include geographic area name, year, meaning of survey component, aggregate description, meaning of aggregate description, meaning of type of government, and amount formatted. \

This dataset **ROCCC**s, meaning that it is *Reliable*, *Original*, *Comprehensive*, *Current*, and *Cited*.

## The Data Analysis Process

### 📚 Preparation of the Data 

To begin with preparation, the dataset ['State Tax Collection by Category: US and States 2016 - 2020'](https://data.census.gov/cedsci/table?q=United%20States&tid=GOVSTIMESERIES.GS00TC02&hidePreview=true) was downloaded from ['Data.Census.gov'](data.census.gov)and uploaded into Google Sheets for cleaning and analysis. 

**Files used included the following:** \
-State_Tax_Collection_2016-2020.csv

### 📈 Processing of the Data 
Data was cleaned in Google Sheets using the following steps: 
1. Checked for duplicates using the count(distinct(unique_key)) functions. No duplicates were found.
2. Filtered and Sorted Data 

### 📊 Analysis of the Data
To talk about analysis, I split the analytical questions down into **actionable tasks**. These tasks are outlined below as well the analytical work I performed.  

- *Is there a relationship between motor collisions and borough?* 
 1. Create a query to calculate the frequency of each borough to determine number of motor collisions in each area. 
 ````
SELECT 
borough, count(*)
FROM `bigquery-public-data.new_york_mv_collisions.nypd_mv_collisions`
GROUP BY borough
ORDER BY count(*) DESC
 ````
This query generated the following results: 
![Borough Frequency Table](bq-results-20210805-114854-8twtisrcwm8v.csv) 

These results are shown visually with the following data visualization using Tableau.

![Borough Frequency Chart](borough_frequency.png) 
 
As you can see above, the frequency chart above produces a table where each borough is ranked by the frequency of motor collisions present. As abundantly clear, the vast majority of motor collisions are not reported to a borough; this is shown by the frequencies found in the null category. 

However, given that the null category is excluded from results, rankings of boroughs are shown as follows: 

![Borough Frequency Chart Without Null](borough_frequency_excludenull.png)

Occurrence of Motor Collisions occur in descending order starting with Brooklyn, Queens, Manhattan, Bronx, and then Staten Island.

### ✳️ Recommendations for how to reduce motor collisions in high-risk areas

My recommendations are to prioritize community resources and officers for the Brooklyn, Queens, and Manhattan boroughs because they have the most motor collisions. By having community engagement events, general education (such as reminders to buckle up and reduce distractions while on the road) and an increase in officers in these areas, the amount of motor collisions would likely fall.

### 🚩 Follow-Up Questions 

1. Is there a correlation between motor collisions and street infrastructure?
2. What are the populations of each borough? And does this impact the amount of motor collisions?
3. Is there a correlation between zip code and motor collisions? Is there a correlation between month and motor collisions?
