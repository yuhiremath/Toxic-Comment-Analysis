# Toxic-Comment-Analysis
Project to determine the probability of a wikipedia comment being toxic, severe_toxic, obscene, threat, insult and identity_hate.

## Dataset for this project
The dataset for this problem can be found in this link --> https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data

## Methods Used
#### Removing Punctuations
* Used the string package which has list of english punctuations to remove the punctuations from the sentences.
* This is done because it helps in processing the text later.
* Alternate approach is to convert these punctuation to specific words.

#### Tokenization
* All the words are made seperate elements.
* Implemented using 're' package of regular expression.

#### Removing Stopwords
* Stopwords does not give postivity or negativity of the sentence.
* Removing stopwords is done using nltk.corpus.stopwords.

#### Lemmatizing and Stemming
* Lemmatizing is done using nltk.WordNetLemmatizer. 
* Lemmatizer ignores the words that is not present in it's own vocabulary. So, those are taken care by Stemming.
* Stemming is crude pruning done using nltk.PorterStemmer.

#### Bag of words (Generating a frequency vector)
* Implemented using sklearn.feature_extraction.text.CountVectorizer. 
* This gives back a sparse matrix of frequency of words.
* Also, the value of n in n-grams can be set using this function.

#### Tf-Idf
* Calculated Tfidf values using sklearn.feature_extraction.text.TfidfVectorizer. 
* This gives a sparse matrix of Tf-Idf values.
* Also, the value of n in n-grams can be set using this function.

## Model
* Used Logistic Regression to train for each label ie Toxic, Severe_toxic.etc

## Score
This approach has given a score(AUC) of 97% in kaggle.

## Note
* In this code I have trained using only TfIdf values to achieve 97% score.
* Also, there is commented section where I have tried to implement word embedding for feature generation using Word2Vec.
