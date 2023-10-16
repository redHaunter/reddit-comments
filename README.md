# Improving Bag of Words (BoW) and Clustering for Text Classification

In this project, we aim to enhance the capabilities of Bag of Words (BoW) and subsequently perform classification using a clustering algorithm we developed.

To begin with, we started by preprocessing the text data. This involved removing common English stopwords, punctuation marks, and pronouns. We then calculated the frequency of word occurrences by splitting the text into pandas series. This frequency distribution forms the foundation of our BoW representation. By selecting an appropriate frequency interval, we can refine the BoW by selecting relevant words, effectively reducing the dimensionality of the word space. 

Subsequently, we employed pre-trained Word2Vec embeddings using the Gensim library API. With the help of these embeddings, we identified ten similar words for each word in our dataset. We then removed these similar words from our series. To expedite the similarity search, we used the AnnoyIndexer. Furthermore, we leveraged the Numba library to accelerate various processing tasks. In addition to this, we removed training data instances with all-zero vectors.

Following these data preprocessing steps, we created feature vectors for each word in every comment. These vectors encoded the position of each word in relation to its presence in the vocabulary or its similarity to other words. Words not found in the vocabulary or similar word lists were encoded as zeros.

Once our data was prepared, we applied a clustering algorithm, as elaborated in our article. It is worth noting that due to the extensive volume of data and limitations in processing capabilities, we had to implement the clustering algorithm for optimal performance.

Upon obtaining the final list, denoted as 'L,' we assigned labels to the dominant comments based on the category they belong to. For testing, we replicated the same preprocessing steps on the test data. We calculated the distance from the test data to the nearest cluster center and assigned the appropriate label accordingly.
