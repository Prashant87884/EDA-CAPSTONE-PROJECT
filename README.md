# EDA_on_Playstore_Data_Team_Achievers
## Data description
Mobile apps are everywhere. They are easy to create and can be lucrative. Because of these two factors, more and more apps are being developed. In this notebook, we will do a comprehensive analysis of the Android app market by comparing over ten thousand apps in Google Play across different categories. We'll look for insights in the data to devise strategies to drive growth and retention.
```
Total number of apps in the dataset =  Unnamed: 0        9659
App               9659
Category          9659
Rating            8196
Reviews           9659
Size              8432
Installs          9659
Type              9659
Price             9659
Content Rating    9659
Genres            9659
Last Updated      9659
Current Ver       9651
Android Ver       9657
```
## Dataset
```
App :- Name of the App
Category :- Category under which the App falls.
Rating :- Application's rating on playstore
Reviews :- Number of reviews of the App.
Size :- Size of the App.
Install :- Number of Installs of the App
Type :- Whether the App is free/paid
Price :- Price of the app (0 if it is Free)
Content Rating :- Appropriate Target Audience of the App.
Genres:- Genre under which the App falls.
Last Updated :- Date when the App was last updated
Current Ver :- Current Version of the Application
Android Ver :- Minimum Android Version required to run the App
```
## Data cleaning

Data cleaning is one of the most essential subtask of any data science project. Although it can be a very tedious process, it's worth should never be undermined.

By looking at a random sample of the dataset rows (from the above task), we observe that some entries in the columns like Installs,Price and Size have a few special characters (+ , $ ,M , k) .This prevents the columns from being purely numeric, making it difficult to use them in subsequent future mathematical calculations. Ideally, as their names suggest, we would want these columns to contain only digits from [0-9].
## explorartory data analysis

**observation 1**
Exploring app categories:-With more than 1 billion active users in 190 countries around the world, Google Play continues to be an important distribution platform to build a global audience. For businesses to get their apps in front of users, it’s important to make them more quickly and easily discoverable on Google Play. To improve the overall search experience, Google has introduced the concept of grouping apps into categories. Which category has the highest share of (active) apps in the market? Is any specific category dominating the market? Which categories have the fewest number of apps? We will see that there are 33 unique app categories present in our dataset. Family and Game apps have the highest market prevalence. Interestingly, Tools, Business and Medical apps are also at the top.<br>
**Observation 2**<br>
**Installs acording to generes**<br>
As we can see communication genere has the highest number of intsalls in this genere social media apps like whatsapp and Gmail are included which has a huge number of customer base as everyone in this day and age uses social media apps.
Then it is followed by social media apps and then productivity and follows.<br>
**Observation3**<br>
**Heatmap**<br>
With more installs, more reviews will come to our dataset. So they are more codependent<br>
**Observation4**<br>
**Rating fluctuation**<br>
After having witnessed the market share for each category of apps, let’s see how all these apps perform on an average. App ratings (on a scale of 1 to 5) impact the discoverability, conversion of apps as well as the company’s overall brand image. Ratings are a key performance indicator of an app.

From our research, we found that the average volume of ratings across all app categories is 4.17. The kde plot plot is skewed to the left indicating that the majority of the apps are highly rated with only a few exceptions in the low-rated apps.<br>
**Observation5**<br>
**Count of applications in each category differentiated by their type**<br>
It looks like certain app categories have more free apps available for download than others.The majority of apps in the Family, Food & Drink, and Tools, as well as Social categories were free to install.
At the same time Family, Sports, Tools, and Medical categories had the biggest number of paid apps available for download.
Let's see how our hero "Installs" affects the results of the above chart.<br>
**Observation6**<br>
**Distribution of subjectivity**<br>
It can be seen that maximum number of sentiment subjectivity lies between 0.4 to 0.7. From this we can conclude that macimum number of users give reviews to the applications, according to their experience.<br>
**Observation7**<br>
**What is the distribution of type of reviews in the dataset?**<br>
First we will merge our 2 DataFrames into a single DataFrame:- In the merged dataframe, we have three new columns i.e.. Sentiment, Sentiment Polarity and Sentiment Subjectivity. Sentiment basically determines the attitude or the emotion of the writer, i.e., whether it is positive or negative or neutral. Sentiment Polarity is float which lies in the range of [-1,1] where 1 means positive statement and -1 means a negative statement. Sentiment Subjectivity generally refer to personal opinion, emotion or judgment, which lies in the range of [0,1].<br>
**Observation8**<br>
**Does sentiment_subjectivity proportional to sentiment_polarity?**<br>
From the above scatter plot it can be concluded that sentiment subjectivity is not always proportional to sentiment polarity but in maximum number of case, shows a proportional behavior, when variance is too high or low.<br>
**Observation9**<br>
**Percentage of Review Sentimets**<br>
As is clear from the pie charts there are 64.1 % of Positive sentiments, 22.1% of Negative sentiments, and 13.8% neutral sentiments.<br>
**Conclusion**<br>
<ol>
  <li>Family category apps have the highest number of application.</li>
  <li>Communication gener has the most number of installs due to their huge user base.</li>
  <li>Most of the apps are rated between 4 to five stars which shows that most of the apps are userfriendly.</li>
  <li>Free apps have high number of installs over paid apps.</li>
  <li>Maximum number of users give reviews to the applications, according to their experience.</li>
  <li>Sentiment subjectivity is not always proportional to sentiment polarity but in maximum number of case, shows a proportional behavior, when variance is too high or low.</li>
  <li>Most of the sentiments are positive with greatest number of percentage.</li>













