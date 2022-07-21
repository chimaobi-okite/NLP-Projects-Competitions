# Covid -Tweet Classification


![covid](https://user-images.githubusercontent.com/70687495/180223270-13dd1044-dea8-4237-8f80-706231697ede.JPG)
## Problem Statement

ML-driven sentiment analysis is an important tool to understand communities’ feelings around major issues such as COVID-19. 
Gathering comprehensive social data for sentiment analysis can be limited, however, if data collection relies only on keywords such as ‘coronavirus’ or ‘covid’.

The objective of this challenge is to develop a machine learning model to assess if a Twitter post is about COVID-19 or not. 
This model will help gather tweet data about the epidemic without relying only on key words like ‘covid’ or ‘coronavirus’ being present,
allowing researchers and engineers to gather a more comprehensive dataset for sentiment analysis.

This model could be put into practice as part of a larger effort to understand online sentiment around COVID-19,
and inform future communications and public interventions by governments and non-government public health organisations.

## Data 
The data used for this challenge has been collected by the Zindi team 
via Twitter API from tweets over the past year. The are ~7,000 tweets in the train set and ~3,000 in the test set.
Tweets have been classified as covid-19-related (1) or not covid-19-related (0). All tweets have had the following keywords removed:

* corona
* coronavirus
* covid
* covid19
* covid-19
* sarscov2
* 19
The tweets have also had usernames and web addresses removed to ensure anonymity.

### Accessing Data

Note that the github url in the pd.read_csv method does not exist. Kindly 
go to [zindi](https://zindi.africa/competitions/zindiweekendz-learning-covid-19-tweet-classification-challenge/data) and access it from there.

## Approach 

Here I used different machine learning approaches to solve this task in other compare results easily.

1. With traditional text processing and ml techniques, I was able to acheieve an F1 score of around 88%, though it was difficult to get the right kind of processing to apply
and I based on more trial and error . Check out the **Traditional ML notebook**  to see more. I also experimented with different models. 


2. Since there was just few labelled examples, using a DistilBert transformer as feature extractor and training a logistics regression model on top,
I achieved around 89% accuracy on validation data. This approach was also more inituitive and easier to interprete.

3. I also finetuned a Distilbert model for text claaification and had a higher F1 score of around 91%. The slight increase in 
performance could be attributed to the fact that I had just few labelled examples.

Approach 2 and 3 canbe seen in the **TransformerForTextClassification** notebook. 
