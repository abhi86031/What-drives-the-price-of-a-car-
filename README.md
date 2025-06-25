# What-drives-the-price-of-a-car-
The task at hand is to identify key drivers for used car prices; analyse the data and recommend used car dealerships as to what consumers value in a used car. 


What drives the price of a car?

OVERVIEW

In this application, you will explore a dataset from Kaggle. The original dataset contained information on 3 million used cars. The provided dataset contains information on 426K cars to ensure speed of processing. Your goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.
CRISP-DM Framework

To frame the task, throughout our practical applications, we will refer back to a standard process in industry for data projects called CRISP-DM. This process provides a framework for working through a data problem. Your first step in this application will be to read through a brief overview of CRISP-DM here. After reading the overview, answer the questions below.
Business Understanding

From a business perspective, we are tasked with identifying key drivers for used car prices. In the CRISP-DM overview, we are asked to convert this business framing to a data problem definition. Using a few sentences, reframe the task as a data task with the appropriate technical vocabulary.

#Summary of Model Performances

    #Train MSE for Linear, Lasso & Ridge models are 1.1511, 1.1586 & 1.1510 respectively
    #Test MSE for Linear, Lasso & Ridge models are 1.1929, 1.1968 & 1.1929 respectively
    #Train MAE for Linear, Lasso & Ridge models are 0.5114,	0.5206	& 0.51131 respectively
    #Test MAE for Linear, Lasso & Ridge models are 0.5189,	0.5277	& 0.5189 respectively
    #R² Score	for Linear, Lasso & Ridge models are 0.2543, 0.2518	& 0.2543 (approx) respectively

# It appears that Ridge regression model is better due to following reasons:-

    # Ridge Regression (with Polynomial Degree 3) performs slightly better than both Linear and Lasso.
    #It has the lowest test MSE and MAE.
    #It's performance is nearly identical to plain Linear Regression but marginally better in every metric.
    #It retains all features (like Linear), while regularising complexity.

#To maximize the price at which a vehicle is sold, dealerships should focus in order of importance on below aspects:

   # Year (vintage) of the vehicle - Generally, newer vehicles command higher prices in the used car market due to factors like updated features and technology, as well as potentially lower mileage.

   # Condition of the vehicle - Vehicles in excellent or good condition typically fetch higher prices compared to those in fair or poor condition.

   # Type of vehicle - Sedans are popular and often come with a higher price tag in the used car market, followed by pickups and wagons.

   # Odometer - Lower mileage typically translates to a higher price, with each mile increase leading to a decrease in value.

   # Drive type - Rear-wheel drive cars tend to have higher value compared to front-wheel drive cars.

   # Cylinders - Vehicles with larger engines, particularly with 8 or 6 cylinders, are preferred and can command higher prices.

   # Fuel type - Diesel cars generally fetch higher prices, but gas cars are also popular, though typically not as expensive as diesel.

   # Car title - A clean title is essential for maximizing the value of a used car.

   # Manufacturer - Toyota and Honda are popular choices in the used car market, while luxury cars may not sell as easily.

# Considering these factors, a customer will ideally look for:-
  #A newer vehicle in excellent condition
  #Low mileage
  #Rear-wheel drive
  #Larger engine size (8 or 6 cylinders)
  #Clean title
  #Preferably from manufacturers like Toyota and Honda. 

#Challenges Faced

    # High Proportion of Missing Data - Many features like VIN, size, and model had substantial missing values, requiring either removal or imputation strategies.
    # Duplicate and Dirty Entries - Duplicate VINs and illogical values (e.g., zero odometer or price) distorted the initial analysis and had to be filtered manually.
    # Categorical Explosion from OneHotEncoding - Features like model, paint_color, and manufacturer caused dimensionality issues post-encoding. Feature selection or dimensionality reduction might be needed in larger models.
    # Non-linear Relationships - Price does not always follow a linear pattern — using only linear models like Ridge/Lasso might miss important interactions. Consider ensemble or tree-based models.
    # No External Data (e.g., regional market conditions) - Features like region and state were removed due to complexity, but may contain valuable information if integrated with external datasets (e.g., weather, demand index).
    # Target Leakage Risk - Some fields (e.g., post date, days listed) were ignored to prevent data leakage, but their indirect effects on pricing could be explored further with care.

#The analysis demonstrates that vehicle pricing can be reasonably predicted using structured features like:

    # Age (derived from Year),
    
    # Manufacturer and model,
    
    # Condition,
    
    # Odometer reading,
    
    # Fuel type and transmission.

# Using models like Ridge Regression, we achieved consistent cross-validation scores around R² = 0.26–0.28, indicating moderate predictive power. With additional features or cleaner data (e.g., external sources like service history or accident reports), model accuracy could be significantly improved.

# The project highlights the value of data-driven decision-making in the used car market, particularly for inventory selection, dynamic pricing, and trend forecasting.

# Future improvements

    # We could perform some feature engineering to the input dataset and verify if it enables reduction in the error.
    # Using an imputer to determine Nan values and verify if there is any change in the result.

