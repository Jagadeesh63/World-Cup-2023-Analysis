# World-Cup-2023-Analysis


In this presentation, we will explore about World Cup 2023 Analysis Dashboard

Step 1: Setup and Data Loading 

Import the necessary data analysis libraries (pandas, numpy, matplotlib, seaborn) and load the datasets into memory.  
Uses pd.read_csv() wrapped in a try-except block to prevent crashes if a file is missing.  
Displays initial data using .head() to verify correct data loading. 

Step 2: Data Preprocessing & Cleaning

2.1 Column Name Standardization:

Defines a custom function clean_cols() that strips trailing spaces, converts text to lowercase, replaces spaces with underscores, and strips out special characters.

2.2 Column Renaming for Consistency:

Standardizes naming across tables (e.g., renaming match_no to match_id, batsman_name to batsman, team_name to country) so all tables use uniform foreign keys.

2.3 Text Processing & Dismissal Categorization:

Standardizes text strings by trimming leading/trailing whitespace (.str.strip()) on player names and teams.  
Uses a lambda function to convert complex dismissal descriptions into a clean binary classification ('out' or 'not out')

2.4 Data Integration & Merging:

Performs left-joins (pd.merge) between performance datasets (batting_df, bowling_df) and player metadata (players_info_df) to add player country and role attributes.  
Checks for missing links to ensure no unmapped players exist.  

2.5 Numeric Data Type Conversion:

Converts numeric statistics into numeric types to prepare them for mathematical calculations and aggregations.  
Renames boundary columns 4s and 6s to fours and sixes for cleaner code referencing.

2.6 Date Processing and Innings Assignment:

Converts the date column to a proper datetime format.  
Merges team match pairings onto the batting dataset to dynamically derive whether a team batted in Innings 1 or Innings 2.

