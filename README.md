# health-mate-machine-learning
Machine learning model for Health Mate Application
We are splitting the dataset into 75% for training and 25% for validation and then using tokenizer to create the vocabularies based on training dataset. Since we are handling text 
classification, so we are using RNN (Recurrent Neural Network). For the layers we are using Bidirectional LSTM because the meaning of the words can be different depending the 
arrangement of the words itself. Beside LSTM we are using Dropout to prevent overfitting and the final layer is only one node because we only have two classification for this 
dataset. We compile the model using binary_crossentropy and adam optimizer. With that kind of setup, we try to run it with 2 epochs, because each epochs is taking an hour or more, 
this can be reduced by modifying the batch size. All of that give us result of 95% Accuracy on the training data and 94% Accuracy on the validation data.
```
Model: "sequential_4"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
embedding_4 (Embedding)      (None, 200, 200)          34259200  
_________________________________________________________________
bidirectional_4 (Bidirection (None, 240)               308160    
_________________________________________________________________
dropout_1 (Dropout)          (None, 240)               0         
_________________________________________________________________
dense_8 (Dense)              (None, 24)                5784      
_________________________________________________________________
dense_9 (Dense)              (None, 1)                 25        
=================================================================
Total params: 34,573,169
Trainable params: 34,573,169
Non-trainable params: 0
_________________________________________________________________
```
For predicting the sentences, we are just passing the sentences into the tokenizer with all of already made vocabularies and then into the model.
