# Predicting a Top 10 Billboard Hit

Contributor: Lauren Cunningham

Data Sources: Billboard Hot 100 Charts, Spotify API

## Objective and Use Case

The music industry is a particularly competitive one and the billboard hot 100 chart is the music industry's standard for measuring competition and success within the industry. The hot 100 chart ranks the top songs each week on the basis of their online streaming and sales revenue. Popular artists regularly appear in the top 100, but I wanted to see whether we could predict what makes a song break into the top 10. The **main objective** for this project was to build a model that classifies whether a song will be a top 10 billboard hit or miss.


As the digital and music industries coevolve, streaming services such as spotify, apple music and the like have become a major source of revenue for artists. As a representative for a music label, I am interested in implementing the use of this model as a tool for recruiting new artists as well as helping in the production of new music with our existing artists. Ensuring that our artists are making it to the top of billboard charts is very valuable to us as it guarantees more streams and revenue. 


## Data Collection and Cleaning 

For my project, I used the spotify API to gather audio feature data for all songs in the billboard hot 100 weekly charts from 2018-2019. The steps below outline my data collection and cleaning process in my **Data_Collection.ipynb** notebook.  

1. Created dataframe using the billboard hot 100 charts; narrowed data to only include songs from 2018-2019

2. Used the spotify API to gather audio features for each of the rows in the hot 100 dataframe

3. Merged the billboard and audio feature dataframes; **'my_dataframe.csv'** has 7715 rows and 28 columns 

Fortunately my datasets were very clean so I was able to dive right into EDA.


## Visualizations

My **Final_Notebook.ipynb** includes my EDA, modeling and evaluation for my project. For my EDA I wanted to explore both my categorical and continuous features. 

![Image](/genres.png)

I wanted to explore genres to get a better sense of what type of music is frequently on the weekly hot 100. As you can see above, there is an overwhelming amount of country, followed by rap and pop. There are several subgenres and genre mixtures so I decided to focus more on the audio features for the remainder of this project.

**Audio Features**

![Image](/audio_features.png)

![Image](/danceability.png)

![Image](/liveness.png)

![Image](/energy.png)

![Image](/tempo.png)

**Balance of Classes**

![Image](/class_imbalance.png)

As you can see from the above barplot, we have significant class imbalance in our dataset with the majority being outside our Top-10 class. This is important to note as we will need deal with this imbalance in our models.

## Modeling 

I chose to use an F1 score as the metric to evaluate my models. An F1 score measures a model's accuracy on a particular dataset. It is the "harmonic mean" of precision and recall and is useful when false positives and false negatives are more important. By finding a balance between precision and recall, it is particularly useful when the distribution of our classes are imbalanced. In the context of this project, we have significant class imbalance, therefore an F1 score seemed most appropriate. 

For modeling, I started with a baseline Dummy Classifier model and got an F1 score of 0.0. The Dummy Classifier was predicting everything as being outside of the Top-10 class, this is due to our class imbalance. To preprocess my data, I used a standard scalar and SMOTE to combat this class imbalance. My Random Forest model ending up being my best model with an F1 score of 0.60. Looking at feature importance, danceability, duration, energy, tempo and valence seemed to be the most indicative for my model. 

## Conclusions 

Using the random forest model, we can predict whether a song will break into the top 10 on the hot 100 charts on the basis of certain audio features - with danceability, energy, tempo and valence being the most important to our model. 

This model is valuable to managers, producers and artists as it can help new and existing artists in the industry make their way up the billboard charts. 

