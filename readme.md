# SMS Spam Classification using Machine Learning

## 1. DESCRIPTION
--------------

The SMS Spam Collection is a set of SMS tagged messages that have been collected for SMS Spam research. It contains one set of SMS messages in English of 5,574 messages, tagged acording being ham (legitimate) or spam. 

## 2. Data Set Information:
-----------

There is one collection:

- The SMS Spam Collection v.1 (text file: smsspamcollection) has a total of 4,827 SMS legitimate messages (86.6%) and a total of 747 (13.4%) spam messages.

The files contain one message per line. Each line is composed by two columns: one with label (ham or spam) and other with the raw text. Here are some examples:

ham   What you doing?how are you?
ham   Ok lar... Joking wif u oni...
ham   dun say so early hor... U c already then say...
ham   MY NO. IN LUTON 0125698789 RING ME IF UR AROUND! H*
ham   Siva is in hostel aha:-.
ham   Cos i was out shopping wif darren jus now n i called him 2 ask wat present he wan lor. Then he started guessing who i was wif n he finally guessed darren lor.
spam   FreeMsg: Txt: CALL to No: 86888 & claim your reward of 3 hours talk time to use from your phone now! ubscribe6GBP/ mnth inc 3hrs 16 stop?txtStop
spam   Sunshine Quiz! Win a super Sony DVD recorder if you canname the capital of Australia? Text MQUIZ to 82277. B
spam   URGENT! Your Mobile No 07808726822 was awarded a L2,000 Bonus Caller Prize on 02/09/03! This is our 2nd attempt to contact YOU! Call 0871-872-9758 BOX95QU

Note: messages are not chronologically sorted.

## 3. Data Pre-Processing:
-----------

In filtering of spam, the pre-processing of the textual information is very critical and important. Main objective of text data preprocessing is to remove data which do not give useful information regarding the class of the document. Furthermore we also want to remove data that is redundant. Most widely used data cleaning steps in the textual retrieval tasks are removing of stopwords and performing stemming to reduce the vocabulary.

## 4. Removal of Stop Words:
------------

In information textual retrieval there are words that do not carry any useful information and hence are ignored during spam detection. In general and for document classification tasks we consider them as words intended to provide structure of the language rather than the content and mostly include pronouns, prepositions and conjunctions.

## 5. Apply Tf-IDF Vectorizer for feature extraction:
------------

Our Naïve Bayes model requires data to be in either Tf-IDF vectors or word vector count. The latter is achieved using Count Vectorizer, but we’ll obtain the former through using Tf-IDF Vectorizer. TF-IDF Vectorizer creates Tf-IDF values for every word in our text messages. Tf-IDF values are computed in a manner that gives a higher value to words appearing less frequently so that words appearing many times due to English syntax don’t overshadow the less frequent yet more meaningful and interesting terms.

## 6. Model Training:
-----------

In this step, we will train our model. Sklearn has many classification algorithms we can choose from. In this problem, we are using Naive Bayes algorithm. It's popular in text classification because of its relative simplicity. In sklearn, the Naive Bayes classifier is implemented in MultinomialNB. MultinomialNB needs the input data in word vector count or tf-idf vectors which we have prepared in data preparation steps. Below is the code that we will need in the model training step. You can see how easy it is to train a NaiveBayes classifer in sklearn.

