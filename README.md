# Amazon Reviews Sentiment Analysis

## Overview
This project processes [Amazon Reviews](https://amazon-reviews-2023.github.io/) from a JSON file, stores the data in Amazon S3, and performs sentiment analysis using Databricks. The pipeline includes data cleaning, preprocessing, model training, and visualization of the results, highlighting products with the most positive reviews in different categories

## Project Architecture
![](https://github.com/ShawonSimon/Amazon-Reviews-Sentiment-Analysis/blob/main/screenshots/sentimentA.jpg?raw=true)

## Technologies Used

- Apache Spark (PySpark): For data processing and machine learning.
- Databricks: For orchestrating the pipeline and running Spark jobs.
- Amazon S3: For data storage.
- Python Libraries: Matplotlib, Pandas, NumPy, and Scikit-learn.

## Project Workflow
1. Data Ingestion:

   - A JSON file containing Amazon reviews is uploaded to an S3 bucket.
   - The data is converted to Parquet format for efficient processing.
2. Data Preprocessing:

   - Removes duplicates and unnecessary columns.
   - Cleans review text by removing special characters and converting to lowercase.
   - Adds a sentiment column: reviews with ratings ≥ 4 are labeled as positive (1), others as negative (0)
3. Feature Engineering:

   - Tokenizes review text into words.
   - Removes stop words.
   - Converts text to numerical features using TF-IDF.
4. Model Training and Evaluation:

   - Splits the data into training and test sets.
   - Trains Naive Bayes, Random Forest, and Decision Tree models using Spark ML pipelines.
   - Evaluates models based on accuracy and generates a classification report.
5. Visualization:

   - Identifies top products in different categories based on positive sentiment.
   - Creates bar charts to display the results.
6. Saving and Deploying Models:
   
   - Saves the best-performing model to S3 for future predictions.

## Results
The project outputs:
   
   - Accuracy metrics for each model.
   - The best-performing model's accuracy and details.
   - Visualizations of the top products by positive sentiment.
