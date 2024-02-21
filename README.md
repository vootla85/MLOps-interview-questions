# MLOps-interview-questions
Uvicorn- It sis a local server to install fast api.
stemming - It use fixed rules such as remove able,ing, es,s, etc to derive a base word
   for example sleeping - sleep
               ablilty -abli in this case abli doesn't make sense to base word.
Lemmatization - It use knowledge of a language (linguistic knowledge to derive a base word).
What is bag of words and drawbacks of bag of words
Bag of words is a simple technique for natural language processing where text is represent as a bag of words, Where each word in text is represented by number.
It use to represent text data.
Benefits of Bag of words:-
The bag-of-words model is a simple and effective way to represent text data for machine learning. The model is easy to understand and implement, and has been shown to be effective for a variety of tasks such as classification, clustering, and information retrieval.
Drawbacks of bag of words:
   it does not take into account the order of the words. This can be a problem when trying to understand the meaning of a sentence or paragraph. 
   it does not account for different forms of a word, such as plural forms.
Some common challenges working with bag of words:
curse of dimensionality: The number of features (words) in the data can grow very quickly as the size of the corpus increases. This can make it difficult to train a model, as the number of parameters can become very large.
bag-of-words models do not account for the order of words in a text. This can be problematic for tasks such as sentiment analysis, where the meaning of a sentence can be very different depending on the order of the words.
TFIDF-  tf means term frequency, IDF means Inverse document frequency
 it is a measure, used in the fields of information retrieval (IR) and machine learning, that can quantify the importance or relevance of string representations (words, phrases, lemmas, etc)  in a document amongst a collection of documents (also known as a corpus). 
 or
 
handy metric for determining how important a term is in a document
Three main application of TFIDF are 1)information retrieval 2)text summarization 3) Machine learning
Using TF-IDF in machine learning & natural language processing
Machine learning algorithms often use numerical data, so when dealing with textual data or any natural language processing (NLP) task, a sub-field of ML/AI dealing with text, that data first needs to be converted to a vector of numerical data by a process known as vectorization. TF-IDF vectorization involves calculating the TF-IDF score for every word in your corpus relative to that document and then putting that information into a vector (see image below using example documents “A” and “B”). Thus each document in your corpus would have its own vector, and the vector would have a TF-IDF score for every single word in the entire collection of documents. Once you have these vectors you can apply them to various use cases such as seeing if two documents are similar by comparing their TF-IDF vector using cosine similarity.

Image with each step of the tf-idf algo broken down with numbers and examples
A = “The car is driven on the road”; B = “The truck is driven on the highway” Image from freeCodeCamp - How to process textual data using TF-IDF in Python (https://www.freecodecamp.org/news/how-to-process-textual-data-using-tf-idf-in-python-cd2bbc0a94a3/)

Using TF-IDF in information retrieval
TF-IDF also has use cases in the field of information retrieval, with one common example being search engines. Since TF-IDF can tell you about the relevant importance of a term based upon a document, a search engine can use TF-IDF to help rank search results based on relevance, with results which are more relevant to the user having higher TF-IDF scores.

Using TF-IDF in text summarization & keyword extraction
Since TF-IDF weights words based on relevance, one can use this technique to determine that the words with the highest relevance are the most important. This can be used to help summarize articles more efficiently or to simply determine keywords (or even tags) for a document.
