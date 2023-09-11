# Crowdfunding_ETL Introduction
  In this project we will be building an ETL pipeline using Python, Pandas, and Python dictionary mthods to extract and transform data. After the data is transformed, we created four CSV files to assist in creating an ERD and table schema.

# Creating the DataFrames

# Creating the Crowdfunding Database
- When creating the contacts DataFrame we decided to use the Python dictionary methods rather than using regular expressions.
- Choosing the Pandas option meant that we had to iterate through the contacts DataFrame, converting each row to a dictionary. We then iterated through each dictionary using Python list comprehensions and adding values for each row to a new list.
- Once that was done we created a new DataFrame that contained the extrated data and slpit each "name" column value into a first and last name column. The first 10 rows of our new DataFrame are shown in the image below
<img width="168" alt="image" src="https://github.com/SwagmasterMatt/Crowdfunding_ETL/assets/135439652/516cddad-da51-4fa7-a053-770dd09f0f1f">

 
# Methodology

# Schema
- To start creating the databse we sketched an ERD of the tables using the four CSV files.
- This sketch was created using QuickDBD. You can access QuickDBD by following this link: http://www.quickdatabasediagrams.com/
![image](https://github.com/SwagmasterMatt/Crowdfunding_ETL/assets/135439652/a976763c-4881-425f-8f2e-e8157f200963)
- We then used our ERD sketch (pictured above) to create table schema for each CSV file.

# Project Members
The collaborators on this project were Matthew Ray and Nick Remen.
