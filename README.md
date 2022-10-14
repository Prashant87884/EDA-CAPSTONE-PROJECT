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






