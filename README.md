# Predicting a Top 10 Billboard Hit

Contributor: Lauren Cunningham
Data Sources: Billboard Hot 100 Charts, Spotify API

## Objective and Use Case

The music industry is a particularly competitive one and the billboard hot 100 chart is the music industry's standard for measuring this competition within the industry. The hot 100 chart ranks the top songs each week on the basis of their online streaming and sales revenue. Popular artists regularly appear in the top 100, but I wanted to see whether we could predict what makes a song break into the top 10. **The main objective for this project was to build a model that classifies whether a song will be a top 10 billboard hit or miss.** 


As the digital and music industries coevolve, streaming services such as spotify, apple music and the like have become a major source of revenue for artists. As a representative for a music label, I am interested in implementing the use of this model as a tool for recruiting new artists as well as helping in the production of new music with our existing artists. Ensuring that our artists are making it to the top of billboard charts is very valuable to us as it guarantees more streams and revenue. 


## Data Collection and Cleaning 

For my project, I used the spotify API to gather audio feature data for all songs in the billboard hot 100 weekly charts from 2018-2019. The steps below outline my data collection and cleaning process in my **Data_Collection.ipynb** notebook.  

1. Created dataframe using the billboard hot 100 charts; narrowed data to only include songs from 2018-2019

2. Used the spotify API to gather audio features for each of the rows in the hot 100 dataframe

3. Merged the billboard and audio feature dataframes; **'my_dataframe.csv'** has 7715 rows and 28 columns 

Fortunately my datasets were very clean so I was able to dive right into EDA.


## Visualizations

My **Final_Notebook.ipynb** includes my EDA, modeling and evaluation for my project. For my EDA I wanted to explore 



## Modeling 

I chose to use an F1 score as the metric to evaluate my models. An F1 score measures a model's accuracy on a particular dataset. It is the "harmonic mean" of precision and recall and is useful when false positives and false negatives are more important. By finding a balance between precision and recall, it is particularly useful when the distribution of our classes are imbalanced. In the context of this project, we have significant class imbalance, therefore an F1 score seemed most appropriate. 

#### Dummy Classifier 


#### Logistic Regression


#### Random Forest 



## Conclusions 