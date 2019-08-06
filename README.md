# Actor or Movie? Classifying Wikipedia Articles

### Introduction

For this project, I used data from 20 different Wikipedia articles. The dataset includes the pages for 10 actors and 10 movies. Rather than analyze the text directly, I used part-of-speech (POS) tagging and named entity recognition (NER) tagging on word-tokenized data to obtain numerical measurements of the dataset. More specifically, I counted the amount of each tag for each actor or movie.

I used four different machine learning algorithms for classifying the articles. The algorithms I used are Naive Bayes, Decision Tree, and the ensemble method Gradient Boosting.

### About the Data Set

#### Actors

This is an informal project, so I simply chose actors I like. That said, I tried to select a broad range of actors, from B-Movies to blockbusters. My chosen actors are Tessa Thompson, Lupita Nyong'o, Winona Ryder, Amy Poehler, Bruce Campbell, Adam Scott, Nicolas Cage, Tim Curry, Margot Robbie, and Sandra Bullock.

#### Movies

For each actor above, I chose a movie they appeared in. The movies are "Sorry to Bother You", "Us", "Heathers", "Wet Hot American Summer", "Evil Dead II", "Piranha 3D", "Con Air", "The Rocky Horror Picture Show", "I, Tonya", and "Miss Congeniality."

### The Process

#### The General Idea

If the machine learning models perform well, this suggests that there are quantifiable differences between how actors and movies are written about on Wikipedia. Nota bene, this is a simple, straightforward analysis and it does not prove anything.

#### Pre-processing

1. Use the [Wikipedia library](https://pypi.org/project/wikipedia/) to gather the content of all Wikipedia pages I will use as my dataset.
2. Pre-process this data to remove citations, punctuation, numbers, other extraneous characters, and stopwords and to tokenize by word. 


#### Analysis

1. Tag the word-tokenized data by part-of-speech and by named entity.
2. Build a frequency distribution of the top three parts of speech and top three named entities
3. Use the counts from each frequency distribution to calculate (for each movie or each actor):
    * Mean
    * Maximum
    * Minimum
    * Range
    * Standard Deviation
4. Select K best features from Movies and from Actors
5. Train ML models
6. Calculate mean F1 score and mean accuracy score for each model

### Results

Naive Bayes and Gradient Boosting are tied for both the highest mean F1 score and the highest mean accuracy score (85.3% and 85%, respectively). I would thus consider these two to be the most reliable models. Decision Tree did not perform quite as well, with an F1 of 81.3% and an accuracy of 70%.

These scores indicate that there are quantifiable differences between Actor and Movie articles and that these differences can be shown effectively even with a small dataset and limited POS and NER tagging.
