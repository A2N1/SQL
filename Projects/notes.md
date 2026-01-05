SQL Learning Projects
1. E-Commerce Sales Analysis
- Focus: Data Analysis & Business Intelligence
- Key Concepts: JOIN, GROUP BY, HAVING, Aggregate functions (SUM, AVG, COUNT).
- Tasks:
  - Customer Segmentation: Identify the top 10% of customers by total spend.
  - Product Performance: Find products that have never been sold (using LEFT JOIN).
  - Inventory Insights: Identify the most and least profitable product categories.
  - Dataset Suggestion: Northwind or Chinook Sample Database.

2. Library Management System
- Focus: Database Design & Schema Architecture
- Key Concepts: CREATE TABLE, Constraints (PRIMARY KEY, FOREIGN KEY, CHECK), Normalization.
- Tasks:
  - Schema Design: Build a relational structure for Books, Authors, Members, and Loans.
  - Data Integrity: Use constraints to ensure a book's "Status" can only be 'Available' or 'Loaned'.
  - Automation: Create a VIEW that lists all members with overdue books and their contact info.

3. Financial Portfolio Tracker
- Focus: Advanced Analytics & Window Functions
- Key Concepts: Window Functions (RANK, LEAD, LAG), CTEs (Common Table Expressions), Date manipulation.
- Tasks:
  - Running Totals: Calculate a cumulative sum of expenses ordered by date.
  - Growth Metrics: Use LAG() to calculate Month-over-Month (MoM) spending growth.
  - Categorization: Use CASE WHEN to tag transactions as "Fixed" or "Variable" costs.

4. Public Data Cleaning
- Focus: Data Engineering & Transformation
- Key Concepts: COALESCE, NULLIF, String functions (SUBSTR, REPLACE), CAST.
Tasks:
  - Standardization: Clean messy phone numbers and address strings into a uniform format.
  - Missing Values: Use COALESCE to handle NULL entries in critical data columns.
  - Deduplication: Identify and remove duplicate entries based on fuzzy matching logic.
  - Dataset Suggestion: Kaggle CSV datasets or NYC Open Data.