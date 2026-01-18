# Netflix Movies & TV Shows - Exploratory Data Analysis Report

## Introduction

The Netflix Movies & TV Shows dataset is a comprehensive collection of content information from the popular streaming platform. This dataset contains detailed records about thousands of movies and TV shows available on Netflix, including essential metadata like content type (whether it's a movie or TV show), production countries, release year, the date it was added to Netflix, content ratings, duration, and genres. By analyzing this data, we can gain valuable insights into Netflix's content strategy, trends in content acquisition, and how the platform's library has evolved over time.

## Dataset Understanding

The dataset contains approximately 8,800 rows and 12 columns, with each row representing a unique piece of content on Netflix. The key columns that were crucial for this analysis include:

- **type**: Distinguishes between Movies and TV Shows
- **country**: Lists the production country or countries
- **release_year**: The year the content was originally released
- **date_added**: The date the content was added to Netflix
- **rating**: Content rating (like PG, R, TV-MA, etc.)
- **duration**: How long the content is
- **listed_in**: The genres or categories the content belongs to

These columns provided the foundation for understanding Netflix's content library and the patterns within it.

## Data Issues and Challenges

Like most real-world datasets, the Netflix data had several challenges that needed to be addressed. One of the most common problems was missing values. Some entries were missing information about the country where content was produced, which is important for geographic analysis. Additionally, some titles didn't have a content rating assigned, which would complicate our analysis of content maturity levels.

Another significant challenge was that multiple values existed in single columns. For example, the country column often contained multiple countries separated by commas (like "United States, Canada, Mexico"), and the listed_in column had multiple genres listed the same way. This required special handling to properly count individual countries and genres separately.

Date formatting was also an issue. The date_added column had some inconsistent formatting and missing dates that needed to be converted into a proper datetime format for time-series analysis.

## Data Cleaning and Preprocessing

To make the data usable for analysis, several cleaning steps were necessary. First, all missing values in the country column were filled with 'Unknown' to preserve the total dataset size without losing information. Similarly, missing values in the rating column were filled with 'Not Rated'. This approach ensured we didn't lose valuable data rows and could still analyze the complete dataset.

The date_added column was converted to a proper datetime format using pandas' datetime conversion with error handling. This conversion allowed us to extract meaningful time information and identify temporal patterns. From this datetime column, we created a new feature called year_added, which represents the year each piece of content was added to Netflix. This year_added column became invaluable for analyzing how Netflix's content acquisition strategy has changed over time.

Importantly, no rows were dropped during this cleaning process. Instead of removing entries with missing values, we chose to fill them with meaningful placeholders. This decision allowed us to maintain the integrity of the dataset and include all available information in our analysis.

## Exploratory Data Analysis (EDA)

The exploratory phase of our analysis revealed fascinating patterns in Netflix's content library. When we analyzed Movies versus TV Shows, we found a clear distribution between the two types of content. This comparison helped us understand Netflix's strategic focus and whether the platform prioritizes one format over the other.

For country-wise analysis, we examined which countries produce the most content on Netflix. Since many titles are co-productions involving multiple countries, we properly split and expanded the country data to count each country's contribution individually. This revealed which nations are Netflix's primary content sources and helped us understand the global nature of the platform's library.

The year-wise content growth analysis showed us how Netflix's acquisition strategy has evolved. By plotting the number of titles added each year, we could see clear trends in growth, plateaus, and potential shifts in strategy. This timeline visualization was particularly useful for understanding how Netflix has scaled its content library over the platform's lifetime.

We also analyzed content ratings and genres separately. The ratings analysis showed which content maturity levels are most common on the platform, while the genre analysis revealed the most popular content categories. Both of these analyses required us to handle the comma-separated genre data by expanding it properly.

## Feature Engineering and Advanced Analysis

Beyond basic exploration, we engineered new features to uncover deeper insights. The Content Age feature was created by calculating the difference between year_added and release_year. This tells us how old content typically is when Netflix adds it to the platform. By comparing average content age between movies and TV shows, we discovered whether Netflix tends to add newer releases or older classics, and whether this strategy differs between content types.

Genre diversity analysis over time revealed how the variety of content genres available on Netflix has changed year by year. By counting the number of unique genres present each year, we could see if Netflix is expanding its genre offerings or maintaining a stable portfolio. This metric is an indicator of content breadth and platform diversity.

Country dependency analysis took a different approach by examining percentage shares instead of raw counts. Rather than just knowing which countries produce the most content, we calculated what percentage of Netflix's total content comes from each country. This percentage-based view normalized the data and gave us a clearer picture of Netflix's reliance on specific regions.

The mature content trend analysis was particularly interesting. We defined mature content as titles with ratings of TV-MA, R, or NC-17, and then tracked how the percentage of mature content has changed over time. Importantly, we analyzed this separately for movies and TV shows, since the platforms' strategies for each format might differ. This analysis revealed whether Netflix is shifting toward or away from mature content.

## Visualizations

Throughout this analysis, we used several types of visualizations to effectively communicate patterns in the data. Bar charts were used to compare categories like movie versus TV show counts, top countries, and top ratings. These charts made it easy to see which categories dominated the dataset at a glance.

Line charts with filled areas were particularly useful for showing trends over time, such as the number of titles added per year and genre diversity trends. The visual representation of these trends made it much easier to spot increases, decreases, and inflection points compared to just reading raw numbers.

Horizontal bar charts were used when displaying ranked data like top countries and top genres, since horizontal layouts work well for labels. These visualizations made it simple to compare multiple categories and rank them simultaneously.

The choice of these visualization types was deliberate. Each type was selected because it effectively highlighted the specific patterns we were trying to understand, making the data story more compelling and easier to follow than statistics alone.

## Final Insights and Results

Our analysis revealed several important insights about Netflix's content strategy. First, Netflix has experienced significant growth in content acquisition over the years, with certain years showing peaks in acquisitions, likely reflecting strategic business decisions.

Geographically, Netflix's content is dominated by a few key countries, particularly the United States and India, but content comes from diverse regions around the world. This indicates Netflix's global production strategy, though there is clear geographic concentration.

When comparing movies and TV shows, we found distinct patterns in how Netflix handles each format. The content age difference between movies and TV shows suggests different acquisition strategies, with potential explanations related to production timelines and licensing agreements.

The trend in mature content over time shows shifting market dynamics. Some content types have seen changes in their representation on the platform, which could reflect both Netflix's strategic decisions and changes in the entertainment industry overall.

Genre diversity has been a consistent aspect of Netflix's platform, with the company maintaining a broad range of content categories to appeal to different audience segments.

## Conclusion

This exploratory data analysis of Netflix's content library provides a comprehensive view of how the platform has built and managed its content strategy over time. By analyzing patterns in geographic distribution, content type, ratings, and genres, we can understand not only what Netflix offers today but also how their strategy has evolved.

The insights from this analysis suggest that Netflix is a truly global platform that carefully balances multiple content types, maintains geographic diversity in its acquisitions, and actively manages the maturity profile of its library. The platform's growth in recent years, combined with its focus on content diversity, demonstrates a thoughtful approach to building an entertainment destination.

This kind of data analysis is valuable because it helps us understand the decisions behind the streaming services we use daily. Whether you're curious about Netflix's business strategy, interested in how data-driven decision-making works, or just fascinated by content trends, this analysis provides concrete evidence of the patterns shaping modern entertainment streaming.
