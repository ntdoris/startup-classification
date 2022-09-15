# Project 3 - Classification: Predicting Startup Failure

## Project Overview & Business Problem

Startups have been the source of much attention in the last few years, with many new companies forming amid a favorable economic backdrop. Given the potential for an economic downturn on the horizon, venture capital companies want to be confident in their portfolios and particularly aware of companies that are at risk of failing. This project uses classification models to predict whether a startup will succeed or fail based on a number of financial and descriptive features.

## The Data

This project uses Crunchbase data on companies founded between 1902 and 2014, sourced from Kaggle. It can be found in the data folder in this GitHub repository. Crunchbase is one of the leading sources for data on early-stage startups. While the full dataset contained ~50,000 observations, including companies in operating status, we focused on a subset containing companies that either closed or were acquired, founded in 1980 or later, resulting in around ~7,000 observations.

## Modeling

### Target

* In this analysis we target status - closed, indicating the company failed, and acquired, indicating the company succeeded
* The status class is imbalanced, with around 60 percent of companies acquired and 40 percent closed. We address this within each of the models with relevant hyper parameters

### Evaluation Metrics

* As our primary focus is to correctly identify the companies that failed, we use recall as our primary evaluation metric. Of all the failed companies in the data, how many did our model correctly identify?
* Our secondary consideration is the ROC AUC score, which represents the true positive rate versus the false positive rate, as we do not want to ignore false positives entirely. False positives represent startups that are incorrectly classified as closed, but actually succeeded
* Finally, we look at accuracy. How accurate is the model overall in predicting status?
![image](https://user-images.githubusercontent.com/102126161/190449893-655939bb-5939-4d58-b6ff-8dee0a3cefce.png)

### Final Model: Extreme Gradient Boosting
![image](https://user-images.githubusercontent.com/102126161/190449824-702332c7-1d63-4fb8-a100-2e6578897b51.png)

* Most important features are 'venture', 'international', and 'time_to_first_funding'
![image](https://user-images.githubusercontent.com/102126161/190449798-d2d75fd2-e382-40ad-94c1-416ba8d9e127.png)

## Key Takeaways

* Funding First
* Timing Matters
* Location, Location, Location 

![image](https://user-images.githubusercontent.com/102126161/190449774-0c938c26-e409-4d7b-9c95-5689b5b22827.png)
![image](https://user-images.githubusercontent.com/102126161/190449727-ea5611cf-b05b-4fd9-b6fe-3fb7a35239e7.png)
![image](https://user-images.githubusercontent.com/102126161/190449747-825e62e1-fcd8-4d6c-9177-0e34cbd88157.png)
![image](https://user-images.githubusercontent.com/102126161/190449697-dda40e45-c4dd-4123-8d09-2b63bdd4b25f.png)


### Next Steps

* Source more recent data
* Use economic indicators to improve prediction
* Separate U.S. and international companies, creating separate models for each category

## For More Information

* Notebook
* Presentation
* For more information, you can reach me at ntdoris2@gmail.com
