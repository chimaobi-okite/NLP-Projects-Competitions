# News Catgorization

## Motivation 
After gaining a handful of knowledge about NLP with transformers and huggingface, I decided to complete an end-to-end (From Getting Data to model deployment) project using these technologies and also compare performance to  that of traditional ML techniques and RNN-based deeplearning approaches.


## Context 
From the beginning, since the first printed newspaper, every news that makes into a page has had a specific section allotted to it. Although pretty much everything changed in newspapers from the ink to the type of paper used, this proper categorization of news was carried over by generations and even to the digital versions of the newspaper. Newspaper articles are not limited to a few topics or subjects, it covers a wide range of interests from politics to sports to movies and so on. For long, this process of sectioning was done manually by people but now technology can do it without much effort. 

## Objective
To use Natural Language Processing to predict which genre or category a piece of news will fall in to from the title and excerpt. 

## Data
The data used here was scrapped from [arisetv](https://www.arise.tv/), one of the most popular news tv in Nigeria. The data folder contains the train and test 
csv files as well as a notebook with code I used to scrap the data. 
* Size of training set: 4,594 
* Size of test set: 811 
* FEATURES: Title:  Title of a news article. Excerpt: short text from the article. 
* There are six distinct sections where each story may fall in to. The Sections are labelled as follows : 0: 'health', 1 :'business', 2: 'politics', 3:'entertainment', 4:'sports', 5: 'tech'

* Want to know more about the data! :stuck_out_tongue_winking_eye: ?
check the hugging dataset card [here](https://huggingface.co/datasets/okite97/news-data) or the data folder for the codes


## Results
| Model                                          | F1-score              | Model size (mb) |
| ---------------------------------------------- | --------------------- |--------------- |
| Logistics Regression + DistilBert Features     |  0.8830944556627599   |  268.036   |
| Fine-tuned Transformer                         | 0.9073589381747773    |  268.000   |
| Logistics-regression + TfidfVectorizer |  0.82   |  0.36  |
| Logistics-regression + TfidfVectorizer + over_sampling |  0.87   |  0.36  |


### Summary Of Results

Looking at the table above, I can say that traditional ML techniques is still the go-to for text classification. This is putting into consideration the model's
performance and size. We can see that the fine-tuned transformer is **744** times larger than the simple Logistics regression with TFID based features (Thats alot to just push aside for 3.44% increase in performance). 

I also experimented with RNNs but was not able to get a good score. It wasnt surprising though,  owing to the fact that there are just about 4000 datapoints with 6 different classes to predict , so even pretrained glove embedding could not able to learn enough




## Demo

Check out a gradio demo on how the model works [here](https://huggingface.co/spaces/okite97/news-demo)

Check the notebooks for more details. 
The *newsml.ipynb* files includes interesting stuffs like experiment tracking with mlflow, parameter optimization, model interpretation with lime etc
