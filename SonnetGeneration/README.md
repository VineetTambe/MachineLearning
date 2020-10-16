# This is a model which generates a sonnet:

Working

1. the dataset is first broken into individual sentences and stored in a list

2. this list is then tokenized to get word index + a zero token (which means null)

3. for each line (sentence) in the input list-> create a sequence for every word such that it has the token of itself + previous words token in that sentence 
so for a sentence containing n words there will be a nxn matrix for each sentence contining 1 word to n words - 
[0 0 0          0        token_first_word]
[0 0 0 token_first_words token_second_word ] ...

this is done in order to train the neural network so that it predicts the next likely word based on the input sequence of previous word - 
so the last value can be  treated as a the output and the rest of the list as input. in this manner success words are generated based on previous outcome.

5. perform one hot encoding on the last column (value to be predicted)

6. building the model - 

simple model - sequential +embedding (dimension = 240 due to lot of vatiaions as input is a language) + bidirectional LSTM + dense layer with softmax activation function + categorical loss function 

7. now train the model epochs = 100 (due to presence of unsructured data)

## Output:

![Output](https://github.com/VineetTambe/MachineLearning/blob/master/SonnetGeneration/ouput.PNG)
