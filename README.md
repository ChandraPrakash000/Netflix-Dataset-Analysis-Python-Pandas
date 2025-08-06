
# Netflix Data Analysis Project
Overview
This project involves an in-depth analysis of the Netflix Movies and TV Shows dataset. The primary goal is to uncover key trends in content evolution, identify prolific creators, and understand how content ratings are distributed across different types of shows and movies. The analysis utilizes Python's pandas for data manipulation and matplotlib and seaborn for data visualization.

Dataset
The dataset used for this analysis is the "Netflix Movies and TV Shows" dataset, publicly available on Kaggle.

Source: rohitgrewal/netflix-data

Analysis Questions & Insights
This project addresses the following key questions:

1. Evolution of Content (Movies vs. TV Shows) Over Time
Methodology: Extracted Release_Year from Release_Date and grouped data by year and content Category (Movie/TV Show) to count releases.

Insight: Visualizes the growth and shifts in Netflix's content library, showing trends in movie vs. TV show releases over the years.

2. Top 10 Most Prolific Directors & Cast Members
Methodology: Used value_counts() on the Director and Cast columns to identify individuals with the most credited titles.

Important Note: The analysis of Director and Cast columns counts the exact string entry. If a title lists multiple directors (e.g., "Director A, Director B"), it is counted as one entry for that specific combined string, not as separate contributions from "Director A" and "Director B". Similarly for Cast.

Insight: Identifies the most frequently appearing creative talents on the platform based on their primary listing.

3. Rating Distribution by Content Type and Category
Methodology: Compared the proportion of various Rating categories between Movie and TV Show content types. Further analyzed rating distributions within these broad content categories.

Insight: Helps understand the typical age suitability of Movies versus TV Shows and reveals if certain ratings are more common for one content type over another (e.g., TV Shows leaning more towards mature ratings).

Methodology and Key Techniques
The project follows a standard data analysis workflow:

Data Loading: Utilized kagglehub to download and load the dataset.

Initial Data Exploration: Employed df.head(), df.columns, df.shape, and df.info() for a preliminary understanding of the data.

Data Cleaning:

Missing Values: Filled missing values in Director, Cast, Country, and Release_Date with 'NA'. Missing Rating values were imputed with the mode (most frequent rating).

Code Snippet Explanation (df['Rating'].replace('NA', df['Rating'].mode()[0], inplace=True)): This line specifically targets the 'Rating' column. df['Rating'].mode()[0] finds the most frequent rating in that column. The replace() method then substitutes all occurrences of 'NA' (our placeholder for missing values) with this most frequent rating directly within the DataFrame (inplace=True).

Date Conversion: Converted the Release_Date column to a datetime object using pd.to_datetime(..., errors='coerce') to enable time-series analysis.

Duplicate Removal: Identified and removed duplicate rows to ensure data integrity.

Data Aggregation: Used groupby() and value_counts() to aggregate data and derive insights for trends, top directors/cast, and rating distributions.

Data Visualization: Employed matplotlib.pyplot and seaborn to create informative plots, including line charts and bar plots, to visually represent findings.

How to Run the Project
To run this analysis locally, follow these steps:

Prerequisites:

Python 3.x installed.

pip (Python package installer).

Install Libraries:
Open your terminal or command prompt and run:

pip install pandas matplotlib seaborn kagglehub

Download the Dataset:
The notebook uses kagglehub to automatically download the dataset. Ensure you have Kaggle API credentials set up if you encounter issues (though kagglehub.dataset_download often handles this seamlessly).

Execute the Jupyter Notebook:
Navigate to the directory containing your Netflix_DataAnalysis.ipynb file and run:

jupyter notebook

This will open Jupyter in your browser. You can then open and run the Netflix_DataAnalysis.ipynb notebook cell by cell.

References
Netflix Movies and TV Shows Dataset: https://www.kaggle.com/datasets/rohitgrewal/netflix-data (or the specific KaggleHub reference used)

Pandas Documentation: https://pandas.pydata.org/docs/

Matplotlib Documentation: https://matplotlib.org/stable/contents.html

Seaborn Documentation: https://seaborn.pydata.org/

KaggleHub Documentation: https://www.kaggle.com/docs/api (for dataset download)

## Note - Analaysis might not be correct as assumptions can be different based on individual, I have assumed Genre fro each film as an exact match of string from Type column. It may vary by actual analysis.

## Any Recommendations or Corrections are the best Lessons. Please do correct if any.
