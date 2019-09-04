# Project 2 - Ames Housing Data and Kaggle Challenge
**by Angela Kunanbaeva**



## Ovjective:


- Provide analysis on housing market in Ames, Iowa


- Identify key features that have the greatest impact on selling price in Ames, Iowa


- Provide  best fit model that predicts the selling price Ames, Iowa



### Project summary:


The way I tackle this project:


1. I started off by cleaning the data. The data contained many null values and zeros, so these should have been taken care of, but for my first model I wanted to use as many features as possible so that I can further analyze their impact on the housing saleprice.
- This was actually very helpful in order to get an overall feel of the data. For instance, without searching any additional information on Ames, Iowa, I could easily identify that the absence or presence of pool for example, didn't play an important role on the selling price. As it turns out, Ames summer temperature is pretty low, so one shouldn't expect the pools to be in demand.


2. I created my initial model using Advanced Regression techniques, such as Linear Regression, Ridge and Lasso models
    - This models work actually really well with this type of dataset, since most of the variables have linear relationship with the selling price


3. After the initial model - I reviewed the score and went on to further analyze the features and their correlation to the housing sale price.
    - I cleaned data with null values in a more thorough and concise way. For instance, the were many variables with over 80% of null data, so there's no point in keeping those in the model. But one has to be very careful with such values, as they may actually represent an absence of the feature, like in the garage areas, or masonry veneer feature, where absence may have a strong effect on the selling price, this leads to the next part.


4. Feature engineering has to be executed in order to achieve a better performance of the model.
    - There are certain features that add up to the value of the house like basement type 1 if its above average condition, but basement type 2 doesn't affect the price. So some of these features a better be binarized, if basement type 2 of average quality strongly affects the price, then it's a good idea to convert it into 0s and 1s to represent below average and above average.
    - Most of the categorical features have to be turned into dummies, and I'm glad I dummified those features as certain categories have a profound effect on the price. These can be seen from the coefficients table.


5. I created the second model in order to filter our the the features that were given the strongest, i.e. highest absolute value. And created a third model using this features only.
    - Out of three model, Ridge and Lasso performed practically identical, but I chose Lasso for its effect to zero out the features because I incorporated many into my model. In my opinion, most of the features have more or less effect on the housing selling price, so it's a good idea to add as many as possible, and with more data, this model can be trained to predict better prices.


6. In the visualization section I used different python modules to see the relationship of the individual features to the housing sale price. There are many features that have different effect on the price, and I get into this information in more detail in the conclusion section.





### Here is the list of the section headings and the links can be found in the project itself:
1. Initial data analysis
2. Dealing with null values
3. Feature engineering
4. Model
5. Coefficients analysis
6. Predicting on test dataset
7. Feature visualization and EDA
8. Conclusion


## Conclusion



**In conclusion:**



1. House prices dropped in 2008 but that was due to overall US property crisis. However, the market recovered in 2008 and it seems that's the maximum price is on the rise


2. Certain features such as Overall quality and Sq.ft area, and of course Location have practically linear relationship with the Sale price


3. The newer your house the better the price


*But there are some peculiarities:*


4. There are features that add up to the value of the house up to a certain point, and then either have no further effect or may even diminish the price:


    - For example, there is 140 thousand price jump from not having a pool to having a pool. But as the pool area increases the prices doesn't necessarily follow this trend. As long as you have a pool up to 250sq.ft you'll can claim the higher value for your house


    - The same with the garage cars: if your garage fits 3 cars you can claim the higher average price for your house, but having more spaces in your garage doesn't linearly adds up to the selling price


    - Absence or presence of the fireplaces doesn't result in price jump, but having 1-2 fireplaces certainly increase the value. Yet 3 or more fireplaces don't


5. Another interesting observation is time of year has a profound effect on average selling price. So in warmer months starting from May till August, the average sale price rises substantially. This may be due to school migration effect, when families move to a different area so children can attend certain schools


6. Also, not having school district as a feature in the dataset limits the model. So in order to make a better model more data including School districts should be included. It certainly plays the most important role in picking the place to rent.



**Summary on the model:**

- The model with less coefficients may certainly perform better, but I feel that most of the features should be included in predicting the price. As they do impact the house value more or less. For instance, Clay-tile roof material adversely effect the price, even with one entry. So more simplistic model won't cover housing data to full extent.


- Also, I'm glad I created dummies for categorical features as Excellent condition of the exterior, or Good garage condition, or Above average basement certainly add value to the house price


- So the best Regression model for this type of dataset is the Lasso model, as it zeros out not important features and allows to use a good number of features
