# MLOps-interview-questions
Uvicorn- It is a local server to run fast api.

Gunicorn :
Gunicorn is mainly an application server using the WSGI standard.

Gunicorn supports working as a process manager and allowing users to tell it which specific worker process class to use. Then Gunicorn would start one or more worker processes using that class.

Gunicorn would act as a process manager, listening on the port and the IP. And it would transmit the communication to the worker processes running the Uvicorn class.
And then the Gunicorn-compatible Uvicorn worker class would be in charge of converting the data sent by Gunicorn to the ASGI standard for FastAPI to use it.
Gunicorn (or also Uvicorn) as a process manager with Uvicorn workers to take advantage of multi-core CPUs, to run multiple processes in parallel.

Uvicorn's capabilities for handling worker processes are more limited than Gunicorn's.


stemming - It use fixed rules such as remove able,ing, es,s, etc to derive a base word
   for example sleeping - sleep
               ablilty -abli in this case abli doesn't make sense to base word.
               
Lemmatization - It use knowledge of a language (linguistic knowledge to derive a base word).

What is bag of words and benfits and drawbacks of bag of words
Bag of words is a simple technique for natural language processing where text is represent as a bag of words, Where each word in text is represented by number.
It use to represent text data.

Benefits of Bag of words:-
The bag-of-words model is a simple and effective way to represent text data for machine learning. The model is easy to understand and implement, and has been shown to be effective for a variety of tasks such as classification, clustering, and information retrieval.

Drawbacks of bag of words:
   it does not take into account the order of the words. This can be a problem when trying to understand the meaning of a sentence or paragraph. 
   it does not account for different forms of a word, such as plural forms.
   
Some common challenges working with bag of words:

Curse of dimensionality: The number of features (words) in the data can grow very quickly as the size of the corpus increases. This can make it difficult to train a model, as the number of parameters can become very large.

bag-of-words models do not account for the order of words in a text. This can be problematic for tasks such as sentiment analysis, where the meaning of a sentence can be very different depending on the order of the words.

Sample example:
Main use of Bag of words is feature Extraction
He is coming to office late.
She is coming to office early
They are coming to school ontime.
We are not going to movie.
Below is the output after stemming of lemmatization
come office late
come office early
come school ontime
go movie

Below Bag of words from the above Sentences
Come office late early school ontime go movie

	F1	F2	F3	F4	F5	F6	F7	F8	O/P
	come	office	late	early	school	ontime	go	movie	Target
S1	1	1	1	0	0	0	0	0	[11100000]
S2	1	1	0	1	0	0	0	0	[11010000]
S3	1	0	0	0	1	1	0	0	[10001100]
S4	0	0	0	0	0	0	1	1	[00000011]
F1-F8 is input for model training.
One more disadvantage is come and office words both assigned by the value 1 but both have different weight 
So, there is no weightage for context.

TFIDF-  tf means term frequency, IDF means Inverse document frequency
the frequency of the word in each document in the corpus. It is the ratio of number of times the word appears in a document compared to the total number of words in that document. It increases as the number of occurrences of that word within the document increases. Each document has its own tf.
 
Inverse Data Frequency (idf): used to calculate the weight of rare words across all documents in the corpus. The words that occur rarely in the corpus have a high IDF score. It is given by the equation below.
 
Combining these two we come up with the TF-IDF score (w) for a word in a document in the corpus. It is the product of tf and idf:
  
Example:
S1: good boy
S2: good girl
S3:boy girl good.

                                TF= No of repetition of words in sentence/No of words in sentence.
								
	    S1	S2	S3
good	1/2	1/2	1/3
Boy	    1/2	0	1/3
girl	0	½	1/3

                                       IDF=log(No of sentence/No of sentence containing words)
words	IDF
Good	Log(3/3)=0
Boy	Log(3/2)
girl	Log(3/2)
                                                   TF*IDF
												   
	F1	           F2	            F3	        O/P
	Good	      Boy        	   Girl	
S1	½*0=0	    ½*Log(3/2)	    0*Log(3/2)	    0,0.088,0
S2	½*0=0	    0*Log(3/2)	    ½*log(3/2)	    0,0,0.088
S3	1/3*0=0 	1/3*Log(3/2)	1/3*log(3/2)	0,0.058.0.058


Three main application of TFIDF are
 1)information retrieval
 2)text summarization
 3) Machine learning

Using TF-IDF in machine learning & natural language processing
Machine learning algorithms often use numerical data, so when dealing with textual data or any natural language processing (NLP) task, a sub-field of ML/AI dealing with text, that data first needs to be converted to a vector of numerical data by a process known as vectorization. TF-IDF vectorization involves calculating the TF-IDF score for every word in your corpus relative to that document and then putting that information into a vector (see image below using example documents “A” and “B”). Thus each document in your corpus would have its own vector, and the vector would have a TF-IDF score for every single word in the entire collection of documents. Once you have these vectors you can apply them to various use cases such as seeing if two documents are similar by comparing their TF-IDF vector using cosine similarity.

Image with each step of the tf-idf algo broken down with numbers and examples
A = “The car is driven on the road”; B = “The truck is driven on the highway” Image from freeCodeCamp - How to process textual data using TF-IDF in Python (https://www.freecodecamp.org/news/how-to-process-textual-data-using-tf-idf-in-python-cd2bbc0a94a3/)

Using TF-IDF in information retrieval
TF-IDF also has use cases in the field of information retrieval, with one common example being search engines. Since TF-IDF can tell you about the relevant importance of a term based upon a document, a search engine can use TF-IDF to help rank search results based on relevance, with results which are more relevant to the user having higher TF-IDF scores.

Using TF-IDF in text summarization & keyword extraction
Since TF-IDF weights words based on relevance, one can use this technique to determine that the words with the highest relevance are the most important. This can be used to help summarize articles more efficiently or to simply determine keywords (or even tags) for a document.

what is word embbedding?
word embbedding is mathematical representation of text.
In NLP model - there dont understand the text so we need to represent the text as numbers.
There are several methods to represent text as a number
1) one hot encoding : In this representation we create one vector as no of words you have in vocabulary, fill everey word with 0 except word which your are trying to represent as 1.
   example
   I	You	Bag	Apple	cat	Dog
   
   0	0	1	0	0	0

Vector representation is long based up on the vocabulary.


2) count based representation:
   1) bag of words
   2) N-gram or 2-gram: similar to bag of words but we take  gorup of n words and count there occurance in a sentence.
   3) TFIDF

   
3) Embeddings:
   Embeddings :It represent the word in a dense vector, while making sure that similar words are close to each other in the embedding space.

What is dense vector ?
Vector representing the word does not mostly consists of zeros.
Similar words
Example:
Apple  is a fruit.
Apple is a mobile brand.
Tea and Pea almost near .

What is embedding space?
Where your embedding data lives.
Different types of embedding are 
1)	Mathematical embedding
2)	One – dimensional embeddings
3)	Two -dimensional embeddings
4)	Three- dimensional embeddings
For example:
I   you   He    Late    Never   Bag   Wizard    Apple   cat   dog
2   11     3     7     13        5      18         8     20    23

Suppose these are the mathematical or one dimensional representation of word embedding, then
      I     HE         Bag        Late  Apple              You
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
1     2     3     4     5     6     7     8     9     10    11    12    13    14

Let consider bad and Apple 
8-5=3 is  the similarity between these two data points
Cosine simialary is also to find the similarity between  two vector

Custom embedding:
Text   --->Embedding Layer ------>  Core Model ----->   Model Out Put

Word2vec:
There are 2 different approaches for word2vec:
1)	continuous Bag-of-words:
2)	Skip-gram
For Example:
I wish none of this has happened. So do all who live to see such times. But that  is not up to us to decide.

I   
        ---->   Wish       In continuous bag of words  we need guess middle word.

 None
                I
Wish      ---->             In skip-gram we guess surrounding  words
                None

Glove stands for global vector:
Fast Text
ELMo.

CPU is central processing Unit.
1)	It handles main processing function of a computer
2)	Core count -2-64 
3)	Runs processes serially
4)	Better at processing one big task at a time

GPU is Graphics processing Unit.
1)	Handles graphic and video rendering
2)	Core count- thousands
3)	Runs processes in parallel
4)	Better at processing several smaller tasks at a time.


   

