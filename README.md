# Hospitalization-Cost-Analysis-SQL-Project
The primary goal of this project is to analyze the factors influencing hospitalization costs.The analysis involves data merging, cleaning, and executing complex SQL queries to derive key insights.

## Repository Structure
The repository for the Capstone SQL Project should include the main SQL script containing all the data cleaning and analytical queries , a README.md file for project context, along with raw datasets and supporting documentation.

## Setup and Installation
To run the SQL queries in this project, you will need an operational SQL environment (e.g., MySQL, PostgreSQL, SQL Server). The queries provided are primarily standard SQL but seem to use MySQL-specific syntax (like the USING clause in JOIN).
 - Create Schema: Start by creating the project schema/database.
 - SQL Format
     - CREATE SCHEMA project;
     - USE project;
 - Load Data: Load the hos_data.csv and med_data.csv files into two respective tables named hos and med within the project schema.
 - Run SQL Script: Execute the commands in the capstone_sql_project.sql file.

## Dataset Structure
The project uses two primary tables linked by a common Customer ID column

##  Key SQL Tasks and Analysis
The main file addresses the following analytical questions:
### Data Merging and Pre-processing 
    - Merging: Creates a view named hos_med by joining hos and med tables using the Customer ID.
    - Primary Keys: Adds a PRIMARY KEY constraint to the Customer ID column in both hos and med tables after handling null/invalid values.
### Diabetes and Heart Issues Analysis 
    - Objective: Retrieve information about people who are diabetic (where HBA1C > 6.5) and have heart problems, calculating their average age, dependent children, BMI, and hospitalization costs.
    - Key SQL Technique: JOIN and GROUP BY with a CASE statement to define 'diabetes' status.
### Cost Analysis by Hospital and City Tier
    - Objective: Find the average hospitalization cost for each combination of Hospital tier and City tier.
    - Data Cleaning: Updates any missing ('?') hospital or city tier values to 'tier - 2' before aggregation.
### Major Surgery and Cancer History
    - Objective: Determine the number of people who have had major surgery (defined as NumberOfMajorSurgeries >= 1) with a history of cancer.
    - Key SQL Technique: Subquery with a CASE statement to categorize major surgery status, followed by COUNT(*) and WHERE filtering.
### Hospital Tier Count by State
    - Objective: Determine the number of tier-1 hospitals in each state.
    - Key SQL Technique: GROUP BY and HAVING clause to filter for 'tier - 1' hospitals8.
