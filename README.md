# Case Study for Recommendation and Bidding Data Scientist Position

### Introduction

In this case study we aim to evaluate your skills in making sense of data, building predictive models, coding style, and presentation skills. 

We expect you to solve this case study in either Python (preferred) or R. If your submission is successful, you will be asked to present your results in a follow-up interview. The first evaluation of your solution will be based on the source code and/or notebook you submit. The presentation in the follow-up interview will be based on the format you are more comfortable with (e.g. Jupyter notebook, R markdown, PowerPoint slides...). Thus make sure to include both the source code and a file of your preference to be used in the presentation.


### Introduction to the Data

You are given the following datasets:

- clicks.csv
Contains the daily number of aggregated clickouts in a hypothetical market. Table schema: date_ymd, click_count. To be used in tasks 1 and 2.

- hotel_details.csv
Contains the following properties of a sample of hotels: hotel_id, city, country, stars, hotel_rating. All the hotels are in one of the following cities: Hanoi, Los Angeles, Miami, New York, Rio de Janeiro, and Stockholm. To be used in tasks 1, 3, and 4.

- hotel_metrics.csv 
Contains a number of daily metrics (date_ymd, hotel_id, impression_count, click_count, booking_count, avg_cpc, avg_clicked_price, avg_length_of_stay, avg_time_to_travel) of a list of accommodations. To be used in tasks 1, 3, and 4.

The columns on these datasets are defined as described below (some columns are present in more than one dataset):
- date_ymd: Date in the yyyymmdd format
- click_count: Number of clickouts made by users. 
- hotel_id: Unique identifier of a given accommodation.
- city:	City where the accommodation is located.
- country: Country where the accommodation is located.	
- stars: Number of stars of the corresponding hotel.	
- hotel_rating: Average rating given by users on the corresponding accommodation. The scale goes from 0 to 100.
- impression_count: Number of impressions of the corresponding accommodation.
- booking_count: Number of bookings made on the corresponding accommodation.	
- avg_cpc: The average clicked CPC of the corresponding accommodation. 
- avg_clicked_price: The average clicked price per night of the accommodation.
- avg_length_of_stay: The average clicked length of stay.
- avg_time_to_travel: The average clicked time to travel.


### Glossary
- advertiser: A booking platform that is active in trivago. Some real-life examples of advertisers would be Expedia, Booking.com, Hotels.com, Trip.com, ...
- clickout: These are clicks made on specific hotel deals, leading the user to the landing page of the corresponding advertiser.
- impression: An impression is defined as the number of times the corresponding hotel appears in the result list of a given search.
- session: A session is defined as an active usage of the trivago website for a continuous amount of time. One given session is contained on a single date.
- CPC: Cost per click. Each clickout the user performs has a CPC linked to it. The advertiser that receives the clickout pays trivago the corresponding CPC value. The value of the CPC is defined by the advertiser in the form of a daily bid. For simplicity, you can assume that each hotel_id has a single CPC placed by each advertiser on a given day.
- Length of stay: Number of nights between check-in and check-out date.
- Time to travel: Number of days between the clickout and the check-in dates.


### Task 1

**a. Since it is the first time you are seeing these data, take some time to get familiar with it. You can use this space to share with us any interesting findings you identified (data property, anomalies, trends, data quality issues, …). Keep in mind that this task is not the main focus of this case study but it is of course a step you should perform for a better understanding of the next tasks. 



## Task 2

**a. Using the dataset clicks.csv, predict the DAILY number of clicks of Sept/2019.



### Task 3

**a. Some of the hotels in the hotel_details.csv have unknown City and Country fields. Every unknown city is still one of the following: Hanoi, Los Angeles, Miami, New York, Rio de Janeiro, and Stockholm. 
Create a model to predict in which city/country the hotels with missing data are located. You can use both hotel_details.csv and hotel_metrics.csv in this task. 

**b What is the accuracy you expect from your model? 




### Task 4
**Now that you have the model from Task 3, let’s imagine the situation where the model was accepted and we want to put it into production. For that, we need to build a Python/PySpark workflow. 
a. What is your plan of action for this workflow? Please design a pipeline flowchart to describe your reasoning.
b. (OPTIONAL) Based on the flowchart you designed, prepare a draft of the modules (e.g. main.py, read_data.py, model.py, write_data.py, etc) of your workflow. For that assume the following:
- The data corresponding to hotel_details.csv is mutable in the sense that new hotels can be included in the dataset. The most up-to-date dataset is available to be imported to your workflow as an output from an upstream workflow;
- The data corresponding to hotel_metrics.csv is produced daily and, thus, a “date_ymd” column is also present in the dataset in addition to the other columns. These data with the additional date_ymd column is also ready to be imported as the output of an upstream workflow;
- You can choose to treat these input datasets as either Hive tables or as python dataframes; 
- Your model is expected to output results daily and write them into an existing table 

Task 4.B is optional and you have the freedom to tackle it in your own way. Other than the bullet points above, you can make any assumptions you want for tackling this task as long as you make them clear on your solution. Even if you do not have a full solution for your workflow, we would still appreciate if you could share a partial solution.
