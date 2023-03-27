# Phase 2 Project

Another module down--you're almost half way there!

![awesome](https://raw.githubusercontent.com/learn-co-curriculum/dsc-phase-2-project-campus/master/halfway-there.gif)

All that remains in Phase 2 is to put our newfound data science skills to use with a large project! This project should take 20 to 30 hours to complete.

## Project Overview

For this project, you will use regression modeling to analyze house sales in a northwestern county.

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this repo. The description of the column names can be found in `column_names.md` in the same folder. 

### Feature Columns 🕵🏽‍♀️
id - Unique ID for each home sold
date - Date of the home sale
price - Price of each home sold
bedrooms - Number of bedrooms
bathrooms - Number of bathrooms, where .5 accounts for a room with a toilet but no shower
sqft_living - Square footage of the apartments interior living space
sqft_lot - Square footage of the land space
floors - Number of floors
waterfront - A dummy variable for whether the apartment was overlooking the waterfront or not
view - An index from 0 to 4 of how good the view of the property was
condition - An index from 1 to 5 on the condition of the apartment,
grade - An index from 1 to 13, where 1-3 falls short of building construction and design, 7 has an average level of construction and design, and 11-13 have a high quality level of construction and design.
sqft_above - The square footage of the interior housing space that is above ground level
sqft_basement - The square footage of the interior housing space that is below ground level
yr_built - The year the house was initially built
yr_renovated - The year of the house’s last renovation
zipcode - What zipcode area the house is in
lat - Lattitude
long - Longitude
sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

### Business Problem 🤔

One of the greatest factors that influence the buying and selling of homes is price. In this study, I will look at a dataset from King County to see what factors influence buying and selling price of a home to help both a homeoweners make informed pricing decisions and home buyers get insight on market price trends and budget to set.

Objectives ✍🏽
👉🏽 This notebook aims to:

- Explore and preprocess the data for regression models
- Build regression models with different experiments

👩🏽‍💻 Machine Learning models to be explored in this project are:

- Linear regression
- Multiple regression
- Polynomial regression
(NB: All models will be explored but application will be dependent on the data)

### Research Question
 - What factors influence house prices and how are they correlated?

### Methods
Steps followed:

### Data Preparation
      1. Importing relevant packages i.e. Pandas, Matplotlib, Seaborn, Scipy, Sklearn and Statsmodel
      2. Data extraction:
          - Dataset `kc_house_data.csv`
     3. Data Cleaning
          - Dropping columns
     4. Data Wrangling
         - Indexing data
         - Dealing with outliers
         - Data standardization and normalization
         - Dealing with categorical data
### Data Modelling
      1. Regression models i.e Linear and multiple were applied to analyze house sales in King county. 
### Model Validation
       The following methods were used to validate the models:
          - Split Train-Test
          - K-Fold Cross validation
          - Bias-Variance Trade off
### Results
       View of King County Median prices from the 70 zip codes given
       
    ![image](https://user-images.githubusercontent.com/119498882/227844540-5b5c56ff-d296-455a-b734-4b3b04385424.png)
     
        Price Trends accross the years using Median price
        
    ![image](https://user-images.githubusercontent.com/119498882/227844832-e2719ba8-1647-409d-81b2-0790cd4e7851.png)
    
        ## Feature Linearity test
        
             ![download](https://user-images.githubusercontent.com/119498882/227845032-8397f762-70c4-4a1d-856d-91df4a3cf69e.png)
             
               A linear relatisonship is observed between Price and Sqft_living, sqft_above, bathrooms and bedrooms
               
        ## Correlation Analysis .corr()>0.70
        
              ![download](https://user-images.githubusercontent.com/119498882/227845596-16d54cf6-58c8-4f31-9f24-2a1c84ee8cd3.png)
                
                    price, sqft_living have a high correlation
                    sqft_living, sqft_above, grade have a high correlation
                    
              Check for top 3 features that are highly correlated to price 
              
                   ![download](https://user-images.githubusercontent.com/119498882/227846096-d6b6e907-76ef-40fd-8d1e-f699125ed2b6.png) 
                   
                         ![download](https://user-images.githubusercontent.com/119498882/227846169-ba51569d-981c-4e2b-868d-7cacbb6dae7f.png)   
                         
             After checking for multicollinearity, the below are the features to be used for modelling:
               
                    ![image](https://user-images.githubusercontent.com/119498882/227846972-47f433e1-2a63-4ff9-bff0-3b42082d95d9.png)
             
             ### Simple Linear Regression

                           ![image](https://user-images.githubusercontent.com/119498882/227847090-ca5db468-3f0f-465f-b6fd-d1a94fcb4681.png)
                               
                              R2 of 45% means the model is only able to account for 45% of the total variation in the dependent variable, while the remaining 55% is                               due to other factors not included in the model or random error. 
                              
                                       ![download](https://user-images.githubusercontent.com/119498882/227847189-09e1afd5-ba4b-4ec4-bdab-fbaa953fa546.png) 
                      
                                 Model accuracy was tested to be 45%
                                 
             ### Multiple Linear Regression
             
                       Added in the othe continuous data i.e.sqft_lot to see if the model would improve:
                                     
                                     ![image](https://user-images.githubusercontent.com/119498882/227847402-79b050ad-9592-473d-95e6-6e45bb0cbc6d.png)

                                         From the summary, the model is only able to account for a total variation of 46% in the dependent variable while the rest                                            54% remain unaccounted for. However the model has improved by 1% with the addition of sqft_lit
                                         
                      Added the categorical data:

                                     ![image](https://user-images.githubusercontent.com/119498882/227847758-79c89ec7-459a-4a3a-b121-b35cbcf1c782.png)
                                     
                           ### Model Validation
                           
                                   1. Split Train-Test
                                          Results:
                                                    Train Mean Squared Error: 0.1138816185667106
                                                    Test Mean Squared Error:  0.11433987779287012
                                                      The test error is not that significantly different from the train meaning that the model is able to
                                                      generalize the future cases well
                                                      
                                   2.  K - Fold Cross Validation score
                                            Results:
                                            
                                            ![download](https://user-images.githubusercontent.com/119498882/227848405-05904cd6-cb12-4f36-b338-8938aeaa9dd7.png)
                                            
                                                  There is no significance differece between Train_score and Test_score
                                            
                                            ![download](https://user-images.githubusercontent.com/119498882/227848576-4db184a3-5649-45a8-b4bc-5eb44d858c66.png)
                                             
                                            ![download](https://user-images.githubusercontent.com/119498882/227848643-3f4b97a9-39f2-40e4-a22b-714e2fe7fc45.png)


                                   3. Bias-Variance Trade-off
                                   
                                             Results:
                                             
                                                  Train bias: 4.134633132394236e-17 
                                                  Train variance: 0.16304818835004653
                                                  
                                                  Test bias: 0.0013848834907673557 
                                                  Test variance: 0.1605880164739517
                                                  
                                                     From the above, our model has a relatively low bias and variance, therefore predictions will be accurate
  
 ### Conclusion
 
            1. The Simple linear regression model can only account for 45% of the total variation for the dependent variables
            2. Multiple regression improves the model as we are now able to account for 59% of the total variations for the dependent variables
            3. Both model validation methods i.e. split trai-test and K-Fold shows that there is no significant difference between the actual and model data.
            4. Bias-Variance tradeoff shows relatively low bias and variance.
            5. We fail to reject the null hypothesis.
            
 ### Recommendation
 
            1. - Apply other advanced methods to see if this improves predictions


 



