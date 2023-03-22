# Predicting Startup Failure

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

### Final Model: Extreme Gradient Boosting

![image](https://github.com/ntdoris/dsc-project-3/blob/main/images/model_performance.png)

* Achieved 80 percent recall, 73 percent ROC AUC score, 72 percent accuracy
* Most important features are 'funding_total_usd', 'founded_year', 'time_first_to_last_funding', and 'international'

![image](https://github.com/ntdoris/dsc-project-3/blob/main/images/feat_importance.png)


## Conclusion

In identifying startups at greatest risk of failure, ABC Ventures should focus on companies that:
* Have low overall funding, or achieve fewer funding rounds
![image](https://github.com/ntdoris/dsc-project-3/blob/main/images/funding_total.png)
![image](https://github.com/ntdoris/dsc-project-3/blob/main/images/funding_rounds.png)

* Are located outside the U.S., or domestically in regions with fewer startups
![image](https://github.com/ntdoris/dsc-project-3/blob/main/images/international.png)
![image](https://github.com/ntdoris/dsc-project-3/blob/main/images/region.png)

* Raise funds at an earlier age


### Next Steps

* Source data on startups founded in 2015 & later
* Separate U.S. and international companies, creating separate models for each category
* Do a deep dive on regions & markets with lowest and highest failure rates


## For More Information

* [Notebook](https://github.com/ntdoris/dsc-project-3/blob/main/nd_project_3.ipynb)
* [Presentation](https://github.com/ntdoris/dsc-project-3/blob/main/presentation.pdf)
* For more information, you can reach me at ntdoris2@gmail.com
