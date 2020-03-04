# Sentweetment Analysizer
<p align="center">
  <img src="images/tweetpic.jpeg">
</p>  

## Table of Contents

* [General Information](#general-information)
    * [Data Gathering](#data-gathering)
* [Technologies](#technologies)
    * [Database](#database)
    * [Python](#python)
    * [Visualization](#visualization)
* [Future Improvements](#future-improvements)

## General Information
<p align="center">
  <img src="images/dnc_candidates.png">
</p>  

Over the years Twitter has continued to become a stronger social media platform with over 338 monthly active users.  Being a microblogging platform, it has allowed for people to interact with each other by expressing themselves through a tweet, which others can reply or show support through retweeting a comment or ‘liking’ it by clicking favorites.  This platform has become quite important to many politicians as a way to express their positions and interact with electorate.  My objective with this project was to analyze the candidate’s tweets through NLP analysis, all to gauge the polarity of their message and find features that could be indicative of the potential likability of their words in future tweets.

### Data Gathering:
<p align="center">
  <img src="images/realtylogos.png">
</p>

Data gathered for this analysis was collected using twitters API along with python library called ```GetOldTweets```.

###### Conclusion


### Sample Information:
Detailed Information on the analysis process is on ```dnc_race.ipynb``` file, under the ```notebooks``` folder.  The information was from DNC Candidates twitter feeds from the beginning of their twitter accounts to February 24th.  Analysis was conducted from the candidates announcement to February 24th.  
<p align="center">
  <img src="images/weekly_tweet_count.png">
</p>

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
• Use another sentiment library (Spacy, Vador).<br>
• Enrich data-set with debate, interview, and major tv apperance dates<br>
• Use different model, like Random Forest Classifier<br>