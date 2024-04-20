# Churn-Rates-with-Codeflix

The team at CodeFlix, a streaming video startup, wants to evaluate the progress their business has made since its launch. They want to analyse the churn rates across two of their customer segments to measure the attractiveness of their service to their customers. 

The analysis is formed of four parts:

## Choosing the Month(s) to Calculate the Churn Rates for & Exploring the Customer Segments
The subscriptions data table covers the period between December 2016 (launch month) and March (2017). As there were no active users before the first day of December 2016, we could only calculate the churn rates for the first three months of 2017.

Using SQL queries, the customer segments 87 and 30 were identified from the data covering the first three months of 2017.

## Define and Apply the Methodology for Calculating Churn Rates
SQL Queries were used to complete the following steps:
- Create a temporary table having the columns "first day" and "last day" with row values being each of the three months between January and March 2017.
- Apply a CROSS JOIN on the subscriptions data table and the temporary table to match each date with the corresponding customer segment number and subscription start/end dates.
- Given that a user is active during any one month when their subscription start start date is before the first day of that month and their subscription end date is either non-existent or after the first day (and inactive otherwise), SQL queries with CASE WHEN statements were used to create the temporary Status table indicating whether each customer from each segment (#30 and #87) is active or inactive at the start of every month.
- Use a SQL query to aggregate the tempoerary Status table by summing the columns (number of customers from each segment who are active/inactive).

## Investigate the Overall Churn Trend since the Company Launched
SQL queries were used to calculate each month's overall churn rate by dividing the total number of inactive customers (from both segments) by the total number of active customers (from both segments). The trend was examined over the first three months of 2017.

## Investigate the Churn Rates Between User Segments
SQL queries were used to calculate each month's churn rate for each of the two customer segments. 
