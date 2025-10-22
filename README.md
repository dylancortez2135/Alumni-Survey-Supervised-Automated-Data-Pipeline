# Alumni-Survey-Supervised-Automated-Data-Pipeline

This project demonstrates a supervised automated data pipeline that automatically ingests raw batches of alumni survey data, transforms them, and loads the cleaned results into a live dashboard.

## 📌 Overview

This is a synthetic version of a real, on-going project that aims to provide a Data Pipeline that converts batches of survey data into actionable and data-backed insights. All process — from data ingestion to the creation of the dashboard — are all automatic except one supervised step: Running the Glue Job (Main Transformation) to ensure reliability and cost efficiency.

## 🧠 Objectives

The survey collects responses from a local University’s alumni to assess demographics and post-graduation performance metrics.
It aims to provide insights into the University’s overall teaching proficiency and career impact by exploring these key questions

  1. Which college degree graduates performed the best?
  2. Which campus produces the most excellent employees?
  3. Which department does DMC Academy produce the most employees in, and what’s their average rating?
  4. What are the top job roles alumni drift into?
  5. Who are the top 100 employees per department?

## ⚙️ Architecture

<img width="1920" height="1080" alt="DMC Alumni Survey Data Pipeline Flow Chart" src="https://github.com/user-attachments/assets/af0037ef-6cb7-4825-b127-274ee49ded28" />

# Step 1: Schema Validation for Lighter Glue Transformation
This step stores and separates Validated schema from Invalid Schema. Since Glue can't gracefully handle issues with the Schema, this step ensures that only compliant-data proceeds to the Main Transformation. 

### Step 2: Data Transformation
This is where the main transformation occur including deduplication, data standardization, and format normalization.

### Step 3: Data Storage
This is where the cleaned data is stored both in Processed-Data/ and Archive/ "folders". Additionally, the data is also registered in a Glue Data Catalog 

### Step 4: Global Deduplication
Since we are dealing with batches of survey data, this is a crucial step that ensures there are no duplicate records across the multiple uploads. 

### Step 5: Data Analysis
This is where our curated data feeds into a live dashboard

### Step 6: Sending the Dashboard Every Week
While this can be fully automated using tools like Microsoft Power Automate, the process currently remains manually supervised to optimize cost and ensure final data verification before distribution.




