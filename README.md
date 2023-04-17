# Disaster tweet classification

This is a notebook created for the Kaggle competition here: https://www.kaggle.com/competitions/nlp-getting-started.

The aim of the competition was to predict which Tweets are about real disasters and which ones are not.

In order to do this, I trained a RNN model with a 2 LSTM layers. I used binary crossentropy for the loss function and an Adam optimizer. I achieved an accuracy 
of 78.21% on the test data of the competition. This was in line with the 78.795% predicted by the k-fold cross validation I performed.

### Key steps
- Data exploration: I noticed there were duplicate tweets with different labels. As it was only a small number (18), I manually adjusted the labels for these tweets. 
- Overfitting: we initially used 10 epochs for the training. However, after plotting the loss and accuracy over epochs it was apparent this was 
overfitting the model. As a result, 3 epochs were used for the final model.
- K-fold cross validation: the data was split into 4 separate folds. I then performed k-fold cross validation and found no significatn differences between the folds. 
The average accuracy of the folds was 78.795%. As a result, we trained the final model on the whole dataset.

### Future improvements
I chose an RNN model with 2 LSTM layers to learn more about how these worked. However, it would be worth exploring how transformers perform on this dataset. Transformers 
have been the performing the best on these kinds of problems in industry. I suspect a pre-trained transformer model like BERT might perform better on this dataset.
