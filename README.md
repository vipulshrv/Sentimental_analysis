# Sentimental_analysis
Built a NLP model to analyse the sentiment in a sentence and return an appropriate emoji.
The model uses pre-trained 50-dimensional GloVe word embeddings and LSTM layer in Keras to give an accuracy score of 90.2% on unseen data.   

Dataset: The dataset used here is EMOJISET which contains sentence seperated by new line and classifies them into one of 5 different emojis.

Steps Done

1. Data Preprocessing- Removed punctuations, converted to lower case and converted the different sentences into lists. Converted different emojis to integers from 1-5.
2. Using GloVe Word Embeddings - GloVe Word Embeddings convert words into unique 50 dimensional vector using the context in which each word is used. Using these pre trained word embeddings we defined the dictionary word_to_vec.
3. Creating a vector for each sentence using the word to vec dictionary.
4. Padding and truncating- Setting up a standard length of 10 words for each sentence. Padding and truncating wherever necessary.
5. Train-Dev-Test Split. Splitting the data by 80:10:10
6. Defining the LSTM architecture. My model architecture consists of:
    1) Embedding Layer
    2) 2 (LSTM and dropout) layer
    3) Dense Layer
    4) Softmax activation
7. Training the model in Keras, and testing it with dev set. The best scoring metrics on the dev set were- Model details: batch size=32, optimizer=Adam, loss=categorical crossentropy , metrics=accuracy, epochs = 50, LSTM output units=128, dropout=0.5
8. Testing on the test set 

Results: Model scores 93.2% accuracy on training and 90.2% accuracy on test dataset.
