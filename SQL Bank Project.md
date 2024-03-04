## Exploring the Expansion of Roads Through the Eyes of The World Bank

![Title Picture](/images/SQL_Bank2.png)

### Have You Ever Wondered How A Country Pays to Build Roads?

The International Development Association (IDA) section of The World Bank provides its recipient member countries with development credits and grants. The goal of the IDA is to help the world's poorest countries by providing credits (zero to low-interest loans) to reduce poverty. Grants are used to help countries create programs to meet their development needs, improve quality of life, and give the economy a boost. 

 ![Road and Mountains](/images/SQL_Bank1.png) 

Throughout history, roads have been an innovative way to connect people. Before roads, think of the modes of transportation used. Typically, people would have traveled by horse or by foot. The wheel was invented prior to paved roads, but it wasn’t the most effective mode of transportation when there was heavy rain. The introduction of paved opened the door for the automotive industry to thrive as well as new technologies such as google maps and waze. Many underdeveloped countries today still do not have paved roads and thus, limited transportation. The IDA provides these countries with loans and grants to help fund projects like these, which is exaclty what we are going to explore!

### The Data
For this project, I downloaded the most updated IDA Statement of Credits and Grants available. This dataset was updated on February 15, 2024. It contains ~10.4k rows and 30 columns. Each row represernts a credit or a Grant. The columns represent different data elements such as: Credit Number, Country, Borrower, Credit Status, Service Charge Rate, Project Name, Original Principal Amount (US$), Due to IDA (US$), etc. The Data Dictionary for this data set can be shown in [**Data Dictionary for IBRD Statement of Loans and IDA Statement of Credits and Grants**](https://finances.worldbank.org/api/assets/FF2A5DB3-BBD2-444D-ADA8-90DF4A166980?download=true)

The data can be found following [**This Link**](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-of-Credits-and-Grants-Latest-Availab/ebmi-69yj/about_data)

I began exploring this dataset with SQL (Standard Query Language) queries using [csvfiddle.io](https://csvfiddle.io/#JTdCJTIyaXNUYWJsZU1ldGFkYXRhT3BlbiUyMiUzQWZhbHNlJTJDJTIyaXNOZXdUYWJsZUZvcm1PcGVuJTIyJTNBZmFsc2UlMkMlMjJpc0NvbmZpcm1EZWxldGVRdWVyeU9wZW4lMjIlM0FmYWxzZSUyQyUyMmlzQ29uZmlybURyb3BUYWJsZU9wZW4lMjIlM0FmYWxzZSUyQyUyMmlzU2hhcmVEaWFsb2dPcGVuJTIyJTNBZmFsc2UlMkMlMjJkYlJlYWR5JTIyJTNBZmFsc2UlMkMlMjJ0YWJsZXMlMjIlM0ElNUIlNUQlMkMlMjJxdWVyaWVzJTIyJTNBJTdCJTIyMCUyMiUzQSU3QiUyMmlkJTIyJTNBMCUyQyUyMnRpdGxlJTIyJTNBJTIyVW50aXRsZWQlMjBxdWVyeSUyMiUyQyUyMmJvZHklMjIlM0ElMjIlMjIlMkMlMjJyZXN1bHQlMjIlM0ElNUIlNUQlMkMlMjJlcnJvciUyMiUzQW51bGwlN0QlN0QlMkMlMjJhY3RpdmVRdWVyeUlkJTIyJTNBMCUyQyUyMmFjdGl2ZVRhYmxlTWV0YWRhdGFDb2x1bW5zJTIyJTNBJTVCJTVEJTJDJTIybG9jYWxUYWJsZXNUb1dhcm4lMjIlM0ElNUIlNUQlMkMlMjJpc1F1ZXJ5SW5Qcm9ncmVzcyUyMiUzQWZhbHNlJTJDJTIyZGlkQWRkTmV3VGFibGVTdWNjZWVkJTIyJTNBbnVsbCUyQyUyMmFkZE5ld1RhYmxlRXJyb3IlMjIlM0FudWxsJTdE). After learning what type of information I was working with, I decided to focus on a specific type of Project that these countries need loans for. There were options related to agriculture, education, water, and power. However, I decided to choose transportation routes such as roadways and highways as my project of choice. 

### Analysis
I began my analysis with these questions in mind:
1.	How much is owed to the IDA?
2.	What country owes the IDA the most and what is their loan total?
3.	How many total transactions does this country have?
4.	How many loans/grants does each country have?
5.	What is the average service charge rate for the given loans?
6.	How many loans/grants have a project name of 'Roads' or the name of 'Highway’?
7.	What is the Sum of the Original Principal Amount (US$) of the loans/grants?
8.	How much is owed to the IDA for these projects?
9.	What is the average service charge rate for these projects?
10.	Which country still owes the most for this specific project?

We know that there are a total of 10,400 transations in this dataset as it is provided by The World Bank website. However, if we didn't know, we could use a simple query to find out.

```sql
SELECT COUNT(*) FROM "Banking_Data_Feb15";
```
![Count Transactions](/images/M4_trans.jpg)

Here we see the count = 10,401 rows. This is including the first row of column headers.

1.
```sql
SELECT SUM("Due to IDA (US$)") FROM "Banking_Data_Feb15";
```
![Question 1](/images/M4_Q1.jpg)

2. 
```sql
SELECT Max("Due to IDA (US$)"), Country FROM "Banking_Data_Feb15"
GROUP BY Country ORDER BY MAX("Due to IDA (US$)") DESC;
```
![Question 2](/images/M4_Q2.jpg)

The country of Ukraine owes the IDA $1,024,995,109.66. Shocked by this amount of money, I looked further into this project. The service charge rate is 0. Using the [Data Dictionary](https://finances.worldbank.org/api/assets/FF2A5DB3-BBD2-444D-ADA8-90DF4A166980?download=true) for IDA Statement of Credits and Grants for reference, I learned that for loans that could have more than one interest rate, the interest rate is listed as “0”. The Project is the [PEACE in Ukraine Project](https://www.worldbank.org/en/news/feature/2023/07/10/the-world-banks-peace-project-supports-the-government-key-programs-in-ukraine), which began to provide financial support to the Ukraine Government and citizens after the Russian Invasion. The money is distributed as following, “Beneficiaries of the PEACE project include 10 million pensioners, 500,000 education employees, 145,000 government employees, 56,000 first responders, and more than 3 million recipients of social assistance and IDPs.”

3. 
```sql
SELECT COUNT(*) FROM "Banking_Data_Feb15"
WHERE "Country" = 'Ukraine';
```
![Question 3](/images/M4_Q3.jpg)

The only loan Ukraine has is for the PEACE project. 

4. 
```sql
SELECT "Country", COUNT(*) FROM "Banking_Data_Feb15"
GROUP BY "Country"
ORDER BY "Country" ASC;
```
![Question 4](/images/M4_Q4.jpg)

5. 
```sql
SELECT AVG("Service Charge Rate") FROM "Banking_Data_Feb15";
```
![Question 5](/images/M4_Q5.jpg)

### Taking SQL Further Down the Road...
Here I began to write SQL queries specific to transportation projects. There were many options including railroads and urban transport, but for simplicity, I stuck to roads and highways.

6. I ran the following query to get the total number of loans/grants for projects listed as a phrase with Road Construction, Road, or Highway. 
```sql
SELECT COUNT(*) FROM Banking_Data_Feb15
WHERE "Project Name" LIKE '%ROAD CONSTRUCTION%' 
OR "Project Name" LIKE '%ROAD%'
OR "Project Name" LIKE '%HIGHWAY%';
```
![Question 6](/images/M4_Q6.jpg)

The wildcard symbol "%", was helpful to find other projects that would be listed as, "ROADWAYS or HIGHWAY MAINT".

7. I was interested in how much money has been used for roadway transportation projects, not just what is still owed to the IDA. For this reason, I wrote a query to calculate the sum of the original principal amount which is the original amount of that loan that is committed and approved. 
```sql
SELECT SUM("Original Principal Amount (US$)") FROM "Banking_Data_Feb15"
WHERE "Project Name" LIKE '%ROAD CONSTRUCTION%' 
OR "Project Name" LIKE '%ROAD%'
OR "Project Name" LIKE '%HIGHWAY%';
```
![Question 7](/images/M4_Q7.jpg)

8. Now I ran a query to see how much money is still owed to the IDA for these projects. 
```sql
SELECT SUM("Due to IDA (US$)") FROM "Banking_Data_Feb15"
WHERE "Project Name" LIKE '%ROAD CONSTRUCTION%' 
OR "Project Name" LIKE '%ROAD%'
OR "Project Name" LIKE '%HIGHWAY%';
```
![Question 8](/images/M4_Q8.jpg)

This is still an insane amount of money, but definitely smaller than the sum of the original amount approved. 

9. I wanted to compare the Service Charge Rate for these projects compared to the total average of the dataset. 
```sql
SELECT AVG("Service Charge Rate") FROM "Banking_Data_Feb15"
WHERE "Project Name" LIKE '%ROAD CONSTRUCTION%' 
OR "Project Name" LIKE '%ROAD%'
OR "Project Name" LIKE '%HIGHWAY%';
```
![Question 9](/images/M4_Q9.jpg)

0.9298 vs 0.8143 may not seem like a lot, but when you owe millions to billions of dollars, that service charge rate is no joke!

10. Finally, I was interested in which country owed the most amount of money to the IDA for the roadway projects.    
```sql
SELECT MAX("Due to IDA (US$)"), "Country" FROM "Banking_Data_Feb15"
WHERE "Project Name" LIKE '%ROAD CONSTRUCTION%' 
OR "Project Name" LIKE '%ROAD%'
OR "Project Name" LIKE '%HIGHWAY%'
GROUP BY "Country" ORDER BY MAX("Due to IDA (US$)") DESC;
```
![Question 10](/images/M4_Q10.jpg)

Here we are, with Viet Nam coming in 1st place for owing the most amount of money to the IDA for these projects. 

### Major Findings

1. The total due to the IDA in this current snapshot for loans is grants is over $197 billion.
2. Ukraine owes the most to the IDA for their PEACE in Ukraine Project, $1,024,995,109.66.
3. The average service charge rate for all the loans and grants is 0.9298.
4. There are 289 projects for road construction, roadways, and highways. *Wildcard used to find any word combinations using road and highway.
5. The total amount originally approved to loan out for these specific projects was over $6 billon, while there is only $1.24 billion left to pay back.
6. The average service charge rate for all the loans and grants is 0.8143.
7. The top 5 countries that owe the IDA the most are: Viet Nam, Pakistan, Ethiopia, Bangladesh, and India. 

### Thank You!

I really enjoyed exploring this financial data using SQL. I hope to utilize SQL more down the road ;) 

Feel free to connect with me on LinkedIn or check my portfolio for new data projects!
