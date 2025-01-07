# Crowdfunding_ETL

**Crowdfunding Data Analysis and Transformation**

This project involves the extraction, transformation, and preparation of crowdfunding campaign data for further analysis. The data processing steps include splitting, cleaning, merging, and restructuring the dataset into multiple DataFrames, which are then exported as CSV files for future use. Below is an overview of the steps performed:
**1.	Dependencies and Data Extraction:**
o	Imported necessary libraries, such as pandas and numpy, for data manipulation and analysis.
o	Loaded the crowdfunding data from an Excel file into a Pandas DataFrame.
**2.	Category and Subcategory DataFrames:**
o	Split the category & sub-category column into separate category and subcategory columns.
o	Extracted unique categories and subcategories, assigned unique IDs, and created separate DataFrames for categories and subcategories.
o	Exported these DataFrames as category.csv and subcategory.csv.
**3.	Campaign DataFrame:**
o	Created a new campaign DataFrame, renaming columns and formatting data for consistency.
o	Converted goal and pledged columns to float and formatted launch_date and end_date to datetime format.
o	Merged the campaign DataFrame with the category and subcategory DataFrames on their respective keys.
o	Dropped irrelevant columns and exported the cleaned DataFrame as campaign.csv.
**4.	Contact DataFrame:**
o	Extracted contact IDs, names, and emails from the contact_info column of another dataset.
o	Parsed the name column into first_name and last_name and removed redundant columns.
o	Reorganized and cleaned the DataFrame, verifying data types before exporting as contacts.csv.
**5.	Output:**
o	The processed data was saved in the Resources folder as:
	category.csv
	subcategory.csv
	campaign.csv
	contacts.csv
This structured approach ensures the data is clean, well-organized, and ready for further analysis or integration into other systems. The exported CSV files are encoded in UTF-8 format for compatibility with most data tools.

**Database Creation and Schema Setup for Crowdfunding**
This script sets up a PostgreSQL database for managing crowdfunding campaign data. It involves creating a database named crowdfunding_db and defining several tables for storing campaign-related information, including categories, subcategories, contacts, and the campaigns themselves. Below is an overview of the SQL commands executed:
**1.	Database Creation:**
o	The database crowdfunding_db is created to hold the crowdfunding-related tables and data.
**2.	Table Definitions:**
o	category Table: Stores information about categories of campaigns, with columns category_id and category_name. The category_id is the primary key.
o	subcategory Table: Stores information about subcategories of campaigns, with columns subcategory_id and subcategory_name. The subcategory_id is the primary key.
o	contacts Table: Stores details about contacts, such as contact_id, first_name, last_name, and email. The contact_id is the primary key.
o	campaign Table: Contains detailed information about crowdfunding campaigns, such as cf_id, contact_id, company_name, description, goal, pledged, outcome, backers_count, country, currency, launch_date, end_date, and foreign keys to the category and subcategory tables. The cf_id is the primary key.
**3.	Foreign Key Constraints:**
o	The campaign table is linked to the contacts, category, and subcategory tables through foreign keys:
	contact_id references the contact_id in the contacts table.
	category_id references the category_id in the category table.
	subcategory_id references the subcategory_id in the subcategory table.
**4.	Select Queries:**
o	After creating the tables and establishing the relationships, the following SELECT queries are used to retrieve all data from each table:
	SELECT * FROM campaign;
	SELECT * FROM category;
	SELECT * FROM contacts;
	SELECT * FROM subcategory;
This script ensures that the necessary tables are created and populated with data for further analysis and reporting related to crowdfunding campaigns. The relationships between the tables are maintained through primary and foreign keys, ensuring data integrity and consistency across the database.

