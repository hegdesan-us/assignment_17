# assignment_17
 Assignment 17

 **URL for the assignment:** 
```
https://github.com/hegdesan-us/assignment_11.git
```
 **URL for solution Jupyter notebook:** 
```
prompt_III.ipynb
```

**Name :** Sanjay Hegde \
**Couse :** UCB AI/ML 

**prompt_II.ipynb :** Original Prompt file (Questions only)

**Directory :** Images \
  Description : Contains the images needed for the prompt questions and the Jupyter notebook 

**Directory : data** \
 Description : Contains the data file needed for the class project\
 Contains file : vehicles.csv

### Data Preperation
 **Heatmap of Missing values**

 
 ![MissingDataImage](images/missing_values_before.png)

- Droping unique value columns as it can't be used for model. id, vin
- Droping region as state can be used instead
- Dropping size as 71% information is missing
- Dropping paint_color as 30% information is missing
- Dropping Drive as 30% information is missing


## Exploratory Data Analysis (EDA)
In this section of the project, the data is explored to see the patterns and trends and observe interesting insights. Below are some interesting observations generated.

- The 'F-150' model is the top-selling car. Many cars in other category needs to be properly tagged.
- 'Gas' is the predominant fuel type for cars in the dataset, surpassing 'Diesel' and 'CNG,' indicating fuel preference among buyers.
- The majority of cars are sold through dealers, underscoring the role of dealerships in the automotive market.
- 'Manual' transmission cars significantly outnumber 'Automatic' transmission cars, showcasing consumer transmission preferences.
- 'Diesel' cars tend to have higher 'Selling_Price' compared to 'Petrol' or 'CNG' vehicles, emphasizing the influence of fuel type on car pricing.
- 'Dealer' sellers usually ask for higher prices than 'Individual' sellers, revealing the impact of seller type on prices.
- 'Automatic' transmission cars typically have higher prices than their 'Manual' counterparts, reflecting consumer preferences.

<h2> Visualizations</h2>

Distribution of Price

 ![Price Distribution](images/price-distribution.png)

Heat Map after cleaning

![Heatmap](images/missing_values_after.png)

Correlation Heatmap

![Correlationheatmap](images/correlation_heat.png)
 

 
## Machine Learning Models 


We have to be using various machine learning models to see which model reduces the __mean absolute error (MAE)__ or __mean squared error (MSE)__ on the cross-validation data respectively. Below are the various machine learning models used. 


| __Machine Learning Models__| __Mean Absolute Error__| __R2 Error__|__Time to Run(sec)__|
| :-:| :-:| :-:|:-:|
|  Linear Regression| 83939779.13678667| 0.5278563705085384|6|
|  Linear Polynomial|	60419849.371127896|	0.6601510360311418|59|
|	 Ridge Regressor|	64006238.171969175|	0.6399783522022104|225|
|	 Lasso Regression|	70079104.16002005|	0.6058197563791127|260|
|	 Linear Seq Regressor|	75396086.80552292|	0.5759128456151473|64|


 ![Different Regression Model MSE Comparision](images/mse_comparision.png)
 ![Different Regression Model R2 Comparision](images/r2_comparision.png)

## Summary of Regression Model selection and feature importance
Looking at the MAE and R2, Linear Polynomial seems to provide optimal price predication in this scenario
Looking at the coefficients, polynomial Feature 5 seems to provide optimal results.
{'transformer__polynomialfeatures__degree': 5}

Here are some major features based on the importance
- year    0.324 +/- 0.002
- model   0.253 +/- 0.001
- odometer0.069 +/- 0.001
- fuel    0.033 +/- 0.001
- transmission0.023 +/- 0.000
- cylinders0.017 +/- 0.000
- type    0.012 +/- 0.000
- state   0.006 +/- 0.000
- title_status0.006 +/- 0.000
- manufacturer0.005 +/- 0.000
- condition0.001 +/- 0.000

 ![Linear Regression - Poly](images/LinearReg-Poly.png)


## Deployment
The general price of a car depends on newer model year, lower odometer readings, fuel type and transmission. Some of the reccomentation include
- The 'F-150' model is the top-selling car. Many cars in other category needs to be properly tagged.
- 'Gas' is the predominant fuel type for cars in the dataset, surpassing 'Diesel' and 'CNG,' indicating fuel preference among buyers.
- The majority of cars are sold through dealers, underscoring the role of dealerships in the automotive market.
- 'Manual' transmission cars significantly outnumber 'Automatic' transmission cars, showcasing consumer transmission preferences.
- 'Diesel' cars tend to have higher 'Selling_Price' compared to 'Petrol' or 'CNG' vehicles, emphasizing the influence of fuel type on car pricing.
- 'Dealer' sellers usually ask for higher prices than 'Individual' sellers, revealing the impact of seller type on prices.
- 'Automatic' transmission cars typically have higher prices than their 'Manual' counterparts, reflecting consumer preferences.

 ![SubplotFuelTrans](images/plt-1.png)
 
 ![SubplotFuelTrans](images/plt-2.png)
 
 ![SubplotFuelTrans](images/plt-3.png)
 
 ![SubplotFuelTrans](images/plt-4.png)
 
 ![SubplotFuelTrans](images/plt-5.png)
 

**Next steps**

- Iterate through models based on selective features for better price model


 

 
