## Exploring Expansion of Transportation Through the Eyes of The World Bank

### Project Description
The International Development Association (IDA) section of The World Bank provides its recipient member countries with development credits and grants. The goal of the IDA is to help the world's poorest countries by providing credits (zero to low-interest loans) to reduce poverty. Grants are used to help countries create programs to meet their development needs, improve quality of life, and give the economy a boost. 

Throughout history, roads have been an innovative way to connect people. Before roads, think of the mode of transportation used. Typically, it was horse or by foot. The wheel was invented prior to paved roads, but it wasn’t the most effective mode of transportation when there was heavy rain. With the introduction of paved or stone roads opened the door for the automotive industry to thrive as well as new technologies such as google maps and waze. Many underdeveloped countries today still do not have paved roads and thus, limited transportation. The IDA provides these countries with loans and grants to help fund projects like these, which is exaclty what we are going to explore!

### The Data
For this project, I downloaded the most updated IDA Statement of Credits and Grants available. This dataset was updated on February 15, 2024. It contains ~10.4k rows and 30 columns. Each row represernts a credit or a Grant. The columns represent different data elements such as: Credit Number, Country, Borrower, Credit Status, Service Charge Rate, Project Name, Original Principal Amount (US$), Due to IDA (US$), etc. The Data Dictionary for this data set can be shown in [**Data Dictionary for IBRD Statement of Loans and IDA Statement of Credits and Grants**](https://finances.worldbank.org/api/assets/FF2A5DB3-BBD2-444D-ADA8-90DF4A166980?download=true)

The data can be found following [**This Link**](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-of-Credits-and-Grants-Latest-Availab/ebmi-69yj/about_data)

I began exploring this dataset with SQL (Standard Query Language) queries using csvfiddle.io. After learning what type of information I was working with, I decided to focus on a specific type of Project that these countries need loans for. There were options related to agriculture, education, water, and power. However, I decided to choose transportation routes such as roadways and highways as my project of choice. 

### Analysis
I began my analysis with these questions in mind:
1.	How much is owed to the IDA?
2.	What country owes the IDA the most and what is their loan total?
3.	How many total transactions does this country have?
4.	How many loans/grants does each country have?
5.	What is the average service charge rate for the given loans?
6.	How many projects are there in this dataset?
7.	How many loans/grants have a project name of 'Roads' or the name of 'Highway’?
8.	What is the Sum of the Original Principal Amount (US$) of the loans/grants?
9.	How much is owed to the IDA for these projects and what is the average service charge rate?
10.	Which country still owes the most for this specific project?

We know that there are a total of 10,400 transations in this dataset as it is provided by The World Bank website. However, if we didn't know, we could use a simple query to find out.

```sql
SELECT COUNT(*) FROM "Banking_Data_Feb15";
```

### 2. You can add any images you'd like. 

<img src="images/dummy_thumbnail.jpg?raw=true"/>


