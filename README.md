# Comprehensive Analysis and Visualization of iPhone Sales Data

This Python code is a detailed implementation of an iPhone sales analysis, focusing on uncovering insights from product ratings, reviews, and pricing data. It demonstrates the application of data analysis techniques to real-world business problems, emphasizing exploratory data inspection, trend identification, and interactive visualizations. The code highlights relationships between key variables such as sale price, discount percentages, and customer engagement, offering actionable insights to inform strategic decision-making.

# Importing Libraries:

  1. import pandas as pd
  2. import numpy as np
  3. import plotly.express as px

  pandas: Used for data manipulation and analysis.
  numpy: Adds support for large, multi-dimensional arrays and matrices.
  plotly.express: For creating interactive plots.

# Reading the Dataset:

  4. data = pd.read_csv('apple.csv')
  Reads the apple.csv file into a DataFrame named data.

# Dataset Information:

  5. data.info()
  Provides a summary of the dataset, including data types and non-null values.

# Displaying the Dataset:

  6. data
  Outputs the entire dataset.

# First 10 Rows and Last 10 Rows:

  7. first10 = data.head(10)
  8. first10
  Extracts and displays the first 10 rows of the dataset.
  
  9. last10 = data.tail(10)
  10. last10
  Extracts and displays the last 10 rows of the dataset.

# Checking for Missing Values:

  11. notnulldata = data.isnull().sum()
  12. notnulldata
  Checks and sums up missing values in each column.

# Descriptive Statistics:

  13. data.describe()
  Provides summary statistics for numerical columns.

# Top 5 Products by Star Rating:

  14. dr = data.sort_values(by='Star Rating', ascending=False).head(5)
  Sorts the data by 'Star Rating' in descending order and selects the top 5 rows.

# Extracting Product Names and Ratings:

  15. product_rating_name = dr[['Product Name','Star Rating']]
  Extracts 'Product Name' and 'Star Rating' from the top 5 products.

# Product Name Extraction:

  16. product_rating = product_rating_name['Product Name']
  Extracts the 'Product Name' from the top-rated products.

# Counting Product Ratings:

  17. product_rating_count = product_rating_name['Product Name'].value_counts()
  Counts the occurrences of each product name in the top-rated products.

# Bar Plot for Number of Ratings:

  18. fig = px.bar(dr, x=label, y=counts, title='Number Of Ratings')
  19. fig.show()
  Creates a bar plot showing the number of ratings for the top-rated products.

# Bar Plot for Number of Reviews:

  20. fig = px.bar(dr, x=label, y=counts, title='Number Of Reviews')
  21. fig.show()
  Creates a bar plot showing the number of reviews for the top-rated products.

# Scatter Plot: Sale Price vs. Ratings:

  22. fg = px.scatter(data_frame=data, x='Number Of Ratings', y='Sale Price', size='Discount Percentage', trendline='ols',title='Sale Price VS Rating')
  23. fg.show()
  Creates a scatter plot to visualize the relationship between 'Sale Price' and 'Number Of Ratings', with bubble size representing 'Discount Percentage'.

# Scatter Plot: Discount Percentage vs. Ratings:

  24. fg = px.scatter(data_frame=data, x='Number Of Ratings', y='Discount Percentage', size='Sale Price', trendline='ols',title='Discount Percentage VS Rating')
  25. fg.show()
  Creates a scatter plot to visualize the relationship between 'Discount Percentage' and 'Number Of Ratings', with bubble size representing 'Sale Price'.

# Extracting Product Names and Sale Prices:

  26. product_sale_price = data[['Product Name','Sale Price']]
  Extracts 'Product Name' and 'Sale Price' from the dataset.

# Identifying the Most and Least Expensive Products:

  27. least_expensive = data.loc[data['Sale Price'].idxmin()]
  28. most_expensive = data.loc[data['Sale Price'].idxmax()]
  Identifies and displays the most and least expensive products based on 'Sale Price'.
