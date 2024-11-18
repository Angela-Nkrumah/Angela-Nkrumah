1.A Descriptive Analysis of the Tv and Movies shows on Amazon Prime from 1920 to 2021.

2.Problem Statement

3.The dashboard is designed to visualise the various metrics in an amazon prime videos dataset between a time period with elements of an exploratory data analysis(EDA) to uncover the trends in the dataset.

4.Source: Data was optained by web scrapping from Kaggle [https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows]. It contains information about various movies and TV shows available on Amazon Prime Video, including titles, genres, ratings, release dates, and more.
  
 Columns:
  
 Show_Id, type, title, director,cast, country, date_added, release_year, rating, duration, listed_in and description.

5.Data Preparation
  
Dataset needed minimal cleaning to maintain high level of integriy.

Steps followed
Step 1 : Standardized column names for easy navigation of dataset

Data Cleaning and transformation: removed duplicates based on unique identifiers (Show_id and titles). 
Handled empty cells by replacing them with null and unknown for columns such as release date and date added.
Outlier Detection: 
Outliers were not established as numeric fields were limited to release and date added.

Dashboard Overview

5.Dashbaord Snap_Shot:![Screenshot 2024-11-14 134038](https://github.com/user-attachments/assets/1deb5004-8430-42b0-91c3-3141d15f54cf)
Cards for Summary Statistics

 ![Screenshot 2024-11-18 195815](https://github.com/user-attachments/assets/790435f9-5933-4a74-9a68-dfa02ed5ad6d)
 ![Screenshot 2024-11-18 200104](https://github.com/user-attachments/assets/f7b38f8d-42a6-431a-af5e-a5d78d16287b)
 ![Screenshot 2024-11-18 200132](https://github.com/user-attachments/assets/50b68233-9cf9-4e99-88f4-028c1305d211)
 ![Screenshot 2024-11-18 200147](https://github.com/user-attachments/assets/21c7a6b2-a776-4496-9f25-c1bbd5a24dc3)
 ![Screenshot 2024-11-18 200205](https://github.com/user-attachments/assets/e122fcf5-ea84-4cbc-be6a-51642945aeeb)
 ![Screenshot 2024-11-18 200218](https://github.com/user-attachments/assets/1dc868fa-3fa6-4dac-b02b-7e241d688579)
 
6.Visualizations:

Ratings Distribution: A bar chart to show ratings across all titles, helping to understand the general quality perception.
Genres Distribution: A bar chart to displays the breakdown of genres which highlights content diversity.
Geographical Distribution: A map visual to illustrate the number of shows available by country as well as the country's predominant genres.
Content Type (TV vs. Movies): A doughnut chart to compare the count of TV shows and movies.
Release Trends: An area chart to visualise the number of titles released over time

7.Insights

Ratings Per Total Show

Count of show_id was highest for 13+ at 2,117, followed by 16+ and ALL.
﻿﻿Across all 25 rating, Count of show_id ranged from 1 to 2,117.﻿﻿

Genres Per total show

﻿Across all 512 genres, the show_id's ranged from 1 to 959.
Drama shows were viewed the most withing the time period of the dataset at 959, followed by Comedy and Drama, Suspense.﻿﻿

Movie shows and Tv shows

﻿Movie shows appeared to be preferred much more over Tv shows. That is (7,814) for movie shows and (1,854) TV Show.

Total Shows Per Release

Movies seem to be much preferred on the streaming site within 1920 to 2021 with the average of movies viewed withing that period to be 78.14 higher than tv shows which is 31.42.
﻿2021 movie shows made up 11.78% of the overall shows viewed on Amazon Prime. 
In 2021, the count of movies surpassed tv shows by 836, marking the it largest divergence between the two categories.

Countries Per Total shows and Genre

USA dominates show IDs:
The United States has the highest number of Show IDs at 341, accounting for a significant portion of the total shows available across countries. This reflects the prominence of U.S. content in the dataset.
Most Popular Genre:
The most prevalent genre across the top countries is action, as seen with the USA, UK, France, Germany, and others. This suggests that action is a leading genre in global entertainment, especially in these regions.
Genre Preferences by Country:
India (246 Show IDs) shares a similar preference for action genre, underlining its significant market for action-based content.
United Kingdom (62 Show IDs) also primarily favors action genre, consistent with global trends.
Canada (35 Show IDs) showcases a blend of action and drama genres, indicating a diverse taste in programming.
Emerging Markets for Diverse Genres:
France (16 Show IDs) has a high concentration ofaAction content, reflecting its growing demand for this genre.
Germany (15 Show IDs) presents a broader genre range, including action, adventure, and drama, signaling that German audiences enjoy a more varied selection of content.
Italy (11 Show IDs) showcases action, Drama, and fantasy genres, indicating a diverse cultural preference, with Action being the most dominant.
Action Genre is a Global Phenomenon:
With Action being the dominant genre across all these countries (USA, India, UK, Canada, France, Germany, and Italy), it highlights the universal appeal of action-packed content worldwide.

﻿Ratings Distribution:
 
It looks like people really enjoy shows rated 13+ the most. With over 2,100 shows in that category, it’s clear that content for teens and older viewers is popular. The 16+ and ALL ratings also have a decent following, so it’s a good idea to keep offering content for these age groups.
Target Audience: Since there’s a wide range of ratings (from 1 to 2,117), it's worth thinking about how to target different groups with specific types of content that match their age and preferences.

Genres Distribution:

Drama is by far the most popular genre, so keep making more drama content—it’s what people want! Comedy and Suspense are also doing well, so it would be smart to create more shows in these genres too.
Content Strategy: Since Drama is the top genre, consider expanding on that, but also try mixing genres. For example, creating a drama-comedy, or drama-action hybrid could attract more viewers.

Geographical Distribution:

The USA has the most shows, but there are other countries like India, the UK, and Canada where people are also watching a lot of content. Think about tailoring content to these countries to match their tastes.
Market Expansion: Countries like France, Germany, and Italy are growing markets, so adding more content that fits their preferences could really help increase viewership there.

Content Type (TV vs. Movies):

 Movies are much more popular than TV shows, so it’s a good idea to keep focusing on movies. That said, adding a few more TV shows to the mix wouldn’t hurt since there are still people who enjoy them.
Content Expansion: Even though movies are taking the lead right now, it’s good to keep an eye on TV shows as they might come back in popularity. Offering a good balance between movies and TV could help attract a wider audience.

Release Trends:

From 1920 to 2021, movies were more popular, and in 2021, they really took off. This shows a shift in what people want to watch, so it might be smart to focus on movie releases for the next couple of years.
Trend Analysis: Stay on top of trends and keep adjusting your content to what people are watching most right now. It’s also helpful to prepare for future shifts in viewing habits.

Total Shows per Country and Genre:

The USA has the highest number of shows, and Action is the most popular genre there. So, it makes sense to keep investing in Action content for countries like the USA, India, and the UK.
Local Content: It’s also worth creating more localized content for countries like France, Germany, and Italy, where Action and Drama are popular. Customizing content to these regions could help attract more viewers.

Action Genre is a Global Phenomenon:

Since Action is popular everywhere, it’s a good idea to keep focusing on it. But you could also experiment with combining it with other genres like Comedy or Adventure to make it even more exciting for different types of viewers.
Content Partnerships: Collaborating with well-known Action franchises or creators could bring in more viewers who love that genre. Exclusive Action shows could become a big draw.

8.Conclusion

In this Amazon Prime Video Dashboard project, we explored content trends by looking at where shows are most popular, which genres people enjoy, ratings, and release dates. The analysis showed that the United States and India have the most content on the platform, with action being a popular genre worldwide. Movies are generally more popular than TV shows, and certain genres and ratings appeal to different regions and age groups. The insights suggest that Amazon Prime Video could benefit from adding more diverse content and focusing on regional preferences to keep viewers engaged. This project highlights how data can be used to understand what audiences enjoy, helping Amazon Prime Video plan content and grow its reach more effectively.
