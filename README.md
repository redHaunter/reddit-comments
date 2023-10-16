# Improving Bag of Words (BoW) and Clustering for Text Classification

In this project, we aim to enhance the capabilities of Bag of Words (BoW) and subsequently perform text classification using a clustering algorithm that we developed.

## Data Preprocessing

To begin, we conducted thorough data preprocessing. This involved the removal of common English stopwords, punctuation marks, and pronouns. We then calculated the frequency of word occurrences by splitting the text into pandas series. This frequency distribution forms the foundation of our BoW representation. By selecting an appropriate frequency threshold, we refine the BoW by selecting relevant words, effectively reducing the dimensionality of the word space.

## Leveraging Word2Vec Embeddings

Subsequently, we employed pre-trained Word2Vec embeddings through the Gensim library API. With the help of these embeddings, we identified ten similar words for each word in our dataset. We then removed these similar words from our series. To expedite the similarity search, we used the AnnoyIndexer. Additionally, we leveraged the Numba library to accelerate various processing tasks. We also removed training data instances with all-zero vectors.

## Feature Vector Creation

Following these data preprocessing steps, we created feature vectors for each word in every comment. These vectors encoded the position of each word in relation to its presence in the vocabulary or its similarity to other words. Words not found in the vocabulary or similar word lists were encoded as zeros.

## Clustering Algorithm

Once our data was prepared, we applied a clustering algorithm, specifically the K-means algorithm, as elaborated in our article. It's essential to note that, given the extensive volume of data and computational limitations, we had to implement the clustering algorithm for optimal performance.

## Label Assignment

Upon obtaining the final list, denoted as 'L,' we assigned labels to the dominant comments based on the category they belong to. 

## Testing

For testing, we replicated the same preprocessing steps on the test data. We calculated the distance from the test data to the nearest cluster center and assigned the appropriate label accordingly.
