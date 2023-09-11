# Crowdfunding_ETL Introduction
In this project we will be building an ETL pipeline using Python, Pandas, and Python dictionary mthods to extract and transform data. After the data is transformed, we created four CSV files to assist in creating an ERD and table schema.

# Creating the DataFrames
- When creating the Category and Subcategory DataFrames the following columns were included:
  - category_id
  - category
  - subcategory_id
  - subcategory
- When creating the Campain DataFrame the following columns were included:
  - cf_id
  - contact_id
  - company_name
  - blurb
  - goal
  - pledged
  - outcome
  - backers_count
  - country
  - currency
  - launched_at
  - deadline
  - category_id
  - subcategory_id    
# Creating the Crowdfunding Database
- When creating the contacts DataFrame we decided to use the Python dictionary methods rather than using regular expressions.
- Choosing the Pandas option meant that we had to iterate through the contacts DataFrame, converting each row to a dictionary. We then iterated through each dictionary using Python list comprehensions and adding values for each row to a new list.
- Once that was done we created a new DataFrame that contained the extrated data and slpit each "name" column value into a first and last name column. The first 10 rows of our new DataFrame are shown in the image below
<img width="164" alt="image" src="https://github.com/SwagmasterMatt/Crowdfunding_ETL/assets/135439652/9044bffe-5d41-4297-9d93-fd26b38e5255">
 
# Methodology

# Schema
- To start creating the databse we sketched an ERD of the tables using the four CSV files.
- This sketch was created using QuickDBD. You can access QuickDBD by following this link: http://www.quickdatabasediagrams.com/
![image](https://github.com/SwagmasterMatt/Crowdfunding_ETL/assets/135439652/a976763c-4881-425f-8f2e-e8157f200963)
- We then used our ERD sketch (pictured above) to create table schema for each CSV file.
CREATE TABLE "Contacts" (
    "contact_id" INT   NOT NULL,
    "first_name" VARCHAR   NOT NULL,
    "last_name" VARCHAR   NOT NULL,
    "email" VARCHAR   NOT NULL,
    CONSTRAINT "pk_Contacts" PRIMARY KEY (
        "contact_id"
     )
);

CREATE TABLE "Category" (
    "category_id" VARCHAR   NOT NULL,
    "category" VARCHAR   NOT NULL,
    CONSTRAINT "pk_Category" PRIMARY KEY (
        "category_id"
     )
);

CREATE TABLE "Subcategory" (
    "subcategory_id" VARCHAR   NOT NULL,
    "subcategory" VARCHAR   NOT NULL,
    CONSTRAINT "pk_Subcategory" PRIMARY KEY (
        "subcategory_id"
     )
);

CREATE TABLE "Campaign" (
    "cf_id" INT   NOT NULL,
    "contact_id" INT   NOT NULL,
    "company_name" VARCHAR   NOT NULL,
    "description" VARCHAR   NOT NULL,
    "goal" FLOAT   NOT NULL,
    "pledged" FLOAT   NOT NULL,
    "outcome" VARCHAR   NOT NULL,
    "backers_count" INT   NOT NULL,
    "country" VARCHAR   NOT NULL,
    "currency" VARCHAR   NOT NULL,
    "launched_date" DATE   NOT NULL,
    "end_date" DATE   NOT NULL,
    "category_id" VARCHAR   NOT NULL,
    "subcategory_id" VARCHAR   NOT NULL,
    CONSTRAINT "pk_Campaign" PRIMARY KEY (
        "cf_id"
     )
);

ALTER TABLE "Campaign" ADD CONSTRAINT "fk_Campaign_contact_id" FOREIGN KEY("contact_id")
REFERENCES "Contacts" ("contact_id");

ALTER TABLE "Campaign" ADD CONSTRAINT "fk_Campaign_category_id" FOREIGN KEY("category_id")
REFERENCES "Category" ("category_id");

ALTER TABLE "Campaign" ADD CONSTRAINT "fk_Campaign_subcategory_id" FOREIGN KEY("subcategory_id")
REFERENCES "Subcategory" ("subcategory_id");


# Project Members
The collaborators on this project were Matthew Ray and Nick Remen.
