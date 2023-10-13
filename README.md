# Methods for Increasing Retail Sales 

**Author**: Matthew Malueg

## Using Sales and Outlet Store Data to Drive Sales Growth and Increase Profitability

Retail outlets can be a competitive market space, even for established companies. With the rise of online shopping and services in recent decades, these challenges will only continue to increase. Using available data on current sales, store locations and types, and other store and item metrics, retailers can aim to increase their market share and drive increased sales at their locations.

### Business problem:

A retail chain is searching for insights on how to increase overall sales at it's various locations.


### Data:
The source for the sales data to be analzyed can be found here: 

https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

This dataset contains 8,523 entries on item sales with 12 features for each item; however, some of these features held little predictive value and were removed in the course of analysis.


## Methods
- Preprocessing measures before being analyzed:
  - Repeated prefixes and suffixes were removed from numerical data features to allow analysis of numeric data.
  - Classification labels that were formatted differently but otherwise equal in meaning were made uniform.
  - Missing values were addressed with appropriate placeholders or imputed values (more on this below).
  - Features with little predictive value were removed, such as the unique item ID.

- After cleaning, features were converted into numeric data for analysis by machine learning models.
  - There was minimal missing data in the given dataset. Missing numerical data were imputed with median values, and all numeric values were then scaled allowing standardized comparisons. This prevented features with drastically different value ranges unintentionally being given different importance.
  - Missing non-numerical data were given a placeholder value of 'NA' to allow analysis by the learning model, without discarding otherwise relevant rows of data.

- Analysis of data
  - Individual features were visualized and explored to find potentially relevant and actionable trends and insights.
  - After preparing and visualizing the dataset, it was analyzed using both Linear Regression and Random Forest Models.
  - The Random Forest Model was further tuned to test for possible increases in predictive power.

## Results

### Average Sales Based upon Outlet Store Type
![Item sales by type of outlet](https://github.com/JKDS87/Prediction-of-Product-Sales/assets/57232899/530fc5c5-3231-460d-afee-aedcded9afe0)

> - The best performing stores were classified as Type 3 Supermarkets, and consistently produced the highest number of sales for individual items. The bulk of sales at Type 3 stores surpassed those Type 1 and Type 2 stores.
>
> - Although Type 1 Supermarkets did have a number of outlier items that performed quite well, with each item selling a high quantity, these outliers were not enough to shift the overall performance of Type 1 stores upward to a comparable degree as Type 3.
>
> - Type 2 Supermarkets performed similarly to Type 1, but with fewer outliers on the higher end; these outliers also sold lower quantities than the Type 1 Supermarkets.

Possible conclusions could indicate that Type 1 Supermarkets offer specific or specialty items that are unavailable at other locations, driving the high number of sales of these outlier items. It may be worth focusing more on the sales of these specific items.



### Outlet Store Type Frequency Based upon Location
![Frequency of store type by location](https://github.com/JKDS87/Prediction-of-Product-Sales/assets/57232899/e0017cec-faeb-4935-aafb-c723ab5d0931)

(To avoid confusion in terminology, 'Location Types' will be refered to as 'Zones')

> **Notable differences regarding the distribution of stores were:**
>
> - All four Outlet Types could be found in Zone 3, and it had a fairly evenly distribution of each type of Outlet Store - Types 1, 2, 3, and Grocery.
> 
> - All three Zones contained Type 1 Supermarkets. They were also the most common Outlet Type, far outnumbering the other three.
> 
> - Type 1 Supermarkets were the *only* type found in Zone 2, with a significantly higher number per zone than any other combination.

Despite having a fairly equal distribution of the three Supermarket store types in Zone 3, Type 3 Supermarkets generated higher sales overall (seen in the previous image). Stakeholders may consider prioritizing selling items in Type 3 stores for increased sales and profitability.

## Model Evaluation

- The final model chosen was the updated 'Random Forest Model' after it had been tuned for increased performance. Of the models investigated, it had the best predictive power.
- Comparing metrics of model performance with training data to performance with real data, metrics indicate it performed as designed.
- The Root Mean Squared Error of an item's overall sales was calculated to be $1,058.15
- The R^2 score of the chosen model was 0.594

## Recommendations:

- Although the model performed as designed, it currently has weak predictive power, and should not be relied on with a high degree of confidence for sales predictions.

  - The values being investigated for our stakeholders were the sales of any particular item in their outlet stores. Sales values ranged from $13,086.96 down to $33.29, with a median total of $2,181.29. With an error of $1,058.15, this model still needs work before being very useful to our stakeholders.

  - The R^2 score of 0.594 tells us that our model only accounts for 59.4% of the variance in predictions. 


## Limitations & Next Steps

- Further model tuning and the introduction of additional sales and store data would help to improve the model's predictive ability and provide more utility to stakeholders wishing to increase sales and profitability.

## Coefficient and Feature Analysis

### Analysis of Linear Regression Model Coefficients
![Linear Regression Coefficients](https://github.com/JKDS87/Sales-Predictions/blob/main/LinearRegressionImportance.png)

We can further examine the features that had the largest impact on determining the predictions of our Linear Regression Model. The features with most predictive power in this instance were indicators of whether the item was found in Supermarkets of type 1, 2, or 3. Those items which were sold in Type 3 had a coefficient of 3,483.73, indicating that being sold in this type of store had a positive impact on projected sales of $3,483.73. Similarly, items in Supermarket types 1 and 2 experienced a positive impact of $2,001.71 and $1,672.55, respectively.

This is in line with previous findings that items found in Supermarket Type 3 locations performed better than others, and had greater sales numbers.

### Analysis of Random Forest Model Feature Importance
![Random Forest Feature Importance](https://github.com/JKDS87/Sales-Predictions/blob/main/RandomForestImportance.png)

Our Random Forest Model found the most predictive features to be, in order of importance:
- Item Max Retail Price
- Being sold in Grocery Stores
- Being sold in Supermarket Type 3 Stores
- Item visibility on shelves
- Year of outlet establishment

 Upon further visualization and inspection, the maximum retail price, item visibility, and placement in Type 3 Supermarkets all had positive impacts on the sales of items. Placement in Grocery stores was shown to have a net negative impact on the sales prices; the establishment year of the store in question also had a negative impact, although this difference was rather small. 
 
 The 'Importance' ranking along the X-axis shows up the percentage each individual feature had on the overall sales, with the maximum sale price having the largest, accounting for over 50% of the models prediction on overall sales figures. The establisment year, although in the top 5 features influencing price, still accounted for well below 10% of the overall prediction, which is in line with the very small negative trend observed in visualizations.

 

### For further information

For any additional questions, please contact **Malueg87@gmail.com**
