# Amazon Prime Tv and Movie Videos (1920 -2021)


## Table of Contents

- [Project Overview](#project-overview)
- [Source](#source)
- [Tools](#tools)
- [Columns in Dataset](#columns-in-dataset)
- [Data Preparation](#data-preparation)
- [Steps followed](#steps-followed)
- [Descriptive Data Analysis](#descriptive-data-analysis)
- [Dashboard Overview](#dashboard-overview)
- [Cards for Summary Statistics](#cards-for-summary-statistics)
- [Visualizations](#visualizations)
- [Insights](#insights)
- [Recommendations](#recommendations)
- [Conclusion](#conclusion)



### Project Overview

A descriptive data analysis dashboard designed to visualize the various metrics in an amazon prime videos dataset between a time period with elements of an exploratory data analysis(EDA) to uncover the trends in the dataset.


## Source

Data was optained by web scrapping from Kaggle [https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows]. It contains information about various movies and TV shows available on Amazon Prime Video, including titles, genres, ratings, release dates, and more.


## Tools

- Excel - Data Cleaning and analysis
- Power BI - Further analysis and visalization

  
 ## Columns in Dataset
  
 Show_Id, type, title, director,cast, country, date_added, release_year, rating, duration, listed_in and description.


## Data Preparation
  
Dataset needed minimal cleaning to maintain high level of integriy.

## Steps followed

1. Standardized column names for easy navigation of dataset
2. Removed duplicates based on unique identifiers (Show_id and titles).
3. Handled empty cells by replacing them with null and unknown for columns such as release date and date added.
4. Outliers were not established as numeric fields were limited to release and date added.


 ## Descriptive Data Analysis

 The analysis explored the dataset to answer key questions such as:

 1. What is the most preferred content?
 2. What are the most preferred genres?
 3. Which locations viewed the most contents?
 4. Which ratings are most preferred?

 
## Dashboard Overview

Dashbaord Snap_Shot: ![Screenshot 2024-11-20 150725](https://github.com/user-attachments/assets/40b218b3-2be1-4219-9e99-5913b533b612)


## Visualizations:

Ratings Distribution:  A bar chart to show ratings across all titles, helping to understand the general quality perception.

Genres Distribution:   A bar chart to displays the breakdown of genres which highlights content diversity.

Geographical Distribution:  A map visual to illustrate the number of shows available by country as well as the country's predominant genres.

Content Type (TV vs. Movies):  A doughnut chart to compare the count of TV shows and movies.

Release Trends:  An area chart to visualise the number of titles released over time


## Insights

Ratings Per Total Show
 
Count of show_id was highest for 13+ at 2,117, followed by 16+ and ALL.
﻿﻿Across all 25 rating, Count of show_id ranged from 1 to 2,117.﻿﻿

Genres Per total show

﻿Across all 512 genres, the show_id's ranged from 1 to 959.
Drama shows were viewed the most withing the time period of the dataset at 959, followed by Comedy and Drama, Suspense.﻿﻿

Movie shows and Tv shows

﻿Movie shows appeared to be preferred much more over Tv shows. That is (7,814) for movie shows and (1,854) TV Show.

Total Shows Per Release

Movies seem to be much preferred on the streaming site within 1920 to 2021 with the average of movies viewed withing that period to be 78.14 higher than tv shows which is 31.42. In ﻿2021 movie shows made up 11.78% of the overall shows viewed on Amazon Prime. In 2021, the count of movies surpassed tv shows by 836, marking the it largest divergence between the two categories.

Countries Per Total shows and Genre

The United States has the highest number of Show IDs at 341, accounting for a significant portion of the total shows available across countries. This reflects the prominence of U.S. content in the dataset. The most prevalent genre across the top countries is action, as seen in the USA, UK, France, Germany, and others. This suggests that action is a leading genre in global entertainment, especially in these regions India (246 Show IDs) shares a similar preference for action genre, underlining its significant market for action-based content. United Kingdom (62 Show IDs) also primarily favors action genre, consistent with global trends. Canada (35 Show IDs) showcases a blend of action and drama genres, indicating a diverse taste in programs. France (16 Show IDs) has a high concentration of action content, reflecting its growing demand for this genre. Germany (15 Show IDs) presents a broader genre range, including action, adventure, and drama, signaling that German audiences enjoy a more varied selection of content. Italy (11 Show IDs) showcases action, drama, and fantasy genres, indicating a diverse cultural preference, with action being the most dominant.
With Action being the dominant genre across all these countries (USA, India, UK, Canada, France, Germany, and Italy), it highlights the universal appeal of action-packed content across these regions..



## Recommendations


﻿Ratings Distribution:
 
Per the visualization, people prefer shows rated 13+ the most. With over 2,100 shows in that category, it’s clear that content for teens and older viewers is popular. The 16+ and ALL ratings also have a decent following, so it’s a good idea to keep offering content for these age groups. Since there’s a wide range of ratings (from 1 to 2,117), it's worth thinking about how to target different groups with specific types of content that match their age and preferences.

Genres Distribution:

Drama is by far the most popular genre, a continous growth in drama contents will yield more views. Comedy and suspense are also doing well, so it would be smart to create more shows in these genres too.  Since Drama is the top genre, consider expanding on that, but also try mixing genres. For example, creating a drama-comedy, or drama-action hybrid could attract more viewers.

Geographical Distribution:

The USA has the most shows, but there are other countries like India, the UK, and Canada where people are also watching a lot of content. Think about tailoring content to these countries to match their tastes. Countries like France, Germany, and Italy are growing markets, so adding more content that fits their preferences could really help increase viewership there.

Content Type (TV vs. Movies):

Movies are much more popular than TV shows, so it’s a good idea to keep focusing on movies. That said, adding a few more TV shows to the mix wouldn’t hurt since there are still people who enjoy them. Even though movies are taking the lead right now, it’s good to keep an eye on TV shows as they might come back in popularity. Offering a good balance between movies and TV could help attract a wider audience.

Release Trends:

From 1920 to 2021, movies were more popular, and in 2021, they really took off. This shows a shift in what people want to watch, so it might bea good idea to focus on movie releases for the next couple of years. Stay on top of trends and keep adjusting content to what people are watching most right now. It’s also helpful to prepare for future shifts in viewing habits.

Total Shows per Country and Genre:

The USA has the highest number of shows, and action is the most popular genre. So, it will be advisable to keep investing in action content for countries like the USA, India, and the UK. It’s also worth creating more localized content for countries like France, Germany, and Italy, where action and Drama are popular. Customizing content to these regions could help attract more viewers.

Action Genre is a Global Phenomenon:

Since action is popular everywhere, it’s a good idea to keep focusing on it. But you could also experiment with combining it with other genres like Comedy or Adventure to make it even more exciting for different types of viewers. Collaborating with well-known action franchises or creators could bring in more viewers who love that genre. Exclusive Action shows could become a big draw.


## Conclusion

In this Amazon Prime Video Dashboard project, we explored content trends by looking at where shows are most popular, which genres people enjoy, ratings, and release dates. The analysis showed that the United States and India have the most content on the platform, with action being a popular genre worldwide. Movies are generally more popular than TV shows, and certain genres and ratings appeal to different regions and age groups. The insights suggest that Amazon Prime Video could benefit from adding more diverse content and focusing on regional preferences to keep viewers engaged. This project highlights how data can be used to understand what audiences enjoy, helping Amazon Prime Video plan content and grow its reach more effectively.
