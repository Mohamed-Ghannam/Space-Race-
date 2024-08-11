# <center><div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Welcome To Space Race</div></center>

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">proplem statement:</div>


<center>
    <img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0701EN-SkillsNetwork/lab_v2/images/landing_1.gif">
</center>

SpaceX, a leader in the space industry, strives to make space travel affordable for everyone. Its accomplishments include sending spacecraft to the international space station, launching a satellite constellation that provides internet access and sending manned missions to space. SpaceX can do this because the rocket launches are relatively inexpensive ($62 million per launch) due to its novel reuse of the first stage of its Falcon 9 rocket. Other providers, which are not able to reuse the first stage, cost upwards of $165 million each. By determining if the first stage will land, we can determine the price of the launch. To do this, we can use public data and machine learning models to predict whether SpaceX – or a competing company – can reuse the first stage.

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Explore:</div>
* How payload mass, launch site, number of flights, and orbits affect first-stage landing success
* Rate of successful landings over time
* Best predictive model for successful landing (binary classification)

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Executive Summary:<div>
The research attempts to identify the factors for a successful rocket landing. To make this determination, the following methodologies where used:
* **Collect** data using SpaceX REST API and web scraping techniques
* **Wrangle** data to create success/fail outcome variable
* **Explore** data with data visualization techniques, considering the following factors: payload, launch site, flight number and yearly trend
* **Analyze** the data, calculating many statistics including: total payload, payload range for successful launches, and total # of successful and failed outcomes
* **Explore** launch site success rates and proximity to geographical markers
* **Visualize** the launch sites with the most success and successful payload ranges
* **Build Models** to predict landing outcomes using logistic regression, support vector machine (SVM), random forest, xgboost , K-nearest neighbor (KNN) and voting models

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Results:</div>

### Exploratory Data Analysis:
* Launch success has improved over time
* KSC LC-39A has the highest success rate among landing sites
* Orbits ES-L1, GEO, HEO, and SSO have a 100% success rate

### Visualization / Analytics:
* Most launch sites are near the equator, and all are close to the coast

### Predictive Analytics
* All models performed similarly on the test set except logistic regression. but the last voting classifier which is a combination of xgboost, svc and knn is more robust to data variablity

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Methodology:</div>

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Data Collection - API:</div>
* **Request data** from SpaceX API (rocket launch data)
* **Decode response** using .json() and convert to a dataframe using .json_normalize()
* **Request information** about the launches from SpaceX API using custom functions
* **Create dictionary** from the data
* **Create dataframe** from the dictionary
* **Filter dataframe** to contain only Falcon 9 launches
* **Replace missing values** of Payload Mass with calculated .mean()
* **Export data** to csv file

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Data Wrangling:</div>
* **Convert outcomes** into 1 for a successful landing and 0 for an unsuccessful landing    

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">EDA with Visualization:</div>
* **Create charts** to analyze relationships and show comparisons

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Maps with Folium:</div>
* **Create maps** to visualize launch sites and view launch outcomes for each site

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Dashboard with Plotly Dash:</div>
* **Create dashboard**
* Pie chart showing successful launches
* Scatter chart showing Payload Mass vs. Success Rate by Booster Version
* line chart showing launch outcome by year for each site
- display information about each flight while hovering over it

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Predictive Analytics:</div>
* **Define** usuful functions
* **Extract** some features 
* **Dealing** with null values
* **Checking** the correlation between varibles 
* **Define** a pipeline for preprocessing including imputing, standardization and encoding
* **Split** the data using train_test_split
* **Apply** GridSearchCV and randomizied search on different algorithms
* **Calculate** accuracy on the test and training data using .score(), cross_val_score() respectively for all models
* **Assess** the confusion matrix, classification report for all models
* **Identify** the best model using roc_auc score, Accuracy, classifcation report and confusion matrix

#  <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Conclusion:</div>
* **Model Performance:** All models performed similarly on the test set except logistic regression. but the last voting classifier which is a combination of xgboost, svc and knn is more robust to data variablity
* **Coast:** All the launch sites are close to the coast
* **Launch Success:** Increases over time
* **KSC LC-39A:** Has the highest success rate among launch sites. Has a 100% success rate for launches less than 5,500 kg 
* **Orbits:** ES-L1, GEO, HEO, and SSO have a 100% success rate
* **Payload Mass:** Across all launch sites, the higher the payload mass (kg), the higher the success rate

# <div style="font-family: Trebuchet MS; background-color: #023047; color: #ffb703; padding: 12px; line-height: 1;">Additional Things to Consider:</div>
* **Dataset:** A larger dataset will help build on the predictive analytics results to help understand if the findings can be generalizable to a larger data set
* **Feature Analysis / PCA:** Additional feature analysis or principal component analysis should be conducted to see if it can help improve accuracy
