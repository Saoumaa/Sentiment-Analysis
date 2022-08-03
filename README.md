# Sentiment Analysis

## Loading and Cleaning the data

This task is to perform sentiment analysis on some reviews from scratch.

The data (texts files) are stored in a a drive, so the first thing done is to get the data from that gdrive.

There are 1000 reviews for both positive and negative reviews respectively.

THE positive review was given a sentiment of 1 while negative review was given a sentiment of 0.

The following libraries were imported to perform this: 
1. string
2. re
3. pathlib from path

The next thing done is to remove punctuations and numbers from the reviews, the imported libraries were used to do this. The reason for doing this is because we don't need a model that understands punctuations but understand word by their usage.

The result from the removal of punctuation and numbers is showwn below.

![image](https://user-images.githubusercontent.com/104036386/182556985-dbdd3aa3-42f8-46ea-a93b-581fee486fad.png)

## Getting the reviews length

The lengths of all the reviews are placed in a python list, and to do this the reviews are splitted using the python split function, then the number of words present in the review is their word count.

ALl the processing mentioned above are done for both cases of negative and positive reviews.

he next thing done is creating both training and testing set. The train set consists of 1400 reviews, 700 from positive and negative reviews. While the test set contain 600 reviews, 300 from both reviews.

## Storing in a dataset.

A dictionary was created to store the reviews, its sentiment, and word counts. Then afterwards the are generally stored in a dataframe.

The dataframe formed was shuffled to make the sentiment not follow each other since they are initially arranged fron negative to positive. This wll prevent the model used from being biased.

#### Standard Deviation

The standard deviation of the reviews length is calculated and stored for reference use.

## Counting the words in the dataset.

To count the words in all of the data, the total words in all the reviews were calculated and stored in a list.

From that, the unique words in the total word list were stored in another list.

Then they are counted using the python count function. The word counts were stored in another list.

Then a dictionary was created to store the word and its count together.

### Sorting the word in asceding order.

With the new dictionary gotten, the words were sorted based on the number of count of each word. The top words are known as stopwords because they occur mostly in all the documents. In this case, they are not removed.

### Ranking by word counts

The word were ranked based on their counts. The most occuring word in all the review documents is ranked 1st, the second was ranked 2nd and so on.

## Tokenizing

The next thing done is to tokenize the words in the documents. The tokenizing is based on the word rankings.

The tokenized words are being stored in a list and added to the previously created dataset.

## Truncating and Padding

The tokenized reviews are truncated and padded using keras preprocessing.

## Modeling

Three models were created to perform sentiment analysis. To do this, some other necessary libraries were imported. 

![image](https://user-images.githubusercontent.com/104036386/182564169-5f1ba679-e219-4d65-9530-e4096ab64e11.png)

### Multi-Layer Perceptron

This is the first model used in this case. It was built with keras Sequential class and other processing were performed.

The image below shows how it was done.

![image](https://user-images.githubusercontent.com/104036386/182564724-51ae0802-c94c-4506-8eb1-b0e470cde149.png)

The result is shown below. The model was trained over 2 epochs.

![image](https://user-images.githubusercontent.com/104036386/182564950-39764d18-9646-4c6b-be27-c2d4ddcc365f.png)

### One Dimension Convolutional Neural Network

The images below shows how the model is built, trained and used.

![image](https://user-images.githubusercontent.com/104036386/182565512-bdce4043-39bd-4bad-bde4-b8b400633299.png)

![image](https://user-images.githubusercontent.com/104036386/182565591-32e289c9-09b7-4ff5-8afb-50bbc0c25380.png)

### Long Short Term Memory Recurrent Neural Network

The images below shows how the model was built, trained and used.

![image](https://user-images.githubusercontent.com/104036386/182565889-065b0843-a149-401e-bcf8-2ca3dfa33f56.png)

![image](https://user-images.githubusercontent.com/104036386/182566044-5d776ae7-365d-4da0-bdc7-3b1fedc95454.png)

Looking at the result, the model can be seen to be ovefitting.

TO improve this, it will be advised to remove the stopwords.
