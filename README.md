# Sales-Prediction-of-big-mart
BigMart have collected 2013 sales data for 1559 products across 10 stores in different cities. Also, certain attributes of each product and store have been defined. So now your aim is to build a predictive model and predict the sales of each product at a particular outlet.

Using this model, BigMart will try to understand the properties of products and outlets which play a key role in increasing sales.

Please note that the data may have missing values as some stores might not report all the data due to technical glitches. Hence, it will be required to treat them accordingly.
# Problem Statement
To predict the sales of each product at a particular outlet.
# Dataset Information

| Variable      | Descriprtion  |
| ------------- | ------------- |
| Item_Identifier | Unique product ID  |
|Item_Weight  | Weight of product  |
| Item_Fat_Content  | Whether the product is low fat or not  |
| Item_Visibility  |  The % of total display area of all products in a store allocated to the particular product |
| Item_Type  | The category to which the product belongs  |
| Item_MRP  |Maximum Retail Price (list price) of the product  |
| Outlet_Identifier | Unique store ID |
| Outlet_Establishment_Year  | The year in which store was established  |
| Outlet_Location_Type  |The size of the store in terms of ground area covered  |
| Item_Outlet_Sales  | The type of city in which the store is located  |
| Outlet_Type  |Whether the outlet is just a grocery store or some sort of supermarket  |
| Item_Outlet_Sales  | Sales of the product in the particulat store. This is the outcome variable to be predicted.  |

## Important insights
### Item_Fat_Content

<img src="https://github.com/sasikirankaye/Sales-Prediction-of-Big-Mart/blob/main/image/Item_Fat_Content.png">
The items bought are more of low fat
### Item_Type
<img src="https://github.com/sasikirankaye/Sales-Prediction-of-Big-Mart/blob/main/image/item_type1.png">
The products available were Fruits-Veggies and Snack Foods but the sales of Seafood and Starchy Foods seems higher and
hence the sales can be improved with having stock of products that are most bought by customers

### Outlet_size
<img src="https://github.com/sasikirankaye/Sales-Prediction-of-Big-Mart/blob/main/image/Outlet_size.png">
most of the outlets are medium sized

### outlet_location_type
<img src="https://github.com/sasikirankaye/Sales-Prediction-of-Big-Mart/blob/main/image/outlet_location_type.png">
most of the outlets are present in the tier3 location

# Predictive Modelling results
In order to find a decent model to predict sales we performed an extensive search of various machine learning models available in Python. In the end, however, models from the h2o package yielded the best results for this task. In particular, deep learning neural networks h2o.deeplearning and gradient boosting regression trees h2o.gbm performed particularly well. An ensemble of various such models, constructed in h2oEnsemble. Here, we used only the 12 most important predictors to avoid over-fitting. To include some features we may have missed with this rather small subset of predictors we supplemented the ensemble with a deep learning neural net using 23 predictors.
|model_id	|mean_residual_deviance|	rmse|	mse	|mae  |
| ------------- | ------------- |
| StackedEnsemble_BestOfFamily_AutoML_20210221_132104|	1.16598e+06	|1079.8|	1.16598e+06|	758.666 |
|StackedEnsemble_AllModels_AutoML_20210221_132104	|1.16664e+06	|1080.11	|1.16664e+06|	758.8|
|GBM_grid__1_AutoML_20210221_132104_model_1|	1.17164e+06	1082.42	|1.17164e+06	|758.741	|0.54757|
|DeepLearning_1_AutoML_20210221_132104|	1.19816e+06	|1094.6|	1.19816e+06|	777.066|
|XRT_1_AutoML_20210221_132104	|1.22038e+06	|1104.71	|1.22038e+06	|773.818|
|GBM_1_AutoML_20210221_132104|	1.22813e+06|	1108.21|	1.22813e+06|	776.96|
