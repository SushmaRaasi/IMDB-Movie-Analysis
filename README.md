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




























  </ol>
  
</ul>

























