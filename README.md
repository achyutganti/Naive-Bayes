# Naive-Bayes
Naive Bayes classifier

The aim of this project is to train a Naive Bayes classifier to classify documents into positive or
negative sentiments. The classifier uses probabilites of words to estimate whether a new test
document holds a positive or a negative sentiment to it. The dataset used to train the classifier
was IMDB Movie Review Dataset. The project was written in Python programming language.
Also, we added a couple of extensions to the Naive Bayes classifier,mainly data-preprocessing
steps, so that we could make it more accurate than use it in its raw form. Those are Stemming
and removing the stop words.

Stemming is the process of grouping words that are forms of itself. For example run, running,
runs etc. These words can be grouped together bacause they all mean the same.
Stop Words - There are words that are used to fill the sentence and they do not hold much
information in the sentence. Those are words like a, an, the, but etc. These are used to
make the sentence clear and they themselves do not hold much value to what we want to
achieve. We instead focus on words like good, bad, amazing etc. that have some sentiment
to them.

Project Write up

1Q. Describe your approach, any interesting problems encountered or experiments
performed, packages used, etc.
The approach was pretty straight-forward. The dataset was pre-divided into train and test data.
Each section was further divided into two classes i.e., positive and the negative class. We began
to train the classifier with the training data and used Python's powerful built-in data-structures like
dictionaries and lists to help us with the process. The approach is as follows
We first figured out the number of unique words in the dataset and their counts and named it
feature vector. This is the vocabulary of our dataset.
After finishing that, we needed to figure out how many of those words are in the positive
class documents and in the negative class documents. We recorded those too in
dictionaries. We used dictionaries so that we could use the keys(words) and the
values(counts) to find the probabilites later on.
Note: All we needed was the counts of the words in the positive and in the negative classes.
Next step was to find the probabilites for each word for both postitve case and for the
negative case.
We can easily classify a new document if we have the probabilities.


We thought it would be a good experiment to train the classifier on raw data as well as on pre-
processed data and then compare the results. But the feature vector for the raw data (without
pre-processing) did not work out.

It had characters other than alphabets like punctuations,alpha numerics and numbers. The result
was not so good and so we went back to pre-processing step.


Packages/ Libraries used
No packages or libraries were used in building the classifier itself. Everything was written from
scratch. But we used a couple of packages for enhancing the performance of the classifier. They
are

NLTK stopwords - This library has a set of words in it, also known as stop words, that can be
imported so that they can be filtered out from the original dataset before training the
classifier. It is done because these stop words don't contribute much on building the classifier
and by removing them will make the classifier more efficient.
NLTK PorterStem - This library was used to stem the words that are redundant and hold the
same meaning. For example, words like teacher, Teacher, TEACHER, teachers, Teachers,
teaching etc., all mean the same and can be converted to 'teacher' or 'teach' by the process
of stemming.
2Q. Demonstrate / test the effectiveness of your classifier.
The Naive Bayes Classifier is a simple yet an effective classifier in terms of performance. It works
on the fact that the occurance of a positive word is more in the positive class documents than in
the negative class documents. And so the probabilities vary.
After training the classifier using the IMBD Movie data, we tested the classifier on a test set that
had 12500 positive documents and 12500 negative documents in it. Out of all the documents, the
algorithm could predict the sentiments of more than 20500 documents correctly. The test
accuracy was about 82.93%

Out of 12500 negative documents 10918 were predicted corrected.
Out of 12500 positive documents 9815 were predicted corrected.
3Q. Include a discussion/analysis of your results. (Consider the meaning of the dataset.
How does your model perform?)
After performing the experiment, we tested the algorithm on a data that has never been seen
before by the Classifier. One issue that we will have to handle is any new words if they are
present in the test data. If the test data has words that were not present in the train data when the
Classifier was being trained, Python will throw a Key Error. One way to handle this was we
assigned tiny probability to these words.
The Classifier did a decent job in classifying both kinds of documents, positive and negative, but
after looking at the results we noticed that it does slightly better on the negative documents than
on the positive ones. As mentioned above 10918 documents out of 12500 negative documents
were classified correctly but only 9815 out of all the positive ones were correctly classified.
We also observed the results and the accuracy of the classifier before and after pre-processing.
The accuracy of the classifier was slightly better after pre-processing but not much. We observed
that pre-processing increased the accuracy by about 4% in the positive class documents and by
about 1% in the negative ones. But pre-processing reduced the size of the training dataset. So
the time taken to train the classifier after the processing was significantly less. Before pre-
processing the data, the classifier took more than 30 minutes to learn from the data but after the
pre-processing step we could manage to train the classifier within 20 minutes.
Further Investigation
Did you try any alternative pre-processing? Why?
This is not a huge pre-processing step but apart from filtering the stop words from the original
data and also stemming the words, we also filtered out the punctuations, numbers and other
alpha-numeric characters from the dataset. We believed that having these in the dataset would
not make the Classifier any more efficient.
Did you look at alternative datasets? What were the results there?
Before performing the experiment on the Movie Reviews Dataset, we made our own custom
dataset to train the Naive Bayes Classifier. The results were amazing. Although we did not record
the accuracy of the classifier, because the dataset was smaller and we knew what to expect, the
algorithm performed well in predicting the sentiments of the documents. As for new words that
were not in the training data, we had to handle them differently which reduced the efficiency but
the algorithm still managed to perform well.
Some misclassifications that we observed. And the General Rule!
The Naive Bayes Classifier does a reasonable job in predicting the sentiments of the documents
but it has its limitations. When the test document has unknown words, i.e., words that were not
included when training the classifier, the classifier shows poor performance. In our case, when
the test data had too many words that were unknown, assigning small probabilities would not
help the classifier in any way to learn the sentiment accurately and hence would be misclassified.
That is one case where we observed some misclassifications of the documents.
So the general rule, according to our analysis or what we have observed is, have a rich training
data. If you train your Classifier having a business problem in mind and trying to overcome it but
if you test it on an entirely different business problem, then you would never achieve good
results.






