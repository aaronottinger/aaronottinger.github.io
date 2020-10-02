# Getting Started with Sentiment Analysis in Python: Positive and Negative Movie Reviews

Introductory remarks

> Sources: [The NLTK Book](http://www.nltk.org/book/ch06.html) and Syak Paul's article for Data Camp, ["Simplifying Sentiment Analysis in Python"](https://www.datacamp.com/community/tutorials/simplifying-sentiment-analysis-python).

# Directions 	

1. Create a virtual environment in Python (see Dylan Medina’s tutorial [here](https://youtu.be/_fCazmtnUzY)). 

2.	Install natural language processing toolkit (either type in the code below or copy and paste it): 

`pip install nltk`

Either a successful installation of NLTK will follow, or you may find that it has already been installed. 

3. Now open up Python (if the natural language toolkit was already installed, make sure that you're using the corresponding version of Python), and "import" the Natural Language Toolkit. 

`import nltk`


`nltk.download()`

At this point, a pop-up window should appear which lists all the corpora, models, and packages that you can download. Under "Collections," select "All packages."

![an image of the NLTK downloader and its contents](nltk_downloader.png)


4. Once you have downloaded "All packages," breath! You've now made it past a major hurdle. Because you have downloaded all of the packages you now have access to a wide variety of datasets, including the Moview Reviews Corpus we're going to use today. If you need to, this really is a good time to walk away and take a breath. 

Yay, movie reivews! But wait, don't get too excited. We're not actually **reading** the moview reviews as one might read them in *The New Yorker*, or a similar periodical. Our movie reviews have already been compiled into a corpus. Instead, we're going to classify each review or document (i.e. **document classification**) as either positive (for a good review) or negative (for a bad review).

> **Pause for Reflection:** What's one problem that you see with classifying documents (movie reviews, in this case) as either postive or negative? Think about the way you feel about some recent films you've watched. Would you be able to classify them as strictly positive or negative? Now, think about how you actually communicate your feelings about a film to different audiences--will all of those audiences register and understand your feedback in the same way? 

5. Now we must load and prepare our dataset by importing the Natural Language Tookit, followed by the Movie Review Corpus. In this same step, we will organize the corpus into individual words as categories, and then shuffle those categories at random. In the next step, we will label those categories as either positive or negative. 

**Note:** If you get lost at any point or you if lost your progress, just re-activate your virtual environment and fire up Python and jump in, starting here:

       import nltk

       from nltk.corpus import movie_reviews

       import random


       documents = [(list(movie_reviews.words(fileid)), category)

                   for category in movie_reviews.categories()
              
                   for fileid in movie_reviews.fileids(category)]

       random.shuffle(documents)
       
6. Next up: Let's define a feature extractor. 

What's a feature extractor? A feature extractor function constructs a dictionary of sorts. We need this collection of words so that our classifier knows what to look for. We don't want too many features because then our learning algorithm will be too idiosyncratic, focusing on too many details, which will make it harder to generalize our search as we add more data. That's what is referred to as ["overfitting"](https://elitedatascience.com/overfitting-in-machine-learning). 

So how does our feature extractor know which words to look for? For classifying documents, like we're doing, our features can be a set of words (our "dictionary"), and then our algorithm will look for words in the reviews that match this set. But instead of just thinking of a bunch of words ourselves, we can use the corpus in front of us to tell us which words are the most freuntly occurring words. We'll select the top 2,000 words in this exercise. Then we can will define the feature extractor so that it just checks to see which word appears in which document or movie review, typifying it as either positive or negative.
 




![an image of the NLTK downloader and its contents](most_important_features.png)

