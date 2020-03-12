# Machine Learning For Detecting Money Laundering

## Introduction
Money laundering is a huge problem globally, it is estimated that $2tn of illicit funds is laundered worldwide each year and integrated into the legitimate economy. People often assume such anonymous shell companies are all based offshore, in fact there exists vast networks of UK registered companies being used for financial crime. UK companies carry a facade of legitimacy whilst also being incredibly quick and easy to set up from anywhere in the world, making them extremely attractive for criminals. 

## Project Aim
The aim of the project is to build a classification model that can detect suspicous companies based solely on publicly available data from the Companies House website. The product would be used in conjuction with exisiting AML procedures to flag companies that require further investigation.

## Data Collection
I collated a dataset of suspicious companies previously linked to money laundering and financial crime networks, based on a list of names suggested by investigative journalists and information leaks including data from the Troika, Azerbaijani and Russian Laundromats. The other "negative" cases were sampled randomly from the complete Companies House database, working on the assumption that the fraction of UK companies being used for financial crime undetected is very small.

Once the list of company names is compiled, I created multiple tools to scrape data for each company in relation to: the company itself; the registered company officers; the Person of Significant Control/Relevant Legal Entity; filing history. The data i set up in four relational databases connected by the company number. Data on Companies House is entered freehand so extensive cleaning and validation is required, for example in the case of unifying instances of the same address entered slightly differently. The various addresses were unified using fuzzy matching and confirmed with regular expressions for street name and number.

## Feature Engineering
Based on the exploratory data analysis and common red flags discussed in investigations, I created several new predictive features. For example, a count of the number of officers based in a "secrecy jurisdiction", defined as a country with Financial Secrecy Index score greater than 60, as per the Tax Justice Network ranking. Other important features included: number of active officers and number of non-human officers.

## Model Selection & Optimisation
I tested a number of different classification models including: K-nearest neighbours, Support Vector Machines, Logistic Regression and Random Forest. After tuning the respective hyperparamters using a GridSearch, the Random Forest Classifier returned the best mean cross-validation score.

## Results
The best performing Random Forest Classifier produced an accuracy score of 96.9% on the testing set, compared to a baseline score of 50%. In this case false negatives are an unwanted risk, so a high recall score is important, the best Random Forest produced a recall of 96.7% on the testing set.

## Conclusion
[TBU]

## Output Model to Pickle
[TBU]

## Productionisation
[TBU]
