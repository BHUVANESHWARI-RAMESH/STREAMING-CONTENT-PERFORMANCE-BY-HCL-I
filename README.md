# STREAMING-CONTENT-PERFORMANCE-BY-HCL-I

Streaming Content Performance Analysis
Project Overview

Digital streaming platforms contain a wide variety of content across genres, languages, and countries. This project analyzes streaming content data to identify high-performing genres, platform trends, and audience engagement patterns.

The analysis helps uncover:

Most popular genres
Platform-wise content trends
Country-wise distribution
High-performing content segments
Availability and popularity insights
Objectives
Load and preprocess streaming platform datasets
Perform exploratory data analysis (EDA)
Analyze genre, platform, and geographic distributions
Identify popularity trends and high-performing segments
Create visualizations for business insights
Store processed results using SQL
Generate a summarized insights report
Technologies Used
Technology	Purpose
Python	Data analysis
Pandas	Data cleaning & manipulation
NumPy	Numerical operations
Matplotlib	Visualization
Seaborn	Statistical charts
SQL	Data storage & querying
Project Workflow
1. Data Collection

Dataset contains:

Title
Genre
Platform
Country
Release Year
Rating
Popularity Score
Duration

Possible datasets:

Netflix titles
Amazon Prime content
Disney+ content
Hulu content
2. Data Cleaning using Pandas
Tasks Performed
Removed null values
Removed duplicate records
Standardized genre and country names
Converted date columns
Handled missing ratings
Example
df.drop_duplicates(inplace=True)

df['genre'] = df['genre'].str.strip()

df.fillna("Unknown", inplace=True)
3. Exploratory Data Analysis (EDA)
Genre Distribution Analysis
Most common genres
Genre popularity trends
Platform Distribution
Content count by platform
Platform-specific strengths
Country Analysis
Country-wise content production
Regional streaming trends
Popularity Analysis
Highly rated genres
Trending content categories
4. Visualization using Matplotlib & Seaborn
Charts Used
Genre Distribution
sns.countplot(y='genre', data=df)
Platform Comparison
sns.barplot(x='platform', y='popularity', data=df)
Country-wise Distribution
df['country'].value_counts().plot(kind='bar')
Heatmap
sns.heatmap(correlation_matrix, annot=True)
5. SQL Integration
Store Cleaned Data
import sqlite3

conn = sqlite3.connect("streaming_analysis.db")

df.to_sql("streaming_content", conn, if_exists="replace", index=False)
Example SQL Queries
Top Genres
SELECT genre, COUNT(*) as total
FROM streaming_content
GROUP BY genre
ORDER BY total DESC;
Most Popular Platform
SELECT platform, AVG(popularity_score)
FROM streaming_content
GROUP BY platform
ORDER BY AVG(popularity_score) DESC;
Key Insights
Genre Insights
Drama and Comedy dominate most platforms
Thriller and Action genres show high engagement
Platform Insights
Netflix contains the highest content volume
Disney+ shows strong family-content dominance
Country Insights
USA contributes the largest content share
India shows rapid growth in regional streaming content
Popularity Trends
Recent releases gain higher engagement
Multi-genre content performs better
Expected Outputs
1. Genre Performance Charts
Top genres by popularity
Genre-wise engagement comparison
2. Platform Analysis Charts
Content count by platform
Average popularity by platform
3. Country-wise Distribution
Top producing countries
Geographic content trends
4. Insights Report

Summary of:

Best-performing genres
Top platforms
Emerging regional trends
Strategic recommendations
