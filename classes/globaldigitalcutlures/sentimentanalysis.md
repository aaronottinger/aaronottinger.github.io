# Getting Started with Sentiment Analysis in Python: Positive and Negative Movie Reviews

Introductory remarks

# Directions 	

1. Create a virtual environment in Python (see Dylan Medina’s tutorial [here](https://youtu.be/_fCazmtnUzY)). 

2.	Install natural language processing toolkit: 

`pip install nltk`

Either a successful installation of NLTK will follow, or you may find that it has already been installed. 

3. Now open up Python (if the natural language toolkit was already installed, make sure that you're using the corresponding version of Python), and "import" the Natural Language Toolkit. 

`import nltk`


`nltk.download()`

At this point, a pop-up window should appear which lists all the corpora, models, and packages that you can download. Under "Collections," select "All packages."

![an image of the NLTK downloader and its contents](nltk_downloader.png)


4. Once you have downloaded "All packages," breath! You've now made it past a major hurdle. Because you have downloaded all of the packages you now have access to a wide variety of datasets, including the Moview Reviews Corpus we're going to use today. If you need to, this really is a good time to walk away and take a breath. 

Yay, movie reivews! But wait, don't get too excited. We're not actually **reading** the moview reviews, as you might read them in *The New Yorker*, or a similar periodical. Our movie reviews have already been compiled into a corpus. Instead, we're going to **classify** each document, otherwise referred to as **document classification**. And we're going to classify each movie review, or each document, as either positive (for a good review) or negative (for a bad review).

> **Reflection:** What's one problem that you see with classifying documents (movie reviews, in this case) as either postive or negative? Is it possible to critque or be hard on a film, and yet, to still appreciate or value it as a work of art? Are all reviews either positive OR negative? So while document classification is a powerful tool for parsing out positive and negative texts, it's important to appreciate that this process can be a little reductive. It may provide a "broad stroke" analysis of a large body of texts, and indeed, the benefit is reading thousands of documents within a second or two. But, we need to remember that such a "broad stroke" approach necessarily comes at the expense of rhetorical subtlties and nuances.

5. Now we must load and prepare our dataset by importing the Natural Language Tookit, followed by the Movie Review Corpus, and then we'll organize this corpus at random (**Note:** If you get lost at any point or you if lost your progress, feel free to re-activate your virtual environment and fire up Python). 

`>>> from nltk.corpus import movie_reviews`
`>>> documents = [(list(movie_reviews.words(fileid)), category)`
`...              for category in movie_reviews.categories()`
`...              for fileid in movie_reviews.fileids(category)]`
`>>> random.shuffle(documents)`



![an image of the NLTK downloader and its contents](most_important_features.png)

