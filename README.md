Medical Text Classifier

Approach:
The program consists of three main tasks.
• Data Preprocessing
• Processing Data
• Building KNN Model
Data Pre-processing:
Report
• Pre processed data in following order:
1) Remove stopwords.
2) Remove Punctuations
3) Remove words whose length is less than 4.
4) Lemmatize words
5) Remove digits present.
• As the dataset was imbalanced checked performance for doing under sampling of classes who were in great numbers and at same time over sampled the classes who were less in numbers.
Processing Data:
1) Converted list of documents which contained list of words to CSR matrix.
2) As the data is textual used TF-IDF technique to process the data.
Building KNN Model:
1) KNN model is based on finding K nearest neighbors which are basically vectors in our vector space model.
2) Used Cosine similarity for distance measurement.
3) Calculated K most similar vectors and obtained their class labels as prediction for text
classification.
Methodology: Data Pre-processing:
1) After tokenizing text from documents, lots of pre-processing was needed as documents contained some unnecessary repeated terms which are not considered important in TF-IDF processing technique such as was, with, the,etc.
Used NLTK for removing all such stopwords.
2) Some of words still contained punctuation mark such as ‘ artery). ’ , ‘ (shock’
associated with them so it was necessary to get rid of those punctuation marks. So these words were replaced without punctuation marks as ‘artery’ and ‘shock’.
Used regular expression python library for removing punctuation marks.
3) Removed words whose length is less than four as those words are of less importance
Used Code from class activity
4) Some words were considered different due to case mismatch so converted all words
to lower case.
5) Lemmatized the words. Words such as accessed were now replaced by access.
Used NLTK for Lemmatization.
The results varied for each pre-processing step got best results when used all the above filtering techniques.
Handling Imbalanced Data:
The datasets contained uneven distribution of samples, 4805 for class 5, 3163 for class 1
followed by 3051,1925,1494 for class 4,3,2 respectively.
Under sampled class 5,1,4 data to 3000 samples and over sampled with replacement class 3 and 2 samples to 3000. So now training data contains 15000 samples.
Got F1 score of 0.73 which was less compared to output without sampling which was 0.756 and later increased to 0.7691 after preprocessing .
Processing Data:
There are various techniques to process text, I used TF-IDF (Term frequency Inverse Document frequency) technique taught in class and used code from in class activity to build CSR matrix. Normalized matrix with L2 norms so that no need to calculate L2 norms while calculating cosine similarity and just dot product of test instance and training instances will serve the purpose.
Combined train data and test data initially to generate CSR matrix.
KNN Model:
1) Cosine similarity indicated better measurement than jaccard similarity and Euclidean distance similarity measures.
2) Divided train data into train and validation set and computed f1 score for different values of K and choose the best k value.
