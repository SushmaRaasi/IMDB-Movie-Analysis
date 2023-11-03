# IMDB-Movie-Analysis

- [Project Description](#project-description)
- [Problem](#problem)
- [Approach](#approach)
    - [Data Cleaning](#data-cleaning)
    - [Data Analysis](#data-analysis)
    - [Five 'Whys' Approach](#five-whys-approach)
    - [Report and Data Story](#report-and-data-story)
- [Tech Stack Used](#tech-stack-used)
- [Dataset](#dataset)
- [Data Cleaning](#data-cleaning)
- [Data Analysis](#data-analysis)
    - [Movie Genre Distribution and Imapct On IMDB Score](#movie-genre-distribution-and-imapct-on-imdb-score)
    - [Movie Duration Analysis](#movie-duration-analysis)
    - [Language Analysis](#language-analysis)
    - [Director Analysis](#director-analysis)
    - [Budget Analysis](#budget-analysis)
- [Result](#result)
  
### Project Description
<p>In this project, the objective is to delve into the intriguing world of movie success on IMDB and decipher the factors that contribute to high ratings. This endeavor holds substantial significance for individuals involved in the movie industry, such as producers, directors, and investors, who seek to make informed decisions about their future cinematic ventures.
</p>

### Problem
<p>The focal point of investigation revolves around understanding the elements that underpin a movie's triumph on IMDB, gauged by lofty IMDB ratings. The profound implications of this problem underscore the necessity to unravel the intricate interplay of diverse variables that shape the trajectory of a film's reception, acclaim, and popularity.</p>

### Approach
<p>This project adopts a systematic approach to decode the factors shaping a movie's success:</p>

#### Data Cleaning
<p>The initial step involves meticulous data preprocessing. This encompasses addressing missing values, eliminating duplicates, and potentially crafting new features through feature engineering to ensure the data is primed for analysis.</p>

#### Data Analysis
<p>The heart of the project lies in the thorough exploration of the dataset. By deciphering correlations between various attributes and IMDB ratings, we endeavor to uncover patterns that illuminate the anatomy of successful movies.</p>

#### Five 'Whys' Approach
<p>Employing the probing "Five 'Whys'" technique, we embark on a journey of unearthing the underlying causes. By iteratively questioning the implications of our findings, we aim to unearth the fundamental drivers behind observed trends.</p>

Q: "Why do movies with higher budgets tend to have higher ratings?"
<br>
A: They can afford better production quality.
<br>
Q: "Why does better production quality lead to higher ratings?"
<br>
A: It enhances the viewer's experience.
<br>
Q: "Why does an enhanced viewer experience lead to higher ratings?"
<br>
A: Viewers are more likely to rate a movie highly if they enjoyed watching it.
<br>
Q: "Why are viewers more likely to rate a movie highly if they enjoyed watching it?"
<br>
A: Positive experiences lead to positive reviews.
<br>
Q: "Why do positive reviews matter?"
<br>
A: They influence other viewers' decisions to watch the movie, increasing its popularity and success.
<br>

#### Report and Data Story
<p>The culmination of our analysis manifests in a comprehensive report. This narrative not only encapsulates the initial problem and our discoveries but also employs visualizations to create an engaging data story that underscores the salient insights garnered.</p>

### Tech Stack Used
<p>Using Google Sheets for data cleaning because of User-Friendly,Collaboration,Data Visualization,Formula Functions and 
Google Docs for reporting is a pragmatic choice and it is Document Creation,Collaboration,VisualEnhancements,Embed Visualizations,Accessibility especially for a project of this nature.</p>

### Dataset

[Raw Dataset](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=780410110)

<br>

[IMDB Movies Dataset After Cleaning](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1089618744)

### Data Cleaning
<p>Organizing and enhancing the presentation of your data in Google Sheets is a great way to improve readability and facilitate the analysis process. By ordering columns, highlighting headers, and applying filters, you're making it easier for yourself and others to navigate and comprehend the dataset. Here's why these actions are beneficial:</p>
<ol>
  <li>Ordered Columns:</li>
  <p>Logical Flow,EasyReference,ImprovedComprehension</p>
  <li>Highlighted Column Headers:</li>
  <p>Visual Distinction,Quick Navigation</p>
  <li>Applied Filters:</li>
  <p>Data Exploration,Focused Analysis</p>
</ol>

<ul>
  <li>Removing Duplicate Rows:</li>
  <p>Removed duplicate rows from your dataset, reducing the total number of rows from 5025 to 4980. Removing duplicates helps in ensuring data integrity and accuracy for your analysis. </p>
  <li>Identifying & Handling the Missing Values:</li>
  <ol>
    <li>Color → blank to “Not Specified”</li>
    <p><i>Reason :</i> By filling the missing values with "Not Specified," we are retaining the information while acknowledging that the specific color information is unknown. This approach is commonly used when dealing with categorical data and a small percentage of missing values. It allows us to include these rows in your analysis while maintaining data integrity and providing transparency about the missing information. </p>
    <li>Content_rating → blank to “Not Rated”</li>
    <p>Reason: By filling the missing values with “Not Rated”,is a reasonable approach, especially when dealing with a larger number of missing values. This option allows you to retain the data for analysis while indicating that the content rating information is unavailable for those specific movies.</p>

<p>Advantages of this approach include: Data Retention,Minimal Bias,Transparency
</p>

<li>Director_name —> blank to “Unknown”</li>
<p>Reason: By filling the missing values in the "director_name" column with a default label like "Unknown" is a practical approach, especially here the director's name is not a central attribute for the analysis. This option allows you to retain the data for analysis while indicating that the director's name is unavailable for those specific movies.
</p>
<p>Advantages of this approach include: Data Retention,Minimal Bias,Transparency and Consistency.</p>

<li>Duration —> blank to Average of duration based on Genre consider sheet 3 and sheet 2.</li>
<p>Reason: By filling the missing values in the "duration" column with the average duration of the available movies is a reasonable approach.
</p>
<p>Advantages of Filling with Average: Retain Data Completeness,Preserve Distribution,Mitigate Bias,Sensible Imputation.
</p>
<p>Filling the missing "duration" values based on movie genres could be a more meaningful approach compared to using the average of another unrelated attribute like "imdb_score." Since different genres might have varying typical durations, imputing missing values based on genre-specific averages can provide a more accurate representation of the data.</p>
<p>Here's approach for imputing the average value :</p>
<ul>
  <li>Group Data by Genre:</li>
  <p>Calculating  the average duration for each genre in the dataset.
We will end up with a table that lists each genre and its corresponding average duration.(simply by using the pivot table) 
</p>
  
  [Click here to see the table with average duration of each genre](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1604100845)
  <li>Match Genre and Impute:</li>
  <p>By Using Vlookup we just need to match the value with the respective Genre.</p>
 
  [Click here to see the newly created Changed Duration Column](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1975220929)
</ul>
<li>Actor_1_name → blank to “Not Specified”</li>
<li>Actor_2_name → blank to “Not Specified”</li>
<li>Actor_3_name → blank to “Not Specified”</li>
<p>Reason: By imputing missing "actor_1_name",”actor_2_name” and 	“actor_3_name” values with a placeholder like "Not Specified" is a reasonable approach, especially if you want to maintain transparency about the missing data and avoid making assumptions about actor names. This approach has the advantage of clearly indicating that the data was missing and that no specific information about the actor was available.</p>

<li>Title_year —> blank to “Not Specified”</li>
<p>Reason: By imputing the blank values in the "title_year" column to a placeholder like "Not Specified" to indicate that the release year is not specified for those movies. This approach is straightforward and transparent, making it clear to anyone reviewing the data that the release year information is missing.</p>

<li>Director_facebook_likes  —>blank to “0”
</li>
<li>Actor_1_facebook_likes  —>blank to “0”	</li>
<li>Actor_2_facebook_likes  —>blank to “0”	</li>
<li>actor_3_facebook_likes  —>blank to “0”</li>

<p>Reason : By imputing the  blank values in the "director_facebook_likes," "actor_1_facebook_likes," "actor_2_facebook_likes," and "actor_3_facebook_likes" columns with a placeholder value like "0". This approach is valid when you don't have specific information available for these fields and want to indicate that the data is missing or unknown.</p>

<li>Plot_keywords —> blank to “Not Specified”</li>
<p>Reason : Imputing the missing values in the "plot_keywords" column with a placeholder like "Not Specified" is a valid approach. This approach maintains data integrity while clearly indicating that the information is missing for those specific rows. This choice is particularly useful when we want to acknowledge the absence of specific information while still including those rows in your analysis.
</p>

<li>Facenumber_in_poster —> blank to 0</li>
<p>Reason : Imputing 0 for the missing values in the "facenumber_in_poster" column is a reasonable choice, especially if the column represents a numeric count and you want to assume that blank values indicate posters with no faces. This approach maintains the integrity of the numeric data and is straightforward to understand.</p>
<li>Language —> blank to “English”</li>
<p>Reason : As the adjacent column is indicating "USA," it's reasonable to assume that most movies released in the USA are typically in the English language. Therefore, I can input the value "English" in the blank rows of the "language" column.</p>

<li>Country —> blank to “Not Specified”
</li>
<p>Reason : Clearly indicates missing data. Preserves data integrity.
</p>
  </ol>
  <li>Exploring and Analyzing Missing Data :</li>
  <ul>
    <li>Conducted detailed analysis to understand the impact of missing data on variables/columns like "gross" and "budget."
</li>
    <li>Calculated descriptive statistics for IMDB scores based on whether "gross" and "budget" were missing or not.
</li>
    <li>Based on analysis, I have decided to impute missing values in "budget" and "gross" columns with 0, as there wasn't a significant impact on IMDB scores.</li>
  </ul>
  
  [Gross Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1530561656)

  ![gross analysis](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/cf685069-e48b-445d-a2df-e186982ff0ac)

  <br>
  
  [Budget Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=29492074)

  <li>Feature Engineering:</li>
  <p>Calculated the Profit Margin by taking the difference between gross and budget.</p>
</ul>

[IMDB Movies Dataset After Cleaning](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1089618744)

### Data Analysis
#### Movie Genre Distribution and Imapct On IMDB Score
<ul>
  <li>DataSet Overview:</li>
  <p>The provided dataset contains information about movies, including their titles, genres, and IMDB scores. The goal of this analysis is to understand the distribution of movie genres and how different genres impact IMDB scores.
</p>
  
  [Click here to see the Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1642294865)
  <li>Insights:</li>
  <p>To start the analysis, I have determined the most common genres of movies in the dataset. By using the COUNTIF function in Excel, to count the occurrences of each genre. I also handled cases where a movie belongs to multiple genres by separating and counting them individually.
</p>
<p>The top 5 most common genres in the dataset are as follows:</p>

![Common Genres](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/d3cf1ea8-e414-49aa-a361-17905a8404dc)

<li>Descriptive Statistics for IMDB Scores by Genre:
</li>
<p>For each of the top 5 genres, Icalculated descriptive statistics using Excel's relevant functions. These statistics provide insights into the central tendency, variability, and overall distribution of IMDB scores within each genre.
</p>
<p>Below are the calculated statistics for the IMDB scores in each of the top 5 genres:
</p>

![descriptive statistics](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/463dd827-4799-4bc4-8503-cbc129135ddb)

<ol>
  <li>Drama:</li>
  <ul>
    <li>With 2571 movies, Drama is the most represented genre in the dataset.
</li>
    <li>The mean IMDB score for Drama is 6.415, which suggests a moderately positive reception among audiences.
</li>
    <li>The median IMDB score of 6.9 indicates that most movies in this genre receive ratings close to this value.</li>
    <li>The mode IMDB score of 7.2 suggests that a significant number of movies have this particular rating.</li>
    <li>Drama has a wide range of scores, from 2 to 9.3, indicating diverse audience reactions.
</li>
    <li>The variance of 0.91 indicates moderate variability in ratings.
</li>
    <li>The standard deviation of 0.95 reflects the extent to which scores deviate from the mean.
</li>
    <li>Drama's ratings are distributed over a broad range, indicating varying levels of audience appreciation.</li>
  </ul>
  
 ![Drama Image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/4340c70b-ff0d-484d-87c6-ee7803653704)

<li>Comedy:</li>
<ul>
  <li>With 1862 movies, Comedy is another genre with a significant presence in the dataset.</li>
  <li>The mean IMDB score for Comedy is 6.443, indicating a generally positive reception.</li>
  <li>The median IMDB score of 6.3 suggests that Comedy movies tend to receive ratings around this value.</li>
  <li>The mode IMDB score of 6.7 suggests a peak in ratings around this point.</li>
  <li>Comedy movies have a range of scores from 1.7 to 9.5, showcasing diverse audience opinions.
</li>
  <li>The higher variance of 1.19 indicates greater variability in ratings compared to other genres.</li>
  <li>The standard deviation of 1.09 suggests a notable spread of scores around the mean.
</li>
  <li>Comedy genre exhibits a wide distribution of ratings, encompassing both high and low scores.
</li>
</ul>

  ![Comedy Image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/d8e4f692-53fd-4097-b2dd-3d9afe396520)

<li>Thriller:</li>
<ul>
  <li>Thriller is represented by 1396 movies in the dataset.</li>
  <li>The mean IMDB score for Thriller is 6.313, indicating a moderately favorable response.</li>
  <li>The median IMDB score of 6.4 suggests that most Thriller movies receive ratings around this value.</li>
  <li>The mode IMDB score of 6.1 suggests a significant number of movies with this rating.
</li>
  <li>Thriller genre's scores range from 2.2 to 9, indicating diverse audience opinions.</li>
  <li>The variance of 1.11 suggests moderate variability in Thriller movie ratings.</li>
  <li>The standard deviation of 1.05 reflects the extent of score deviation from the mean.</li>
  <li>Thriller's ratings are distributed over a moderate range, reflecting varying audience perceptions.</li>
</ul>

![Thriller Image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/53a85e17-3b40-46e9-94fb-dbc209d2ad68)

  <li>Romance:</li>
  <ul>
    <li>Romance movies are represented by 1098 entries in the dataset.
</li>
    <li>The mean IMDB score for Romance is 6.445, indicating a moderately positive reception.</li>
    <li>The median IMDB score of 6.5 suggests that Romance movies often receive ratings around this value.</li>
    <li>The mode IMDB score of 6.5 indicates a peak in ratings around this point.</li>
    <li>Romance movies have scores ranging from 2.1 to 8.6, showing varying degrees of audience appreciation.
</li>
    <li>The lower variance of 1 indicates relatively lower variability in Romance movie ratings.
</li>
    <li>The standard deviation of 1 reflects a moderate spread of scores around the mean.</li>
    <li>Romance genre's ratings exhibit a relatively compact distribution with a focus on moderate scores.</li>
  </ul>
  
  ![Romance Image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/bd084eed-145a-4d9b-b063-95258cdd4779)

  <li>Adventure:</li>
  <ul>
    <li>Adventure movies are represented by 914 entries in the dataset.</li>
    <li>The mean IMDB score for Adventure is 6.441, indicating a moderately positive reception.</li>
    <li>The median IMDB score of 6.6 suggests that most Adventure movies receive ratings around this value.</li>
    <li>The mode IMDB score of 6.7 suggests a significant number of movies with this rating.
</li>
    <li>Adventure genre's scores range from 1.9 to 8.9, reflecting diverse audience opinions.</li>
    <li>The higher variance of 1.28 indicates greater variability in Adventure movie ratings./li>
    <li>The standard deviation of 1.28 reflects a wider spread of scores around the mean.</li>
    <li>Adventure genre's ratings exhibit a wide distribution, encompassing a range of scores.</li>
  </ul>
</ol>
<li>
  Overall:
</li>
<p>From the analysis of the provided statistics, it is evident that different genres show variations in audience reception as reflected in their IMDB scores. Some genres have wider ranges of scores, while others have more compact distributions. Genres like Comedy and Adventure have higher variability in ratings, indicating diverse audience opinions, while genres like Romance have more consistent ratings. The mean, median, mode, variance, and standard deviation values provide insights into each genre's performance and audience preferences.</p>
</ul>

#### Movie Duration Analysis
<ul>
  <li>Dataset Overview:
</li>
  <p>The dataset at hand comprises information about movies, including their durations and IMDB scores. The objective of this analysis is to investigate the distribution of movie durations and discern any potential relationship between movie duration and IMDB scores.</p>
  
  [Click here to see the Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1023029157)

 ![overview](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/eeac5d12-dcbd-457c-8544-bdddb6c6f117)

  <br>
  
![imdb Vs duration image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/97546da1-b6b5-43c3-8f1e-b8ead5aaba93)

  <br>
  <li>Insights:</li>
  <p>for every additional minute in movie duration, the average IMDB score increases by approximately 0.0117 points.</p>

<p>Based on the above analysis I can interpret the positive slope value as evidence that longer movie durations are generally associated with higher IMDB scores, though the strength of this relationship might be moderate.
</p>
</ul>

#### Language Analysis
<ul>
  <li>Dataset Overview:</li>
  <p>The dataset at hand comprises information about movies, including their Languages and IMDB scores.The objective of this analysis is to Analyze the distribution of movies based on their language and its impact on IMDb scores can provide valuable insights into the preferences of audiences.</p>
  
  <li>Insights:</li>

  [Click here to see the Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1577361208)

<br>
 
  ![count of movies](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/cab4218f-ead9-4a6a-8f47-d3b1e0dd0079)

<br>
  <p>Based on the Above BarChart I have presented my analysis of the common languages ( top 5 ).
</p>

[click here to view the top 5 movies info](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1412770151)

<br>

![movies vs Language image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/ec38bac1-b1cb-4b4a-bee5-3c269fac1a7e)

<br>

![imdb scores vs Language](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/5e763043-ceb6-46d6-8ab6-c4f9153563c1)

<br>
<ol>
  <li>English:</li>
  
  ![english 1](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/c458a340-e224-47f0-9f55-95d12d22555f)

  <br>
  
![english 2](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/ccf8c7b9-910c-4084-b048-869fd3d9b13e)

  <p>Overall, an average rating of 6.4, a median of 6.5, and a low standard deviation of 1.12 collectively suggest that movies in this language receive ratings that are moderately positive, consistently clustered around the central value, and have relatively low variability in audience opinions. Audiences generally have similar expectations when it comes to the quality of movies in this language, and there are fewer extreme ratings that significantly deviate from the central tendency.
</p>

  <li>French:</li>
  
  ![French 1](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/d5334ffd-0ff4-4d99-9e6d-7ae13f8000f8)

  <br>
  
![French 2](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/c3292f63-d1cd-4d8c-991f-62626eee1642)

  <br>
  <p>Overall, an average rating of 7.04, a median of 7.2, and a low standard deviation of 0.73 collectively suggest that movies in this language tend to receive ratings that are above average, consistently clustered around the central value, and have relatively low variability in audience opinions. Audiences generally have similar, positive expectations when it comes to the quality of movies in this language, with very few extreme ratings that deviate significantly from the central tendency.</p>

  <li>Spanish:</li>
  
![spanish 1 image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/4784f67e-fcb7-443a-8a7b-1752f03ed4da)

<br>

![spanish 2 image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/0ec82c1f-4439-487a-8390-a61da0e250db)

<br>
<p>Overall, an average rating of 6.94, a median of 7.15, and a low standard deviation of 0.86 collectively suggest that movies in this language tend to receive ratings that are above average, consistently clustered around the central value, and have relatively low variability in audience opinions. Audiences generally have similar, positive expectations when it comes to the quality of movies in this language, with very few extreme ratings that deviate significantly from the central tendency.</p>

<li>Hindi:</li>

![hindi 1 image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/26ae29a8-b6a2-4354-b626-43c8a6eb6f39)

<br>

![hindi 2 image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/1e658248-6145-47f9-800f-1f2590d532f0)

<br>
<p>Overall, an average rating of 6.63, a median of 6.95, and a relatively high standard deviation of 1.4 collectively suggest that movies in this language category tend to have ratings that are slightly below the median of the entire dataset. Additionally, there is considerable variability in audience opinions, with a notable presence of both high and low ratings. Audiences might have a more diverse range of experiences when watching movies in this language, with less predictability in terms of quality compared to languages with lower standard deviations and more symmetric distributions.
</p>

<li>Mandarin:</li>

![mandarin 1 image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/5de3f8fa-3595-417f-85b2-c40ee1e4f86e)

<br>

![mandarin 2 image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/6ec5756d-dfca-4df4-ba66-bf74228d7266)

<br>
<p>Overall, an average rating of 6.79, a median of 7.05, and a moderate standard deviation of 1.04 collectively suggest that movies in this language tend to have ratings that are slightly above average. While there is some variability in audience opinions and a mix of ratings, the majority of movies in this language fall within a moderate range of ratings. Audiences might have a moderate level of predictability in terms of quality when watching movies in this language, with slightly more consistency in ratings compared to languages with higher standard deviations and more negatively skewed distributions.
</p>
</ol>

#### Director Analysis:</li>
<ul>
  <li>Dataset Overview:
</li>
  <p>The main objective is to analyze the influence of directors on movie ratings and identifying the top directors is a valuable task in understanding the impact of filmmakers on a movie's success.</p>
  <li>Data Preparation:</li>
  <p>Creating a new column to calculate the average IMDb score for each director. By using Pivot table Feature.</p>
  
  [Pivot Table Info](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1700369999)

  <li>Identify Top Directors:</li>
  <p>Calculate the 90th percentile score for the average IMDb scores to determine the threshold for selecting top directors.By using PERCENTILE Function.
</p>

[Top Directors Info](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=450148558)

<li>Compare Top Directors to Overall Distribution:</li>

[Click here to see the Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1532100628)
<ul>
  <li>Create a Histogram
</li>
  
  ![imdb score Vs directors average image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/621c46e7-7d9c-493b-b620-b62d92854f05)

  <br>
  <li>Summary Statistics</li>
  
![summary stats](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/5c0560a4-290a-4c02-a1a7-600ffcb09a09)

  <br>
  <p>Based on the summary statistics, here are some interpretations:
</p>
  <ul>
    <li>Movies directed by top directors tend to have higher IMDb scores on average (7.883) compared to all movies (6.441).
</li>
    <li>The IMDb scores for top directors' movies exhibit less variability (low standard deviation) compared to the overall distribution, indicating that they constantly receive higher ratings.</li>
  </ul>
</ul>
</ul>

#### Budget Analysis
<ul>
  <li>
    Dataset Overview:
  </li>
  <p>With the correlation coefficient, and identification of movies with the highest profit margin, These insights help to find the financial performance and the relationship between budgets and earnings in the movie dataset.</p>
  
  <li>Correlation Analysis:
</li>

![correlation image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/f92b82a7-fb48-4bd5-bda1-d668a6505283)

<ul>
   <li>The correlation coefficient of 0.12.</li>
   <li>The positive sign (+0.12) indicates that there is a positive relationship between movie budgets and gross earnings. In other words, as movie budgets increase, there is a tendency for gross earnings to increase, but the relationship is not strong.
</li>
   <li>The magnitude of 0.122 is relatively close to zero. This suggests that the correlation between budgets and gross earnings is weak. In practical terms, the increase in budgets does not strongly predict an increase in gross earnings, and vice versa.</li>
   <li>The weak correlation could indicate that other factors, such as movie quality, marketing, release timing, and audience reception, might have a more significant impact on gross earnings than budgets alone.</li>
</ul>

  <li>Profit Margin Analysis:
</li>
<p>The profit margin represents the financial success of each movie.</p>

![profit margin analysis image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/09a49fcd-3306-4c94-bfae-3b6476f3efa2)

<br>
<p>The movie with the highest profit margin is Avatar with a profit Margin as 523505847.</p>

![max profit image image](https://github.com/SushmaRaasi/IMDB-Movie-Analysis/assets/79751402/451fbec2-0f7c-483d-bb16-88e0d3efa81a)

<br>

[click here to see the Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=629714056)

</ul>

### Result
<p>In conclusion, The analysis demonstrates that a combination of factors, including genre, duration, language, director, budget, and profit margin, collectively shapes a movie's success on IMDb. These insights are invaluable to stakeholders in the film industry, enabling them to make data-driven decisions when producing, directing, and investing in future cinematic ventures.From this project I learnt the need of data filtration and how to generate deeper insights for a problem mentioned.
</p>


























