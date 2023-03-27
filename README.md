# Phase 2 Project

Another module down--you're almost half way there!

![awesome](https://raw.githubusercontent.com/learn-co-curriculum/dsc-phase-2-project-campus/master/halfway-there.gif)

All that remains in Phase 2 is to put our newfound data science skills to use with a large project! This project should take 20 to 30 hours to complete.

## Project Overview

For this project, you will use regression modeling to analyze house sales in a northwestern county.

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this repo. The description of the column names can be found in `column_names.md` in the same folder. 

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
        
  ![image](https://user-images.githubusercontent.com/119498882/227851567-a2e19e9b-6a99-49c3-8ada-b14c743dbc47.png)
    
On the trend of prices map, we used median prices from the 70 given zip codes. It is observed that there is no linear relationship
between year built and prices. It is expected as house prices are volatile and are influenced by different direct and indirect factors
including economic and political. (Each year cannot be the same)!

        ## Feature Linearity test
        
   ![download](https://user-images.githubusercontent.com/119498882/227845032-8397f762-70c4-4a1d-856d-91df4a3cf69e.png)
            
A linear relatisonship is observed between Price and Sqft_living, sqft_above, bathrooms and bedrooms
               
 ## Correlation Analysis .corr()>0.70
        
   ![download](https://user-images.githubusercontent.com/119498882/227845596-16d54cf6-58c8-4f31-9f24-2a1c84ee8cd3.png)
                
 price, sqft_living have a high correlation
 sqft_living, sqft_above, grade have a high correlation
                    
Identify for top 3 features that are highly correlated to price 
              
   ![download](https://user-images.githubusercontent.com/119498882/227846096-d6b6e907-76ef-40fd-8d1e-f699125ed2b6.png) 
                   
   ![download](https://user-images.githubusercontent.com/119498882/227846169-ba51569d-981c-4e2b-868d-7cacbb6dae7f.png)   
                         
 After checking for multicollinearity, the below are the features to be used for modelling:
               
   ![image](https://user-images.githubusercontent.com/119498882/227846972-47f433e1-2a63-4ff9-bff0-3b42082d95d9.png)
             
  ### Simple Linear Regression

   ![image](https://user-images.githubusercontent.com/119498882/227850337-0e9b5325-0d7b-4c75-b6e1-111ae9e9c852.png)
                               
  R2 of 45% means the model is only able to account for 45% of the total variation in the dependent variable, while the remaining 
  55% is due to other factors not included in the model or random error.                             
                              
  ![download](https://user-images.githubusercontent.com/119498882/227847189-09e1afd5-ba4b-4ec4-bdab-fbaa953fa546.png)
                                       
 Model accuracy was tested to be 45%
   
   ![image](https://user-images.githubusercontent.com/119498882/227851884-985c39a2-2fb5-4f11-8877-5ea603695e08.png)
   
 The prediction column shows price prediction using the model above i.e. print(results.predict([7.07,8.64,1])) = [12.64642298] (First row results)
                                  
   ### Multiple Linear Regression
             
Added in the othe continuous data i.e.sqft_lot to see if the model would improve:
                                     
   ![image](https://user-images.githubusercontent.com/119498882/227847402-79b050ad-9592-473d-95e6-6e45bb0cbc6d.png)

From the summary, the model is only able to account for a total variation of 46% in the dependent variable while the rest 54% remain
unaccounted for. However the model has improved by 1% with the addition of sqft_lit                                           
                                         
Added the categorical data:

   ![image](https://user-images.githubusercontent.com/119498882/227847758-79c89ec7-459a-4a3a-b121-b35cbcf1c782.png)
                                     
   ### Model Validation
                           
     1. Split Train-Test
     
         Results:
         
         Train Mean Squared Error: 0.1138816185667106
         Test Mean Squared Error:  0.11433987779287012
         The test error is not that significantly different from the train meaning that the model is able to generalize the
         future cases well
                                                      
     2.  K - Fold Cross Validation score
     
         Results:
                                            
   ![download](https://user-images.githubusercontent.com/119498882/227848405-05904cd6-cb12-4f36-b338-8938aeaa9dd7.png)
                                            
    There is no significance differece between Train_score and Test_score
                                            
   ![download](https://user-images.githubusercontent.com/119498882/227848576-4db184a3-5649-45a8-b4bc-5eb44d858c66.png)
                                             
   ![download](https://user-images.githubusercontent.com/119498882/227848643-3f4b97a9-39f2-40e4-a22b-714e2fe7fc45.png)

3. Bias-Variance Trade-off

   Results:
   
   Train bias: 4.134633132394236e-17, 
   Train variance: 0.16304818835004653
    
   Test bias: 0.0013848834907673557, 
   Test variance: 0.1605880164739517
                                                  
 From the above, our model has a relatively low bias and variance, therefore predictions will be accurate
  
 ### Conclusion
 
            1. The Simple linear regression model can only account for 45% of the total variation for the dependent variables
            2. Multiple regression improves the model as we are now able to account for 59% of the total variations for the 
            dependent variables
            3. Both model validation methods i.e. split trai-test and K-Fold shows that there is no significant difference between 
            the actual and model data.
            4. Bias-Variance tradeoff shows relatively low bias and variance.
            5. We fail to reject the null hypothesis.
            
 ### Recommendation
 
            1. - Apply other advanced methods to see if this improves predictions

 



