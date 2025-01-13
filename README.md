# Fake News Classifier Using LSTM RNN

## Dataset:
train.csv: A full training dataset with the following attributes:
1. id: unique id for a news article
2. title: the title of a news article
3. author: author of the news article
4. text: the text of the article; could be incomplete
5. label: a label that marks the article as potentially unreliable
        1: unreliable
        0: reliable

## Steps:
1. Understand the Data
2. Data cleaning: Removed any null-values, as here we cannot replace a author name or a title on our own
3. Converted the text into vectors using Word Embedding:
   
   3.1. Initialized Vocabulary size
   
   3.2. Stemming
   
   3.3. Remove any Stop words
   
   3.4. Coverted each word into numbers/vector using One Hot Encoding
   
   3.5. Embedding Representation
   
        3.5.1. Make a length of all the sentences same using padding : here we have used post padding
   
   3.6. Creating Model
   
         3.6.1. Specify the number of dimensions for word embeddings (feature representation for each word)

         3.6.2. Initialize a sequential model, where layers are stacked sequentially
   
         3.6.3. Add an embedding layer to convert words into dense vector representations
   
         3.6.4. Add an LSTM layer with 100 units to capture sequential patterns and dependencies in the input
   
         3.6.5. Add a dense layer with a sigmoid activation to output probabilities for binary classification
   
         3.6.6. Compile the model using binary cross-entropy as the loss function, Adam as the optimizer, and accuracy as the evaluation metric
   
         3.6.7. Fit the model with epoch 10 and batch size 64

   ## Model Evaluation:

   1. Accuracy: 0.9083678541839271
   2. Confusion Matrix:
      
        array([[3158,  261],
               [292, 2324]])
   4. Classification Report:
      
                          precision    recall  f1-score   support
          
                     0       0.92      0.92      0.92      3419
                     1       0.90      0.89      0.89      2616
          
              accuracy                           0.91      6035
             macro avg       0.91      0.91      0.91      6035
          weighted avg       0.91      0.91      0.91      6035

## References for understanding Word Embedding and LSTM RNN
1. https://colah.github.io/posts/2015-08-Understanding-LSTMs/
2. https://www.youtube.com/@krishnaik06/search
3. https://www.geeksforgeeks.org/deep-learning-introduction-to-long-short-term-memory/


