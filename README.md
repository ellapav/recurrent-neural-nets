# recurrent-neural-nets

%---------------------------------------- Data ------------------------------------------%

Keras has several datasets that can be loaded, one of them is the IMDB dataset for sentiment classification of reviews (see https://keras.io/datasets/). This is a dataset of 25,000 movies reviews from IMDB, labeled by sentiment (positive/negative). Reviews have been preprocessed, and each review is encoded as a list of word indexes (integers).

Ex. "3" encodes the 3rd most frequent word in the data. 

We'll consider the top 50000 words. (i.e. num_words = 5000)



%------------------------------------ Goal of the project ---------------------------------------%

Create a Keras sequential model to create an LSTM model for predicting sentiment.

Here is the architecture:

1. Embedding layer with 64 hidden states (maps words to a vector of length 8, 16, or 32)

2. An LSTM layer ( it can have either 16, 32, 64, or 128 hidden states)

3. Dense layer with sigmoid output (0 = good sentiment, and 1 = bad sentiment)

The model is compiled with binary cross entropy and the Adam optimizer. 

We train for 10 epochs and report the accuracy on the 'out of sample' test set.

We also report a table of accuracies when we vary the vector length and the hidden states. 


%------------------------------------ Required Packages --------------------------------------%

```
keras
```

%------------------------------------ Results --------------------------------------%
This dataset contains 25,000 movie reviews, labeled as either positive or negative. 
In this model we considered the 5000 most used words, and chunks of 500 word strings, and used this to find long-term dependencies inside the strings of words.

Using an embedding layer, then an LSTM layer (included in the Keras Sequential model package), and a final dense layer we found the following accuracies when we varied Hidden States and Vector Length:

<img src="./accuracy-results.png" alt="accuracy-results" width="250"/>


Thus, all the Accuracies of the vectors and hidden states were in the range 85.2% to 87.2%, which is fairly high and indicates this LSTM model did a good job discerning whether a string of words had a good or bad sentiment. 
One thing that may improve computation time when running this model is the use of mini-batching. 
