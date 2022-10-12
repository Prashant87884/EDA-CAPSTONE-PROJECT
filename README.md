# EDA-CAPSTONE-PROJECT
# Hotel Bookings Exploratory Data Analysis

## Objective
We have a hotel bookings dataset. 

- **Programming Language** : Python
- **NoteBook** : Google Colab

Our main objective is to perform EDA on the given dataset and draw useful conclusions about general trends in hotel bookings and draw some useful conclusions.

## Dataset
We have a hotel bookings dataset. This dataset contains booking information for a City hotel and a Resort hotel. It contains 32 Columns. The information in the rows is as follows.

```
- hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for not canceled and 1 for canceled)
- lead_time: time in days between booking and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: Month of arrival
- arrival_date_week_number: Week number of the year of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: Number of weekend nights spent in a hotel
- stays_in_week_nights: Number of weeknights spent in a hotel
- adults: Number of adults in single booking record.
- children: Number of children in single booking record.
- babies: Number of babies in single booking record. 
- meal: Type of meal chosen.
- country: Country of origin of customers.
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for 
                     Yes)
- previous_cancellations: Number of previous canceled bookings.
- previous_bookings_not_canceled: Number of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: Number of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Total Revenue/Number of room sold.
- required_car_parking_spaces: Number of car parking asked in booking
- total_of_special_requests: Total number of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.
```

- Total number of rows in data: 119390
- Total number of columns: 32
## Data Cleaning

Creating the copy of original dataset and performing operations on it.


### (1) Handling null values
- Dropping the column 'company' from dataset as it had 112593 Null values and was of no use.
- Null values in column `country` were replaced by 'other countries'.
- Null values in column `children` were replaced by 0.
- Null values in the column 'agent' were replaced by 0.

### (2) Removing Duplicate rows
There are 32001 duplicate rows still present in dataset after the data cleaning.
All duplicate rows were dropped.
  

### (3) Converting columns to appropriate data types
- Changed data type of `reservation_status_date` to date type.
- Changed data type of `children`, `company`, `agent` to int type.


### (4) Removing outliers

- One outlier was found in the `adr` column. Simply dropped it.

### (5) Creating new columns
- Created new column `stays_in_total_night` by adding the column `stays_in_weekend_nights`+`stays_in_week_nights`.
- Created new column `total_guests` by adding `adults`+`children`+`babies`.

## Exploratory Data Analysis(EDA)

Performed EDA and tried answering the following questions:

## Correlation Heatmap
- stays_in_total_nights and lead_time have slight correlation. This shows that long stays or vacations are planned way before the arrival.
- adr and total_people are positively correlated which is true as more number of people means more booking hence more revenue therefore more profit.

## Following questions were asked and we tried to answer them doing following analysis.
- Univariate Analysis
- Hotel Wise Analysis
- Room Wise Analysis
- Distribution Channel Wise Analysis
- Customer Nationality Analysis
- Time Wise Analysis
- What are the chances of whether or not a hotel was likely to receive a disproportionately high number of special requests? 
```
### 1 - Univariate Analysis

 Q1) Which type of meal was most preferred by the guests.
 - Bed and breakfast was the most preferred meal type bu the guests.
 - Hotels can increase the quality of this type of meal in order to maintain good Hospitable environment.
 
 Q2) Which type of customers make more number of bookings?
 - 'Transient'(Lasting or continuing for a short period of time) customer type made the most number of bookings.
 - Hotels can create ambience by keeping the Transient customer type in mind in order to make more customer retention. 
 
 Q3) Which agent made the most number of bookings?
 - Agent ID 9 made the most number of bookings followed Agent ID 240.
 
 Q4) Which deposit type is more preferred by customers?
 - Almost all customers preferred No Deposit type booking.
 - Hotels can promote 'No Deposit' type bookings more as most number of customers are preferring this.
 - Customers are preferring 'No Deposit' type bookings as it is risk free and flexible in case of booking cancellation in the future.
 
 ### 2 - Hotel Wise Analysis
 
 Q1) Which type of hotel is mostly booked by guests?
 - Almost 60% booking are of City Hotels and 40% bookings are of Resort Hotels.
 - City Hotel has more bookings(almost 1.5 times) in comparison to Resort hotel.
 
 Q2) What is relationship between Hotel Type and Total Stay?
 - Customers are preferring city hotels more for bookings of stay of less than 6 days.
 - Customers are preferring City Hotel for shorter stays(less than 6 days) & Resort Hotels are preferred for      longer stays(more than or equal to 6 days).
 - For the stay of exactly 7, 10 or 14 days (especially 7 days) customers prefer the Resort hotels (May be for  mini vacation or to celebrate functions like engagements or marriages, office success parties or other close intimate events.
 
 Q3) Which type of hotel generates more revenue?
 - The average adr of City hotel is approx 110 and average adr of Resort hotels is around 100.
 - City Hotels are generating more revenue in comparison to Resort Hotels.
 - Although City Hotels are booked almost 1.5 times more than Resort Hotels, the difference in revenue of City Hotels and Resort Hotels is very less as people prefer resort hotels for longer stays and as we have assumed that Resort hotels are preferred for close intimate events which increase the revenue of the      Resort Hotels.

 Q4) Which Hotel has high lead time?
 - The median lead time of both the type of hotel is more or less same.
 - There were many on the spot bookings(lead time = 0) in the data set as well as many bookings were make 6 moths in advanced to arrival.
 - Median lead time of City hotels is slightly more than median lead time of Resort hotel ,Lead time of both type of hotels are more or less similar, so from the above graph we can conclude that customers prefer to book hotel approximately 45 days before the checkin.
 
 Q5)  Which type of hotel has higher waiting period?
 - City Hotels have more waiting period hence City hotels are much more busy in comparison to Resort Hotels.
 
 Q6)  Which type to hotel has high booking cancellation rate?
 - The booking cancellation rate of City hotel is approximately 30% & for Resort hotels it is approximately 24%
 - So from Q4, Q5, Q6 we can conclude that hotel cancellation is not related with waiting period or lead time. Thus our Correlation heatmap is relevant.
City Hotels are prefered more for casual stays and Resort Hotels are prefered more for events hence cancellation is more in City Hotels.

 Q7)  Which hotel type has higher number of repeated guests?
 - Customer retention of Resort Hotel is slightly more than City Hotel because City hotels are used more for Casual stays but the Resort hotels are more used for intimate events.
 
 ### 3 - Room Wise Analysis
 
 Q1)   Which room type is more in demand?
 - Customers prefer Room type 'A' the most followed by room type 'D' and room type 'E'.
 
 Q2)  Which room type generates the higher ADR?
 - The Room type 'H' generates the max adr followed by room type 'G', 'F'.
 - Room type 'H', 'G', 'F' are preferred very less by customers and yet create high adr so we can assume that they fall in luxury class and very less customers can afford it.
 - Room type 'A' is most preferred in economy class, followed by room type 'D'.
 
 Q3)  When the hotel does not assign the room preferred by the customer, does it leads to cancellation?
 - From the above graph we can conclude that the hotel not assigning the preferred room type by customer generally doesn't leads to cancellation.
 - But when hotels don't assign the preferred room type to customer, their ADR decreases hence profit decreases.
 
 ### 4 - Distribution Channel Wise Analysis
 
 Q1)  Which distribution channel is mostly preferred by the customers?
 - TA/TO are most preferred distribution channel by the customers.
 - Hotels can partner with these agents and operator or advertise using them as medium in order to increase their business.
 
 Q2)  Which Distribution channel brings more ADR?
 - TA/TO brings the most number of customers but the revenue generated per room is most through Global Distribution System(GDS).
 - Hotels can think about a way to bring more customers through GDS in order to increase overall profitability.
 
 ### 5 -  Customer's Nationality Analysis
 
 Q1) What is the nationality of the guests?
 - Most number of guests are from PORTUGAL followed by GREAT BRITAIN and FRANCE.
 - 9 out of 10 max guests's nationality belongs to the European countries.
 - Out of 176990 guests 139708 guest's nationality belongs to EUROPE, which is roughly 79% of total guests. So it is safe to conclude that data in this dataset is of European hotels.
 
 ### 6 - Time Wise Analysis
 
 Q1) Which year witnessed the highest number of guests?
 - 2016 witnessed maximum number of guests followed by the year 2017.
 - Although the year 2015 witnessed the minimum number of guests, in the year 2015 Resort hotel type booking is more than City hotel.

 Q2) Which time of the year is best to stay in hotel?
 - Instead of the month of DECEMBER the total number of guests in every month are more than 10k. But from the graph there is a very clear visible spike is in the month of JULY and AUGUST, so we can conclude that the best time of the year to book a hotel is in JULY and AUGUST.
 - The data in the dataset is of European Hotels, as during the month of JULY and AUGUST it is summers in Europe and the weather, natural sceneries and landscapes are breathtaking therefore the tourism industries boom during this period of time thus there is a clear visible spike in total number of guests during this period.
 - In the months of November, December, January and February there is extreme winters in Europe, therefore there is a clear visible decline in total guests during this period of time.
 - Even after analyzing the data of CITY and RESORT hotel seperately the fact that the "Best time to book an hotel is month of JULY and AUGUST" remains the same.
 - Throughout the year the people prefer CITY hotels more than the RESORT hotel.
 
 Q3)  In which month of the year Revenue is the highest?
 - In the month of August the revenue of hotels is maximum followed by the month of July.
 - The above analysis further supported our assumption that the data in the dataset is of european hotels. And as the month of June, July, August, September witness summers in the Europe, the number of bookings are more and Hotels make most profit during these months only. So we can also assume that hotels increase prices of the room during these months. And as the month of November, December, January, February witness Winters in europe The number of booking are low thus hotels reduce the prices of room during these months and their revenue also reduce.
 
 Q4) Is there any change in Month wise revenue when we analyze data seperately for Resort and City hotels?
 - During the peak months (June to September) the Resort hotel's earning of revenue is way more than City hotels( which earn more or less same throughout the year), which further proves our assumption that City hotels are booked more for Casual stays thus their price increase very less during summers, while Resort hotels are booked more for Close intimate events which happen during peak of tourism season, so the Resort hotel owner earn more during this period of time.
 
 Q5) What is the trend of bookings within a month?
 - Most of the bookings throughout the year is made by guests of type couple(or two individual) so the hotels can devise their plans and offers keeping this in mind.
  - The hotel booking trend of singles is opposite to the booking trend of couples and families. The number of bookings of singles reduces during the peak of the tourism season which is strange, one of the reason may be, they are travelling in a group.
 
 Q6) What is the optimal length of stay in order to get the best daily rate?
 - Hotel's Point of view: The optimal length of stay to get the best daily rate is less than or equal to 2 weeks, because it is the most frequently booked length of stay by the customer
 - Customer's point of view: The optimal length of stay to get the best daily rate is more than 2 weeks.
 
 ### 7 - What are the chances of whether or not a hotel was likely to receive a disproportionately high number of special requests?
 
 - Hotels will likely receive a disproportionately high number of special requests in the case of children among the guests and also in case of 2 to 4 adults in the group.
 - Hotels can expect disproportionately high number of special requests from every market segments except 'corporate', 'groups', 'aviation'.

```

Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:
  -  Bar Plot.
  -  Histogram.
  - Scatter Plot.
  - Pie Chart.
  - Line Plot.
  - Heatmap.
  - Box Plot
             
```

## Conclusion

```
From our analysis we concluded that our dataset of Hotel bookings is of european hotels as 80% of the guests belong to European nationality. The data set consists of information about bookings of two type of hotels(City Hotel and Resort Hotel). The data set has the data of hotel bookings of three years(2015, 2016, 2017).

The meal type Bed and Breakfast is the most preferred meal type.

City hotels were more busy than Resort hotels .We have observed that city hotel are the most preferred/booked hotel throughout the year. High lead time or waiting period doesn't generally leads to cancellation.

One thing that we noticed was, for less tha 6 days people booked City hotels and for more than 6 days (especially 7 days) people prefer the Resort hotels more, thus we can conclude that City hotels are used more for casual stays and Resort hotels are used more for Picnics, Events or Family vacations.

From our analysis we found out that the bookings of the hotels will be on the peak in the month of June - Sept(especially July and August) as in europe generally the summers are observed during the month of June - September and during this period of time the european landscapes and natural scenaries are breathtaking and the weather is beautiful that is why the tourism industry of europe booms during this time. One surprising thing that we found out during the analysis is that, though the booking of city hotel is more than resort hotel throughout the year, during the summers the earning of Resort hotel is more then the city hotels. The reason of this could be during the summers the customers generally go for picnics or vacations with their families, so they prefer Resort hotels more for such kind of activities. Benefitting from this the Resort hotels generally increase the tariff of the rooms.The hotel booking trend of singles(individuals) is opposite to the booking trend of couples(two people) and families(more than 2 people). The number of bookings of singles reduces during the peak of the tourism season which is strange, one of the reason may be, they are travelling in a group or with their families.

The maximum bookings happen through Travel Agents and Tour operators, while the maximum ADR is generated from bookings coming via the GDS(Global Distribution System). Among various agents, Agent ID 9 brings the most number of bookings followed by agent ID 240. The market segment which makes the most number of bookings is Transient. Most of the customers preferred the 'No Deposit' bookings as it is more flexible and risk free in case of future cancellation.

The room type most in demand is 'A' followed by room type 'D' & 'E'. The Room type 'H' generates the max ADR followed by room type 'G', 'F'. Room type 'H', 'G' & 'F' are preferred very less by customers and yet create high ADR so we can assume that they fall in luxury class and very less customers can afford it. Many a times the hotels doesn't assign the customers the room preferred by the them, this doesn't leads to cancellation. Hotels manage this by providing the room other than customer's prefrance to the customers by reducing the charge of the room, thus overall ADR reduces and hotel's profit reduces.

And many more conclusions.
```
## Challenges
```
- There was a lot of duplicate data.
- There were Null Values in the dataset.
- Data was present in wrong datatype format.
- Choosing appropriate visualization techniques to use was difficult.
