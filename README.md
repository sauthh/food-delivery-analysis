# Food Delivery Analysis

This proje
This project was done in collaboration with my friend, Christopher Way.


## Abstract

This study presents an exploration into how one can properly take advantage of data from food delivery services in order to develop a model to predict food delivery times based upon a variety of factors. The study is motivated by the rapid growth of food delivery apps like UberEats, DoorDash, and Grubhub, especially in the context of the post-covid delivery sphere, which has significantly higher usage than pre-covid levels. V arious factors are analyzed in order to understand their impact on delivery services. The findings are intended to assist both users and drivers by providing a clearer understanding of delivery times to enable better planning and service efficiency. Using a dataset containing 45,593 rows and 19 unique columns, the study conducts an exploratory data analysis, revealing key insights such as the impact of weather conditions on delivery times and the predominance of certain age groups among delivery personnel. Several regression models were used to analyze the data, with a specific focus on Gradient Boosting, Random Forest, and Decision Tree regression. The results were deduced by a focus on metrics like Mean Squared Error (MSE), Mean Absolute Error (MAE), and R-squared. The results indicate that driver ratings, multiple deliveries, and road traffic density are significant factors in determining delivery times. The study concludes that the Gradient Boosting and Random Forest models were most effective in predicting delivery times, with r-squared metrics of about .6 for each. The study gives valuable insights into the food delivery industry, with implications for both drivers and users to optimize their delivery experiences.

## Background/Motivation

Food delivery apps such as UberEats, DoorDash, Grubhub, etc. have exploded in popularity in recent years. Their user base was slowly growing in the late 2010’s; however, due to COVID-19, their usage increased exponentially. Most people were hesitant to leave their houses due to the fear of catching the virus, so they turned to food delivery apps to still get the food they craved for. Furthermore, for the people who wanted to earn some money, it was a way for them to do so with limited contact with the customers. It kept the economy going and kept both the drivers and users content with the service.

As we were looking for datasets to use, we came across this one and it piqued our interest. I, Saurav Thapa, have experience doing DoorDash in a small town and seeing this data made me curious as to how delivery time was impacted by the rating of the person, type of city, type of vehicle, order type, etc. We wanted to take a deeper look into the delivery drivers and how delivery time can be affected by numerous factors.

Our findings from this project will help users and delivery drivers alike in seeing how delivery is affected by various factors. For example, users can look at the results to determine how long it would take for their food to be delivered, so they can time it more accurately. If they are out of their home and plan to get back at a certain time, they can more precisely order the food so it gets to their doorstep not too long after they get home. For delivery drivers, they can better estimate how long it will take to deliver, so if a customer is waiting on an order, they can give them a better guess. Additionally, they can decide to take on multiple orders if they realize that they can deliver multiple foods in time.

## Exploratory Data Analysis

Looking through the dataset, it contains 45,593 rows and 19 unique columns, them being ID, Delivery_person_ID, Delivery_person_Age, Delivery_person_Ratings, Restaurant_latitude, Restaurant_longitude, Delivery_locaiton_latitude, Delivery_location _longitude, Order_Date, Time_Ordered, Time_Order_picked, Weatherconditions, Road_traffic density, V ehicle_condition, Type_of_order, Type_of_vehicle, Multiple_deliveries, Festival, City, and Time_taken(min). The data was collected from February to April, but March had the higher order amount, which was around 31,989 orders.



Our initial findings showed that cloudy and foggy conditions resulted in longer delivery time, so sunny days allowed for faster time. The data contained roughly the same amount of food types: 11,533 snack orders, 11,458 meal orders, 11322 drink orders, and 11,280 buffet orders. Additionally, it took roughly around 26.28 minutes for each type of order. Ages 20-39 were the primary delivery drivers, and ages below or above were not recorded. Next, food was picked up within 15 minutes from order placement no matter the conditions. Motorcycle was also the most popular delivery method, while bicycle was the least preferred by the drivers. Lately, the dataset skewed left for ratings, meaning most were 4.5 or higher.
