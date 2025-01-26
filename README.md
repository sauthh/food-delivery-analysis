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

![Time Taken for Delivery by Weather Conditions](https://github.com/sauthh/food-delivery-analysis/blob/f4da883c805464211b981c9db3de161a991f0a09/Figures/figure1.png)

![Count of Delivery Person Ratings](https://github.com/sauthh/food-delivery-analysis/blob/c1f1fc56379c9f84c319d1f960306f53d936f642/Figures/figure2.png)

Our initial findings showed that cloudy and foggy conditions resulted in longer delivery time, so sunny days allowed for faster time. The data contained roughly the same amount of food types: 11,533 snack orders, 11,458 meal orders, 11322 drink orders, and 11,280 buffet orders. Additionally, it took roughly around 26.28 minutes for each type of order. Ages 20-39 were the primary delivery drivers, and ages below or above were not recorded. Next, food was picked up within 15 minutes from order placement no matter the conditions. Motorcycle was also the most popular delivery method, while bicycle was the least preferred by the drivers. Lately, the dataset skewed left for ratings, meaning most were 4.5 or higher.

![Average Time Taken](https://github.com/sauthh/food-delivery-analysis/blob/2eba44134d0fa6cb788f51bd41f91937b981baf5/Figures/figure3.png) ![Food Amount](https://github.com/sauthh/food-delivery-analysis/blob/2eba44134d0fa6cb788f51bd41f91937b981baf5/Figures/figure4.png)

![Average Time Taken by Type of Order](https://github.com/sauthh/food-delivery-analysis/blob/2eba44134d0fa6cb788f51bd41f91937b981baf5/Figures/figure5.png)

## Model Development

Before analyzing our dataset more in depth, we had to prepare it for modeling. First, we removed “ID”, “Delivery_person_ID”, and “Weatherconditions” from the dataset. The two different ID columns were removed because they were irrelevant to our experiment. “Vehicle_condition” was removed because there was no context surrounding it. For example, we searched up vehicle condition 0 on google and it showed that it meant the vehicle was inoperative, which made no sense so our only option was to drop it. Next, we removed “(min)” from the rows and converted it to integers because it made analyzing harder as the values would be string and not numbers. Additionally, any columns that contained numbers were converted to integers for the purpose of running the model. We also removed any null, “NaN”, and 0 values from the columns except for a couple columns where it made sense to have 0 as a value.

Initially, when approaching the problem of how to calculate food delivery time, we were unsure of the best type of model to use. We tested a large variety of different regression models such as linear, lasso, ridge, elasticnet, support vector, k-nearest neighbor, decision tree, gradient boosting, quantile, huber, and gaussian process. After running the models, we settled on three models to use as they provided the most accuracy when performing the regression, which were gradient boosting, random forest, and decision tree.

## Result and Insights

When we ran the various different models, we were looking for three key aspects: mean squared error, mean absolute error, and r-squared. Mean Squared Error (MSE) is the average of the squares of errors. It gives more weight to large errors due to the squaring of each term and is more sensitive to outliers. A lower MSE indicates a better fit for the model to the dataset. Mean Absolute Error (MAE) is the average magnitude of errors in a set of predictions. This is the average over the test sample of the absolute differences between predictions and actual observation which is less sensitive to outliers compared to MSE. Lastly, R-squared is a statistical measure that represents the proportion of variance for the dependent variable explained by the independent variables in a regression model. It ranges from 0 to 1, where a higher value indicates a better fit of the model of the dataset. However, it does not indicate whether the model is appropriate. In terms of graphing, we were looking for a linear upward trend as the actual time needed to match up with the predicted time. Lastly, feature importance told us what the model considered which values were most important when running it. A higher number obviously meant more importance. 

Firstly, running Gradient Boosting gave us a MSE of 33.5651 and R-squared of 0.6162, which was the most accurate of any model we ran. Running a feature importance showed us that the rating of the driver was the most important factor followed by multiple delivered and road traffic density. This makes sense because drivers tend to have a rating around 4.5 and users give 4 or 5 on average. If they have a rating close to a 5, it means they have exceptional service and deliver food in time without messing anything up. For graphing, it had a general upward trend, but there were too many errors when predicting the delivery time to the actual time.

![Gradient Boosting](https://github.com/sauthh/food-delivery-analysis/blob/2eba44134d0fa6cb788f51bd41f91937b981baf5/Figures/figure6.png)


