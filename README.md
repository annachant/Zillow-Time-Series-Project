# Predicting Best Real Estate Investments by Zip Code

# Unofficial Intelligence Group
![image](https://user-images.githubusercontent.com/89176309/154104964-b6febece-a44a-4d08-b2e6-5cc5b53be5ca.png)

Real Estate is still the best long-term investment.  Given enough time, almost all real estate will appreciate in value, which means the investment market LOVES to buy and sell it.  For those with enough money, vision, focus, and tenacity, the real estate market offers the opportunity for profit, whether it’s for land to grow lumber, residential development, or building skyscrapers.  

## Business Understanding and Dataset

What are the top 5 best zip codes for us to invest in?

While this is simple question, the potential complexities of answering it can be daunting.  Best by what metric?  Price?  Location?  Long-term return on investment?  Short-term gain?  What about risk?  All of these items matter, and they require numerous decisions before any real investigations can be done.  

Our contractor, MTB Investment Group, has asked us to answer the above question.  In our talks with them, we have suggested an initial strategy of focusing on Houston, TX, the nation's 4th largest city.  Houston has many of the attributes sought by people who are relocating - warm climate, diverse culture, lower cost of living (25.6 percent below the average of the nation's most populous metropolitan areas), recreation, arts, quality schools and universities, etc. For our evaluation, we are looking at Zillow Research’s market dataset that ranges from April, 1996 through April, 2018.  We will use the years January 2015 - April 2018 for our analysis.  This dataset has sales price, zip codes, date of sale, and location information for the entire United States.  Our rationale is as simple as the question – “Location, Location, Location”.  While initial investment will be high because the properties are highly desirable and convenient, the return can also be equally high, and risk is minimized.  

Of course, there is no such thing as no risk, and there are factors that cannot be completely anticipated.  Nonetheless, we believe the analysis here provides the most effective strategy for our clients to proceed.

## Exploratory Data Analysis and First Steps

Our dataset, from Zillow, covered dates from 1996 - 2018; over 14723 rows × 272 columns.  It included housing prices by month, zip codes and city, county and motropolitan areas.  Time series datasets offer special challenges for modeling, and this one particularly so.  Because of its format, there was a considerable amount of work to make sure the data was in an optimum form for the analysis.  We grouped the Houston zip codes into a single dataset.  We also had to “melt” the table that the data is stored in, in order to set the index of the data frame to the time of sale (by month).  These time of sale values we’re originally in columns; “melting” the table moved these items to the index, resulting in over 250 less columns than the original files, but vastly increasing the number of rows.  


PICTURES!

## Modeling & Evaluation

We then ran a test of our modeling and evaluation procedures on a single zip code -- train-test split, adfuller test for stationarity, finding best parameters using auto-ARIMA, SARIMAX modeling, calculation of MAPE (Mean Absolute Percentage Error), camparing real and predicted values, and testing the forecasting model performance.  The final result for each tested zip code will be a graph with the median home price beginning with 2015 - 2018, continuing with a forecast and confidence interval through 2021, as shown here:

![image](https://user-images.githubusercontent.com/89176309/154710457-b9051a91-7157-40e7-8055-a5f7079024e8.png)

With a successful implmentation of our baseline model and procedure, we created a function which took all of our Houston area zips and ran the modeling on each zip, and stored the predictions in a dictionary.

To evaluate our models, we sorted the zip codes by the dollar amount projected increase on the training set.  Those zip codes were:

77060 - Aldine area (forecasted increase of ~24% over 3 years)

77015 - Channelview area (forecasted increase of ~23% over 3 years)

77598 - Webster area (forecasted increase of ~23% over 3 years)

77099 - Sugar Land area (forecasted increase of ~22% over 3 years)

77093 - Kingwood area (forecasted increase of ~15% over 3 years)

![image](https://user-images.githubusercontent.com/89176309/154755053-84b862a0-4632-4a5e-a2b1-bf529e6717ec.png)

## Recommendations and Next Steps

We recommend that MTB Investment Group, center their investment strategy in the Houston, TX area, in the zip codes listed above.  We further recommend that their evaluation of growth in the Houston area be a continuing process, as a wise investment strategy would be hold out a portion of their resource for other areas in Houston that might show surges of growth in the future.

## Repository Struction

├── data
|   ├── zillow_data.csv

├── personal notebooks
|   ├── 
|   ├── 
|   ├── 

├── .gitignore

├── Presentation.pdf

├── Combined Notebook.ipynb

├── README.md

