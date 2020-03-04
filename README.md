# Sentweetment Analysizer
<p align="center">
  <img src="images/tweetpic.jpeg">
</p>  

Over the years Twitter has continued to become a stronger social media platform with over 338 monthly active users.  Being a microblogging platform, it has allowed for people to interact with each other by expressing themselves through a tweet, which others can reply or show support through retweeting a comment or ‘liking’ it by clicking favorites.  This platform has become quite important to many politicians as a way to express their positions and interact with electorate.  My objective with this project was to analyze the candidate’s tweets through NLP analysis, all to gauge the polarity of their message and find features that could be indicative of the potential likability of their words in future tweets.

## Table of Contents

* [General Information](#general-information)
    * [Data Gathering](#data-gathering)
    * [Data Information](#data-information)
* [Technologies](#technologies)
    * [Database](#database)
    * [Python](#python)
    * [Visualization](#visualization)
* [Future Improvements](#future-improvements)

### What are you trying to do?
<p align="center">
  <img src="images/dnc_candidates.png">
</p>  

## General Information
Investing in a home is a milestone many aim to achieve, whether viewed as just a starter home or potential AirBnB investment, it all begins with data.  This project began with just a simple believe to be tested: The ratio between bedrooms to bathrooms have an impact on home values. But it’s potential with further enrichment is quite limitless. 

![](images/distributions.png)

### Data Gathering:
<p align="center">
  <img src="images/realtylogos.png">
</p>

Data used for this analysis was gathered from Zillow, Realtor, and Realty Austin websites.  The data gathering techniques where separated into three phases, which are located under the ```src``` folder.  Two ```csv``` files, the results of the webscraping, are stored in the ```data``` directory.

1)   Scraping:  Three scrappers were used to gather current listing information from each site, code can be found under ```scrapper``` folder.  
2)  Transform:  It was transformed into a clean pandas dataframe through custom functions, located on the ```data_transformer``` folder.
3)  Cleansing:  Functions on the ```data_cleansing``` folder utilized the transform functions to clean the data and store clean data back to mongodb.   

### Data Information:
Data used in the study included square footage, number of beds, baths, and value for all single and multi-family homes, condo, and townhomes with active listings in the Austin housing market from December 2019 to January 2020, inside the city limits. This data was used to calculate averages and test for significance between equal ratio vs unequal ratio homes. All figures shown in the article represent the mean value for each data point unless otherwise specified. 

### Hypothesis Testing:

###### Step 1: Set up the hypothesis
The null hypothesis is that the ratio between bedrooms to bathrooms has no statistically significant difference to the mean value of homes.

Alternative hypothesis is that there is a significant difference to the mean value.

>**H0: μ = μ 0**

>**H1: μ ≠ μ 0**

###### Step 2: Select test statistic
To test this hypothesis the z-test was chosen.
The significance level was set at: 0.05

A z-test is a statistical test used to determine whether two population means are different when the variances are known and the sample size is large.

<p align="center">
  <img src="images/z-statistic.png">
</p>

###### Step 3: Set up decision rule
Reject the null hypothesis if test-statistic > 1.96 or if test-statistic < -1.96.
<p align="center" style="width:10%" >
  <img src="images/normdist.png">
</p>

###### Step 4: Compute the test statistic
This will be a two-tailed test

![](images/z-score.png)

###### Step 5: Conclusion
Given the results of our test we conclude that we must reject the null-hypothesis.  There is enough evidence to say that ratios between homes do have an effect on home values.
The z-score of 3.386 > 1.96 with a p-value of 0.001 well below our 0.05 significance level. 


### Sample Information:
Detailed Information on the analysis process is on ```real_estate_analysis.ipynb``` file, under the ```notebooks``` folder.

The IQR (interquartile range) method of outlier detection was implemented as part of the data cleansing process.

<table style="width:120%" align="center">
  <tr>
    <td>Original Total sample-size: 4,880</td>
    <td>Adjested Total sample-size: 4,318</td>
  </tr>
  <tr>
    <td>Original Equal sample-size: 1,605</td>
    <td>Adjested Equal sample-size: 1,424</td>
  </tr>
  <tr>
    <td>Original Unequal sample-size: 3,275</td>
    <td>Adjested Unequal sample-size: 2,894</td>
  </tr>
</table>
<p align="center">
  <img src="images/Original Sample.png" width="400">
  <img src="images/Adjusted Sample.png" width="400">
  <img src="images/count_tables.png">
  <img src="images/map.png">
</p>
The map shown only displays 2,000 of my 4,318 total sample.  

## Technologies
<p align="center">
  <img src="images/logos.png">
</p>

###### Database:
Data Storage: Mongodb<br>

###### Python:
Data Gathering: Beautiful Soup, API, Selenium<br>
Data Analysis: Python 3, Numpy, Pandas, Scikit-Learn, Scipy, HTML, CSS, Flask<br>

###### Visualization:
Data Visualization: Plotly, Matplotlib, Seaborn

## Future Improvements
• Use another sentiment library (Spacy, NLTK).<br>
• Enrich data-set with debate, interview, and major tv apperance dates<br>
• Use different model, like Random Forest Classifier<br>