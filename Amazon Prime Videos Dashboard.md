-A Descriptive Analysis of the Tv and Movies shows on Amazon Prime from 1920 to 2021.

Dashboard Link : https://app.powerbi.com/groups/me/reports/384d017e-e935-44dc-9e7d-1626c1a36de1/ReportSection

Problem Statement
The dashboard is designed to visuals the various metrics in an amazon prime videos dataset between a time period with elements of an exploratory data analysis(EDA) to uncover the trends in the dataset.

- Source:
- Coulmns:
   Show_Id, type, title, director,cast, country, date_added, release_year, rating, duration, listed_in and description.

- Data Prepartion
Dataset needed minimal cleaning to maintain high level of analysis.
Steps followed
Step 1 : Standardized column names for easy navigation of dataset

-Data Cleaning and transformation: removed duplicates  based on unique identifiers (Show_id and titles). 
 Handled empty cells by replacing them with null and unkown for columns such as release date and date added.
-Outlier Detection: 
 Outliers were not established as numeric fields were limited to release and date added.

Dashboard Overview
Dashbaord Snap_Shot:![Screenshot 2024-11-14 134038](https://github.com/user-attachments/assets/1deb5004-8430-42b0-91c3-3141d15f54cf)
Cards for Summary Statistics
Total Titles: Snap_shot ![Screenshot 2024-11-13 175059](https://github.com/user-attachments/assets/16658dd8-a61b-453e-95b3-e75ce1d3d004)
Total Genres: Snap_shot ![Screenshot 2024-11-13 175211](https://github.com/user-attachments/assets/152ae772-9cf0-4f81-a202-d1b2db0455bc)
Total Directors: Snap_shot ![Screenshot 2024-11-14 123009](https://github.com/user-attachments/assets/fd9f1b68-3a0f-4486-a2fe-eea3c1f1cc05)
Total Ratings:Snap_shot ![Screenshot 2024-11-13 175158](https://github.com/user-attachments/assets/b842be83-b63d-4ef8-8041-538e2f262daa)
Date Range (Start and End Years): Snap_shot ![Screenshot 2024-11-13 175230](https://github.com/user-attachments/assets/118d993e-58c1-48b7-a46b-4d3fcf3699eb), 
![Screenshot 2024-11-13 175237](https://github.com/user-attachments/assets/9eb41ab6-6dbe-44ca-aa84-d637c5fdedd1)

Visualizations:
Ratings Distribution: A bar chart to show ratings across all titles, helping to understand the general quality perception.
Genres Distribution:A bar chart to displays the breakdown of genres which highlights content diversity.
Geographical Distribution: A map visual to illustrate the number of shows available by country as well as the country's predominent genres.
Content Type (TV vs. Movies): A doughnut chart to compare the count of TV shows and movies.
Release Trends: An area chart to visualize the number of titles released over time

Insights
Ratings Per Total Show
Count of show_id was highest for 13+ at 2,117, followed by 16+ and ALL.
﻿﻿Across all 25 rating, Count of show_id ranged from 1 to 2,117.﻿﻿

Genres Per total show
﻿Across all 512 genres,The show_id ranged from 1 to 959.
Drama shows were viewed the most withing the time period of the datset at 959, followed by Comedy and Drama, Suspense.﻿﻿

Movie shows and Tv shows
﻿Movie shows appeared to be preferred much more over Tv shows.That is,(7,814) for movie shows and (1,854) TV Show.

Total Shows Per Release
Movies seem to be much prefered on the streaming site within 1920 to 2021 with the average of movies viewed withing that period to be 78.14 higher than tv shows which is 31.42.
﻿2021 movie shows made up 11.78% of the overall shows viewed on Amazon Prime. 
In 2021, the count of movies surpassed tv shows by 836, marking the it largest divergence between the two categories.

Countries Per Total shows and Genre
USA dominates show IDs:
The United States has the highest number of Show IDs at 341, accounting for a significant portion of the total shows available across countries. This reflects the prominence of U.S. content in the dataset.
Most Popular Genre:
The most prevalent genre across the top countries is Action, as seen with the USA, UK, France, Germany, and others. This suggests that Action is a leading genre in global entertainment, especially in these regions.
Genre Preferences by Country:
India (246 Show IDs) shares a similar preference for Action genre, underlining its significant market for action-based content.
United Kingdom (62 Show IDs) also primarily favors Action genre, consistent with global trends.
Canada (35 Show IDs) showcases a blend of Action and Drama genres, indicating a diverse taste in programming.
Emerging Markets for Diverse Genres:
France (16 Show IDs) has a high concentration of Action content, reflecting its growing demand for this genre.
Germany (15 Show IDs) presents a broader genre range, including Action, Adventure, and Drama, signaling that German audiences enjoy a more varied selection of content.
Italy (11 Show IDs) showcases Action, Drama, and Fantasy genres, indicating a diverse cultural preference, with Action being the most dominant.
Action Genre is a Global Phenomenon:
With Action being the dominant genre across all these countries (USA, India, UK, Canada, France, Germany, and Italy), it highlights the universal appeal of action-packed content worldwide.

﻿Ratings Distribution:
What to Do: It looks like people really enjoy shows rated 13+ the most. With over 2,100 shows in that category, it’s clear that content for teens and older viewers is popular. The 16+ and ALL ratings also have a decent following, so it’s a good idea to keep offering content for these age groups.
Target Audience: Since there’s a wide range of ratings (from 1 to 2,117), it's worth thinking about how to target different groups with specific types of content that match their age and preferences.

Genres Distribution:
What to Do: Drama is by far the most popular genre, so keep making more drama content—it’s what people want! Comedy and Suspense are also doing well, so it would be smart to create more shows in these genres too.
Content Strategy: Since Drama is the top genre, consider expanding on that, but also try mixing genres. For example, creating a drama-comedy, or drama-action hybrid could attract more viewers.

Geographical Distribution:
What to Do: The USA has the most shows, but there are other countries like India, the UK, and Canada where people are also watching a lot of content. Think about tailoring content to these countries to match their tastes.
Market Expansion: Countries like France, Germany, and Italy are growing markets, so adding more content that fits their preferences could really help increase viewership there.

Content Type (TV vs. Movies):
What to Do: Movies are much more popular than TV shows, so it’s a good idea to keep focusing on movies. That said, adding a few more TV shows to the mix wouldn’t hurt since there are still people who enjoy them.
Content Expansion: Even though movies are taking the lead right now, it’s good to keep an eye on TV shows as they might come back in popularity. Offering a good balance between movies and TV could help attract a wider audience.

Release Trends:
What to Do: From 1920 to 2021, movies were more popular, and in 2021, they really took off. This shows a shift in what people want to watch, so it might be smart to focus on movie releases for the next couple of years.
Trend Analysis: Stay on top of trends and keep adjusting your content to what people are watching most right now. It’s also helpful to prepare for future shifts in viewing habits.

Total Shows per Country and Genre:
What to Do: The USA has the highest number of shows, and Action is the most popular genre there. So, it makes sense to keep investing in Action content for countries like the USA, India, and the UK.
Local Content: It’s also worth creating more localized content for countries like France, Germany, and Italy, where Action and Drama are popular. Customizing content to these regions could help attract more viewers.

Action Genre is a Global Phenomenon:
What to Do: Since Action is popular everywhere, it’s a good idea to keep focusing on it. But you could also experiment with combining it with other genres like Comedy or Adventure to make it even more exciting for different types of viewers.
Content Partnerships: Collaborating with well-known Action franchises or creators could bring in more viewers who love that genre. Exclusive Action shows could become a big draw.

