# Seattle Airbnb Data Analysis

## Project Introduction

This project is a data analysis to [Seattle Airbnb Open data](https://www.kaggle.com/airbnb/seattle), which describes the listing activity of homestays in Seattle.

### Dataset

The dataset contains three files:

- **listings.csv** - including full descriptions, average review scores and price of 3818 homestays.
- **reviews.csv** - including 84849 reviewers' id and their detailed comments.
- **calendar.csv** - including price of 3723 homestays in a year from 2016/1/4 to 2017/1/4.

### Target

When we travel to other cities, accomodation is the first thing we need to consider. According to the dataset and my life experience, I put forward following three questions, and the target of this project is to find answers of these questions.

1. **When will it be cheaper to book a homestay in Seattle?**
2. **What are main factors that influence the price? **
3. **What factors people care about most when choosing an accomodation?**

### Method

To find the answer of each question, I used following methods to do data analysis.

1. **Analyze calendar data, search the relationship between date and price.**
2. **Analyze listings data, search the relationship between price and some features we care about, and use LightGBM model to get importance of each feature.**
3. **Analyze reviews data, generate word cloud from reviewers' comments, to find the words which appear in comments frequently.**

### Result

In response to above questions , I analyzed the dataset and got the answer of each question as following.

#### Answer 1:

- It will be **cheapest** to book a homestay in **January**, while most **expensive** in **July**.

<img src="C:\Users\zengh\Desktop\Project1_Writing_a_data_scientist_blog_post\Answer1-1.png" style="zoom:67%;" />

- Price always  **increase** on **Friday** and **Saturday**, so try to avoid booking accomodataion on these two days in a week.

<img src="C:\Users\zengh\Desktop\Project1_Writing_a_data_scientist_blog_post\Answer1-2.png" alt="Answer1-2" style="zoom:60%;" />

#### Answer 2:

- **Location** is an important factor that can influence the price. **Average price** in the region whose **zipcode is 98134** is **highest**, while in the region whose **zipcode is 98106** you can book **cheap** homestay. What's more, listings **near Kaanapali** are usually **expensive** while those **near Holly park** can be very **cheap**.

<img src="C:\Users\zengh\Desktop\Project1_Writing_a_data_scientist_blog_post\Answer2-1.png" alt="Answer2-1" style="zoom:80%;" />

- **The number of amenities** listings have can also influence the price. In general, listings with **more amenities** usually are **more expensive**. But this phenomenon is not that unconditional, actually it also depends on what kinds of amenities listings have.

<img src="C:\Users\zengh\Desktop\Project1_Writing_a_data_scientist_blog_post\Answer2-2.png" alt="Answer2-2" style="zoom:60%;" />

- For some kinds of amenities, listings with them or without them may have different prices. A homestay **with TV** will obviously **more expensive** than that without, But a homestay **with cats or dogs** usually **cheaper** than that without cats of dog. (In following picture, '1' means with that amenity, '0' means without that)

<img src="C:\Users\zengh\Desktop\Project1_Writing_a_data_scientist_blog_post\Answer2-3.png" alt="Answer2-3" style="zoom:80%;" />

- **Location**, **cleaning fee**, **available time**, **reviews**(including number of reviews per month and review scores),  **number of amenities** might be top 5 important factors for the price.

#### Answer 3:

- Location, property of accomodation, comfort, cleanliness might be factors that guests care about most.

<img src="C:\Users\zengh\Desktop\Project1_Writing_a_data_scientist_blog_post\reviews_wordcloud.png" alt="reviews_wordcloud" style="zoom:80%;" />

### Conclusion

Therefore, according to data analysis above, there are some tips for gusts to find cheap accomodations and some tips for new hosts to improve competitiveness and get more bookings.

#### Tips for gusts:

- At different time the price can be very different, try to **avoid travel Seattle between June and August**, and **avoid booking homestays on Friday and Saturday**. If you want to visit Seattle with lowest price, booking on weekday in January might be the best choice.
- Try to **avoid choosing homestays near Kaanapali or in the region whose zipcode is 98134**. You may find cheap homestays near Holly park.
- **Don't choose homestays with too much amenities**, those with necessary amenities can just be ok.

#### Tips for hosts:

- Homestays **near some popular places** or with **convenient transportation** are usually more preffered.
-  If your location is not that good, don't worry. Try your best to **make your house clean and comfortable**.
- Make sure that your house **has necessary amenities**,  like TV and air conditioning. It would be better if there is a **kitchen** in your house.

## Libraries

All libraries I used in this project are as following:

- numpy
- pandas
- matplotlib
- seaborn
- sklearn
- lightgbm
- time
- warnings

## Description of each file

- Seattle_Airbnb_Open_Data - Dataset, including three files.

> - listings.csv
> - calendar.csv
> - reviews.csv

- listings_data_cleaning.ipynb - code used to clean listings data.
- listings_data_analysis.ipynb - code used to analyze relationship between price and other features and preprocess data using listings data.
- listings_data_predict.ipynb - code used to make price predict model.
- calendar_data_analysis.ipynb - code used to analyze calendar data.
- reviews_data_analysis.ipynb - code used to analyze reviews data.

## Acknowledgement

Data Source - Seattle Airbnb Open Data https://www.kaggle.com/airbnb/seattle





