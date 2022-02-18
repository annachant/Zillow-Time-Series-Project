# Predicting Best Real Estate Investments by Zip Code

# Z-Max Realty Research
![image](https://user-images.githubusercontent.com/89176309/154104964-b6febece-a44a-4d08-b2e6-5cc5b53be5ca.png)

Real Estate is still the best long-term investment.  Given enough time, almost all real estate will appreciate in value, which means the investment market LOVES to buy and sell it.  For those with enough money, vision, focus, and tenacity, the real estate market offers the opportunity for profit, whether it’s for land to grow lumber, residential development, or building skyscrapers.  

## Business Understanding and Dataset

What are the top 5 best zip codes for us to invest in?

While this is simple question, the potential complexities of answering it can be daunting.  Best by what metric?  Price?  Location?  Long-term return on investment?  Short-term gain?  What about risk?  All of these items matter, and they require numerous decisions before any real investigations can be done.  

Our contractor, MTB Investment Group, has asked us to answer the above question.  In our talks with them, we have suggested an initial strategy of focusing on Houston, TX, looking at Zillow Research’s market dataset that ranges from April, 1996 through April, 2018.  We will use the years January 2015 - April 2018 for our analysis.  This dataset has sales price, zip codes, date of sale, and location information for the entire United States.  Our rationale is as simple as the question – “Location, Location, Location”.  While initial investment will be high because the properties are highly desirable and convenient, the return can also be equally high, and risk is minimized.  

Of course, there is no such thing as no risk, and there are factors that cannot be completely anticipated, such as civil war in the old Soviet Union, or a worldwide pandemic.  Nonetheless, we believe the analysis here provides the most effective strategy for our clients to proceed.

## Exploratory Data Analysis

Time series datasets offer special challenges for modeling, and this one particularly so.  Because of its format, there was a considerable amount of work to make sure the data was in an optimum form for the analysis.  We grouped the Houston zip codes into a single dataset.  We also had to “melt” the table that the data is stored in, in order to set the index of the data frame to the time of sale (by month).  These time of sale values we’re originally in columns; “melting” the table moved these items to the index, resulting in over 250 less columns than the original files, but vastly increasing the number of rows.  

PICTURES!

## Modeling

Before modeling, the data is split into train and test sets.  Again, this is a little different than normal procedure, because since this is data over time, it’s important not to do anything that might randomize the data.  This is done by taking the last portion of the dataset (the last 20% for our models) and setting it aside as test data, and using the remainder as training data for our model. The graph here illustrates:

![image](https://user-images.githubusercontent.com/89176309/154710731-84e3b927-6674-48e7-9852-590d2b832662.png)

We then ran a test of our modeling procedures on a single zip code (train-test split, adfuller test for stationarity, finding best parameters using auto-ARIMA, SARIMAX modeling, calculation of MAPE (Mean Absolute Percentage Error), camparing real and predicted values, and testing the forecasting model performance.  The final result for each tested zip code will be a graph with the average home price beginning with 2015 - 2018, continuing with a forecast and confidence interval through 2021, as shown here:

![image](https://user-images.githubusercontent.com/89176309/154710457-b9051a91-7157-40e7-8055-a5f7079024e8.png)

With a successful implmentation of our baseline model and procedure, we created a function which took all of our Houston area zips and ran the modeling on each zip, and stored the predictions in a dictionary.

## Evaluation

## Recommendations and Next Steps

## Repository Struction


