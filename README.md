# IMDB-Movie-Analysis

### Project Decription
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

  image

  <br>
  
  [Budget Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=29492074)

  <li>Feature Engineering:</li>
  <p>Calculated the Profit Margin by taking the difference between gross and budget.</p>
</ul>

[IMDB Movies Dataset After Cleaning](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1089618744)

### Data Analysis
#### 1 Movie Genre Distribution and Imapct On IMDB Score
<ul>
  <li>DataSet Overview:</li>
  <p>The provided dataset contains information about movies, including their titles, genres, and IMDB scores. The goal of this analysis is to understand the distribution of movie genres and how different genres impact IMDB scores.
</p>
  
  [Click here to see the Analysis](https://docs.google.com/spreadsheets/d/1SMZSdNtMuPcIv08dkJdy3ocLVNKTVH_GnTW0vXZEUyo/edit#gid=1642294865)
  <li>Insights:</li>
  <p>To start the analysis, I have determined the most common genres of movies in the dataset. By using the COUNTIF function in Excel, to count the occurrences of each genre. I also handled cases where a movie belongs to multiple genres by separating and counting them individually.
</p>
<p>The top 5 most common genres in the dataset are as follows:</p>
Common Generes image
<li>Descriptive Statistics for IMDB Scores by Genre:
</li>
<p>For each of the top 5 genres, Icalculated descriptive statistics using Excel's relevant functions. These statistics provide insights into the central tendency, variability, and overall distribution of IMDB scores within each genre.
</p>
<p>Below are the calculated statistics for the IMDB scores in each of the top 5 genres:
</p>
descriptive statistics image
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
  Drama Image
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
Comedy Image
  
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
Thriller Image

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
  Romance Image
  
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



























