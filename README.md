# King County Housing Sales Data
![Washington Street](https://github.com/asoylatte03/KC_Housing_data/blob/main/Images/bruce-w-kjtcH8I27v4-unsplash.jpg)
This is a repository for Flatiron School's Phase 2 Project analyzing housing sales data from Kings County, located in the northwest region of the U.S.
## Library Prerequesites
Our project utilizes several additional libraries such as the `usaddress` library in order to generate `zipcode` data based on property `address`, `pyproj`, as well as `bokeh`. Ensure that before you `git clone`, that you have these libraries installed in your local computer. 
You can do so by either using `pip` or `conda`
```
pip install usaddress or conda install -c conda-forge usaddress
```
```
pip install pyproj or conda install -c conda-forge pyproj
```
```
pip install bokeh or conda install bokeh
```
## Project Overview
In this project we analyzed King County Housing Sales data. Our goal was to construct a predictive model using multilinear regression based on select key features. Data was evaluated and a baseline model was created. Twelve iterations of the baseline model were then produced, calculating the MAE and R<sup>2</sup> coefficient respectively. Our final predictive model's performance was evaluated based on select price ranges. We concluded that number of bathrooms, the grade of the house, and the house' condition had the biggest effect on predicting sale price. 

## Business Problem & Stakeholder Understanding 
For the purposes of this project, we are a group of data scientists working for a real estate development company. Our concern is to identify the key features that contribute to an increased sale price. Throughout our analysis we're interested in the following questions: 
- How can we use our model to identify undervalued properties?
- How can we increase the selling price of these properties by highlighting specific features ? 

## Data
Data was gathered from the King County Housing Sales dataset. Information about the dataset's glossary can be found [here](https://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r)

The King County Housing Sales dataset contains information on 30,155 properties and 25 features for houses sold from 2021-2022. Information on each property includes number of bathrooms/bedrooms, floors, square footage of the lot, address, and more. 

The Zip Codes dataset was collected from [here](https://www.unitedstateszipcodes.org/) and contains information on all zipcodes within King County, % of population, and the city associated with them. 

## Baseline Simple Linear Regression Model 
![Simple Linear Regression](https://github.com/asoylatte03/KC_Housing_data/blob/main/Images/baseline_model.jpg)

Our initial simple linear regression model utilized `sqft_living` as a predictor variable for `price`. Our baseline model only accounted for ~ 32% of the variance observed in property sale price. Additionally, the model had a mean absolute error (MAE) of approximately $285,317 between the predicted and actual prices of the property. 

## Modeling A Multilinear Regression Model 
![Residual Distribution](https://github.com/asoylatte03/KC_Housing_data/blob/main/Images/residual_distribution.png)

Our most advanced model takes into account multiple features alongside living space, including the number of bathrooms, property age, patio size, grade, property location, and property condition. This comprehensive model explained ~70% of the variance observed in sale price as well as an MAE of  ~$170,000. Additionally, the residuals of this model follow a normal distribution suggesting that the model’s predictions align well with the actual values.
## Evaluation
Our data was evaluated at several property price ranges to understand its overall performance. We found that our model performs best when predicting property sale price for properties sold between $500,000 and $1M USD. Additionally, based on our model's results, we decided to narrow our focus on undervalued properties by looking at properties where the predicted price was greater than the actual price. We found that properties sold at a price less than $1M USD comprised the majority of undervalued assets. 
## Key Features
### Property Grade 
![Property Grade](https://github.com/asoylatte03/KC_Housing_data/blob/main/Images/filtered_graderenov.jpg)
The quality and design of a property, as measured by its grade, have a significant impact on its sale price. An improvement of 1 point in the grade was associated with an average increase in the sale price of approximately $98,592 USD. Enhancements in the overall quality and design of a property, such as the addition of amenities or the use of better materials in both exterior and interior finishes, can contribute to this price increase.
### Number of Bathrooms
![Bathroom Renovations](https://github.com/asoylatte03/KC_Housing_data/blob/main/Images/filtered_bathroomrenov.jpg)
The number of bathrooms in a property also plays a role in determining its sale price. The addition of a full bathroom was found to result in an average increase of approximately $7,300 USD in the sale price. Constructing an additional bathroom can be seen as an investment that adds value to the property and appeals to potential buyers.
### Property Condition
![Property Condition](https://github.com/asoylatte03/KC_Housing_data/blob/main/Images/filtered_buildingcondition.jpg)
Furthermore, the condition of a property, reflecting its wear and tear and the level of repairs and maintenance it has undergone, can impact its sale price. Improving the condition of a property by 1 point was associated with an average increase in the sale price of approximately $44,051 USD. Enhancing the condition of a property not only extends its lifespan but also enhances its value, as it indicates a well-maintained and appealing property to prospective buyers. This can involve general repairs and maintenance activities that improve the overall condition and functionality of the property.
## Limitations & Future Considerations
Future iterations of our model could incorporate information about the initial purchase price of the property. By considering the price at which the property was bought, we can gain insights into the effect sizes of different features and their impact on the appreciation or depreciation of the property's value over time. This additional context would provide a more comprehensive understanding of the factors affecting property prices during the sale process. Additionally, the interactions between features could be considered as an overall predictor for sale price such as the number of bedrooms and bathrooms. The addition of outside data sources that explain features like schooling or distance to mass transit could also improve the predictive power of our model. 
