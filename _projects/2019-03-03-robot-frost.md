---
layout: post
title: Robot Frost
subtitle: Epigram Generation Using NLP
date: 2019-03-16 00:00:00
featured_image: '/assets/images/2019/3/default_model.png'
---

>"What is an Epigram? A dwarfish whole, Its body brevity, and wit its soul." 
> -Samuel Taylor Coleridge ("Epigram", 1809)

I trained 5 recurrent neural networks to produce epigrams in the style of 5 very different authors: Robert Frost, Oscar Wilde, T.S. Eliot, Rupi Kaur, and William Shakespeare. Some outperformed others.

I scraped quotes by each author from various parts of the internet using BeautifulSoup. I wanted better familiarity with non-relational databases that weren't using SQL, so I used MongoDB with pymongo, which I might actively prefer now. The number of texts collected varied - Rupi had a limited body of work, Shakespeare had plenty of writings to work off of, and Frost/Eliot/Wilde had enough to work with but would have been less repetitive and would have overfit less easily with greater input. 

I performed a rough exploratory data analysis (EDA) on the texts to better understand the differences in their writing styles, in the hopes of better training individual RNNs with [textgenrnn](https://github.com/minimaxir/textgenrnn), which works on top of Keras and Tensorflow. For the EDA and beginnings of modeling, I used the popular nltk, gensim, vader and spaCy libraries.

<div class="gallery" data-columns="1">
	<img src="/assets/images/2019/3/sentiment.png">
	<img src="/assets/images/2019/3/sylls.png">
	<img src="/assets/images/2019/3/grade.png">
</div>


Insight into why the next two are bolded is necessary. The topic grouping achieved on these types of short texts can kind of vague, so I included quotes from each author that seemed to represent one of the topic-clusters (vague representations of connected ideas that appear together with a comparatively high frequency) contained in each bullet point on the left. 

<div class="gallery" data-columns="1">
	<img src="/assets/images/2019/3/topics1.png">
	<img src="/assets/images/2019/3/topics2.png">
</div>

I will eventually host the Flask app I created on Heroku for others to play with and to collect the really good ones people come up with. 

<p align="center">
<img src="/assets/images/2019/3/flaskwilde.png">
</p>

Until then, here are a few favorites:

  
**Wilde**:
- “The moment one sits down to think, one becomes a present that the poets are not at all.”

  

**Frost:**
- “A brook to this finger long as stood the more, and then be sure—there had been for there. It was the moon’s: she held them to him.”

  

**Kaur:**
- “i am still half-brack into me. i understand this world broke you. it has been so hard on your feet. i don’t blame you for not changing up thinking of all the ends to love you to fill.”

  

**Eliot:**
- “You who were with me in the skeleton, the barren New England midnight and drink out in a crueller that stars.”

  

**Shakespeare:**
- “When thou art that said I have some so enjoy, and conscience with the first than thief, when I have seen thy beauty of a fair weed”

  

For the most part these sort of make a poetic sort of sense, but they fall apart in the last 20%. Here is where more data really would help, trying to do this with between 6k - 110k lines (depending on the author) is pretty tough in terms of patterns really being strongly represented by something like a neural network.

You can see more about the project details in on [GitHub:](https://github.com/alexpfox/epigram_generator)

I'd love to extend this pipeline to quotes from Hunter S. Thompson and other writers in the future.