# Sentimental_analysis
Built a NLP model to analyse the sentiment in a sentence and return an appropriate emoji.
The model uses pre-trained 50-dimensional GloVe word embeddings and LSTM layer in Keras to give an accuracy score of 90.2% on unseen data.   

Dataset: The dataset used here is EMOJISET which contains sentences and classifies them into one of 5 different emojis.

Part 1: Using GloVe Word Embeddings
GloVe Word Embeddings convert words into unique 50 dimensional vector using the context in which each word is used. Using these pre trained word embeddings we defined the dictionary word_to_vec.

Part 2: Using LSTM: Long Short Term Memory
LSTM has a special architecture which enables it to forget the unnecessary information .The sigmoid layer takes the input X(t) and h(t-1) and decides which parts from old output should be removed (by outputting a 0). This gate is called forget gate f(t). The output of this gate is f(t)*c(t-1). 
The next step is to decide and store information from the new input X(t) in the cell state. A Sigmoid layer decides which of the new information should be updated or ignored. A tanh layer creates a vector of all the possible values from the new input. These two are multiplied to update the new cell sate. This new memory is then added to old memory c(t-1) to give c(t). 
Finally, we need to decide what we’re going to output. A sigmoid layer decides which parts of the cell state we are going to output. Then, we put the cell state through a tanh generating all the possible values and multiply it by the output of the sigmoid gate, so that we only output the parts we decided to.

My model architecture consists of:
1) Embedding Layer
2) 2 (LSTM and dropout) layer
3) Dense Layer
4) Softmax activation

Model details: batch size=32, optimizer=Adam, loss=categorical crossentropy , metrics=accuracy, epochs = 50, LSTM output units=128

Results: Model scores 93.2% accuracy on training and 90.2% accuracy on test dataset.
